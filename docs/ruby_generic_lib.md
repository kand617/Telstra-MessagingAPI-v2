# Getting started


The Telstra SMS Messaging API allows your applications to send and receive SMS text messages from Australia's leading network operator.

It also allows your application to track the delivery status of both sent and received SMS messages.


## How to Build

This client library is a Ruby gem which can be compiled and used in your Ruby and Ruby on Rails project. This library requires a few gems from the RubyGems repository.

1. Open the command line interface or the terminal and navigate to the folder containing the source code.
2. Run ``` gem build telstra_messaging_api.gemspec ``` to build the gem.
3. Once built, the gem can be installed on the current work environment using ``` gem install telstra_messaging_api-2.2.2.gem ```

![Building Gem](https://apidocs.io/illustration/ruby?step=buildSDK&workspaceFolder=Telstra%20Messaging%20API-Ruby&workspaceName=Telstra%20Messaging%20API-Ruby&projectName=telstra_messaging_api&gemName=telstra_messaging_api&gemVer=2.2.2)

## How to Use

The following section explains how to use the TelstraMessagingApi Ruby Gem in a new Rails project using RubyMine&trade;. The basic workflow presented here is also applicable if you prefer using a different editor or IDE.

### 1. Starting a new project

Close any existing projects in RubyMine&trade; by selecting ``` File -> Close Project ```. Next, click on ``` Create New Project ``` to create a new project from scratch.

![Create a new project in RubyMine](https://apidocs.io/illustration/ruby?step=createNewProject0&workspaceFolder=Telstra%20Messaging%20API-Ruby&workspaceName=TelstraMessagingApi&projectName=telstra_messaging_api&gemName=telstra_messaging_api&gemVer=2.2.2)

Next, provide ``` TestApp ``` as the project name, choose ``` Rails Application ``` as the project type, and click ``` OK ```.

![Create a new Rails Application in RubyMine - step 1](https://apidocs.io/illustration/ruby?step=createNewProject1&workspaceFolder=Telstra%20Messaging%20API-Ruby&workspaceName=TelstraMessagingApi&projectName=telstra_messaging_api&gemName=telstra_messaging_api&gemVer=2.2.2)

In the next dialog make sure that correct *Ruby SDK* is being used (minimum 2.0.0) and click ``` OK ```.

![Create a new Rails Application in RubyMine - step 2](https://apidocs.io/illustration/ruby?step=createNewProject2&workspaceFolder=Telstra%20Messaging%20API-Ruby&workspaceName=TelstraMessagingApi&projectName=telstra_messaging_api&gemName=telstra_messaging_api&gemVer=2.2.2)

This will create a new Rails Application project with an existing set of files and folder.

### 2. Add reference of the gem

In order to use the TelstraMessagingApi gem in the new project we must add a gem reference. Locate the ```Gemfile``` in the *Project Explorer* window under the ``` TestApp ``` project node. The file contains references to all gems being used in the project. Here, add the reference to the library gem by adding the following line: ``` gem 'telstra_messaging_api', '~> 2.2.2' ```

![Add references of the Gemfile](https://apidocs.io/illustration/ruby?step=addReference&workspaceFolder=Telstra%20Messaging%20API-Ruby&workspaceName=TelstraMessagingApi&projectName=telstra_messaging_api&gemName=telstra_messaging_api&gemVer=2.2.2)

### 3. Adding a new Rails Controller

Once the ``` TestApp ``` project is created, a folder named ``` controllers ``` will be visible in the *Project Explorer* under the following path: ``` TestApp > app > controllers ```. Right click on this folder and select ``` New -> Run Rails Generator... ```.

![Run Rails Generator on Controllers Folder](https://apidocs.io/illustration/ruby?step=addCode0&workspaceFolder=Telstra%20Messaging%20API-Ruby&workspaceName=TelstraMessagingApi&projectName=telstra_messaging_api&gemName=telstra_messaging_api&gemVer=2.2.2)

Selecting the said option will popup a small window where the generator names are displayed. Here, select the ``` controller ``` template.

![Create a new Controller](https://apidocs.io/illustration/ruby?step=addCode1&workspaceFolder=Telstra%20Messaging%20API-Ruby&workspaceName=TelstraMessagingApi&projectName=telstra_messaging_api&gemName=telstra_messaging_api&gemVer=2.2.2)

Next, a popup window will ask you for a Controller name and included Actions. For controller name provide ``` Hello ``` and include an action named ``` Index ``` and click ``` OK ```.

![Add a new Controller](https://apidocs.io/illustration/ruby?step=addCode2&workspaceFolder=Telstra%20Messaging%20API-Ruby&workspaceName=TelstraMessagingApi&projectName=telstra_messaging_api&gemName=telstra_messaging_api&gemVer=2.2.2)

A new controller class anmed ``` HelloController ``` will be created in a file named ``` hello_controller.rb ``` containing a method named ``` Index ```. In this method, add code for initialization and a sample for its usage.

![Initialize the library](https://apidocs.io/illustration/ruby?step=addCode3&workspaceFolder=Telstra%20Messaging%20API-Ruby&workspaceName=TelstraMessagingApi&projectName=telstra_messaging_api&gemName=telstra_messaging_api&gemVer=2.2.2)

## How to Test

You can test the generated SDK and the server with automatically generated test
cases as follows:

  1. From terminal/cmd navigate to the root directory of the SDK.
  2. Invoke: `bundle exec rake`

## Initialization

### Authentication
In order to setup authentication and initialization of the API client, you need the following information.

| Parameter | Description |
|-----------|-------------|
| o_auth_client_id | OAuth 2 Client ID |
| o_auth_client_secret | OAuth 2 Client Secret |



API client can be initialized as following.

```ruby
# Configuration parameters and credentials
o_auth_client_id = 'o_auth_client_id' # OAuth 2 Client ID
o_auth_client_secret = 'o_auth_client_secret' # OAuth 2 Client Secret

client = TelstraMessagingApi::TelstraMessagingApiClient.new(
  o_auth_client_id: o_auth_client_id,
  o_auth_client_secret: o_auth_client_secret
)
```

The added initlization code can be debugged by putting a breakpoint in the ``` Index ``` method and running the project in debug mode by selecting ``` Run -> Debug 'Development: TestApp' ```.

![Debug the TestApp](https://apidocs.io/illustration/ruby?step=addCode4&workspaceFolder=Telstra%20Messaging%20API-Ruby&workspaceName=TelstraMessagingApi&projectName=telstra_messaging_api&gemName=telstra_messaging_api&gemVer=2.2.2&initLine=client%2520%253D%2520TelstraMessagingApiClient.new%2528%2527o_auth_client_id%2527%252C%2520%2527o_auth_client_secret%2527%2529)


You must now authorize the client.

### Authorizing your client

This SDK uses *OAuth 2.0 authorization* to authorize the client.

The `authorize()` method will exchange the OAuth client credentials for an *access token*.
The access token is an object containing information for authorizing client requests.

 You must pass the *[scopes](#scopes)* for which you need permission to access.
```ruby
begin
  client.auth.authorize(scope: [TelstraMessagingApi::OAuthScopeEnum::NSMS])
rescue TelstraMessagingApi::OAuthProviderException => ex
  # handle exception
end
```

The client can now make authorized endpoint calls.


### Scopes

Scopes enable your application to only request access to the resources it needs while enabling users to control the amount of access they grant to your application. Available scopes are defined in the `OAuthScopeEnum` enumeration.

| Scope Name | Description |
| --- | --- |
| `NSMS` | NSMS |

### Storing an access token for reuse

It is recommended that you store the access token for reuse.

You can store the access token in a file or a database.

```ruby
# store token
save_token_to_database(client.config.o_auth_token)
```

### Creating a client from a stored token

To authorize a client from a stored access token, just set the access token after creating the client:

```ruby
client = TelstraMessagingApi::TelstraMessagingApiClient.new
client.config.o_auth_token = load_token_from_database
```

### Complete example

```ruby
require 'telstra_messaging_api'

include TelstraMessagingApi

# function for storing token to database
def save_token_to_database(token)
  # code to save the token to database
end

# function for loading token from database
def load_token_from_database
  # load token from database and return it (return None if no token exists)
end

# Configuration parameters and credentials
o_auth_client_id = 'o_auth_client_id' # OAuth 2 Client ID
o_auth_client_secret = 'o_auth_client_secret' # OAuth 2 Client Secret

#  create a new client
client = TelstraMessagingApiClient.new(
  o_auth_client_id: o_auth_client_id,
  o_auth_client_secret: o_auth_client_secret
)

# obtain access token, needed for client to be authorized
previous_token = load_token_from_database
if previous_token
  # restore previous access token
  client.config.o_auth_token = previous_token
else
  # obtain new access token
  begin
    token = client.auth.authorize(scope: [OAuthScopeEnum::NSMS])
    save_token_to_database(token)
  rescue OAuthProviderException => ex
    # handle exception
  end
end

# the client is now authorized and you can use controllers to make endpoint calls
```


# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [MessagingController](#messaging_controller)
* [OAuthAuthorizationController](#o_auth_authorization_controller)

## <a name="messaging_controller"></a>![Class: ](https://apidocs.io/img/class.png ".MessagingController") MessagingController

### Get singleton instance

The singleton instance of the ``` MessagingController ``` class can be accessed from the API Client.

```ruby
messaging = client.messaging
```

### <a name="get_sms_status"></a>![Method: ](https://apidocs.io/img/method.png ".MessagingController.get_sms_status") get_sms_status

> Get Message Status


```ruby
def get_sms_status(message_id); end
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| message_id |  ``` Required ```  | Unique identifier of a message - it is the value returned from
a previous POST call to https://api.telstra.com/v2/messages/sms |


#### Example Usage

```ruby
message_id = 'messageId'

result = messaging.get_sms_status(message_id)

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



### <a name="retrieve_sms_responses"></a>![Method: ](https://apidocs.io/img/method.png ".MessagingController.retrieve_sms_responses") retrieve_sms_responses

> Retrieve Messages


```ruby
def retrieve_sms_responses; end
```

#### Example Usage

```ruby

result = messaging.retrieve_sms_responses()

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



### <a name="create_send_sms"></a>![Method: ](https://apidocs.io/img/method.png ".MessagingController.create_send_sms") create_send_sms

> Send Message


```ruby
def create_send_sms(payload); end
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| payload |  ``` Required ```  | A JSON or XML payload containing the recipient's phone number and text message.

The recipient number should be in the format '04xxxxxxxx' where x is a digit |


#### Example Usage

```ruby
payload = SendSMSRequest.new

result = messaging.create_send_sms(payload)

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



### <a name="get_mms_status"></a>![Method: ](https://apidocs.io/img/method.png ".MessagingController.get_mms_status") get_mms_status

> Get MMS Status


```ruby
def get_mms_status(messageid); end
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| messageid |  ``` Required ```  | Unique identifier of a message - it is the value returned from
a previous POST call to https://api.telstra.com/v2/messages/mms |


#### Example Usage

```ruby
messageid = 'messageid'

result = messaging.get_mms_status(messageid)

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



### <a name="create_send_mms"></a>![Method: ](https://apidocs.io/img/method.png ".MessagingController.create_send_mms") create_send_mms

> Send MMS


```ruby
def create_send_mms(body); end
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | A JSON or XML payload containing the recipient's phone number
and MMS message.The recipient number should be in the format '04xxxxxxxx'
where x is a digit |


#### Example Usage

```ruby
body = SendMMSRequest.new

result = messaging.create_send_mms(body)

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

The singleton instance of the ``` OAuthAuthorizationController ``` class can be accessed from the API Client.

```ruby
oAuthAuthorization = client.o_auth_authorization
```

### <a name="create_request_token"></a>![Method: ](https://apidocs.io/img/method.png ".OAuthAuthorizationController.create_request_token") create_request_token

> *Tags:*  ``` Skips Authentication ``` 

> Create a new OAuth 2 token.


```ruby
def create_request_token(authorization,
                             scope = nil,
                             _field_parameters = nil); end
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| authorization |  ``` Required ```  | Authorization header in Basic auth format |
| scope |  ``` Optional ```  | Requested scopes as a space-delimited list. |
| _field_parameters | ``` Optional ``` | Additional optional form parameters are supported by this method |


#### Example Usage

```ruby
authorization = 'Authorization'
scope = 'scope'
# key-value map for optional form parameters
formParams = { 'key' => 'value' }

result = oAuthAuthorization.create_request_token(authorization, scope, formParams)

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | OAuth 2 provider returned an error. |
| 401 | OAuth 2 provider says client authentication failed. |



### <a name="create_request_token_1"></a>![Method: ](https://apidocs.io/img/method.png ".OAuthAuthorizationController.create_request_token_1") create_request_token_1

> *Tags:*  ``` Skips Authentication ``` 

> Create a new OAuth 2 token.


```ruby
def create_request_token_1(authorization,
                               scope = nil,
                               _field_parameters = nil); end
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| authorization |  ``` Required ```  | Authorization header in Basic auth format |
| scope |  ``` Optional ```  | Requested scopes as a space-delimited list. |
| _field_parameters | ``` Optional ``` | Additional optional form parameters are supported by this method |


#### Example Usage

```ruby
authorization = 'Authorization'
scope = 'scope'
# key-value map for optional form parameters
formParams = { 'key' => 'value' }

result = oAuthAuthorization.create_request_token_1(authorization, scope, formParams)

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | OAuth 2 provider returned an error. |
| 401 | OAuth 2 provider says client authentication failed. |



### <a name="create_request_token_2"></a>![Method: ](https://apidocs.io/img/method.png ".OAuthAuthorizationController.create_request_token_2") create_request_token_2

> *Tags:*  ``` Skips Authentication ``` 

> Create a new OAuth 2 token.


```ruby
def create_request_token_2(authorization,
                               scope = nil,
                               _field_parameters = nil); end
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| authorization |  ``` Required ```  | Authorization header in Basic auth format |
| scope |  ``` Optional ```  | Requested scopes as a space-delimited list. |
| _field_parameters | ``` Optional ``` | Additional optional form parameters are supported by this method |


#### Example Usage

```ruby
authorization = 'Authorization'
scope = 'scope'
# key-value map for optional form parameters
formParams = { 'key' => 'value' }

result = oAuthAuthorization.create_request_token_2(authorization, scope, formParams)

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | OAuth 2 provider returned an error. |
| 401 | OAuth 2 provider says client authentication failed. |



### <a name="create_request_token_1"></a>![Method: ](https://apidocs.io/img/method.png ".OAuthAuthorizationController.create_request_token_1") create_request_token_1

> *Tags:*  ``` Skips Authentication ``` 

> Create a new OAuth 2 token.


```ruby
def create_request_token_1(authorization,
                               scope = nil,
                               _field_parameters = nil); end
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| authorization |  ``` Required ```  | Authorization header in Basic auth format |
| scope |  ``` Optional ```  | Requested scopes as a space-delimited list. |
| _field_parameters | ``` Optional ``` | Additional optional form parameters are supported by this method |


#### Example Usage

```ruby
authorization = 'Authorization'
scope = 'scope'
# key-value map for optional form parameters
formParams = { 'key' => 'value' }

result = oAuthAuthorization.create_request_token_1(authorization, scope, formParams)

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | OAuth 2 provider returned an error. |
| 401 | OAuth 2 provider says client authentication failed. |



### <a name="create_request_token_2"></a>![Method: ](https://apidocs.io/img/method.png ".OAuthAuthorizationController.create_request_token_2") create_request_token_2

> *Tags:*  ``` Skips Authentication ``` 

> Create a new OAuth 2 token.


```ruby
def create_request_token_2(authorization,
                               scope = nil,
                               _field_parameters = nil); end
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| authorization |  ``` Required ```  | Authorization header in Basic auth format |
| scope |  ``` Optional ```  | Requested scopes as a space-delimited list. |
| _field_parameters | ``` Optional ``` | Additional optional form parameters are supported by this method |


#### Example Usage

```ruby
authorization = 'Authorization'
scope = 'scope'
# key-value map for optional form parameters
formParams = { 'key' => 'value' }

result = oAuthAuthorization.create_request_token_2(authorization, scope, formParams)

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | OAuth 2 provider returned an error. |
| 401 | OAuth 2 provider says client authentication failed. |



[Back to List of Controllers](#list_of_controllers)



