# Getting started


The Telstra SMS Messaging API allows your applications to send and receive SMS text messages from Australia's leading network operator.

It also allows your application to track the delivery status of both sent and received SMS messages.


## How to Build


The generated code has dependencies over external libraries like UniRest. These dependencies are defined in the ```PodFile``` file that comes with the SDK. 
To resolve these dependencies, we use the Cocoapods package manager.
Visit https://guides.cocoapods.org/using/getting-started.html to setup Cocoapods on your system.
Open command prompt and type ```pod --version```. This should display the current version of Cocoapods installed if the installation was successful.

Using command line, navigate to the directory containing the generated files (including ```PodFile```) for the SDK. 
Run the command ```pod install```. This should install all the required dependencies and create the ```pods``` directory in your project directory.

![Installing dependencies using Cocoapods](https://apidocs.io/illustration/objc?step=AddDependencies&workspaceFolder=Telstra%20Messaging%20API-ObjC&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPI&rootNamespace=TelstraMessagingAPI)

Open the project workspace using the (TelstraMessagingAPI.xcworkspace) file. Invoke the build process using `Command(⌘)+B` shortcut key or using the `Build` menu as shown below.

![Building SDK using Xcode](https://apidocs.io/illustration/objc?step=BuildSDK&workspaceFolder=Telstra%20Messaging%20API-ObjC&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPI&rootNamespace=TelstraMessagingAPI)


## How to Use

The generated code is a Cocoa Touch Static Library which can be used in any iOS project. The support for these generated libraries go all the way back to iOS 6.

The following section explains how to use the TelstraMessagingAPI library in a new iOS project.     
### 1. Starting a new project
To start a new project, left-click on the ```Create a new Xcode project```.
![Create Test Project - Step 1](https://apidocs.io/illustration/objc?step=Test1&workspaceFolder=Telstra%20Messaging%20API-ObjC&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPI&rootNamespace=TelstraMessagingAPI)

Next, choose **Single View Application** and click ```Next```.
![Create Test Project - Step 2](https://apidocs.io/illustration/objc?step=Test2&workspaceFolder=Telstra%20Messaging%20API-ObjC&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPI&rootNamespace=TelstraMessagingAPI)

Provide **Test-Project** as the product name click ```Next```.
![Create Test Project - Step 3](https://apidocs.io/illustration/objc?step=Test3&workspaceFolder=Telstra%20Messaging%20API-ObjC&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPI&rootNamespace=TelstraMessagingAPI)

Choose the desired location of your project folder and click ```Create```.
![Create Test Project - Step 4](https://apidocs.io/illustration/objc?step=Test4&workspaceFolder=Telstra%20Messaging%20API-ObjC&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPI&rootNamespace=TelstraMessagingAPI)

### 2. Adding the static library dependency
To add this dependency open a terminal and navigate to your project folder. Next, input ```pod init``` and press enter.
![Add dependency - Step 1](https://apidocs.io/illustration/objc?step=Add0&workspaceFolder=Telstra%20Messaging%20API-ObjC&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPI&rootNamespace=TelstraMessagingAPI)

Next, open the newly created ```PodFile``` in your favourite text editor. Add the following line : pod 'TelstraMessagingAPI', :path => 'Vendor/TelstraMessagingAPI'
![Add dependency - Step 2](https://apidocs.io/illustration/objc?step=Add1&workspaceFolder=Telstra%20Messaging%20API-ObjC&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPI&rootNamespace=TelstraMessagingAPI)

Execute `pod install` from terminal to install the dependecy in your project. This would add the dependency to the newly created test project.
![Add dependency - Step 3](https://apidocs.io/illustration/objc?step=Add2&workspaceFolder=Telstra%20Messaging%20API-ObjC&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPI&rootNamespace=TelstraMessagingAPI)


## How to Test

Unit tests in this SDK can be run using Xcode. 

First build the SDK as shown in the steps above and naivgate to the project directory and open the TelstraMessagingAPI.xcworkspace file.

Go to the test explorer in Xcode as shown in the picture below and click on `run tests` from the menu. 
![Run tests](https://apidocs.io/illustration/objc?step=RunTests&workspaceFolder=Telstra%20Messaging%20API-ObjC&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPI&rootNamespace=TelstraMessagingAPI)


## Initialization

### Authentication
In order to setup authentication and initialization of the API client, you need the following information.

| Parameter | Description |
|-----------|-------------|
| oAuthClientId | OAuth 2 Client ID |
| oAuthClientSecret | OAuth 2 Client Secret |



Configuration variables can be set as following.
```Objc
// Configuration parameters and credentials
Configuration_OAuthClientId = "Configuration_OAuthClientId"; // OAuth 2 Client ID
Configuration_OAuthClientSecret = "Configuration_OAuthClientSecret"; // OAuth 2 Client Secret

```

# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [MessagingController](#messaging_controller)
* [OAuthAuthorizationController](#o_auth_authorization_controller)

## <a name="messaging_controller"></a>![Class: ](https://apidocs.io/img/class.png ".MessagingController") MessagingController

### Get singleton instance
```objc
Messaging* messaging = [[Messaging alloc]init] ;
```

### <a name="get_sms_status_async_with_message_id"></a>![Method: ](https://apidocs.io/img/method.png ".MessagingController.getSMSStatusAsyncWithMessageId") getSMSStatusAsyncWithMessageId

> Get Message Status


```objc
function getSMSStatusAsyncWithMessageId:(NSString*) messageId
                completionBlock:(CompletedGetSMSStatus) onCompleted(messageId)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| messageId |  ``` Required ```  | Unique identifier of a message - it is the value returned from
a previous POST call to https://api.telstra.com/v2/messages/sms |





#### Example Usage

```objc
    // Parameters for the API call
    NSString* messageId = @"messageId";

    [self.messaging getSMSStatusAsyncWithMessageId: messageId  completionBlock:^(BOOL success, HttpContext* context, OutboundPollResponse* response, NSError* error) { 
       //Add code here
    }];
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | Invalid or missing request parameters |
| 401 | Invalid or no credentials passed in the request |
| 403 | Authorization credentials passed and accepted but account does
not have permission |
| 404 | The requested URI does not exist |
| 405 | The requested resource does not support the supplied verb |
| 415 | API does not support the requested content type |
| 422 | The request is formed correctly, but due to some condition
the request cannot be processed e.g. email is required and it is not provided
in the request |
| 501 | The HTTP method being used has not yet been implemented for
the requested resource |
| 503 | The service requested is currently unavailable |
| 0 | An internal error occurred when processing the request |



### <a name="retrieve_sms_responses_with_completion_block"></a>![Method: ](https://apidocs.io/img/method.png ".MessagingController.retrieveSMSResponsesWithCompletionBlock") retrieveSMSResponsesWithCompletionBlock

> Retrieve Messages


```objc
function retrieveSMSResponsesWithCompletionBlock:(CompletedGetRetrieveSMSResponses) onCompleted()
```



#### Example Usage

```objc

    [self.messaging retrieveSMSResponsesWithCompletionBlock:  ^(BOOL success, HttpContext* context, NSArray<InboundPollResponse> * response, NSError* error) { 
       //Add code here
    }];
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | Invalid or missing request parameters |
| 401 | Invalid or no credentials passed in the request |
| 403 | Authorization credentials passed and accepted but account does
not have permission |
| 404 | The requested URI does not exist |
| 405 | The requested resource does not support the supplied verb |
| 415 | API does not support the requested content type |
| 422 | The request is formed correctly, but due to some condition
the request cannot be processed e.g. email is required and it is not provided
in the request |
| 501 | The HTTP method being used has not yet been implemented for
the requested resource |
| 503 | The service requested is currently unavailable |
| 0 | An internal error occurred when processing the request |



### <a name="create_send_sms_async_with_payload"></a>![Method: ](https://apidocs.io/img/method.png ".MessagingController.createSendSMSAsyncWithPayload") createSendSMSAsyncWithPayload

> Send Message


```objc
function createSendSMSAsyncWithPayload:(SendSMSRequest*) payload
                completionBlock:(CompletedPostSendSMS) onCompleted(payload)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| payload |  ``` Required ```  | A JSON or XML payload containing the recipient's phone number and text message.

The recipient number should be in the format '04xxxxxxxx' where x is a digit |





#### Example Usage

```objc
    // Parameters for the API call
    SendSMSRequest* payload = [[SendSMSRequest alloc]init];

    [self.messaging createSendSMSAsyncWithPayload: payload  completionBlock:^(BOOL success, HttpContext* context, MessageSentResponse* response, NSError* error) { 
       //Add code here
    }];
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | Invalid or missing request parameters |
| 401 | Invalid or no credentials passed in the request |
| 403 | Authorization credentials passed and accepted but account does
not have permission |
| 404 | The requested URI does not exist |
| 405 | The requested resource does not support the supplied verb |
| 415 | API does not support the requested content type |
| 422 | The request is formed correctly, but due to some condition
the request cannot be processed e.g. email is required and it is not provided
in the request |
| 501 | The HTTP method being used has not yet been implemented for
the requested resource |
| 503 | The service requested is currently unavailable |
| 0 | An internal error occurred when processing the request |



### <a name="get_mms_status_async_with_messageid"></a>![Method: ](https://apidocs.io/img/method.png ".MessagingController.getMMSStatusAsyncWithMessageid") getMMSStatusAsyncWithMessageid

> Get MMS Status


```objc
function getMMSStatusAsyncWithMessageid:(NSString*) messageid
                completionBlock:(CompletedGetMMSStatus) onCompleted(messageid)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| messageid |  ``` Required ```  | Unique identifier of a message - it is the value returned from
a previous POST call to https://api.telstra.com/v2/messages/mms |





#### Example Usage

```objc
    // Parameters for the API call
    NSString* messageid = @"messageid";

    [self.messaging getMMSStatusAsyncWithMessageid: messageid  completionBlock:^(BOOL success, HttpContext* context, OutboundPollResponse* response, NSError* error) { 
       //Add code here
    }];
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | Invalid or missing request parameters |
| 401 | Invalid or no credentials passed in the request |
| 403 | Authorization credentials passed and accepted but account does
not have permission |
| 404 | The requested URI does not exist |
| 405 | The requested resource does not support the supplied verb |
| 415 | API does not support the requested content type |
| 422 | The request is formed correctly, but due to some condition
the request cannot be processed e.g. email is required and it is not provided
in the request |
| 501 | The HTTP method being used has not yet been implemented for
the requested resource |
| 503 | The service requested is currently unavailable |
| 0 | An internal error occurred when processing the request |



### <a name="create_send_mms_async_with_body"></a>![Method: ](https://apidocs.io/img/method.png ".MessagingController.createSendMMSAsyncWithBody") createSendMMSAsyncWithBody

> Send MMS


```objc
function createSendMMSAsyncWithBody:(SendMMSRequest*) body
                completionBlock:(CompletedPostSendMMS) onCompleted(body)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | A JSON or XML payload containing the recipient's phone number
and MMS message.The recipient number should be in the format '04xxxxxxxx'
where x is a digit |





#### Example Usage

```objc
    // Parameters for the API call
    SendMMSRequest* body = [[SendMMSRequest alloc]init];

    [self.messaging createSendMMSAsyncWithBody: body  completionBlock:^(BOOL success, HttpContext* context, MessageSentResponse* response, NSError* error) { 
       //Add code here
    }];
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | Invalid or missing request parameters |
| 401 | Invalid or no credentials passed in the request |
| 403 | Authorization credentials passed and accepted but account does
not have permission |
| 404 | The requested URI does not exist |
| 405 | The requested resource does not support the supplied verb |
| 415 | API does not support the requested content type |
| 422 | The request is formed correctly, but due to some condition
the request cannot be processed e.g. email is required and it is not provided
in the request |
| 501 | The HTTP method being used has not yet been implemented for
the requested resource |
| 503 | The service requested is currently unavailable |
| 0 | An internal error occurred when processing the request |



[Back to List of Controllers](#list_of_controllers)

## <a name="o_auth_authorization_controller"></a>![Class: ](https://apidocs.io/img/class.png ".OAuthAuthorizationController") OAuthAuthorizationController

### Get singleton instance
```objc
OAuthAuthorization* oAuthAuthorization = [[OAuthAuthorization alloc]init] ;
```

### <a name="create_request_token_async_with_authorization"></a>![Method: ](https://apidocs.io/img/method.png ".OAuthAuthorizationController.createRequestTokenAsyncWithAuthorization") createRequestTokenAsyncWithAuthorization

> *Tags:*  ``` Skips Authentication ``` 

> Create a new OAuth 2 token.


```objc
function createRequestTokenAsyncWithAuthorization:(NSString*) authorization
                scope:(NSString*) scope
                fieldParameters:(NSDictionary*) fieldParameters
                completionBlock:(CompletedPostRequestToken) onCompleted(authorization scope : scope  formParameters : formParams)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| authorization |  ``` Required ```  | Authorization header in Basic auth format |
| scope |  ``` Optional ```  | Requested scopes as a space-delimited list. |
| fieldParameters | ``` Optional ``` | Additional optional form parameters are supported by this method |





#### Example Usage

```objc
    // Parameters for the API call
    NSString* authorization = @"Authorization";
    NSString* scope = @"scope";
    // Dictionary for optional form parameters
    NSMutableDictionary* formParamsMutable = [[NSMutableDictionary alloc] init];
    NSDictionary *formParams= [formParamsMutable copy];

    [self.oAuthAuthorization createRequestTokenAsyncWithAuthorization: authorization scope : scope  formParameters : formParams  completionBlock:^(BOOL success, HttpContext* context, OAuthToken* response, NSError* error) { 
       //Add code here
    }];
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | OAuth 2 provider returned an error. |
| 401 | OAuth 2 provider says client authentication failed. |



[Back to List of Controllers](#list_of_controllers)



