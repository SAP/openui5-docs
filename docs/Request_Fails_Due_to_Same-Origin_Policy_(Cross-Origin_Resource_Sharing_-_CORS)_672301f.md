<!-- copy672301f4f47640a8b2bc817d2ce0f512 -->

| loio |
| -----|
| 672301f4f47640a8b2bc817d2ce0f512 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/672301f4f47640a8b2bc817d2ce0f512) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/672301f4f47640a8b2bc817d2ce0f512)</div>

## Request Fails Due to Same-Origin Policy \(Cross-Origin Resource Sharing - CORS\)

If you use a remote URL in your code, for example a remote OData service, such as the publicly available Northwind OData service, the browser may refuse to connect to a remote URL. Due to the same-origin policy, browsers deny AJAX requests to service endpoints in case the service endpoint has a different domain/subdomain, protocol, or port than the app.

***

<a name="copy672301f4f47640a8b2bc817d2ce0f512__section_a3s_mvw_p1b"/>

### Preview

   
  
Violations of the same-origin policy in Google Chrome<a name="copy672301f4f47640a8b2bc817d2ce0f512__fig_jyf_f1k_c5"/>

 ![](loio2c36d72282e34903a97197783fe92122_HiRes.png "Violations of the same-origin policy in Google Chrome") 

***

<a name="copy672301f4f47640a8b2bc817d2ce0f512__section_q5w_mvw_p1b"/>

### Root Cause

Normally, the remote system would be configured to send the cross-origin resource sharing \(CORS\) headers to make the browser also allow direct access to remote URLs. However, if you, for example, use a Northwind OData service, you cannot modify the publicly available service. Then when you try to execute XHR requests \(`XMLHttpRequest`\) the browser prevents the call due to the same-origin policy.

***

<a name="copy672301f4f47640a8b2bc817d2ce0f512__section_v4n_mvw_p1b"/>

### Resolution

To solve the issue, you have the following options:

-   SAP Web IDE: Configure a destination as described below \(recommended\)

-   Local Development: Configure a local proxy \(CORS anywhere\)

-   Workaround: Disable the same-origin policy in the browser for local testing \(not recommended, only for testing\)

-   Set the CORS-relevant response headers on the remote system \(if possible\)


***

<a name="copy672301f4f47640a8b2bc817d2ce0f512__UsingHelperService"/>

### SAP Web IDE: Configure a destination

SAP Web IDE and the SAP Cloud Platform offer destinations that allow you to easily connect to remote systems. The destination to the Northwind OData service is an internet proxy made available inside the app at `<protocol>://<domain>/destinations/northwind/*`. Any request that is sent to this location is forwarded to `https://services.odata.org` automatically.

***

#### Create Destination in SAP Cloud Platform Cockpit

|Requested URL|Forwarded To|
|-------------|------------|
| `/destinations/northwind/V2/Northwind/Northwind.svc/$metadata` | `https://services.odata.org/V2/Northwind/Northwind.svc/$metadata` |
| `/destinations/northwind/V2/Northwind/Northwind.svc/Invoices` | `https://services.odata.org/V2/Northwind/Northwind.svc/Invoices` |

The destination itself is configured inside the SAP Cloud Platform Cockpit. For more information, see [Create a Northwind Destination](Create_a_Northwind_Destination_3a16c7a.md).

***

#### neo-app.json

For SAP Web IDE, a `neo-app.json` file is needed to make sure that the destination and resource mapping are available in the app. It has to be located in the root folder \(`webapp`\), on the same level as the `user.project.json` file that is automatically created.

If it does not exist yet, create a `neo-app.json` file and reference the Northwind destination there. Just copy the content of the code into that file and try to run the app again.

``` js
*HIGHLIGHT START*{
  "routes": [
    {
      "path": "/destinations/northwind",
      "target": {
        "type": "destination",
        "name": "northwind"
      },
      "description": "Northwind OData Service"
    }
  ]
}*HIGHLIGHT END*
```

> Note:
> If the file already exists, for example, because you already created it to map the OpenUI5 resources, just append the destination to the existing `route` definitions.
> 
> 

***

#### manifest.json

In the `manifest.json` descriptor file of your app, you can now change the data source to use the remote destination, for example:

