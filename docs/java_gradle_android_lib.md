# Getting started


The Telstra SMS Messaging API allows your applications to send and receive SMS text messages from Australia's leading network operator.

It also allows your application to track the delivery status of both sent and received SMS messages.


## How to Build

The generated code uses a few Gradle dependencies e.g., Jackson, Volley,
and Apache HttpClient. The reference to these dependencies is already
added in the build.gradle file will be installed automatically. Therefore,
you will need internet access for a successful build.

* In order to open the client library in Android Studio click on ``` Open an Existing Android Project ```.

![Importing SDK into Android Studio - Step 1](https://apidocs.io/illustration/android?step=import1&workspaceFolder=Telstra%20Messaging%20API&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPILib&rootNamespace=com.telstra.tapi)

* Browse to locate the folder containing the source code. Select the location of the TelstraMessagingAPI gradle project and click ``` Ok ```.

![Importing SDK into Android Studio - Step 2](https://apidocs.io/illustration/android?step=import2&workspaceFolder=Telstra%20Messaging%20API&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPILib&rootNamespace=com.telstra.tapi)

* Upon successful import, the project can be built by clicking on ``` Build > Make Project ``` or  pressing ``` Ctrl + F9 ```.

![Importing SDK into Android Studio - Step 3](https://apidocs.io/illustration/android?step=import3&workspaceFolder=Telstra%20Messaging%20API&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPILib&rootNamespace=com.telstra.tapi)

## How to Use

The following section explains how to use the TelstraMessagingAPI library in a new project.

### 1. Starting a new project 

For starting a new project, click on ``` Create New Android Studio Project ```.

![Add a new project in Android Studio - Step 1](https://apidocs.io/illustration/android?step=createNewProject0&workspaceFolder=Telstra%20Messaging%20API&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPILib&rootNamespace=com.telstra.tapi)

Here, configure the new project by adding the name, domain and location of the sample application followed by clicking ``` Next ```.

![Create a new Android Studio Project - Step 2](https://apidocs.io/illustration/android?step=createNewProject1&workspaceFolder=Telstra%20Messaging%20API&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPILib&rootNamespace=com.telstra.tapi)

Following this, select the `Phone and Tablet` option as shown in the illustration below and click `Next`.

![Create a new Android Studio Project - Step 3](https://apidocs.io/illustration/android?step=createNewProject2&workspaceFolder=Telstra%20Messaging%20API&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPILib&rootNamespace=com.telstra.tapi)

In the following step, choose ``` Empty Activity ``` as the activity type and click ``` Next ```.

![Create a new Android Studio Project - Step 4](https://apidocs.io/illustration/android?step=createNewProject3&workspaceFolder=Telstra%20Messaging%20API&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPILib&rootNamespace=com.telstra.tapi)

In this step, provide an ``` Activity Name ``` and ``` Layout Name ``` and click ``` Finish ```.  This would take you to the newly created project.

![Create a new Android Studio Project - Step 4](https://apidocs.io/illustration/android?step=createNewProject4&workspaceFolder=Telstra%20Messaging%20API&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPILib&rootNamespace=com.telstra.tapi)

### 2. Add reference of the library project

In order to add a dependency to this sample application, click on the android button shown in the project explorer on the left side as shown in the picture. Click on ``` Project ``` in the drop down that emerges.  

![Adding dependency to the client library - Step 1](https://apidocs.io/illustration/android?step=testProject0&workspaceFolder=Telstra%20Messaging%20API&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPILib&rootNamespace=com.telstra.tapi)

Right click the sample application in the project explorer and click on ``` New > Module ```  as shown in the picture.

![Adding dependency to the client library - Step 2](https://apidocs.io/illustration/android?step=testProject1&workspaceFolder=Telstra%20Messaging%20API&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPILib&rootNamespace=com.telstra.tapi)

Choose ``` Import Gradle Project ``` and click ``` Next ```.

![Adding dependency to the client library - Step 3](https://apidocs.io/illustration/android?step=testProject2&workspaceFolder=Telstra%20Messaging%20API&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPILib&rootNamespace=com.telstra.tapi)

Click on ``` Finish ``` which would take you back to the sample application with the refernced SDK. 

![Adding dependency to the client library - Step 4](https://apidocs.io/illustration/android?step=testProject3&workspaceFolder=Telstra%20Messaging%20API&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPILib&rootNamespace=com.telstra.tapi)

In the following step naigate to the ``` SampleApplication >  app > build.gradle ``` file and add the following line ```compile project(path: ':TelstraMessagingAPI')``` to the dependencies section as shown in the illustration below.

![Adding dependency to the client library - Step 5](https://apidocs.io/illustration/android?step=testProject4&workspaceFolder=Telstra%20Messaging%20API&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPILib&rootNamespace=com.telstra.tapi)

Finally, press ``` Sync Now ``` in the warning visible as shown in the picture below.

![Adding dependency to the client library - Step 6](https://apidocs.io/illustration/android?step=testProject5&workspaceFolder=Telstra%20Messaging%20API&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPILib&rootNamespace=com.telstra.tapi)

### 3. Write sample code

Once the ``` SampleApplication ``` is created, a file named ``` SampleApplication > app > src > main > java > MainActivity ``` will be visible in the *Project Explorer* with an ``` onCreate ``` method. This is the entry point for the execution of the created project.
Here, you can add code to initialize the client library and instantiate a *Controller* class. Sample code to initialize the client library and using controller methods is given in the subsequent sections.

## How to Test

The generated code and the server can be tested using automatically generated test cases. 
JUnit is used as the testing framework and test runner.

In Android Studio, for running the tests do the following:

1. Right click on *SampleApplication > TelstraMessagingAPILib > androidTest > java)* from the project explorer.
2. Select "Run All Tests" or use "Ctrl + Shift + F10" to run the Tests.

## Initialization

### Authentication
In order to setup authentication and initialization of the API client, you need the following information.

| Parameter | Description |
|-----------|-------------|
| oAuthClientId | OAuth 2 Client ID |
| oAuthClientSecret | OAuth 2 Client Secret |



API client can be initialized as following. The `appContext` being passed is the Android application [`Context`](https://developer.android.com/reference/android/content/Context.html).

```java
// Configuration parameters and credentials
String oAuthClientId = "oAuthClientId"; // OAuth 2 Client ID
String oAuthClientSecret = "oAuthClientSecret"; // OAuth 2 Client Secret

com.telstra.tapi.Configuration.initialize(appContext);
TelstraMessagingAPIClient client = new TelstraMessagingAPIClient(oAuthClientId, oAuthClientSecret);
```

You must authorize now authorize the client.

### Authorizing your client

This SDK uses *OAuth 2.0 authorization* to authorize the client.

The `authorize()` method will exchange the OAuth client credentials for an *access token*.
The access token is an object containing information for authorizing client requests.

 You must pass the *[scopes](#scopes)* for which you need permission to access.
```java
client.auth().authorize(scopes, null, new APICallBack<OAuthToken>() {
                    
    @Override
    public void onSuccess(HttpContext context, OAuthToken response) {
        // TODO Do something after the client is authorized
    }
                    
    @Override
    public void onFailure(HttpContext context, Throwable error) {
        // TODO Handle failure
    }
});
```

The client can now make authorized endpoint calls.


### Scopes

Scopes enable your application to only request access to the resources it needs while enabling users to control the amount of access they grant to your application. Available scopes are defined in the `com.telstra.tapi.Models.OAuthScopeEnum` enumeration.

| Scope Name | Description |
| --- | --- |
| `NSMS` | NSMS |

### Storing an access token for reuse

It is recommended that you store the access token for reuse.

```java
// store token in some way
storeAccessToken(com.telstra.tapi.Configuration.oAuthToken);
```

### Creating a client from a stored token

To authorize a client from a stored access token, just set the access token in `Configuration` along with the other configuration parameters before creating the client:

```java
// load token later...
com.telstra.tapi.Configuration.oAuthToken = loadAccessToken();

// Set other configuration, then instantiate client
TelstraMessagingAPIClient client = new TelstraMessagingAPIClient();
```


# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [MessagingController](#messaging_controller)

## <a name="messaging_controller"></a>![Class: ](https://apidocs.io/img/class.png "com.telstra.tapi.controllers.MessagingController") MessagingController

### Get singleton instance

The singleton instance of the ``` MessagingController ``` class can be accessed from the API Client.

```java
MessagingController messaging = client.getMessaging();
```

### <a name="get_sms_status_async"></a>![Method: ](https://apidocs.io/img/method.png "com.telstra.tapi.controllers.MessagingController.getSMSStatusAsync") getSMSStatusAsync

> Get Message Status


```java
void getSMSStatusAsync(
        final String messageId,
        final APICallBack<OutboundPollResponse> callBack)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| messageId |  ``` Required ```  | Unique identifier of a message - it is the value returned from
a previous POST call to https://api.telstra.com/v2/messages/sms |


#### Example Usage

```java
String messageId = "messageId";
// Invoking the API call with sample inputs
messaging.getSMSStatusAsync(messageId, new APICallBack<OutboundPollResponse>() {
    public void onSuccess(HttpContext context, OutboundPollResponse response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
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



### <a name="retrieve_sms_responses_async"></a>![Method: ](https://apidocs.io/img/method.png "com.telstra.tapi.controllers.MessagingController.retrieveSMSResponsesAsync") retrieveSMSResponsesAsync

> Retrieve Messages


```java
void retrieveSMSResponsesAsync(final APICallBack<List<InboundPollResponse>> callBack)
```

#### Example Usage

```java
// Invoking the API call with sample inputs
messaging.retrieveSMSResponsesAsync(new APICallBack<List<InboundPollResponse>>() {
    public void onSuccess(HttpContext context, List<InboundPollResponse> response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
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



### <a name="create_send_sms_async"></a>![Method: ](https://apidocs.io/img/method.png "com.telstra.tapi.controllers.MessagingController.createSendSMSAsync") createSendSMSAsync

> Send Message


```java
void createSendSMSAsync(
        final SendSMSRequest payload,
        final APICallBack<MessageSentResponse> callBack)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| payload |  ``` Required ```  | A JSON or XML payload containing the recipient's phone number and text message.

The recipient number should be in the format '04xxxxxxxx' where x is a digit |


#### Example Usage

```java
try {
    SendSMSRequest payload = new SendSMSRequest();
    // Invoking the API call with sample inputs
    messaging.createSendSMSAsync(payload, new APICallBack<MessageSentResponse>() {
        public void onSuccess(HttpContext context, MessageSentResponse response) {
            // TODO success callback handler
        }
        public void onFailure(HttpContext context, Throwable error) {
            // TODO failure callback handler
        }
    });
} catch(JsonProcessingException e) {
    // TODO Auto-generated catch block
    e.printStackTrace();
}
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



### <a name="get_mms_status_async"></a>![Method: ](https://apidocs.io/img/method.png "com.telstra.tapi.controllers.MessagingController.getMMSStatusAsync") getMMSStatusAsync

> Get MMS Status


```java
void getMMSStatusAsync(
        final String messageid,
        final APICallBack<OutboundPollResponse> callBack)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| messageid |  ``` Required ```  | Unique identifier of a message - it is the value returned from
a previous POST call to https://api.telstra.com/v2/messages/mms |


#### Example Usage

```java
String messageid = "messageid";
// Invoking the API call with sample inputs
messaging.getMMSStatusAsync(messageid, new APICallBack<OutboundPollResponse>() {
    public void onSuccess(HttpContext context, OutboundPollResponse response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
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



### <a name="create_send_mms_async"></a>![Method: ](https://apidocs.io/img/method.png "com.telstra.tapi.controllers.MessagingController.createSendMMSAsync") createSendMMSAsync

> Send MMS


```java
void createSendMMSAsync(
        final SendMMSRequest body,
        final APICallBack<MessageSentResponse> callBack)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | A JSON or XML payload containing the recipient's phone number
and MMS message.The recipient number should be in the format '04xxxxxxxx'
where x is a digit |


#### Example Usage

```java
try {
    SendMMSRequest body = new SendMMSRequest();
    // Invoking the API call with sample inputs
    messaging.createSendMMSAsync(body, new APICallBack<MessageSentResponse>() {
        public void onSuccess(HttpContext context, MessageSentResponse response) {
            // TODO success callback handler
        }
        public void onFailure(HttpContext context, Throwable error) {
            // TODO failure callback handler
        }
    });
} catch(JsonProcessingException e) {
    // TODO Auto-generated catch block
    e.printStackTrace();
}
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



