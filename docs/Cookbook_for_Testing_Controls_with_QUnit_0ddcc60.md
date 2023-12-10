<!-- loio0ddcc60b05ee40dea1a3be09e8fee8f7 -->

| loio |
| -----|
| 0ddcc60b05ee40dea1a3be09e8fee8f7 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/0ddcc60b05ee40dea1a3be09e8fee8f7) | [demo kit latest release](https://sdk.openui5.org/topic/0ddcc60b05ee40dea1a3be09e8fee8f7)</div>

## Cookbook for Testing Controls with QUnit

***

### Test Cases

You can use a factory function. To keep this pointer and have a descriptive message, you should use the test inside of the function and pass a test name to it.

Internally, we prefer to pass an object to the test for retrieving the values - it makes the test cases readable.

```js
// "Bar" required from module "sap/m/Bar"
// "Core" required from module "sap/ui/core/Core"
function renderBarInPageTestCase(sTestName, oOptions) {
    QUnit.test(sTestName, function (assert) { 
        // System under Test
        var oBar = new Bar();

        oBar.placeAt("qunit-fixture");

        // Act
        oBar.applyTagAndContextClassFor(oOptions.context);

        Core.applyChanges();

        // Assert
       assert.strictEqual(oBar.getDomRef().nodeName, oOptions.expectedTag.toUpperCase());
       assert.ok(oBar.$().hasClass(oOptions.expectedClass), "The bar has the context class: " + oOptions.expectedClass);

        // Cleanup
        oBar.destroy();
    });
};

renderBarInPageTestCase("Should render the header context", {
    context : "header",
    expectedTag : "header",
    expectedClass : "sapMHeader-CTX"
});

renderBarInPageTestCase("Should render the header context", {
    context : "subheader",
    expectedTag : "header",
    expectedClass : "sapMSubHeader-CTX"
});

renderBarInPageTestCase("Should render the header context", {
    context : "footer",
    expectedTag : "footer",
    expectedClass : "sapMFooter-CTX"
});
```

***

### Testing Control Events

You cannot test for event parameters in OpenUI5 so you have to record them. Nevertheless, you can still use Sinon to retain the spy's call counting capabilities. Here is a working example for this:

```js
// "HashChanger" required from module "sap/ui/core/routing/HashChanger"
QUnit.test("Should set the Hash", function(assert) { 
    //Arrange
    var aCalls = [],
        fnHashChanged = function(oEvt) {
                 aCalls.push({ newHash : oEvt.getParameter("newHash"), oldHash : oEvt.getParameter("oldHash") });
        },
        oSpy = this.spy(fnHashChanged);

    
    //System under Test
    var oHashChanger = new HashChanger();
    oHashChanger.init();
    oHashChanger.attachEvent("hashChanged", oSpy);

    //Act
    oHashChanger.setHash("one", true);
    oHashChanger.setHash("two");

    //Assert
    assert.strictEqual(oSpy.callCount, 2, "did change the Hash two times");

    assert.strictEqual(aCalls[0].newHash, "one", "first event was correct"); 
    assert.strictEqual(aCalls[1].newHash, "two", "second event was correct");
    
    //Cleanup
    oHashChanger.destroy();
});
```

***

### Testing User Interactions

When testing user interactions, you can use `sap.ui.test.qunit` to trigger events.

Here is an example for when a user presses [Esc\] on the select:

```js
// "Item" required from module "sap/ui/core/Item"
// "Select" required from module "sap/m/Select"
// "KeyCodes" required from module "sap/ui/events/KeyCodes"
// "Core" required from module "sap/ui/core/Core"
// "QUnitUtils" required from module "sap/ui/qunit/QUnitUtils"
QUnit.test("Should close the popup menu if it is open and you press escape", function(assert) {
    // Arrange
    var oConstructor = {
        items: [
        new Item({
            key: "0",
            text: "item 0"
        }),

        new Item({
            key: "1",
            text: "item 1"
        })
       ]
    };

    // System under test
    var oSelect = new Select(oConstructor);

    oSelect.placeAt("select-content");
    Core.applyChanges();

    // Arrange after rendering
    oSelect.focus();
    var fnEscapeSpy = this.spy(oSelect, "onsapescape");
    var fnCloseSpy = this.spy(oSelect, "close");

    // Act
    QUnitUtils.triggerKeydown(oSelect.getDomRef(), KeyCodes.ESCAPE);

    // Assertion
    assert.strictEqual(fnEscapeSpy.callCount, 1, "onsapescape() method was called exactly once");
    assert.strictEqual(fnCloseSpy.callCount, 0, "close() method is not called");

    // Cleanup
    oSelect.destroy();
});
```

***

### Testing the Re-rendering

In this example, you will test to see whether the control fails to rerender. The control has overwritten the setter of the tooltip property to avoid triggering a re-rendering.

To test this, we add an `eventDelegate` to see how often the rendering function is called. We need to make sure that we apply the changes after setting the property because we want OpenUI5 to render synchronously:

```js
// "Label" required from module "sap/m/Label"
// "Core" required from module "sap/ui/core/Core"
QUnit.test("Should suppress rerendering when tooltip is set", function(assert) { 
    // Arrange
    var oConstructor = {
        tooltip : "foo"
        };
    var oRerenderingSpy = this.spy();

    // System under Test
    var oLabel = new Label(oConstructor);
    oLabel.placeAt("qunit-fixture");
    Core.applyChanges();

    oLabel.addEventDelegate({
        onBeforeRendering : oRerenderingSpy
    });

    // Act
    oLabel.setTooltip("bar");
    Core.applyChanges();

    // Assert
    assert.strictEqual(oRerenderingSpy.callCount, 0, "Did not rerender");
    assert.strictEqual(oLabel.getTooltip(), "bar", "Tooltip property got set");
    assert.strictEqual(oLabel.$().attr("title"), "bar", "Tooltip got updated");

    // Cleanup
    oLabel.destroy();
});
```

`applyChanges()` enforces a synchronous rendering and **must not** be used in productive code.

**For test scenarios only**, you may use the test helper module **`sap/ui/qunit/utils/nextUIUpdate`** instead.

> ### Restriction:  
> Using `nextUIUpdate` in combination with fake timers has some pitfalls. If fake timers are used, it is not possible to use `await`. In this case, you need to chain to the `nextUIUpdate` Promise and always use `clock.tick()` within the chaining in order to execute the rendering.
> 
> The main difference to `applyChanges()` is that `nextUIUpdate()` does not synchronously trigger a re-rendering \(which by intention we wanted to get rid of\), but just waits for the next rendering cycle to complete. Due to this asynchronous nature, switching to it may be slightly more work than in other more straightforward cases.

As a replacement for `applyChanges()` **in tests only**, use:

```js
QUnit.test("Simple Component Instance",
  async function(assert){
    await nextUIUpdate();
    ...
});
 
// nextUIUpdate with fake timers
QUnit.test("Test with fake timers", function() {
    this.clock = sinon.useFakeTimers();
 
    // Using runAll is not always necessary but ensures, that no timeouts are left unprocessed
    this.clock.runAll();
    nextUIUpdate().then(() => {
        this.clock.tick();
        // Continue with your test
    });
}
```

***

### Testing with Models

As your control should work together with models, it makes sense to do integration tests with a mock server. This is especially important for more complex controls, e.g. using paging. When testing with models, you need to make sure that you also set up/destroy the model itself inside your test. In the following, we will show an example using the OData V2 mock server:

```js

// "MockServer" required from module "sap/ui/app/MockServer"

function startMockServer(iRespondAfter) {
    // configure respond to requests delay
    MockServer.config({
        autoRespond : true,
        autoRespondAfter : iRespondAfter || 10
    });

    // create mockserver
    var oMockServer = new MockServer({
        rootUri : "http://sap.com/service/"
    });

    // start and return
    oMockServer.simulate("data/metadata.xml", "data");
    oMockServer.start();
    return oMockServer;
}

//Your test:
QUnit.test("Should do something with the model", function (assert) {
    //Arrange
    var oMockServer = startMockServer(0),
    
    // System under Test + Act

    //Cleanup
    oMockServer.stop();
});
```

When using the OData V2 mock server, you can use async tests since calling respond each time on the mock server does not help the readability of the test.

After setting up the OData V2 mock server, we set up the model as follows:

```js

// "ODataModel" required from module "sap/ui/model/v2/ODataModel"
// "jQuery" required from module "sap/ui/thirdparty/jquery"

function createODataModel(sURL, mSettings) {
    sURL = sURL || "http://sap.com/service/";
    var oModel = new ODataModel(sURL);
    
    mSettings = mSettings || {};
    jQuery.each(mSettings, function(sProperty, vValue) {
        sProperty = sProperty[0].toUpperCase() + sProperty.substring(1);
        oModel["set" + sProperty](vValue);
    });
    
    return oModel;
}

//Your test:
QUnit.test("Should do something with the model", function(assert) {
    // Arrange
    var oModel = createODataModel(),
    oMockServer = startMockServer(0),
    done = assert.async();

    // System under Test + Act + call done();

    // Cleanup
    oModel.destroy();
    oMockServer.stop();
});
```

You can now bind your model against your control and test whatever you want.

We use `clock.tick` to trigger the server response. If you didn't do this, the text of the label would still be empty:

```js
// "Label" required from module "sap/m/Label"
// "Core" required from module "sap/ui/core/Core"

//Your test:
QUnit.test("Should do something with the model", function(assert) {
    // Arrange
    var oModel = createODataModel(),
        oMockServer = startMockServer(50);

    // System under Test
    var oLabel = new Label({
        text : "{/myProperty}"
    });

    oLabel.placeAt("qunit-fixture");
    Core.applyChanges();

    // Act - trigger the request
    sinon.clock.tick(50);

    // Assert
    assert.strictEqual("myExpected", oLabel.getText(), "The expected text was present");

    // Cleanup
    oModel.destroy();
    oMockServer.stop();
    sinon.clock.reset() 
});
```

***

<a name="loio0ddcc60b05ee40dea1a3be09e8fee8f7__section_ljv_b3r_rzb"/>

### Testing for a Theme Change

```js
sap.ui.require(["sap/ui/core/Theming"], (Theming) => {
    QUnit.test("Check if theme change was done correctly", function(assert){
        const myTestFunction = () => {
            // Test changes are applied
            Theming.detachApplied(myTestFunction);
        }
        Theming.setTheme("myTestTheme");
        Theming.attachApplied(myTestFunction);
    });
});
```