``` js
{
  "_version": "1.12.0",
  "sap.app": {
	...
	"dataSources": {
	  "invoiceRemote": {

		"uri": "*HIGHLIGHT START*/destinations/northwind/*HIGHLIGHT END*V2/Northwind/Northwind.svc/",
		"type": "OData",
		"settings": {
		  "odataVersion": "2.0"
		}
	  }
	}
  },
  "sap.ui": {
	...
  },
  "sap.ui5": {
	...
  }
}
```

After this change, you can run the app in SAP Web IDE without disabling the same-origin policy of your browser. The destination now manages the connection to the remote service.

***

<a name="copy672301f4f47640a8b2bc817d2ce0f512__CORSAnywhere"/>

### Local Development: Configure a local proxy \(CORS anywhere\)

A proxy is simply a service end point on the same domain of your app to overcome the restrictions. It receives requests from the app, forwards them to another server, and finally returns the corresponding response from the remote service.

Follow the below steps to configure such a proxy in your poject.

Prerequisites: NodeJS is installed on your machine.

***

#### package.json

``` json
{
	"name": "Sample-Package",
	"version": "1.0.0",
	"description": "Sample package.json",
*HIGHLIGHT START*	"scripts": {
		"proxy": "node proxy.js"
	},
	"devDependencies": {
		"cors-anywhere": "^0.4.1"
	},*HIGHLIGHT END*
	"dependencies": {
	}
}
```

Add the `devDependency` called `"cors-anywhere": "^0.4.1"` to your existing `package.json`. Run `node install` to install the npm module. Add the `proxy` script to the `scripts` section in the `package.json` so that you can run a script via `npm run <script_name>`.

***

#### proxy.js \(new\)

``` js
*HIGHLIGHT START*var cors_proxy = require('cors-anywhere');

// Listen on a specific IP Address
var host = 'localhost';

// Listen on a specific port, adjust if necessary
var port = 8081;

cors_proxy.createServer({
	originWhitelist: [], // Allow all origins
	requireHeader: ['origin', 'x-requested-with'],
	removeHeaders: ['cookie', 'cookie2']
}).listen(port, host, function() {
	console.log('Running CORS Anywhere on ' + host + ':' + port);
});*HIGHLIGHT END*
```

Create a new file `proxy.js`, and copy the above script into your project directory. This is the pre-configured proxy server we are going to use to prevent the occurrence of **same-origin policy error**. We can start it by running the command `node proxy.js` or `npm run proxy. It runs a local proxy on port` in the console.

***

#### manifest.json

``` json
{
	"sap.app": {
		...
		"dataSources": {
			"northwind": {
				*HIGHLIGHT START*"uri": "http://localhost:8081/https://services.odata.org/V2/Northwind/Northwind.svc/",
*HIGHLIGHT END*
				"type": "OData",
				"settings": {
					"odataVersion": "2.0"
				}
			}
		}
	}
}
```

To use a service in the `local ui5 application` we have to change the `uri` in the `manifest` file.

> Note:
> The `uri` must start with `http://localhost:<port>`.
> 
> 

> Note:
> By default, you can't run the request in your browser with the `proxy.js` script. It throws the following exception: `exception Missing required request header. Must specify one of: origin,x-requested-with`. If you want to test the service in your browser, you can temporarily comment out the line `requireHeader: ['origin', 'x-requested-with']` from your `proxy.js`.
> 
> 

For more information on CORS Anywhere, see [https://www.npmjs.com/package/cors-anywhere](https://www.npmjs.com/package/cors-anywhere)

***

<a name="copy672301f4f47640a8b2bc817d2ce0f512__DisablingSameOriginPolicy"/>

### Workaround: Disable the same-origin policy in the browser \(not recommended, only for testing\)

. It runs a local proxyIn Google Chrome, you can easily disable the same-origin policy of Chrome by running Chrome with the following command: `[your-path-to-chrome-installation-dir]\chrome.exe --disable-web-security --user-data-dir`. Make sure that all instances of Chrome are closed before you run the command. This allows all web sites to break out of the same-origin policy and connect to the remote service directly.

> Note:
> **This approach is not recommended for productive apps. Running Chrome this way for surfing on the internet poses a security risk.** However, it allows you to avoid the need of setting up a proxy at development time or for testing purposes.
> 
> 

