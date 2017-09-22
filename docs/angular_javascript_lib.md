# Getting started


The Telstra SMS Messaging API allows your applications to send and receive SMS text messages from Australia's leading network operator.

It also allows your application to track the delivery status of both sent and received SMS messages.


## How to Build

The generated SDK requires AngularJS framework to work. If you do not already have angular downloaded, please go ahead and do it from [here](https://angularjs.org/).
If any of your models have `Date` or `Datetime` type fields or your endpoints have `Date`/`Datetime` type response, you will need to download and link [angular-moment](https://cdnjs.cloudflare.com/ajax/libs/angular-moment/1.0.1/angular-moment.min.js) and [moment.js](https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.17.1/moment.min.js) with your project.

## How to Use

The following section describes how to use the generated SDK in an existing/new project.

### 1. Configure Angular and Generated SDK
Perform the following steps to configure angular and the SDK:
+ Make a `scripts` folder inside the root folder of the project. If you already have a `scripts` folder, skip to the next step.
+ Move the `angular.min.js` file inside the scripts folder. 
+ Move the `TelstraMessagingAPILib` folder inside the scripts folder.
+ If any of the Custom Types in your API have `Date`/`Datetime` type fields or any endpoint has `Date`/`Datetime` response, you will need to download angular-moment and moment.js. Move these 2 files into the `scripts` folder as well.

![folder-structure-image](https://apidocs.io/illustration/angularjs?step=folderStructure&workspaceFolder=Telstra%20Messaging%20API-Angular&projectName=TelstraMessagingAPILib)

### 2. Open Project Folder
Open an IDE/Text Editor for JavaScript like Sublime Text. The basic workflow presented here is also applicable if you prefer using a different editor or IDE.  
Click on `File` and select `Open Folder`

Select the folder of your SDK and click on `Select Folder` to open it up in Sublime Text. The folder will become visible in the bar on the left.

![open-folder-image](https://apidocs.io/illustration/angularjs?step=openFolder&workspaceFolder=Telstra%20Messaging%20API-Angular)

### 3. Create an Angular Application
Since Angular JS is used for client-side web development, in order to use the generated library, you will have to develop an application first.
If you already have an angular application, [skip to Step 6](#6-include-sdk-references-in-html-file). Otherwise, follow these steps to create one:

+ In the IDE, click on `File` and choose `New File` to create a new file.
+ Add the following starting code in the file:
```js
var app = angular.module('myApp', []);
app.controller('testController', function($scope) 
{

});
```
+ Save it with the name `app.js` in the `scripts` folder.


### 4. Create HTML File
Skip to the next step if you are working with an existing project and already have an html file. Otherwise follow the steps to create one:
+ Inside the IDE, right click on the project folder name and select the `New File` option to create a new test file.
+ Save it with an appropriate name such as `index.html` in the root of your project folder.
`index.html` should look like this:
```html
<!DOCTYPE html>
<html>
<head>
	<title>Angular Project</title>
	<script></script>
</head>

<body>
</body>

</html>
```

![initial-html-code-image](https://apidocs.io/illustration/angularjs?step=initialCode&workspaceFolder=Telstra%20Messaging%20API-Angular)

### 5. Including links to Angular in HTML file
Your HTML file needs to have a link to `angular.min.js` file to use Angular-JS. Add the link using `script` tags inside the `head` section of `index.html` like:
```html
<script src="scripts/angular.min.js" ></script>
```
If any of the Custom Types that you have defined have `Date`/`Datetime` type fields or any endpoint has `Date`/`Datetime` response, you will also need to link to angular-moment and moment.js like:
```html
<script src="scripts/angular.min.js" ></script>
<script src="scripts/moment.min.js" ></script>
<script src="scripts/angular-moment.min.js" ></script>
```

### 6. Include SDK references in HTML file
Import the reference to the generated SDK files inside your html file like:
```html
<head>
    ...
    <!-- Helper files -->
    <script src="scripts/TelstraMessagingAPILib/Module.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Configuration.js"></script>
    <script src="scripts/TelstraMessagingAPILib/ModelFactory.js"></script>
    <script src="scripts/TelstraMessagingAPILib/ObjectMapper.js"></script>
    <script src="scripts/TelstraMessagingAPILib/APIHelper.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Http/Client/HttpContext.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Http/Client/RequestClient.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Http/Request/HttpRequest.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Http/Response/HttpResponse.js"></script>

    <!-- API Controllers -->
    <script src="scripts/TelstraMessagingAPILib/Controllers/BaseController.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Controllers/MessagingController.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Controllers/OAuthAuthorizationController.js"></script>


    <!-- Models -->
    <script src="scripts/TelstraMessagingAPILib/Models/BaseModel.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/MessageTypeEnum.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/MessageSentResponse.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/OutboundPollResponse.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/StatusEnum.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/Message.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/SendSMSRequest.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/SendMMSRequest.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/MMSContent.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/InboundPollResponse.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/OAuthScopeEnum.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/OAuthToken.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/OAuthProviderErrorEnum.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/OAuthScopeEnum.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/OAuthToken.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/OAuthProviderErrorEnum.js"></script>

    ...
</head>
```
> The `Module.js` file should be imported before the other files. After `Module.js`, `Configuration.js` should be imported.
> The `ModelFactory.js` file is needed by `ObjectMapper.js` file. The `ObjectMapper` in turn, is needed by `BaseController.js`.

### 7. Including link to `app.js` in HTML file
Link your `app.js` file to your `index.html` file like:
```html
<head>
	...
	<script src="scripts/app.js"></script>
</head>
```
> The link to app.js needs to be included at the very end of the head tag, after the SDK references have been added

### 8. Initializing the Angular App
You need to initialize your app and the controller associated with your view inside your `index.html` file. Do so like:
+ Add ng-app directive to initialize your app inside the `body` tag.
```html
<body ng-app="myApp">
```
+ Add ng-controller directive to initialize your controller and bind it with your view (`index.html` file).
```html
...
<body ng-app="myApp">
	<div ng-controller="testController">
		...
	</div>
	...
</body>
...
```

### 9. Consuming the SDK 
In order to use the generated SDK's modules, controllers and factories, the project needs to be added as a dependency in your angular app's module. This will be done inside the `app.js` file.
Add the dependency like this:

```js
var app = angular.module('myApp', ['TelstraMessagingAPILib']);
```
At this point, the SDK has been successfully included in your project. Further steps include using a service/factory from the generated SDK. To see working example of this, please head on [over here](#list-of-controllers) and choose any class to see its functions and example usage.  

### 10. Running The App
To run the app, simply open up the `index.html` file in a browser.

![app-running](https://apidocs.io/illustration/angularjs?step=appRunning)

## Initialization


The Angular Application can be initialized as following:
```JavaScript
var app = angular.module('myApp', [TelstraMessagingAPILib]);
// now controllers/services can be created which import
// the factories provided by the sdk
```
### Authentication
In order to setup authentication and initialization of the Angular App, you need the following information.

| Parameter | Description |
|-----------|-------------|
| oAuthClientId | OAuth 2 Client ID |
| oAuthClientSecret | OAuth 2 Client Secret |



```JavaScript
var app = angular.module('myApp', [TelstraMessagingAPILib]);
app.factory('config', function($scope, Configuration) 
{
    return {
        setConfigVars: function() {
            // Configuration parameters and credentials
            Configuration.oAuthClientId = 'oAuthClientId'; // OAuth 2 Client ID
            Configuration.oAuthClientSecret = 'oAuthClientSecret'; // OAuth 2 Client Secret
            
        }
    };
});
```

You must now authorize the client.

### Authorizing your client


This SDK uses *OAuth 2.0 authorization* to authorize the client.

The `authorize()` method will exchange the OAuth client credentials for an *access token*.
The access token is an object containing information for authorizing client requests.

 You must pass the *[scopes](#scopes)* for which you need permission to access.
```JavaScript
var app = angular.module('OAuthTest', ['TelstraMessagingAPILib']);

app.controller('oauthClientController', function($scope, OAuthManager, OAuthScopeEnum) {
    var scopes = [OAuthScopeEnum.NSMS];
    var promise = OAuthManager.authorize(scopes);
    promise.then(function(success) {
        // client successfully authorized
    });
});
```

The client can now make authorized endpoint calls.



### Scopes

Scopes enable your application to only request access to the resources it needs while enabling users to control the amount of access they grant to your application. Available scopes are defined in the `TelstraMessagingAPILib/Models/OAuthScopeEnum` enumeration.

| Scope Name | Description |
| --- | --- |
| `NSMS` | NSMS |




### Creating a client from an existing token

To authorize a client from an existing access token, just set the access token in `Configuration` along with the other configuration parameters:

```JavaScript
var app = angular.module('OAuthTest', ['TelstraMessagingAPILib']);

app.controller('config', function($scope, Configuration) {
    Configuration.oAuthToken = sessionStorage.getItem('token'); // the existing token stored in sessionStorage of browser
});
```


### Complete example
In this example, `app.js` will check if the access token has been obtained. If it hasn't been, the client needs to be authorized first.
After authorization, endpoint calls can be made.

#### `app.js`

```JavaScript
var app = angular.module('OAuthTest', ['TelstraMessagingAPILib']);

app.controller('oauthClientController', function($scope, OAuthManager, Configuration, OAuthScopeEnum) {
    Configuration.oAuthClientId = 'oAuthClientId'; // OAuth 2 Client ID
    Configuration.oAuthClientSecret = 'oAuthClientSecret'; // OAuth 2 Client Secret

    Configuration.oAuthTokenUpdateCallback = function(token) {
        sessionStorage.setItem('token', token);
    }

    if (OAuthManager.isTokenSet()) {
        // token was already set, make API calls as required
    } else {
        // since token is not set, client needs to obtain
        // an access token first
        var scopes = [OAuthScopeEnum.NSMS];
        var promise = OAuthManager.authorize(scopes);
        promise.then(function(success) {
            // client successfully authorized
            // make endpoint calls as required
        });
    }

});
```

#### `index.html`
```html
<!DOCTYPE html>
<html>

<head>
    <title>OAuthTest</title>
    <meta charset="UTF8">

    <script src="scripts/angular.min.js"></script>

    <script src="scripts/TelstraMessagingAPILib/Module.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Configuration.js"></script>
    <script src="scripts/TelstraMessagingAPILib/ModelFactory.js"></script>
    <script src="scripts/TelstraMessagingAPILib/ObjectMapper.js"></script>
    <script src="scripts/TelstraMessagingAPILib/APIHelper.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Servers.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Environments.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Http/Client/HttpContext.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Http/Request/HttpRequest.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Http/Response/HttpResponse.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Http/Client/RequestClient.js"></script>

    <!-- API Controllers -->
    <script src="scripts/TelstraMessagingAPILib/Controllers/BaseController.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Controllers/MessagingController.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Controllers/OAuthAuthorizationController.js"></script>


    <!-- Models -->
    <script src="scripts/TelstraMessagingAPILib/Models/BaseModel.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/MessageTypeEnum.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/MessageSentResponse.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/OutboundPollResponse.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/StatusEnum.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/Message.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/SendSMSRequest.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/SendMMSRequest.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/MMSContent.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/InboundPollResponse.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/OAuthScopeEnum.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/OAuthToken.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/OAuthProviderErrorEnum.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/OAuthScopeEnum.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/OAuthToken.js"></script>
    <script src="scripts/TelstraMessagingAPILib/Models/OAuthProviderErrorEnum.js"></script>


    <script src="scripts/TelstraMessagingAPILib/OAuthManager.js"></script>
    <script src="scripts/app.js"></script>

</head>


<body ng-app="OAuthTest">
    <div ng-controller="oauthClientController">

    </div>
</body>

</html>
```



# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [MessagingController](#messaging_controller)
* [OAuthAuthorizationController](#o_auth_authorization_controller)

## <a name="messaging_controller"></a>![Class: ](https://apidocs.io/img/class.png ".MessagingController") MessagingController

### Get singleton instance

The singleton instance of the ``` MessagingController ``` class can be accessed via Dependency Injection.

```js
	app.controller("testController", function($scope, MessagingController, OutboundPollResponse, InboundPollResponse, MessageSentResponse){
	});
```

### <a name="get_sms_status"></a>![Method: ](https://apidocs.io/img/method.png ".MessagingController.getSMSStatus") getSMSStatus

> Get Message Status


```javascript
function getSMSStatus(messageId)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| messageId |  ``` Required ```  | Unique identifier of a message - it is the value returned from
a previous POST call to https://api.telstra.com/v2/messages/sms |



#### Example Usage

```javascript


	app.controller("testController", function($scope, MessagingController, OutboundPollResponse){
        var messageId = 'messageId';


		var result = MessagingController.getSMSStatus(messageId);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | Invalid or missing request parameters |
| 401 | Invalid or no credentials passed in the request |
| 403 | Authorization credentials passed and accepted but account does<br>not have permission |
| 404 | The requested URI does not exist |
| 405 | The requested resource does not support the supplied verb |
| 415 | API does not support the requested content type |
| 422 | The request is formed correctly, but due to some condition<br>the request cannot be processed e.g. email is required and it is not provided<br>in the request |
| 501 | The HTTP method being used has not yet been implemented for<br>the requested resource |
| 503 | The service requested is currently unavailable |
| 0 | An internal error occurred when processing the request |




### <a name="retrieve_sms_responses"></a>![Method: ](https://apidocs.io/img/method.png ".MessagingController.retrieveSMSResponses") retrieveSMSResponses

> Retrieve Messages


```javascript
function retrieveSMSResponses()
```

#### Example Usage

```javascript


	app.controller("testController", function($scope, MessagingController, InboundPollResponse){


		var result = MessagingController.retrieveSMSResponses();
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | Invalid or missing request parameters |
| 401 | Invalid or no credentials passed in the request |
| 403 | Authorization credentials passed and accepted but account does<br>not have permission |
| 404 | The requested URI does not exist |
| 405 | The requested resource does not support the supplied verb |
| 415 | API does not support the requested content type |
| 422 | The request is formed correctly, but due to some condition<br>the request cannot be processed e.g. email is required and it is not provided<br>in the request |
| 501 | The HTTP method being used has not yet been implemented for<br>the requested resource |
| 503 | The service requested is currently unavailable |
| 0 | An internal error occurred when processing the request |




### <a name="create_send_sms"></a>![Method: ](https://apidocs.io/img/method.png ".MessagingController.createSendSMS") createSendSMS

> Send Message


```javascript
function createSendSMS(payload)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| payload |  ``` Required ```  | A JSON or XML payload containing the recipient's phone number and text message.

The recipient number should be in the format '04xxxxxxxx' where x is a digit |



#### Example Usage

```javascript


	app.controller("testController", function($scope, MessagingController, MessageSentResponse){
        var payload = new SendSMSRequest({"key":"value"});


		var result = MessagingController.createSendSMS(payload);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | Invalid or missing request parameters |
| 401 | Invalid or no credentials passed in the request |
| 403 | Authorization credentials passed and accepted but account does<br>not have permission |
| 404 | The requested URI does not exist |
| 405 | The requested resource does not support the supplied verb |
| 415 | API does not support the requested content type |
| 422 | The request is formed correctly, but due to some condition<br>the request cannot be processed e.g. email is required and it is not provided<br>in the request |
| 501 | The HTTP method being used has not yet been implemented for<br>the requested resource |
| 503 | The service requested is currently unavailable |
| 0 | An internal error occurred when processing the request |




### <a name="get_mms_status"></a>![Method: ](https://apidocs.io/img/method.png ".MessagingController.getMMSStatus") getMMSStatus

> Get MMS Status


```javascript
function getMMSStatus(messageid)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| messageid |  ``` Required ```  | Unique identifier of a message - it is the value returned from
a previous POST call to https://api.telstra.com/v2/messages/mms |



#### Example Usage

```javascript


	app.controller("testController", function($scope, MessagingController, OutboundPollResponse){
        var messageid = 'messageid';


		var result = MessagingController.getMMSStatus(messageid);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | Invalid or missing request parameters |
| 401 | Invalid or no credentials passed in the request |
| 403 | Authorization credentials passed and accepted but account does<br>not have permission |
| 404 | The requested URI does not exist |
| 405 | The requested resource does not support the supplied verb |
| 415 | API does not support the requested content type |
| 422 | The request is formed correctly, but due to some condition<br>the request cannot be processed e.g. email is required and it is not provided<br>in the request |
| 501 | The HTTP method being used has not yet been implemented for<br>the requested resource |
| 503 | The service requested is currently unavailable |
| 0 | An internal error occurred when processing the request |




### <a name="create_send_mms"></a>![Method: ](https://apidocs.io/img/method.png ".MessagingController.createSendMMS") createSendMMS

> Send MMS


```javascript
function createSendMMS(body)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | A JSON or XML payload containing the recipient's phone number
and MMS message.The recipient number should be in the format '04xxxxxxxx'
where x is a digit |



#### Example Usage

```javascript


	app.controller("testController", function($scope, MessagingController, MessageSentResponse){
        var body = new SendMMSRequest({"key":"value"});


		var result = MessagingController.createSendMMS(body);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | Invalid or missing request parameters |
| 401 | Invalid or no credentials passed in the request |
| 403 | Authorization credentials passed and accepted but account does<br>not have permission |
| 404 | The requested URI does not exist |
| 405 | The requested resource does not support the supplied verb |
| 415 | API does not support the requested content type |
| 422 | The request is formed correctly, but due to some condition<br>the request cannot be processed e.g. email is required and it is not provided<br>in the request |
| 501 | The HTTP method being used has not yet been implemented for<br>the requested resource |
| 503 | The service requested is currently unavailable |
| 0 | An internal error occurred when processing the request |




[Back to List of Controllers](#list_of_controllers)

## <a name="o_auth_authorization_controller"></a>![Class: ](https://apidocs.io/img/class.png ".OAuthAuthorizationController") OAuthAuthorizationController

### Get singleton instance

The singleton instance of the ``` OAuthAuthorizationController ``` class can be accessed via Dependency Injection.

```js
	app.controller("testController", function($scope, OAuthAuthorizationController, OAuthToken){
	});
```

### <a name="create_request_token"></a>![Method: ](https://apidocs.io/img/method.png ".OAuthAuthorizationController.createRequestToken") createRequestToken

> *Tags:*  ``` Skips Authentication ``` 

> Create a new OAuth 2 token.


```javascript
function createRequestToken(authorization, scope, formParams)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| authorization |  ``` Required ```  | Authorization header in Basic auth format |
| scope |  ``` Optional ```  | Requested scopes as a space-delimited list. |
| fieldParameters | ``` Optional ``` | Additional optional form parameters are supported by this method |



#### Example Usage

```javascript


	app.controller("testController", function($scope, OAuthAuthorizationController, OAuthToken){
        var authorization = 'Authorization';
        var scope = 'scope';
    // key-value map for optional form parameters
    var formParams = [];


		var result = OAuthAuthorizationController.createRequestToken(authorization, scope, formParams);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | OAuth 2 provider returned an error. |
| 401 | OAuth 2 provider says client authentication failed. |




### <a name="create_request_token"></a>![Method: ](https://apidocs.io/img/method.png ".OAuthAuthorizationController.createRequestToken") createRequestToken

> *Tags:*  ``` Skips Authentication ``` 

> Create a new OAuth 2 token.


```javascript
function createRequestToken(authorization, scope, formParams)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| authorization |  ``` Required ```  | Authorization header in Basic auth format |
| scope |  ``` Optional ```  | Requested scopes as a space-delimited list. |
| fieldParameters | ``` Optional ``` | Additional optional form parameters are supported by this method |



#### Example Usage

```javascript


	app.controller("testController", function($scope, OAuthAuthorizationController, OAuthToken){
        var authorization = 'Authorization';
        var scope = 'scope';
    // key-value map for optional form parameters
    var formParams = [];


		var result = OAuthAuthorizationController.createRequestToken(authorization, scope, formParams);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | OAuth 2 provider returned an error. |
| 401 | OAuth 2 provider says client authentication failed. |




[Back to List of Controllers](#list_of_controllers)



