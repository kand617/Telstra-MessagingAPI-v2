# Getting started


The Telstra SMS Messaging API allows your applications to send and receive SMS text messages from Australia's leading network operator.

It also allows your application to track the delivery status of both sent and received SMS messages.


## How to Build

The generated code uses the Newtonsoft Json.NET NuGet Package. If the automatic NuGet package restore
is enabled, these dependencies will be installed automatically. Therefore,
you will need internet access for build.

1. Open the solution (TelstraMessagingAPI.sln) file.
2. Invoke the build process using `Ctrl+Shift+B` shortcut key or using the `Build` menu as shown below.

![Building SDK using Visual Studio](https://apidocs.io/illustration/cs?step=buildSDK&workspaceFolder=Telstra%20Messaging%20API-CSharp&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPI.PCL)

## How to Use

The build process generates a portable class library, which can be used like a normal class library. The generated library is compatible with Windows Forms, Windows RT, Windows Phone 8,
Silverlight 5, Xamarin iOS, Xamarin Android and Mono. More information on how to use can be found at the [MSDN Portable Class Libraries documentation](http://msdn.microsoft.com/en-us/library/vstudio/gg597391%28v=vs.100%29.aspx).

The following section explains how to use the TelstraMessagingAPI library in a new console project.

### 1. Starting a new project

For starting a new project, right click on the current solution from the *solution explorer* and choose  ``` Add -> New Project ```.

![Add a new project in the existing solution using Visual Studio](https://apidocs.io/illustration/cs?step=addProject&workspaceFolder=Telstra%20Messaging%20API-CSharp&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPI.PCL)

Next, choose "Console Application", provide a ``` TestConsoleProject ``` as the project name and click ``` OK ```.

![Create a new console project using Visual Studio](https://apidocs.io/illustration/cs?step=createProject&workspaceFolder=Telstra%20Messaging%20API-CSharp&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPI.PCL)

### 2. Set as startup project

The new console project is the entry point for the eventual execution. This requires us to set the ``` TestConsoleProject ``` as the start-up project. To do this, right-click on the  ``` TestConsoleProject ``` and choose  ``` Set as StartUp Project ``` form the context menu.

![Set the new cosole project as the start up project](https://apidocs.io/illustration/cs?step=setStartup&workspaceFolder=Telstra%20Messaging%20API-CSharp&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPI.PCL)

### 3. Add reference of the library project

In order to use the TelstraMessagingAPI library in the new project, first we must add a projet reference to the ``` TestConsoleProject ```. First, right click on the ``` References ``` node in the *solution explorer* and click ``` Add Reference... ```.

![Open references of the TestConsoleProject](https://apidocs.io/illustration/cs?step=addReference&workspaceFolder=Telstra%20Messaging%20API-CSharp&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPI.PCL)

Next, a window will be displayed where we must set the ``` checkbox ``` on ``` TelstraMessagingAPI.PCL ``` and click ``` OK ```. By doing this, we have added a reference of the ```TelstraMessagingAPI.PCL``` project into the new ``` TestConsoleProject ```.

![Add a reference to the TestConsoleProject](https://apidocs.io/illustration/cs?step=createReference&workspaceFolder=Telstra%20Messaging%20API-CSharp&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPI.PCL)

### 4. Write sample code

Once the ``` TestConsoleProject ``` is created, a file named ``` Program.cs ``` will be visible in the *solution explorer* with an empty ``` Main ``` method. This is the entry point for the execution of the entire solution.
Here, you can add code to initialize the client library and acquire the instance of a *Controller* class. Sample code to initialize the client library and using controller methods is given in the subsequent sections.

![Add a reference to the TestConsoleProject](https://apidocs.io/illustration/cs?step=addCode&workspaceFolder=Telstra%20Messaging%20API-CSharp&workspaceName=TelstraMessagingAPI&projectName=TelstraMessagingAPI.PCL)

## How to Test

The generated SDK also contain one or more Tests, which are contained in the Tests project.
In order to invoke these test cases, you will need *NUnit 3.0 Test Adapter Extension for Visual Studio*.
Once the SDK is complied, the test cases should appear in the Test Explorer window.
Here, you can click *Run All* to execute these test cases.

## Initialization

### Authentication
In order to setup authentication and initialization of the API client, you need the following information.

| Parameter | Description |
|-----------|-------------|
| oAuthClientId | OAuth 2 Client ID |
| oAuthClientSecret | OAuth 2 Client Secret |



API client can be initialized as following.

```csharp
// Configuration parameters and credentials
string oAuthClientId = "oAuthClientId"; // OAuth 2 Client ID
string oAuthClientSecret = "oAuthClientSecret"; // OAuth 2 Client Secret

TelstraMessagingAPIClient client = new TelstraMessagingAPIClient(oAuthClientId, oAuthClientSecret);
```


You must now authorize the client.

### Authorizing your client

This SDK uses *OAuth 2.0 authorization* to authorize the client.

The `Authorize()` method will exchange the OAuth client credentials for an *access token*.
The access token is an object containing information for authorizing client requests.

 You must pass the *[scopes](#scopes)* for which you need permission to access.
```csharp
try
{
    client.Auth.Authorize(scope=new List<OAuthScopeEnum>(){OAuthScopeEnum.NSMS});
}
catch (OAuthProviderException e)
{
    //handle exception here
}
```

The client can now make authorized endpoint calls.


### Scopes

Scopes enable your application to only request access to the resources it needs while enabling users to control the amount of access they grant to your application. Available scopes are defined in the `TelstraMessagingAPI.PCL.Models.OAuthScopeEnum` enumeration.

| Scope Name | Description |
| --- | --- |
| `NSMS` | NSMS |

### Storing an access token for reuse

It is recommended that you store the access token for reuse.

You can store the access token in a file or a database.

```csharp
// store token
SaveTokenToDatabase(Configuration.OAuthToken);
```

### Creating a client from a stored token

To authorize a client from a stored access token, just set the access token after creating the client:

```csharp
client = TelstraMessagingAPIClient();
Configuration.UpdateAccessToken(LoadTokenFromDatabase());
```

### Complete example
```csharp
using TelstraMessagingAPI.PCL;
using TelstraMessagingAPI.PCL.Models;
using TelstraMessagingAPI.PCL.Exceptions;
using System.Collections.Generic;

namespace OAuthTestApplication
{
    class Program
    {
        static void Main(string[] args)
        {
            // Configuration parameters and credentials
           string oAuthClientId = "oAuthClientId"; // OAuth 2 Client ID
           string oAuthClientSecret = "oAuthClientSecret"; // OAuth 2 Client Secret
           
            TelstraMessagingAPIClient client = new TelstraMessagingAPIClient(oAuthClientId, oAuthClientSecret);

            //callback for storing token for reuse when token is updated
            Configuration.OAuthTokenUpdateCallback = SaveTokenToDatabase;

            //obtain access token, needed for client to be authorized
            OAuthToken storedToken = LoadTokenFromDatabase();
            if (storedToken != null)
            {
                Configuration.OAuthToken = storedToken;
            }
            else
            {
                try
                {
                    storedToken = client.Auth.Authorize(new List<OAuthScopeEnum>(){OAuthScopeEnum.NSMS});
                    SaveTokenToDatabase(storedToken);
                }
                catch (OAuthProviderException e)
                {
                    //Handle Exception here
                }
            }
        }

        //function for storing token to database
        static void SaveTokenToDatabase(OAuthToken token)
        {
            //Save token here
        }

        //function for loading token from database
        static OAuthToken LoadTokenFromDatabase()
        {
            OAuthToken token = null;
            //token = Get token here
            return token;
        }
    }
}

// the client is now authorized and you can use controllers to make endpoint calls
```


# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [MessagingController](#messaging_controller)
* [OAuthAuthorizationController](#o_auth_authorization_controller)

## <a name="messaging_controller"></a>![Class: ](https://apidocs.io/img/class.png "TelstraMessagingAPI.PCL.Controllers.MessagingController") MessagingController

### Get singleton instance

The singleton instance of the ``` MessagingController ``` class can be accessed from the API Client.

```csharp
MessagingController messaging = client.Messaging;
```

### <a name="get_sms_status"></a>![Method: ](https://apidocs.io/img/method.png "TelstraMessagingAPI.PCL.Controllers.MessagingController.GetSMSStatus") GetSMSStatus

> Get Message Status


```csharp
Task<Models.OutboundPollResponse> GetSMSStatus(string messageId)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| messageId |  ``` Required ```  | Unique identifier of a message - it is the value returned from
a previous POST call to https://api.telstra.com/v2/messages/sms |


#### Example Usage

```csharp
string messageId = "messageId";

Models.OutboundPollResponse result = await messaging.GetSMSStatus(messageId);

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


### <a name="retrieve_sms_responses"></a>![Method: ](https://apidocs.io/img/method.png "TelstraMessagingAPI.PCL.Controllers.MessagingController.RetrieveSMSResponses") RetrieveSMSResponses

> Retrieve Messages


```csharp
Task<List<Models.InboundPollResponse>> RetrieveSMSResponses()
```

#### Example Usage

```csharp

List<Models.InboundPollResponse> result = await messaging.RetrieveSMSResponses();

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


### <a name="create_send_sms"></a>![Method: ](https://apidocs.io/img/method.png "TelstraMessagingAPI.PCL.Controllers.MessagingController.CreateSendSMS") CreateSendSMS

> Send Message


```csharp
Task<Models.MessageSentResponse> CreateSendSMS(Models.SendSMSRequest payload)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| payload |  ``` Required ```  | A JSON or XML payload containing the recipient's phone number and text message.

The recipient number should be in the format '04xxxxxxxx' where x is a digit |


#### Example Usage

```csharp
var payload = new Models.SendSMSRequest();

Models.MessageSentResponse result = await messaging.CreateSendSMS(payload);

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


### <a name="get_mms_status"></a>![Method: ](https://apidocs.io/img/method.png "TelstraMessagingAPI.PCL.Controllers.MessagingController.GetMMSStatus") GetMMSStatus

> Get MMS Status


```csharp
Task<Models.OutboundPollResponse> GetMMSStatus(string messageid)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| messageid |  ``` Required ```  | Unique identifier of a message - it is the value returned from
a previous POST call to https://api.telstra.com/v2/messages/mms |


#### Example Usage

```csharp
string messageid = "messageid";

Models.OutboundPollResponse result = await messaging.GetMMSStatus(messageid);

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


### <a name="create_send_mms"></a>![Method: ](https://apidocs.io/img/method.png "TelstraMessagingAPI.PCL.Controllers.MessagingController.CreateSendMMS") CreateSendMMS

> Send MMS


```csharp
Task<Models.MessageSentResponse> CreateSendMMS(Models.SendMMSRequest body)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | A JSON or XML payload containing the recipient's phone number
and MMS message.The recipient number should be in the format '04xxxxxxxx'
where x is a digit |


#### Example Usage

```csharp
var body = new Models.SendMMSRequest();

Models.MessageSentResponse result = await messaging.CreateSendMMS(body);

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

## <a name="o_auth_authorization_controller"></a>![Class: ](https://apidocs.io/img/class.png "TelstraMessagingAPI.PCL.Controllers.OAuthAuthorizationController") OAuthAuthorizationController

### Get singleton instance

The singleton instance of the ``` OAuthAuthorizationController ``` class can be accessed from the API Client.

```csharp
OAuthAuthorizationController oAuthAuthorization = client.OAuthAuthorization;
```

### <a name="create_request_token"></a>![Method: ](https://apidocs.io/img/method.png "TelstraMessagingAPI.PCL.Controllers.OAuthAuthorizationController.CreateRequestToken") CreateRequestToken

> *Tags:*  ``` Skips Authentication ``` 

> Create a new OAuth 2 token.


```csharp
Task<Models.OAuthToken> CreateRequestToken(string authorization, string scope = null, Dictionary<string, object> fieldParameters = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| authorization |  ``` Required ```  | Authorization header in Basic auth format |
| scope |  ``` Optional ```  | Requested scopes as a space-delimited list. |
| fieldParameters | ``` Optional ``` | Additional optional form parameters are supported by this method |


#### Example Usage

```csharp
string authorization = "Authorization";
string scope = "scope";
// key-value map for optional form parameters
var formParams = new Dictionary<string, object>();


Models.OAuthToken result = await oAuthAuthorization.CreateRequestToken(authorization, scope, formParams);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | OAuth 2 provider returned an error. |
| 401 | OAuth 2 provider says client authentication failed. |


### <a name="create_request_token1"></a>![Method: ](https://apidocs.io/img/method.png "TelstraMessagingAPI.PCL.Controllers.OAuthAuthorizationController.CreateRequestToken1") CreateRequestToken1

> *Tags:*  ``` Skips Authentication ``` 

> Create a new OAuth 2 token.


```csharp
Task<Models.OAuthToken> CreateRequestToken1(string authorization, string scope = null, Dictionary<string, object> fieldParameters = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| authorization |  ``` Required ```  | Authorization header in Basic auth format |
| scope |  ``` Optional ```  | Requested scopes as a space-delimited list. |
| fieldParameters | ``` Optional ``` | Additional optional form parameters are supported by this method |


#### Example Usage

```csharp
string authorization = "Authorization";
string scope = "scope";
// key-value map for optional form parameters
var formParams = new Dictionary<string, object>();


Models.OAuthToken result = await oAuthAuthorization.CreateRequestToken1(authorization, scope, formParams);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | OAuth 2 provider returned an error. |
| 401 | OAuth 2 provider says client authentication failed. |


### <a name="create_request_token2"></a>![Method: ](https://apidocs.io/img/method.png "TelstraMessagingAPI.PCL.Controllers.OAuthAuthorizationController.CreateRequestToken2") CreateRequestToken2

> *Tags:*  ``` Skips Authentication ``` 

> Create a new OAuth 2 token.


```csharp
Task<Models.OAuthToken> CreateRequestToken2(string authorization, string scope = null, Dictionary<string, object> fieldParameters = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| authorization |  ``` Required ```  | Authorization header in Basic auth format |
| scope |  ``` Optional ```  | Requested scopes as a space-delimited list. |
| fieldParameters | ``` Optional ``` | Additional optional form parameters are supported by this method |


#### Example Usage

```csharp
string authorization = "Authorization";
string scope = "scope";
// key-value map for optional form parameters
var formParams = new Dictionary<string, object>();


Models.OAuthToken result = await oAuthAuthorization.CreateRequestToken2(authorization, scope, formParams);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | OAuth 2 provider returned an error. |
| 401 | OAuth 2 provider says client authentication failed. |


### <a name="create_request_token"></a>![Method: ](https://apidocs.io/img/method.png "TelstraMessagingAPI.PCL.Controllers.OAuthAuthorizationController.CreateRequestToken") CreateRequestToken

> *Tags:*  ``` Skips Authentication ``` 

> Create a new OAuth 2 token.


```csharp
Task<Models.OAuthToken> CreateRequestToken(string authorization, string scope = null, Dictionary<string, object> fieldParameters = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| authorization |  ``` Required ```  | Authorization header in Basic auth format |
| scope |  ``` Optional ```  | Requested scopes as a space-delimited list. |
| fieldParameters | ``` Optional ``` | Additional optional form parameters are supported by this method |


#### Example Usage

```csharp
string authorization = "Authorization";
string scope = "scope";
// key-value map for optional form parameters
var formParams = new Dictionary<string, object>();


Models.OAuthToken result = await oAuthAuthorization.CreateRequestToken(authorization, scope, formParams);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | OAuth 2 provider returned an error. |
| 401 | OAuth 2 provider says client authentication failed. |


[Back to List of Controllers](#list_of_controllers)



