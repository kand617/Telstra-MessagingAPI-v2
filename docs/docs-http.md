# 

**`API Version:`** `2.2.2`


The Telstra SMS Messaging API allows your applications to send and receive SMS text messages from Australia's leading network operator.

It also allows your application to track the delivery status of both sent and received SMS messages.




## Server Configuration for Base URLs

This section provides details on the environments available and lists down the servers in each of the environment. The default environment for this API is set to `production` while the default server is set to `default`.
### Environments

An environment consists of a set of servers with base URL values. The environment can be changed programatically allowing rapid switching between different environments e.g.the user can specify a Production and Testing Environment.The available environments for this API are: 

#### production
This environment comprises of the following servers: 

| Name | Base URL | 
|-----------|-------------|
| default | https://tapi.telstra.com/v2 |
| access token server | https://sapi.telstra.com/v1/oauth |




## Authentication
This API uses `OAuth v2.0` with `Client Credentials` grant type.

#### Token Endpoint
Access token can be obtained from the token endpoint at path `/token`. It will use server `access token server` which will serve as the base URL for this endpoint. 


### Scopes

The API makes use of the following OAuth scopes: 

| Name | Value | Description |
| ---- | ----- | ----------- |
| NSMS | `NSMS` | NSMS |





# <a name="api_reference"></a>API Reference

* [Messaging](#messaging)

## <a name="messaging"></a>![Endpoint Group: ](https://apidocs.io/img/class.png "Messaging") Messaging


### <a name="get_sms_status"></a>![Endpoint: ](https://apidocs.io/img/method.png "Get SMS Status") Get SMS Status


**`GET`** `/messages/sms/{messageId}/status`

> Get Message Status



#### Scopes
The list of required scopes for this endpoint are:

- [`NSMS`](#scopes)



#### Path Parameters
| Parameter | Type | Tags | Description | Example |
|-----------|------| ---- |-------------| ----------------------------------- |
| messageId | string |  ``` Required ```  | Unique identifier of a message - it is the value returned from<br>a previous POST call to https://api.telstra.com/v2/messages/sms | `"messageId"` | 

#### Responses
**200** 

> Success


 *Example Body* (**[OutboundPollResponse](#outbound_poll_response)**) 

```
{
  "to": "to",
  "receivedTimestamp": "receivedTimestamp",
  "sentTimestamp": "sentTimestamp",
  "deliveryStatus": "PEND"
}
```


**400** 

> Invalid or missing request parameters


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 185,
  "message": "message"
}
```
**401** 

> Invalid or no credentials passed in the request


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 185,
  "message": "message"
}
```
**403** 

> Authorization credentials passed and accepted but account does
not have permission


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 185,
  "message": "message"
}
```
**404** 

> The requested URI does not exist


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 185,
  "message": "message"
}
```
**405** 

> The requested resource does not support the supplied verb


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 185,
  "message": "message"
}
```
**415** 

> API does not support the requested content type


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 185,
  "message": "message"
}
```
**422** 

> The request is formed correctly, but due to some condition
the request cannot be processed e.g. email is required and it is not provided
in the request


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 185,
  "message": "message"
}
```
**501** 

> The HTTP method being used has not yet been implemented for
the requested resource


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 185,
  "message": "message"
}
```
**503** 

> The service requested is currently unavailable


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 185,
  "message": "message"
}
```
**Default** 

> An internal error occurred when processing the request


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 185,
  "message": "message"
}
```


### <a name="retrieve_sms_responses"></a>![Endpoint: ](https://apidocs.io/img/method.png "Retrieve SMS Responses") Retrieve SMS Responses


**`GET`** `/messages/sms`

> Retrieve Messages



#### Scopes
The list of required scopes for this endpoint are:

- [`NSMS`](#scopes)



#### Responses
**200** 

> Success


 *Example Body* (**[[InboundPollResponse](#inbound_poll_response)]**) 

```
[
  {
    "to": "to",
    "from": "from",
    "body": "body",
    "receivedTimestamp": "receivedTimestamp",
    "moreMessages": 185,
    "messageId": "messageId"
  }
]
```


**400** 

> Invalid or missing request parameters


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 185,
  "message": "message"
}
```
**401** 

> Invalid or no credentials passed in the request


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 185,
  "message": "message"
}
```
**403** 

> Authorization credentials passed and accepted but account does
not have permission


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 185,
  "message": "message"
}
```
**404** 

> The requested URI does not exist


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 185,
  "message": "message"
}
```
**405** 

> The requested resource does not support the supplied verb


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 185,
  "message": "message"
}
```
**415** 

> API does not support the requested content type


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 185,
  "message": "message"
}
```
**422** 

> The request is formed correctly, but due to some condition
the request cannot be processed e.g. email is required and it is not provided
in the request


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 185,
  "message": "message"
}
```
**501** 

> The HTTP method being used has not yet been implemented for
the requested resource


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 185,
  "message": "message"
}
```
**503** 

> The service requested is currently unavailable


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 185,
  "message": "message"
}
```
**Default** 

> An internal error occurred when processing the request


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 185,
  "message": "message"
}
```


### <a name="send_sms"></a>![Endpoint: ](https://apidocs.io/img/method.png "Send SMS") Send SMS


**`POST`** `/messages/sms`

> Send Message



#### Scopes
The list of required scopes for this endpoint are:

