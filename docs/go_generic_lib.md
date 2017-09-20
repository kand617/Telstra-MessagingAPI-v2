# Getting started


The Telstra SMS Messaging API allows your applications to send and receive SMS text messages from Australia's leading network operator.

It also allows your application to track the delivery status of both sent and received SMS messages.


## How to Build


* In order to successfully build and run your SDK files, you are required to have the following setup in your system:
    * **Go**  (Visit [https://golang.org/doc/install](https://golang.org/doc/install) for more details on how to install Go)
    * **Java VM** Version 8 or later
    * **Eclipse 4.6 (Neon)** or later ([http://www.eclipse.org/neon/](http://www.eclipse.org/neon/))
    * **GoClipse** setup within above installed Eclipse (Follow the instructions at [this link](https://github.com/GoClipse/goclipse/blob/latest/documentation/Installation.md#instructions) to setup GoClipse)
* Ensure that ```GOPATH``` environment variable is set in the system variables. If not, set it to your workspace directory where you will be adding your Go projects.
* The generated code uses unirest-go http library. Therefore, you will need internet access to resolve this dependency. If Go is properly installed and configured, run the following command to pull the dependency:

```Go
go get github.com/apimatic/unirest-go
```

This will install unirest-go in the ```GOPATH``` you specified in the system variables.

Now follow the steps mentioned below to build your SDK:

1. Open eclipse in the Go language perspective and click on the ```Import``` option in ```File``` menu.

![Importing SDK into Eclipse - Step 1](https://apidocs.io/illustration/go?step=import0)

2. Select ```General -> Existing Projects into Workspace``` option from the tree list.

![Importing SDK into Eclipse - Step 2](https://apidocs.io/illustration/go?step=import1)

3. In ```Select root directory```, provide path to the unzipped archive for the generated code. Once the path is set and the Project becomes visible under ```Projects``` click ```Finish```

![Importing SDK into Eclipse - Step 3](https://apidocs.io/illustration/go?step=import2&workspaceFolder=Telstra%20Messaging%20API-GoLang&projectName=telstramessagingapi_lib)

4. The Go library will be imported and its files will be visible in the Project Explorer

![Importing SDK into Eclipse - Step 4](https://apidocs.io/illustration/go?step=import3&projectName=telstramessagingapi_lib)

## How to Use

The following section explains how to use the TelstramessagingapiLib library in a new project.

### 1. Add a new Test Project

Create a new project in Eclipse by ```File``` -> ```New``` -> ```Go Project```

![Add a new project in Eclipse](https://apidocs.io/illustration/go?step=createNewProject0)

Name the Project as ```Test``` and click ```Finish```

![Create a new Maven Project - Step 1](https://apidocs.io/illustration/go?step=createNewProject1)

Create a new directory in the ```src``` directory of this project

![Create a new Maven Project - Step 2](https://apidocs.io/illustration/go?step=createNewProject2&projectName=telstramessagingapi_lib)

Name it ```test.com```

![Create a new Maven Project - Step 3](https://apidocs.io/illustration/go?step=createNewProject3&projectName=telstramessagingapi_lib)

Now create a new file inside ```src/test.com```

![Create a new Maven Project - Step 4](https://apidocs.io/illustration/go?step=createNewProject4&projectName=telstramessagingapi_lib)

Name it ```testsdk.go```

![Create a new Maven Project - Step 5](https://apidocs.io/illustration/go?step=createNewProject5&projectName=telstramessagingapi_lib)

In this Go file, you can start adding code to initialize the client library. Sample code to initialize the client library and using its methods is given in the subsequent sections.

### 2. Configure the Test Project

You need to import your generated library in this project in order to make use of its functions. In order to import the library, you can add its path in the ```GOPATH``` for this project. Follow the below steps:

Right click on the project name and click on ```Properties```

![Adding dependency to the client library - Step 1](https://apidocs.io/illustration/go?step=testProject0&projectName=telstramessagingapi_lib)

Choose ```Go Compiler``` from the side menu. Check ```Use project specific settings``` and uncheck ```Use same value as the GOPATH environment variable.```. By default, the GOPATH value from the environment variables will be visible in ```Eclipse GOPATH```. Do not remove this as this points to the unirest dependency.

![Adding dependency to the client library - Step 2](https://apidocs.io/illustration/go?step=testProject1)

Append the library path to this GOPATH

![Adding dependency to the client library - Step 3](https://apidocs.io/illustration/go?step=testProject2&workspaceFolder=Telstra%20Messaging%20API-GoLang)

Once the path is appended, click on ```OK```

### 3. Build the Test Project

Right click on the project name and click on ```Build Project```

![Build Project](https://apidocs.io/illustration/go?step=buildProject&projectName=telstramessagingapi_lib)

### 4. Run the Test Project

If the build is successful, right click on your Go file and click on ```Run As``` -> ```Go Application```

![Run Project](https://apidocs.io/illustration/go?step=runProject&projectName=telstramessagingapi_lib)

## Initialization

### Authentication
In order to setup authentication of the API client, you need the following information.

| Parameter | Description |
|-----------|-------------|
| oAuthClientId | OAuth 2 Client ID |
| oAuthClientSecret | OAuth 2 Client Secret |


To configure these for your generated code, open the file "Configuration.go" and edit it's contents.


# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [messaging_pkg](#messaging_pkg)
* [oauthauthorization_pkg](#oauthauthorization_pkg)

## <a name="messaging_pkg"></a>![Class: ](https://apidocs.io/img/class.png ".messaging_pkg") messaging_pkg

### Get instance

Factory for the ``` MESSAGING ``` interface can be accessed from the package messaging_pkg.

```go
messaging := messaging_pkg.NewMESSAGING()
```

### <a name="get_sms_status"></a>![Method: ](https://apidocs.io/img/method.png ".messaging_pkg.GetSMSStatus") GetSMSStatus

> Get Message Status


```go
func (me *MESSAGING_IMPL) GetSMSStatus(messageId string)(*models_pkg.OutboundPollResponse,error)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| messageId |  ``` Required ```  | Unique identifier of a message - it is the value returned from
a previous POST call to https://api.telstra.com/v2/messages/sms |


#### Example Usage

```go
messageId := "messageId"

var result *models_pkg.OutboundPollResponse
result,_ = messaging.GetSMSStatus(messageId)

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



### <a name="retrieve_sms_responses"></a>![Method: ](https://apidocs.io/img/method.png ".messaging_pkg.RetrieveSMSResponses") RetrieveSMSResponses

> Retrieve Messages


```go
func (me *MESSAGING_IMPL) RetrieveSMSResponses()([]*models_pkg.InboundPollResponse,error)
```

#### Example Usage

```go

var result []*models_pkg.InboundPollResponse
result,_ = messaging.RetrieveSMSResponses()

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



### <a name="create_send_sms"></a>![Method: ](https://apidocs.io/img/method.png ".messaging_pkg.CreateSendSMS") CreateSendSMS

> Send Message


```go
func (me *MESSAGING_IMPL) CreateSendSMS(payload *models_pkg.SendSMSRequest)(*models_pkg.MessageSentResponse,error)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| payload |  ``` Required ```  | A JSON or XML payload containing the recipient's phone number and text message.

The recipient number should be in the format '04xxxxxxxx' where x is a digit |


#### Example Usage

```go
var payload *models_pkg.SendSMSRequest

var result *models_pkg.MessageSentResponse
result,_ = messaging.CreateSendSMS(payload)

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



### <a name="get_mms_status"></a>![Method: ](https://apidocs.io/img/method.png ".messaging_pkg.GetMMSStatus") GetMMSStatus

> Get MMS Status


```go
func (me *MESSAGING_IMPL) GetMMSStatus(messageid string)(*models_pkg.OutboundPollResponse,error)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| messageid |  ``` Required ```  | Unique identifier of a message - it is the value returned from
a previous POST call to https://api.telstra.com/v2/messages/mms |


#### Example Usage

```go
messageid := "messageid"

var result *models_pkg.OutboundPollResponse
result,_ = messaging.GetMMSStatus(messageid)

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



### <a name="create_send_mms"></a>![Method: ](https://apidocs.io/img/method.png ".messaging_pkg.CreateSendMMS") CreateSendMMS

> Send MMS


```go
func (me *MESSAGING_IMPL) CreateSendMMS(body *models_pkg.SendMMSRequest)(*models_pkg.MessageSentResponse,error)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | A JSON or XML payload containing the recipient's phone number
and MMS message.The recipient number should be in the format '04xxxxxxxx'
where x is a digit |


#### Example Usage

```go
var body *models_pkg.SendMMSRequest

var result *models_pkg.MessageSentResponse
result,_ = messaging.CreateSendMMS(body)

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

## <a name="oauthauthorization_pkg"></a>![Class: ](https://apidocs.io/img/class.png ".oauthauthorization_pkg") oauthauthorization_pkg

### Get instance

Factory for the ``` OAUTHAUTHORIZATION ``` interface can be accessed from the package oauthauthorization_pkg.

```go
oAuthAuthorization := oauthauthorization_pkg.NewOAUTHAUTHORIZATION()
```

### <a name="create_request_token"></a>![Method: ](https://apidocs.io/img/method.png ".oauthauthorization_pkg.CreateRequestToken") CreateRequestToken

> *Tags:*  ``` Skips Authentication ``` 

> Create a new OAuth 2 token.


```go
func (me *OAUTHAUTHORIZATION_IMPL) CreateRequestToken(
            authorization string,
            scope *string,
                fieldParameters map[string]interface{})(*models_pkg.OAuthToken,error)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| authorization |  ``` Required ```  | Authorization header in Basic auth format |
| scope |  ``` Optional ```  | Requested scopes as a space-delimited list. |
| fieldParameters | ``` Optional ``` | Additional optional form parameters are supported by this method |


#### Example Usage

```go
authorization := "Authorization"
scope := "scope"
// key-value map for optional form parameters
	formParams := map[string]interface{}{"key" : "value"}


var result *models_pkg.OAuthToken
result,_ = oAuthAuthorization.CreateRequestToken(authorization, scope, formParams)

```

#### Errors
 
| Error Code | Error Description |
|------------|-------------------|
| 400 | OAuth 2 provider returned an error. |
| 401 | OAuth 2 provider says client authentication failed. |



### <a name="create_request_token1"></a>![Method: ](https://apidocs.io/img/method.png ".oauthauthorization_pkg.CreateRequestToken1") CreateRequestToken1

> *Tags:*  ``` Skips Authentication ``` 

> Create a new OAuth 2 token.


```go
func (me *OAUTHAUTHORIZATION_IMPL) CreateRequestToken1(
            authorization string,
            scope *string,
                fieldParameters map[string]interface{})(*models_pkg.OAuthToken,error)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| authorization |  ``` Required ```  | Authorization header in Basic auth format |
| scope |  ``` Optional ```  | Requested scopes as a space-delimited list. |
| fieldParameters | ``` Optional ``` | Additional optional form parameters are supported by this method |


#### Example Usage

```go
authorization := "Authorization"
scope := "scope"
// key-value map for optional form parameters
	formParams := map[string]interface{}{"key" : "value"}


var result *models_pkg.OAuthToken
result,_ = oAuthAuthorization.CreateRequestToken1(authorization, scope, formParams)

```

#### Errors
 
| Error Code | Error Description |
|------------|-------------------|
| 400 | OAuth 2 provider returned an error. |
| 401 | OAuth 2 provider says client authentication failed. |



### <a name="create_request_token2"></a>![Method: ](https://apidocs.io/img/method.png ".oauthauthorization_pkg.CreateRequestToken2") CreateRequestToken2

> *Tags:*  ``` Skips Authentication ``` 

> Create a new OAuth 2 token.


```go
func (me *OAUTHAUTHORIZATION_IMPL) CreateRequestToken2(
            authorization string,
            scope *string,
                fieldParameters map[string]interface{})(*models_pkg.OAuthToken,error)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| authorization |  ``` Required ```  | Authorization header in Basic auth format |
| scope |  ``` Optional ```  | Requested scopes as a space-delimited list. |
| fieldParameters | ``` Optional ``` | Additional optional form parameters are supported by this method |


#### Example Usage

```go
authorization := "Authorization"
scope := "scope"
// key-value map for optional form parameters
	formParams := map[string]interface{}{"key" : "value"}


var result *models_pkg.OAuthToken
result,_ = oAuthAuthorization.CreateRequestToken2(authorization, scope, formParams)

```

#### Errors
 
| Error Code | Error Description |
|------------|-------------------|
| 400 | OAuth 2 provider returned an error. |
| 401 | OAuth 2 provider says client authentication failed. |



### <a name="create_request_token11"></a>![Method: ](https://apidocs.io/img/method.png ".oauthauthorization_pkg.CreateRequestToken11") CreateRequestToken11

> *Tags:*  ``` Skips Authentication ``` 

> Create a new OAuth 2 token.


```go
func (me *OAUTHAUTHORIZATION_IMPL) CreateRequestToken11(
            authorization string,
            scope *string,
                fieldParameters map[string]interface{})(*models_pkg.OAuthToken,error)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| authorization |  ``` Required ```  | Authorization header in Basic auth format |
| scope |  ``` Optional ```  | Requested scopes as a space-delimited list. |
| fieldParameters | ``` Optional ``` | Additional optional form parameters are supported by this method |


#### Example Usage

```go
authorization := "Authorization"
scope := "scope"
// key-value map for optional form parameters
	formParams := map[string]interface{}{"key" : "value"}


var result *models_pkg.OAuthToken
result,_ = oAuthAuthorization.CreateRequestToken11(authorization, scope, formParams)

```

#### Errors
 
| Error Code | Error Description |
|------------|-------------------|
| 400 | OAuth 2 provider returned an error. |
| 401 | OAuth 2 provider says client authentication failed. |



### <a name="create_request_token21"></a>![Method: ](https://apidocs.io/img/method.png ".oauthauthorization_pkg.CreateRequestToken21") CreateRequestToken21

> *Tags:*  ``` Skips Authentication ``` 

> Create a new OAuth 2 token.


```go
func (me *OAUTHAUTHORIZATION_IMPL) CreateRequestToken21(
            authorization string,
            scope *string,
                fieldParameters map[string]interface{})(*models_pkg.OAuthToken,error)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| authorization |  ``` Required ```  | Authorization header in Basic auth format |
| scope |  ``` Optional ```  | Requested scopes as a space-delimited list. |
| fieldParameters | ``` Optional ``` | Additional optional form parameters are supported by this method |


#### Example Usage

```go
authorization := "Authorization"
scope := "scope"
// key-value map for optional form parameters
	formParams := map[string]interface{}{"key" : "value"}


var result *models_pkg.OAuthToken
result,_ = oAuthAuthorization.CreateRequestToken21(authorization, scope, formParams)

```

#### Errors
 
| Error Code | Error Description |
|------------|-------------------|
| 400 | OAuth 2 provider returned an error. |
| 401 | OAuth 2 provider says client authentication failed. |



### <a name="create_request_token1"></a>![Method: ](https://apidocs.io/img/method.png ".oauthauthorization_pkg.CreateRequestToken1") CreateRequestToken1

> *Tags:*  ``` Skips Authentication ``` 

> Create a new OAuth 2 token.


```go
func (me *OAUTHAUTHORIZATION_IMPL) CreateRequestToken1(
            authorization string,
            scope *string,
                fieldParameters map[string]interface{})(*models_pkg.OAuthToken,error)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| authorization |  ``` Required ```  | Authorization header in Basic auth format |
| scope |  ``` Optional ```  | Requested scopes as a space-delimited list. |
| fieldParameters | ``` Optional ``` | Additional optional form parameters are supported by this method |


#### Example Usage

```go
authorization := "Authorization"
scope := "scope"
// key-value map for optional form parameters
	formParams := map[string]interface{}{"key" : "value"}


var result *models_pkg.OAuthToken
result,_ = oAuthAuthorization.CreateRequestToken1(authorization, scope, formParams)

```

#### Errors
 
| Error Code | Error Description |
|------------|-------------------|
| 400 | OAuth 2 provider returned an error. |
| 401 | OAuth 2 provider says client authentication failed. |



### <a name="create_request_token"></a>![Method: ](https://apidocs.io/img/method.png ".oauthauthorization_pkg.CreateRequestToken") CreateRequestToken

> *Tags:*  ``` Skips Authentication ``` 

> Create a new OAuth 2 token.


```go
func (me *OAUTHAUTHORIZATION_IMPL) CreateRequestToken(
            authorization string,
            scope *string,
                fieldParameters map[string]interface{})(*models_pkg.OAuthToken,error)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| authorization |  ``` Required ```  | Authorization header in Basic auth format |
| scope |  ``` Optional ```  | Requested scopes as a space-delimited list. |
| fieldParameters | ``` Optional ``` | Additional optional form parameters are supported by this method |


#### Example Usage

```go
authorization := "Authorization"
scope := "scope"
// key-value map for optional form parameters
	formParams := map[string]interface{}{"key" : "value"}


var result *models_pkg.OAuthToken
result,_ = oAuthAuthorization.CreateRequestToken(authorization, scope, formParams)

```

#### Errors
 
| Error Code | Error Description |
|------------|-------------------|
| 400 | OAuth 2 provider returned an error. |
| 401 | OAuth 2 provider says client authentication failed. |



[Back to List of Controllers](#list_of_controllers)



