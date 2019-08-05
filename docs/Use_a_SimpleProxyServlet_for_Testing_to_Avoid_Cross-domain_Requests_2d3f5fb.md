<!-- loio2d3f5fb63a2f4090942375df80abc39f -->

| loio |
| -----|
| 2d3f5fb63a2f4090942375df80abc39f |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/2d3f5fb63a2f4090942375df80abc39f) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/2d3f5fb63a2f4090942375df80abc39f)</div>

## Use a SimpleProxyServlet for Testing to Avoid Cross-domain Requests

If you are testing locally in your Java Eclipse environment and you want to access an OData service in the ABAP system, a proxy is needed to ensure the same-origin policy. In an SAPUI5 application project you can use a SimpleProxyServlet for local testing.

> Note:
> Be aware that due to security reasons the `SimpleProxyServlet` is restricted to local testing purposes only. It can only be used for local host scenarios \(accessing Gateway services to avoid cross-domain issues\) and will not work when deployed on an application server. For productive use, refer to a mature proxy servlet.
> 
> 

> Note:
> If you have issues with accessing HTTPS systems via the `ResourceServlet` or the `SimpleProxyServlet` it may be necessary to import the root certificate into the Java keystore.
> 
> 

Ideally, all OData service URLs should be in one file to make the exchange easier - either in the `index.html`, or in one separate .js file that needs to be included. The application is responsible for exchanging the URLs before checking in and after checking out to the SAPUI5 Repository. You can also use the helper function `getServiceUrl`, for which the application is responsible as well. See the following example:

``` html
<script>
//var serviceUrl = "/mypath/myservice";       //url when running on the ABAP system
//var serviceUrl = "proxy/mypath/myservice";  //url when running locally in Eclipse
var serviceUrl = getServiceUrl("/mypath/myservice");
function getServiceUrl(sServiceUrl) {
  //for local testing prefix with proxy
  //if you and your team use a special host name or IP like 127.0.0.1 for localhost please adapt the if statement below 
  if (window.location.hostname == "localhost") {
      return "proxy" + sServiceUrl;
  } else {
      return sServiceUrl;
  }
}
</script>
```

As parameter for the `getServiceUrl` helper method, use the URL of the OData service document without \{protocol\}://\{host name\}:\{port number\}, for example: */mypath/myservice*.

> Note:
> Place the script tag before the script that calls the view \(`sap.ui.view`\).
> 
> 

***

<a name="loio2d3f5fb63a2f4090942375df80abc39f__section_4107381EFDEE47F39063E52AE8E35FEA"/>

### Intranet Servers

The `SimpleProxyServlet` allows proxy requests to an arbitrary server in the intranet.

The proxy URL that is used in the coding looks like this: *proxy/<service url\>*.

Open the `web.xml` file located in the `<WebContent folder name>/WEB-INF` folder, and configure the parameter `com.sap.ui5.proxy.REMOTE_LOCATION` of the `SimpleProxyServlet` where the placeholders `{protocol}`, `{host name}`, and `{port number}` have to be exchanged by the real protocol, host name and port number:

``` xml
  <servlet>
    <servlet-name>SimpleProxyServlet</servlet-name>
    <servlet-class>com.sap.ui5.proxy.SimpleProxyServlet</servlet-class>
  </servlet>

  <servlet-mapping>
    <servlet-name>SimpleProxyServlet</servlet-name>
    <url-pattern>/proxy/*</url-pattern>
  </servlet-mapping>

  <context-param>
    <param-name>com.sap.ui5.proxy.REMOTE_LOCATION</param-name>
    <param-value>{protocol}://{host name}:{port number}</param-value>
  </context-param>
```

***

<a name="loio2d3f5fb63a2f4090942375df80abc39f__section_B34F4B95794A49D7A12871CC22A6C29B"/>

### Internet Servers

The `SimpleProxyServlet` can be configured for proxy requests to internet servers in the same way as for intranet servers. Additional proxy settings may be necessary.

As the `SimpleProxyServlet` automatically uses the proxy settings from your Eclipse, this can be configured in Eclipse under *Window* \> *Preferences* \> *General* \> *Network Connections*. Here you can specify the proxy entries and the proxy bypass.

For example, set *Active Provider* to Manual, *Schema*=HTTP, *Host*=proxy, *Port*=8080 under proxy entries and localhost, \*.mycompany.corp as *Host* under proxy bypass.

***

<a name="loio2d3f5fb63a2f4090942375df80abc39f__section_1490F589E7374BD294D004B6D51C6A59"/>

### Simple Proxy Servlet - Restriction Regarding `DELETE` Requests

The simple proxy servlet currently does not support the sending of `HTTP DELETE` requests with content. This is due to restrictions of the Java SE functionality that is used. If an `HTTP DELETE` request with content is sent, an HTTP 500 result status is returned with the description: "The HttpUrlConnection used by the SimpleProxyServlet doesn't allow to send content with the HTTP method DELETE. Due to spec having content for DELETE methods is possible but the default implementation of the HttpUrlConnection doesn't allow this!"

For practical purposes, this restriction should have only minor effects for the following reasons:

-   When applying a REST-like programming style, an `HTTP DELETE` request would use the URL to transmit which objects should be deleted, but not the content.

-   When building your own protocol that uses the content of the HTTP request, you would typically use `HTTP POST`.


