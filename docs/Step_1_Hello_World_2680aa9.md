<!-- loio2680aa9b16c14a00b01261d04babbb39 -->

| loio |
| -----|
| 2680aa9b16c14a00b01261d04babbb39 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/2680aa9b16c14a00b01261d04babbb39) | [demo kit latest release](https://sdk.openui5.org/topic/2680aa9b16c14a00b01261d04babbb39)</div>

## Step 1: Hello World!

As you know OpenUI5 is all about HTML5. Let’s get started with building a first “Hello World” with only HTML.

***

### Preview

   
  
<a name="loio2680aa9b16c14a00b01261d04babbb39__fig_r1j_pst_mr"/>The browser shows the text "Hello World"

 ![](images/loio396ccf66ea6c4ad1a488355d3ea18ad7_HiRes.png "The browser shows the text "Hello World"") 

***

### Coding

You can view and download all files at [Walkthrough - Step 1](https://sdk.openui5.org/entity/sap.m.tutorial.walkthrough/sample/sap.m.tutorial.walkthrough.01).

```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>SAPUI5 Walkthrough</title>
</head>
<body>
	<div>Hello World</div>
</body>
</html>


```

Create a new folder `webapp` which will contain all sources of the app we will create throughout this tutorial. Therefore, we refer to this folder as “app folder”.

Now create a new root HTML file called `index.html` in your app folder. An HTML document consists basically of two sections: head and body. The head part will be used by the browser to process the document. Using meta tags we can influence the behavior of the browser.

In this case we will tell the browser to use `UTF-8` as the document character set. We will also give our app a title that will be displayed in the browser. Be aware that our hard-coded title can be overruled by the app, for example to show a title in the language of the user.

The body part describes the layout of the page. In our case we simply display “Hello World” by using a `div` tag.

> ### Tip:  
> Typically, the content of the `webapp` folder is deployed to a Web server as an application package. When deploying the `webapp` folder itself the URL for accessing the `index.html` file contains `webapp` in the path.

***

### Conventions

-   Name the root HTML file of the app `index.html` and locate it in the `webapp` folder.


**Parent topic:** [Walkthrough](Walkthrough_3da5f4b.md "In this tutorial we will introduce you to all major development paradigms of OpenUI5.")

**Previous:** [Step 2: Bootstrap](Step_2_Bootstrap_fe12df2.md "Before we can do something with OpenUI5, we need to load and initialize it. This process of loading and initializing OpenUI5 is called bootstrapping. Once this bootstrapping is finished, we simply display an alert.")