- [`NSMS`](#scopes)



#### Request Headers
>Accept=application/json;
>Content-Type=application/json;

#### Request Body
Raw 

|  Type | Tags | Description |
| ------| ---- |-------------| 
| [SendSMSRequest](#send_sms_request) |  ``` Required ```  | A JSON or XML payload containing the recipient's phone number and text message.<br><br>The recipient number should be in the format '04xxxxxxxx' where x is a digit | 

 *Example Body* 
``` 
{
  "to": "to",
  "body": "body",
  "from": "from",
  "validity": 185,
  "scheduledDelivery": 185,
  "notifyURL": "notifyURL",
  "replyRequest": true
}
``` 

#### Responses
**200** 

> Success


 *Example Body* (**[MessageSentResponse](#message_sent_response)**) 

```
{
  "messages": [
    {
      "to": "to",
      "deliveryStatus": "deliveryStatus",
      "messageId": "messageId",
      "messageStatusLink": "messageStatusLink"
    }
  ],
  "messageType": "messageType",
  "numberSegments": 143,
  "numberDestinations": 143
}
```


**400** 

> Invalid or missing request parameters


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**401** 

> Invalid or no credentials passed in the request


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**403** 

> Authorization credentials passed and accepted but account does
not have permission


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**404** 

> The requested URI does not exist


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**405** 

> The requested resource does not support the supplied verb


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**415** 

> API does not support the requested content type


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**422** 

> The request is formed correctly, but due to some condition
the request cannot be processed e.g. email is required and it is not provided
in the request


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**501** 

> The HTTP method being used has not yet been implemented for
the requested resource


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**503** 

> The service requested is currently unavailable


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**Default** 

> An internal error occurred when processing the request


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```


### <a name="get_mms_status"></a>![Endpoint: ](https://apidocs.io/img/method.png "Get MMS Status") Get MMS Status


**`GET`** `/messages/mms/{messageid}/status`

> Get MMS Status




#### Path Parameters
| Parameter | Type | Tags | Description | Example |
|-----------|------| ---- |-------------| ----------------------------------- |
| messageid | string |  ``` Required ```  | Unique identifier of a message - it is the value returned from<br>a previous POST call to https://api.telstra.com/v2/messages/mms | `"messageid"` | 

#### Responses
**200** 


 *Example Body* (**[OutboundPollResponse](#outbound_poll_response)**) 

```
{
  "to": "to",
  "receivedTimestamp": "receivedTimestamp",
  "sentTimestamp": "sentTimestamp",
  "deliveryStatus": "PEND"
}
```


**400** 

> Invalid or missing request parameters


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**401** 

> Invalid or no credentials passed in the request


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**403** 

> Authorization credentials passed and accepted but account does
not have permission


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**404** 

> The requested URI does not exist


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**405** 

> The requested resource does not support the supplied verb


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**415** 

> API does not support the requested content type


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**422** 

> The request is formed correctly, but due to some condition
the request cannot be processed e.g. email is required and it is not provided
in the request


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**501** 

> The HTTP method being used has not yet been implemented for
the requested resource


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**503** 

> The service requested is currently unavailable


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**Default** 

> An internal error occurred when processing the request


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```


### <a name="send_mms"></a>![Endpoint: ](https://apidocs.io/img/method.png "Send MMS") Send MMS


**`POST`** `/messages/mms`

> Send MMS



#### Scopes
The list of required scopes for this endpoint are:

- [`NSMS`](#scopes)



#### Request Headers
>Accept=application/json;
>Content-Type=application/json;

#### Request Body
Raw 

|  Type | Tags | Description |
| ------| ---- |-------------| 
| [Send MMS Request](#send_mms_request) |  ``` Required ```  | A JSON or XML payload containing the recipient's phone number<br>and MMS message.The recipient number should be in the format '04xxxxxxxx'<br>where x is a digit | 

 *Example Body* 
``` 
{
  "from": "from",
  "to": "to",
  "subject": "subject",
  "replyRequest": true,
  "MMSContent": [
    {
      "type": "type",
      "filename": "filename",
      "payload": "payload"
    }
  ]
}
``` 

#### Responses
**200** 


 *Example Body* (**[MessageSentResponse](#message_sent_response)**) 

```
{
  "messages": [
    {
      "to": "to",
      "deliveryStatus": "deliveryStatus",
      "messageId": "messageId",
      "messageStatusLink": "messageStatusLink"
    }
  ],
  "messageType": "messageType",
  "numberSegments": 143,
  "numberDestinations": 143
}
```


**400** 

> Invalid or missing request parameters

**401** 

> Invalid or no credentials passed in the request


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**403** 

> Authorization credentials passed and accepted but account does
not have permission


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**404** 

> The requested URI does not exist


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**405** 

> The requested resource does not support the supplied verb


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**415** 

> API does not support the requested content type


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**422** 

> The request is formed correctly, but due to some condition
the request cannot be processed e.g. email is required and it is not provided
in the request


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**501** 

> The HTTP method being used has not yet been implemented for
the requested resource


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**503** 

> The service requested is currently unavailable


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```
**Default** 

> An internal error occurred when processing the request


 *Example Body* (**[Error_Error_Error](#error_error_error)**) 

```
{
  "status": 143,
  "message": "message"
}
```


[Back to API Reference](#api_reference)

# <a name="models"></a> Models

### List of Models

* [Error_Error_Error](#error_error_error)
* [MessageType](#message_type)
* [MessageSentResponse](#message_sent_response)
* [OutboundPollResponse](#outbound_poll_response)
* [Status](#status)
* [Message](#message)
* [SendSMSRequest](#send_sms_request)
* [Send MMS Request](#send_mms_request)
* [MMSContent](#mms_content)
* [InboundPollResponse](#inbound_poll_response)
* [OAuth Scope](#o_auth_scope)
* [OAuthToken](#o_auth_token)
* [OAuthProvider](#o_auth_provider)
* [OAuthProviderError](#o_auth_provider_error)
* [OAuth Scope](#o_auth_scope)
* [OAuthToken](#o_auth_token)
* [OAuthProvider](#o_auth_provider)
* [OAuthProviderError](#o_auth_provider_error)
* [OAuth Scope](#o_auth_scope)
* [OAuthToken](#o_auth_token)
* [OAuthProvider](#o_auth_provider)
* [OAuthProviderError](#o_auth_provider_error)
* [OAuth Scope](#o_auth_scope)
* [OAuthToken](#o_auth_token)
* [OAuthProvider](#o_auth_provider)
* [OAuthProviderError](#o_auth_provider_error)
* [OAuth Scope](#o_auth_scope)
* [OAuthToken](#o_auth_token)
* [OAuthProvider](#o_auth_provider)
* [OAuthProviderError](#o_auth_provider_error)
* [OAuth Scope](#o_auth_scope)
* [OAuthToken](#o_auth_token)
* [OAuthProvider](#o_auth_provider)
* [OAuthProviderError](#o_auth_provider_error)
* [OAuth Scope](#o_auth_scope)
* [OAuthToken](#o_auth_token)
* [OAuthProvider](#o_auth_provider)
* [OAuthProviderError](#o_auth_provider_error)
* [OAuth Scope](#o_auth_scope)
* [OAuthToken](#o_auth_token)
* [OAuthProvider](#o_auth_provider)
* [OAuthProviderError](#o_auth_provider_error)
* [OAuth Scope](#o_auth_scope)
* [OAuthToken](#o_auth_token)
* [OAuthProvider](#o_auth_provider)
* [OAuthProviderError](#o_auth_provider_error)
* [OAuth Scope](#o_auth_scope)
* [OAuthToken](#o_auth_token)
* [OAuthProvider](#o_auth_provider)
* [OAuthProviderError](#o_auth_provider_error)
## <a name="error_error_error"></a>![Type: ](https://apidocs.io/img/method.png "Error_Error_Error") Error_Error_Error



> Returns error status code and message





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| status | number |  ``` Optional ```  | The status code. | 
| message | string |  ``` Optional ```  | Message describing the error. | 



#### Example
```
{
  "status": 158,
  "message": "message"
}
```



## <a name="message_type"></a>![Type: ](https://apidocs.io/img/method.png "MessageType") MessageType



> TODO: Add a model description





This type must take a value from the following `string` enumeration of values:

| Name | Value | Description |
| ---- | ----- | ----------- |
| SMS | `SMS` | TODO: Add description | 
| MMS | `MMS` | TODO: Add description | 
| RCS | `RCS` | TODO: Add description | 



#### Example
```
SMS
```



## <a name="message_sent_response"></a>![Type: ](https://apidocs.io/img/method.png "MessageSentResponse") MessageSentResponse



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| messages | [Message](#message) |  ``` Required ```  ``` Collection ```  | TODO: Add a property description | 
| messageType | string |  ``` Required ```  | TODO: Add a property description | 
| numberSegments | number |  ``` Required ```  | TODO: Add a property description | 
| numberDestinations | number |  ``` Required ```  | TODO: Add a property description | 



#### Example
```
{
  "messages": [
    {
      "to": "to",
      "deliveryStatus": "deliveryStatus",
      "messageId": "messageId",
      "messageStatusLink": "messageStatusLink"
    }
  ],
  "messageType": "messageType",
  "numberSegments": 207,
  "numberDestinations": 207
}
```



## <a name="outbound_poll_response"></a>![Type: ](https://apidocs.io/img/method.png "OutboundPollResponse") OutboundPollResponse



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| to | string |  ``` Optional ```  | The phone number (recipient) the message was sent to (in E.164<br>format). | 
| receivedTimestamp | string |  ``` Optional ```  | The date and time when the message was recieved by recipient. | 
| sentTimestamp | string |  ``` Optional ```  | The date and time when the message was sent. | 
| deliveryStatus | [Status](#status) |  ``` Optional ```  | TODO: Add a property description | 



#### Example
```
{
  "to": "to",
  "receivedTimestamp": "receivedTimestamp",
  "sentTimestamp": "sentTimestamp",
  "deliveryStatus": "PEND"
}
```



## <a name="status"></a>![Type: ](https://apidocs.io/img/method.png "Status") Status



> TODO: Add a model description





This type must take a value from the following `string` enumeration of values:

| Name | Value | Description |
| ---- | ----- | ----------- |
| PEND | `PEND` | TODO: Add description | 
| SENT | `SENT` | TODO: Add description | 
| DELIVRD | `DELIVRD` | TODO: Add description | 
| EXPIRED | `EXPIRED` | TODO: Add description | 
| DELETED | `DELETED` | TODO: Add description | 
| UNDVBL | `UNDVBL` | TODO: Add description | 
| REJECTED | `REJECTED` | TODO: Add description | 
| READ | `READ` | TODO: Add description | 



#### Example
```
PEND
```



## <a name="message"></a>![Type: ](https://apidocs.io/img/method.png "Message") Message



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| to | string |  ``` Required ```  | TODO: Add a property description | 
| deliveryStatus | string |  ``` Required ```  | TODO: Add a property description | 
| messageId | string |  ``` Required ```  | TODO: Add a property description | 
| messageStatusLink | string |  ``` Required ```  | TODO: Add a property description | 



#### Example
```
{
  "to": "to",
  "deliveryStatus": "deliveryStatus",
  "messageId": "messageId",
  "messageStatusLink": "messageStatusLink"
}
```



## <a name="send_sms_request"></a>![Type: ](https://apidocs.io/img/method.png "SendSMSRequest") SendSMSRequest



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| to | string |  ``` Required ```  | Phone number (in E.164 format) to send the SMS to. This number<br>can be in international format if preceeded by a ‘+’, or in national format. | 
| body | string |  ``` Required ```  | The text body of the message. Messages longer than 160 characters<br>will be counted as multiple messages. | 
| from | string |  ``` Optional ```  | Phone number (in E.164 format) the SMS was sent from. If not<br>present, the serverice will use the mobile number associated with the application,<br>or it be an Alphanumeric address of up to 11 characters. | 
| validity | number |  ``` Optional ```  | How long the platform should attempt to deliver the message for.<br>This period is specified in minutes from the message | 
| scheduledDelivery | number |  ``` Optional ```  | How long the platform should wait before attempting to send the<br>message - specified in minutes. | 
| notifyURL | string |  ``` Optional ```  | Contains a URL that will be called once your message has been<br>processed. The status may be delivered, expired, deleted, etc. | 
| replyRequest | boolean |  ``` Optional ```  | If set to true, the reply message functionality will be implemented<br>and the to address will be ignored if present. If false or not present,<br>then normal message handling is implemented. | 



#### Example
```
{
  "to": "to",
  "body": "body",
  "from": "from",
  "validity": 44,
  "scheduledDelivery": 44,
  "notifyURL": "notifyURL",
  "replyRequest": false
}
```



## <a name="send_mms_request"></a>![Type: ](https://apidocs.io/img/method.png "Send MMS Request") Send MMS Request



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| from | string |  ``` Required ```  | This will be the source address that will be displayed on the<br>receiving device. If it is not present then it will default to the MSISDN<br>assigned to the app. If replyRequest is set to true, then this field will<br>be ignored. | 
| to | string |  ``` Required ```  | This is the destination address. | 
| subject | string |  ``` Required ```  | The subject that will be used in an MMS message. | 
| replyRequest | boolean |  ``` Required ```  | If set to true, the reply message functionality will be implemented<br>and the to address will be ignored if present. | 
| MMSContent | [MMSContent](#mms_content) |  ``` Required ```  ``` Collection ```  | An Array of content that will be sent in an MMS message. If this<br>array is present it will cause the “body” element to be ignored, and the<br>message will be sent as an MMS. | 



#### Example
```
{
  "from": "from",
  "to": "to",
  "subject": "subject",
  "replyRequest": false,
  "MMSContent": [
    {
      "type": "type",
      "filename": "filename",
      "payload": "payload"
    }
  ]
}
```



## <a name="mms_content"></a>![Type: ](https://apidocs.io/img/method.png "MMSContent") MMSContent



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| type | string |  ``` Required ```  | The following types are supported audio/amr 	audio/aac 	audio/mp3<br>	audio/mpeg3 	audio/mpeg 	audio/mpg 	audio/wav 	audio/3gpp 	audio/mp4<br>	image/gif 	image/jpeg 	image/jpg 	image/png 	image/bmp 	video/mpeg4<br>	video/mp4 	video/mpeg 	video/3gpp 	video/3gp 	video/h263 	text/plain<br>	text/x-vCard 	text/x-vCalendar | 
| filename | string |  ``` Required ```  | The file name to be associated with the content. Some devices<br>will display this file name with a placeholder for the content. | 
| payload | string |  ``` Required ```  | TODO: Add a property description | 



#### Example
```
{
  "type": "type",
  "filename": "filename",
  "payload": "payload"
}
```



## <a name="inbound_poll_response"></a>![Type: ](https://apidocs.io/img/method.png "InboundPollResponse") InboundPollResponse



> Poll for incoming messages returning the latest. Only works if no
> callback url was specified when provisioning a number.





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| to | string |  ``` Optional ```  | The phone number (recipient) that the message was sent to(in<br>E.164 format). | 
| from | string |  ``` Optional ```  | The phone number (sender) that the message was sent from (in<br>E.164 format). | 
| body | string |  ``` Optional ```  | Text body of the message that was sent | 
| receivedTimestamp | string |  ``` Optional ```  | The date and time when the message was recieved by recipient. | 
| moreMessages | number |  ``` Optional ```  | Indicates if there are more messages that can be polled from<br>the server. 0=No more messages available. Anything else indicates there<br>are more messages on the server. | 
| messageId | string |  ``` Optional ```  | Optional message ID of the SMS you sent. Use this ID to view<br>the message status or get responses. | 



#### Example
```
{
  "to": "to",
  "from": "from",
  "body": "body",
  "receivedTimestamp": "receivedTimestamp",
  "moreMessages": 44,
  "messageId": "messageId"
}
```



## <a name="o_auth_scope"></a>![Type: ](https://apidocs.io/img/method.png "OAuth Scope") OAuth Scope



> OAuth 2 scopes supported by the API





This type must take a value from the following `string` enumeration of values:

| Name | Value | Description |
| ---- | ----- | ----------- |
| NSMS | `NSMS` | NSMS | 



#### Example
```
NSMS
```



## <a name="o_auth_token"></a>![Type: ](https://apidocs.io/img/method.png "OAuthToken") OAuthToken



> OAuth 2 Authorization endpoint response





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| access_token | string |  ``` Required ```  | Access token | 
| token_type | string |  ``` Required ```  | Type of access token | 
| expires_in | long |  ``` Optional ```  | Time in seconds before the access token expires | 
| scope | string |  ``` Optional ```  | List of scopes granted<br>This is a space-delimited list of strings. | 
| expiry | long |  ``` Optional ```  | Time of token expiry as unix timestamp (UTC) | 



#### Example
```
{
  "access_token": "access_token",
  "token_type": "token_type",
  "expires_in": 44,
  "scope": "scope",
  "expiry": 44
}
```



## <a name="o_auth_provider"></a>![Type: ](https://apidocs.io/img/method.png "OAuthProvider") OAuthProvider



> OAuth 2 Authorization endpoint exception





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| error | [OAuthProviderError](#o_auth_provider_error) |  ``` Required ```  | Error code | 
| error_description | string |  ``` Optional ```  | Human-readable text providing additional information on error.<br>Used to assist the client developer in understanding the error that occurred. | 
| error_uri | string |  ``` Optional ```  | A URI identifying a human-readable web page with information about the error, used to provide the client developer with additional information about the error | 



#### Example
```
{
  "error": "invalid_request",
  "error_description": "error_description",
  "error_uri": "error_uri"
}
```



## <a name="o_auth_provider_error"></a>![Type: ](https://apidocs.io/img/method.png "OAuthProviderError") OAuthProviderError



> OAuth 2 Authorization error codes





This type must take a value from the following `string` enumeration of values:

| Name | Value | Description |
| ---- | ----- | ----------- |
| invalid_request | `invalid_request` | The request is missing a required parameter, includes an unsupported parameter value (other than grant type), repeats a parameter, includes multiple credentials, utilizes more than one mechanism for authenticating the client, or is otherwise malformed. | 
| invalid_client | `invalid_client` | Client authentication failed (e.g., unknown client, no client authentication included, or unsupported authentication method). | 
| invalid_grant | `invalid_grant` | The provided authorization grant (e.g., authorization code, resource owner credentials) or refresh token is invalid, expired, revoked, does not match the redirection URI used in the authorization request, or was issued to another client. | 
| unauthorized_client | `unauthorized_client` | The authenticated client is not authorized to use this authorization grant type. | 
| unsupported_grant_type | `unsupported_grant_type` | The authorization grant type is not supported by the authorization server. | 
| invalid_scope | `invalid_scope` | The requested scope is invalid, unknown, malformed, or exceeds the scope granted by the resource owner. | 



#### Example
```
invalid_request
```



## <a name="o_auth_scope"></a>![Type: ](https://apidocs.io/img/method.png "OAuth Scope") OAuth Scope



> OAuth 2 scopes supported by the API





This type must take a value from the following `string` enumeration of values:

| Name | Value | Description |
| ---- | ----- | ----------- |
| NSMS | `NSMS` | NSMS | 



#### Example
```
NSMS
```



## <a name="o_auth_token"></a>![Type: ](https://apidocs.io/img/method.png "OAuthToken") OAuthToken



> OAuth 2 Authorization endpoint response





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| access_token | string |  ``` Required ```  | Access token | 
| token_type | string |  ``` Required ```  | Type of access token | 
| expires_in | long |  ``` Optional ```  | Time in seconds before the access token expires | 
| scope | string |  ``` Optional ```  | List of scopes granted<br>This is a space-delimited list of strings. | 
| expiry | long |  ``` Optional ```  | Time of token expiry as unix timestamp (UTC) | 



#### Example
```
{
  "access_token": "access_token",
  "token_type": "token_type",
  "expires_in": 44,
  "scope": "scope",
  "expiry": 44
}
```



## <a name="o_auth_provider"></a>![Type: ](https://apidocs.io/img/method.png "OAuthProvider") OAuthProvider



> OAuth 2 Authorization endpoint exception





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| error | [OAuthProviderError](#o_auth_provider_error) |  ``` Required ```  | Error code | 
| error_description | string |  ``` Optional ```  | Human-readable text providing additional information on error.<br>Used to assist the client developer in understanding the error that occurred. | 
| error_uri | string |  ``` Optional ```  | A URI identifying a human-readable web page with information about the error, used to provide the client developer with additional information about the error | 



#### Example
```
{
  "error": "invalid_request",
  "error_description": "error_description",
  "error_uri": "error_uri"
}
```



## <a name="o_auth_provider_error"></a>![Type: ](https://apidocs.io/img/method.png "OAuthProviderError") OAuthProviderError



> OAuth 2 Authorization error codes





This type must take a value from the following `string` enumeration of values:

| Name | Value | Description |
| ---- | ----- | ----------- |
| invalid_request | `invalid_request` | The request is missing a required parameter, includes an unsupported parameter value (other than grant type), repeats a parameter, includes multiple credentials, utilizes more than one mechanism for authenticating the client, or is otherwise malformed. | 
| invalid_client | `invalid_client` | Client authentication failed (e.g., unknown client, no client authentication included, or unsupported authentication method). | 
| invalid_grant | `invalid_grant` | The provided authorization grant (e.g., authorization code, resource owner credentials) or refresh token is invalid, expired, revoked, does not match the redirection URI used in the authorization request, or was issued to another client. | 
| unauthorized_client | `unauthorized_client` | The authenticated client is not authorized to use this authorization grant type. | 
| unsupported_grant_type | `unsupported_grant_type` | The authorization grant type is not supported by the authorization server. | 
| invalid_scope | `invalid_scope` | The requested scope is invalid, unknown, malformed, or exceeds the scope granted by the resource owner. | 



#### Example
```
invalid_request
```



## <a name="o_auth_scope"></a>![Type: ](https://apidocs.io/img/method.png "OAuth Scope") OAuth Scope



> OAuth 2 scopes supported by the API





This type must take a value from the following `string` enumeration of values:

| Name | Value | Description |
| ---- | ----- | ----------- |
| NSMS | `NSMS` | NSMS | 



#### Example
```
NSMS
```



## <a name="o_auth_token"></a>![Type: ](https://apidocs.io/img/method.png "OAuthToken") OAuthToken



> OAuth 2 Authorization endpoint response





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| access_token | string |  ``` Required ```  | Access token | 
| token_type | string |  ``` Required ```  | Type of access token | 
| expires_in | long |  ``` Optional ```  | Time in seconds before the access token expires | 
| scope | string |  ``` Optional ```  | List of scopes granted<br>This is a space-delimited list of strings. | 
| expiry | long |  ``` Optional ```  | Time of token expiry as unix timestamp (UTC) | 



#### Example
```
{
  "access_token": "access_token",
  "token_type": "token_type",
  "expires_in": 44,
  "scope": "scope",
  "expiry": 44
}
```



## <a name="o_auth_provider"></a>![Type: ](https://apidocs.io/img/method.png "OAuthProvider") OAuthProvider



> OAuth 2 Authorization endpoint exception





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| error | [OAuthProviderError](#o_auth_provider_error) |  ``` Required ```  | Error code | 
| error_description | string |  ``` Optional ```  | Human-readable text providing additional information on error.<br>Used to assist the client developer in understanding the error that occurred. | 
| error_uri | string |  ``` Optional ```  | A URI identifying a human-readable web page with information about the error, used to provide the client developer with additional information about the error | 



#### Example
```
{
  "error": "invalid_request",
  "error_description": "error_description",
  "error_uri": "error_uri"
}
```



## <a name="o_auth_provider_error"></a>![Type: ](https://apidocs.io/img/method.png "OAuthProviderError") OAuthProviderError



> OAuth 2 Authorization error codes





This type must take a value from the following `string` enumeration of values:

| Name | Value | Description |
| ---- | ----- | ----------- |
| invalid_request | `invalid_request` | The request is missing a required parameter, includes an unsupported parameter value (other than grant type), repeats a parameter, includes multiple credentials, utilizes more than one mechanism for authenticating the client, or is otherwise malformed. | 
| invalid_client | `invalid_client` | Client authentication failed (e.g., unknown client, no client authentication included, or unsupported authentication method). | 
| invalid_grant | `invalid_grant` | The provided authorization grant (e.g., authorization code, resource owner credentials) or refresh token is invalid, expired, revoked, does not match the redirection URI used in the authorization request, or was issued to another client. | 
| unauthorized_client | `unauthorized_client` | The authenticated client is not authorized to use this authorization grant type. | 
| unsupported_grant_type | `unsupported_grant_type` | The authorization grant type is not supported by the authorization server. | 
| invalid_scope | `invalid_scope` | The requested scope is invalid, unknown, malformed, or exceeds the scope granted by the resource owner. | 



#### Example
```
invalid_request
```



## <a name="o_auth_scope"></a>![Type: ](https://apidocs.io/img/method.png "OAuth Scope") OAuth Scope



> OAuth 2 scopes supported by the API





This type must take a value from the following `string` enumeration of values:

| Name | Value | Description |
| ---- | ----- | ----------- |
| NSMS | `NSMS` | NSMS | 



#### Example
```
NSMS
```



## <a name="o_auth_token"></a>![Type: ](https://apidocs.io/img/method.png "OAuthToken") OAuthToken



> OAuth 2 Authorization endpoint response





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| access_token | string |  ``` Required ```  | Access token | 
| token_type | string |  ``` Required ```  | Type of access token | 
| expires_in | long |  ``` Optional ```  | Time in seconds before the access token expires | 
| scope | string |  ``` Optional ```  | List of scopes granted<br>This is a space-delimited list of strings. | 
| expiry | long |  ``` Optional ```  | Time of token expiry as unix timestamp (UTC) | 



#### Example
```
{
  "access_token": "access_token",
  "token_type": "token_type",
  "expires_in": 44,
  "scope": "scope",
  "expiry": 44
}
```



## <a name="o_auth_provider"></a>![Type: ](https://apidocs.io/img/method.png "OAuthProvider") OAuthProvider



> OAuth 2 Authorization endpoint exception





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| error | [OAuthProviderError](#o_auth_provider_error) |  ``` Required ```  | Error code | 
| error_description | string |  ``` Optional ```  | Human-readable text providing additional information on error.<br>Used to assist the client developer in understanding the error that occurred. | 
| error_uri | string |  ``` Optional ```  | A URI identifying a human-readable web page with information about the error, used to provide the client developer with additional information about the error | 



#### Example
```
{
  "error": "invalid_request",
  "error_description": "error_description",
  "error_uri": "error_uri"
}
```



## <a name="o_auth_provider_error"></a>![Type: ](https://apidocs.io/img/method.png "OAuthProviderError") OAuthProviderError



> OAuth 2 Authorization error codes





This type must take a value from the following `string` enumeration of values:

| Name | Value | Description |
| ---- | ----- | ----------- |
| invalid_request | `invalid_request` | The request is missing a required parameter, includes an unsupported parameter value (other than grant type), repeats a parameter, includes multiple credentials, utilizes more than one mechanism for authenticating the client, or is otherwise malformed. | 
| invalid_client | `invalid_client` | Client authentication failed (e.g., unknown client, no client authentication included, or unsupported authentication method). | 
| invalid_grant | `invalid_grant` | The provided authorization grant (e.g., authorization code, resource owner credentials) or refresh token is invalid, expired, revoked, does not match the redirection URI used in the authorization request, or was issued to another client. | 
| unauthorized_client | `unauthorized_client` | The authenticated client is not authorized to use this authorization grant type. | 
| unsupported_grant_type | `unsupported_grant_type` | The authorization grant type is not supported by the authorization server. | 
| invalid_scope | `invalid_scope` | The requested scope is invalid, unknown, malformed, or exceeds the scope granted by the resource owner. | 



#### Example
```
invalid_request
```



## <a name="o_auth_scope"></a>![Type: ](https://apidocs.io/img/method.png "OAuth Scope") OAuth Scope



> OAuth 2 scopes supported by the API





This type must take a value from the following `string` enumeration of values:

| Name | Value | Description |
| ---- | ----- | ----------- |
| NSMS | `NSMS` | NSMS | 



#### Example
```
NSMS
```



## <a name="o_auth_token"></a>![Type: ](https://apidocs.io/img/method.png "OAuthToken") OAuthToken



> OAuth 2 Authorization endpoint response





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| access_token | string |  ``` Required ```  | Access token | 
| token_type | string |  ``` Required ```  | Type of access token | 
| expires_in | long |  ``` Optional ```  | Time in seconds before the access token expires | 
| scope | string |  ``` Optional ```  | List of scopes granted<br>This is a space-delimited list of strings. | 
| expiry | long |  ``` Optional ```  | Time of token expiry as unix timestamp (UTC) | 



#### Example
```
{
  "access_token": "access_token",
  "token_type": "token_type",
  "expires_in": 44,
  "scope": "scope",
  "expiry": 44
}
```



## <a name="o_auth_provider"></a>![Type: ](https://apidocs.io/img/method.png "OAuthProvider") OAuthProvider



> OAuth 2 Authorization endpoint exception





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| error | [OAuthProviderError](#o_auth_provider_error) |  ``` Required ```  | Error code | 
| error_description | string |  ``` Optional ```  | Human-readable text providing additional information on error.<br>Used to assist the client developer in understanding the error that occurred. | 
| error_uri | string |  ``` Optional ```  | A URI identifying a human-readable web page with information about the error, used to provide the client developer with additional information about the error | 



#### Example
```
{
  "error": "invalid_request",
  "error_description": "error_description",
  "error_uri": "error_uri"
}
```



## <a name="o_auth_provider_error"></a>![Type: ](https://apidocs.io/img/method.png "OAuthProviderError") OAuthProviderError



> OAuth 2 Authorization error codes





This type must take a value from the following `string` enumeration of values:

| Name | Value | Description |
| ---- | ----- | ----------- |
| invalid_request | `invalid_request` | The request is missing a required parameter, includes an unsupported parameter value (other than grant type), repeats a parameter, includes multiple credentials, utilizes more than one mechanism for authenticating the client, or is otherwise malformed. | 
| invalid_client | `invalid_client` | Client authentication failed (e.g., unknown client, no client authentication included, or unsupported authentication method). | 
| invalid_grant | `invalid_grant` | The provided authorization grant (e.g., authorization code, resource owner credentials) or refresh token is invalid, expired, revoked, does not match the redirection URI used in the authorization request, or was issued to another client. | 
| unauthorized_client | `unauthorized_client` | The authenticated client is not authorized to use this authorization grant type. | 
| unsupported_grant_type | `unsupported_grant_type` | The authorization grant type is not supported by the authorization server. | 
| invalid_scope | `invalid_scope` | The requested scope is invalid, unknown, malformed, or exceeds the scope granted by the resource owner. | 



#### Example
```
invalid_request
```



## <a name="o_auth_scope"></a>![Type: ](https://apidocs.io/img/method.png "OAuth Scope") OAuth Scope



> OAuth 2 scopes supported by the API





This type must take a value from the following `string` enumeration of values:

| Name | Value | Description |
| ---- | ----- | ----------- |
| NSMS | `NSMS` | NSMS | 



#### Example
```
NSMS
```



## <a name="o_auth_token"></a>![Type: ](https://apidocs.io/img/method.png "OAuthToken") OAuthToken



> OAuth 2 Authorization endpoint response





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| access_token | string |  ``` Required ```  | Access token | 
| token_type | string |  ``` Required ```  | Type of access token | 
| expires_in | long |  ``` Optional ```  | Time in seconds before the access token expires | 
| scope | string |  ``` Optional ```  | List of scopes granted<br>This is a space-delimited list of strings. | 
| expiry | long |  ``` Optional ```  | Time of token expiry as unix timestamp (UTC) | 



#### Example
```
{
  "access_token": "access_token",
  "token_type": "token_type",
  "expires_in": 44,
  "scope": "scope",
  "expiry": 44
}
```



## <a name="o_auth_provider"></a>![Type: ](https://apidocs.io/img/method.png "OAuthProvider") OAuthProvider



> OAuth 2 Authorization endpoint exception





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| error | [OAuthProviderError](#o_auth_provider_error) |  ``` Required ```  | Error code | 
| error_description | string |  ``` Optional ```  | Human-readable text providing additional information on error.<br>Used to assist the client developer in understanding the error that occurred. | 
| error_uri | string |  ``` Optional ```  | A URI identifying a human-readable web page with information about the error, used to provide the client developer with additional information about the error | 



#### Example
```
{
  "error": "invalid_request",
  "error_description": "error_description",
  "error_uri": "error_uri"
}
```



## <a name="o_auth_provider_error"></a>![Type: ](https://apidocs.io/img/method.png "OAuthProviderError") OAuthProviderError



> OAuth 2 Authorization error codes





This type must take a value from the following `string` enumeration of values:

| Name | Value | Description |
| ---- | ----- | ----------- |
| invalid_request | `invalid_request` | The request is missing a required parameter, includes an unsupported parameter value (other than grant type), repeats a parameter, includes multiple credentials, utilizes more than one mechanism for authenticating the client, or is otherwise malformed. | 
| invalid_client | `invalid_client` | Client authentication failed (e.g., unknown client, no client authentication included, or unsupported authentication method). | 
| invalid_grant | `invalid_grant` | The provided authorization grant (e.g., authorization code, resource owner credentials) or refresh token is invalid, expired, revoked, does not match the redirection URI used in the authorization request, or was issued to another client. | 
| unauthorized_client | `unauthorized_client` | The authenticated client is not authorized to use this authorization grant type. | 
| unsupported_grant_type | `unsupported_grant_type` | The authorization grant type is not supported by the authorization server. | 
| invalid_scope | `invalid_scope` | The requested scope is invalid, unknown, malformed, or exceeds the scope granted by the resource owner. | 



#### Example
```
invalid_request
```



## <a name="o_auth_scope"></a>![Type: ](https://apidocs.io/img/method.png "OAuth Scope") OAuth Scope



> OAuth 2 scopes supported by the API





This type must take a value from the following `string` enumeration of values:

| Name | Value | Description |
| ---- | ----- | ----------- |
| NSMS | `NSMS` | NSMS | 



#### Example
```
NSMS
```



## <a name="o_auth_token"></a>![Type: ](https://apidocs.io/img/method.png "OAuthToken") OAuthToken



> OAuth 2 Authorization endpoint response





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| access_token | string |  ``` Required ```  | Access token | 
| token_type | string |  ``` Required ```  | Type of access token | 
| expires_in | long |  ``` Optional ```  | Time in seconds before the access token expires | 
| scope | string |  ``` Optional ```  | List of scopes granted<br>This is a space-delimited list of strings. | 
| expiry | long |  ``` Optional ```  | Time of token expiry as unix timestamp (UTC) | 



#### Example
```
{
  "access_token": "access_token",
  "token_type": "token_type",
  "expires_in": 44,
  "scope": "scope",
  "expiry": 44
}
```



## <a name="o_auth_provider"></a>![Type: ](https://apidocs.io/img/method.png "OAuthProvider") OAuthProvider



> OAuth 2 Authorization endpoint exception





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| error | [OAuthProviderError](#o_auth_provider_error) |  ``` Required ```  | Error code | 
| error_description | string |  ``` Optional ```  | Human-readable text providing additional information on error.<br>Used to assist the client developer in understanding the error that occurred. | 
| error_uri | string |  ``` Optional ```  | A URI identifying a human-readable web page with information about the error, used to provide the client developer with additional information about the error | 



#### Example
```
{
  "error": "invalid_request",
  "error_description": "error_description",
  "error_uri": "error_uri"
}
```



## <a name="o_auth_provider_error"></a>![Type: ](https://apidocs.io/img/method.png "OAuthProviderError") OAuthProviderError



> OAuth 2 Authorization error codes





This type must take a value from the following `string` enumeration of values:

| Name | Value | Description |
| ---- | ----- | ----------- |
| invalid_request | `invalid_request` | The request is missing a required parameter, includes an unsupported parameter value (other than grant type), repeats a parameter, includes multiple credentials, utilizes more than one mechanism for authenticating the client, or is otherwise malformed. | 
| invalid_client | `invalid_client` | Client authentication failed (e.g., unknown client, no client authentication included, or unsupported authentication method). | 
| invalid_grant | `invalid_grant` | The provided authorization grant (e.g., authorization code, resource owner credentials) or refresh token is invalid, expired, revoked, does not match the redirection URI used in the authorization request, or was issued to another client. | 
| unauthorized_client | `unauthorized_client` | The authenticated client is not authorized to use this authorization grant type. | 
| unsupported_grant_type | `unsupported_grant_type` | The authorization grant type is not supported by the authorization server. | 
| invalid_scope | `invalid_scope` | The requested scope is invalid, unknown, malformed, or exceeds the scope granted by the resource owner. | 



#### Example
```
invalid_request
```



## <a name="o_auth_scope"></a>![Type: ](https://apidocs.io/img/method.png "OAuth Scope") OAuth Scope



> OAuth 2 scopes supported by the API





This type must take a value from the following `string` enumeration of values:

| Name | Value | Description |
| ---- | ----- | ----------- |
| NSMS | `NSMS` | NSMS | 



#### Example
```
NSMS
```



## <a name="o_auth_token"></a>![Type: ](https://apidocs.io/img/method.png "OAuthToken") OAuthToken



> OAuth 2 Authorization endpoint response





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| access_token | string |  ``` Required ```  | Access token | 
| token_type | string |  ``` Required ```  | Type of access token | 
| expires_in | long |  ``` Optional ```  | Time in seconds before the access token expires | 
| scope | string |  ``` Optional ```  | List of scopes granted<br>This is a space-delimited list of strings. | 
| expiry | long |  ``` Optional ```  | Time of token expiry as unix timestamp (UTC) | 



#### Example
```
{
  "access_token": "access_token",
  "token_type": "token_type",
  "expires_in": 44,
  "scope": "scope",
  "expiry": 44
}
```



## <a name="o_auth_provider"></a>![Type: ](https://apidocs.io/img/method.png "OAuthProvider") OAuthProvider



> OAuth 2 Authorization endpoint exception





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| error | [OAuthProviderError](#o_auth_provider_error) |  ``` Required ```  | Error code | 
| error_description | string |  ``` Optional ```  | Human-readable text providing additional information on error.<br>Used to assist the client developer in understanding the error that occurred. | 
| error_uri | string |  ``` Optional ```  | A URI identifying a human-readable web page with information about the error, used to provide the client developer with additional information about the error | 



#### Example
```
{
  "error": "invalid_request",
  "error_description": "error_description",
  "error_uri": "error_uri"
}
```



## <a name="o_auth_provider_error"></a>![Type: ](https://apidocs.io/img/method.png "OAuthProviderError") OAuthProviderError



> OAuth 2 Authorization error codes





This type must take a value from the following `string` enumeration of values:

| Name | Value | Description |
| ---- | ----- | ----------- |
| invalid_request | `invalid_request` | The request is missing a required parameter, includes an unsupported parameter value (other than grant type), repeats a parameter, includes multiple credentials, utilizes more than one mechanism for authenticating the client, or is otherwise malformed. | 
| invalid_client | `invalid_client` | Client authentication failed (e.g., unknown client, no client authentication included, or unsupported authentication method). | 
| invalid_grant | `invalid_grant` | The provided authorization grant (e.g., authorization code, resource owner credentials) or refresh token is invalid, expired, revoked, does not match the redirection URI used in the authorization request, or was issued to another client. | 
| unauthorized_client | `unauthorized_client` | The authenticated client is not authorized to use this authorization grant type. | 
| unsupported_grant_type | `unsupported_grant_type` | The authorization grant type is not supported by the authorization server. | 
| invalid_scope | `invalid_scope` | The requested scope is invalid, unknown, malformed, or exceeds the scope granted by the resource owner. | 



#### Example
```
invalid_request
```



## <a name="o_auth_scope"></a>![Type: ](https://apidocs.io/img/method.png "OAuth Scope") OAuth Scope



> OAuth 2 scopes supported by the API





This type must take a value from the following `string` enumeration of values:

| Name | Value | Description |
| ---- | ----- | ----------- |
| NSMS | `NSMS` | NSMS | 



#### Example
```
NSMS
```



## <a name="o_auth_token"></a>![Type: ](https://apidocs.io/img/method.png "OAuthToken") OAuthToken



> OAuth 2 Authorization endpoint response





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| access_token | string |  ``` Required ```  | Access token | 
| token_type | string |  ``` Required ```  | Type of access token | 
| expires_in | long |  ``` Optional ```  | Time in seconds before the access token expires | 
| scope | string |  ``` Optional ```  | List of scopes granted<br>This is a space-delimited list of strings. | 
| expiry | long |  ``` Optional ```  | Time of token expiry as unix timestamp (UTC) | 



#### Example
```
{
  "access_token": "access_token",
  "token_type": "token_type",
  "expires_in": 44,
  "scope": "scope",
  "expiry": 44
}
```



## <a name="o_auth_provider"></a>![Type: ](https://apidocs.io/img/method.png "OAuthProvider") OAuthProvider



> OAuth 2 Authorization endpoint exception





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| error | [OAuthProviderError](#o_auth_provider_error) |  ``` Required ```  | Error code | 
| error_description | string |  ``` Optional ```  | Human-readable text providing additional information on error.<br>Used to assist the client developer in understanding the error that occurred. | 
| error_uri | string |  ``` Optional ```  | A URI identifying a human-readable web page with information about the error, used to provide the client developer with additional information about the error | 



#### Example
```
{
  "error": "invalid_request",
  "error_description": "error_description",
  "error_uri": "error_uri"
}
```



## <a name="o_auth_provider_error"></a>![Type: ](https://apidocs.io/img/method.png "OAuthProviderError") OAuthProviderError



> OAuth 2 Authorization error codes





This type must take a value from the following `string` enumeration of values:

| Name | Value | Description |
| ---- | ----- | ----------- |
| invalid_request | `invalid_request` | The request is missing a required parameter, includes an unsupported parameter value (other than grant type), repeats a parameter, includes multiple credentials, utilizes more than one mechanism for authenticating the client, or is otherwise malformed. | 
| invalid_client | `invalid_client` | Client authentication failed (e.g., unknown client, no client authentication included, or unsupported authentication method). | 
| invalid_grant | `invalid_grant` | The provided authorization grant (e.g., authorization code, resource owner credentials) or refresh token is invalid, expired, revoked, does not match the redirection URI used in the authorization request, or was issued to another client. | 
| unauthorized_client | `unauthorized_client` | The authenticated client is not authorized to use this authorization grant type. | 
| unsupported_grant_type | `unsupported_grant_type` | The authorization grant type is not supported by the authorization server. | 
| invalid_scope | `invalid_scope` | The requested scope is invalid, unknown, malformed, or exceeds the scope granted by the resource owner. | 



#### Example
```
invalid_request
```



## <a name="o_auth_scope"></a>![Type: ](https://apidocs.io/img/method.png "OAuth Scope") OAuth Scope



> OAuth 2 scopes supported by the API





This type must take a value from the following `string` enumeration of values:

| Name | Value | Description |
| ---- | ----- | ----------- |
| NSMS | `NSMS` | NSMS | 



#### Example
```
NSMS
```



## <a name="o_auth_token"></a>![Type: ](https://apidocs.io/img/method.png "OAuthToken") OAuthToken



> OAuth 2 Authorization endpoint response





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| access_token | string |  ``` Required ```  | Access token | 
| token_type | string |  ``` Required ```  | Type of access token | 
| expires_in | long |  ``` Optional ```  | Time in seconds before the access token expires | 
| scope | string |  ``` Optional ```  | List of scopes granted<br>This is a space-delimited list of strings. | 
| expiry | long |  ``` Optional ```  | Time of token expiry as unix timestamp (UTC) | 



#### Example
```
{
  "access_token": "access_token",
  "token_type": "token_type",
  "expires_in": 135,
  "scope": "scope",
  "expiry": 135
}
```



## <a name="o_auth_provider"></a>![Type: ](https://apidocs.io/img/method.png "OAuthProvider") OAuthProvider



> OAuth 2 Authorization endpoint exception





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| error | [OAuthProviderError](#o_auth_provider_error) |  ``` Required ```  | Error code | 
| error_description | string |  ``` Optional ```  | Human-readable text providing additional information on error.<br>Used to assist the client developer in understanding the error that occurred. | 
| error_uri | string |  ``` Optional ```  | A URI identifying a human-readable web page with information about the error, used to provide the client developer with additional information about the error | 



#### Example
```
{
  "error": "invalid_request",
  "error_description": "error_description",
  "error_uri": "error_uri"
}
```



## <a name="o_auth_provider_error"></a>![Type: ](https://apidocs.io/img/method.png "OAuthProviderError") OAuthProviderError



> OAuth 2 Authorization error codes





This type must take a value from the following `string` enumeration of values:

| Name | Value | Description |
| ---- | ----- | ----------- |
| invalid_request | `invalid_request` | The request is missing a required parameter, includes an unsupported parameter value (other than grant type), repeats a parameter, includes multiple credentials, utilizes more than one mechanism for authenticating the client, or is otherwise malformed. | 
| invalid_client | `invalid_client` | Client authentication failed (e.g., unknown client, no client authentication included, or unsupported authentication method). | 
| invalid_grant | `invalid_grant` | The provided authorization grant (e.g., authorization code, resource owner credentials) or refresh token is invalid, expired, revoked, does not match the redirection URI used in the authorization request, or was issued to another client. | 
| unauthorized_client | `unauthorized_client` | The authenticated client is not authorized to use this authorization grant type. | 
| unsupported_grant_type | `unsupported_grant_type` | The authorization grant type is not supported by the authorization server. | 
| invalid_scope | `invalid_scope` | The requested scope is invalid, unknown, malformed, or exceeds the scope granted by the resource owner. | 



#### Example
```
invalid_request
```




