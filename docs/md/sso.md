# sso.proto



#### This file was generated from [sso.proto](https://github.com/HiberGlobal/api/blob/master/sso.proto).

## Table of Contents

- Services
  - [SingleSignOnService](#singlesignonservice)

- Messages
  - [DundasSSO](#dundassso)
  - [DundasSSO.Request](#dundasssorequest)
  - [DundasSSO.Response](#dundasssoresponse)
  - [ZendeskTokenRequest](#zendesktokenrequest)
  - [ZendeskTokenRequest.Response](#zendesktokenrequestresponse)

- Enums

- [Scalar Value Types](#scalar-value-types)


## SingleSignOnService
Single sign on support service.

### Zendesk
> **rpc** Zendesk([ZendeskTokenRequest](#zendesktokenrequest))
    [ZendeskTokenRequest.Response](#zendesktokenrequestresponse)

Zendesk SSO using custom JWT

### Dundas
> **rpc** Dundas([DundasSSO.Request](#dundasssorequest))
    [DundasSSO.Response](#dundasssoresponse)

Dundas SSO


## Messages

### DundasSSO

Create a session id for the Dundas BI tool.


### DundasSSO.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | The organization to get a session id for. |
| current_session_id | [ string](#string) | Include the current session id to validate it. If it is valid, the server will not create a new session id. This makes it easier to avoid having multiple sessions. |
| kill_other_sessions | [ bool](#bool) | Kill any other sessions for your account. |

### DundasSSO.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| session_id | [ string](#string) | A valid session id for the given organization. If a session id was given, and it was valid, this is that session id. |
| session_id_subdomain | [ string](#string) | The subdomain to write the session id to, for convenience. |

### ZendeskTokenRequest




### ZendeskTokenRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| token | [ string](#string) | none |


## Enums
## Scalar Value Types

| .proto Type | Notes | C++ Type | Java Type | Python Type |
| ----------- | ----- | -------- | --------- | ----------- |
| <div><h4 id="#double" /></div><a name="double" /> double |  | double | double | float |
| <div><h4 id="#float" /></div><a name="float" /> float |  | float | float | float |
| <div><h4 id="#int32" /></div><a name="int32" /> int32 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint32 instead. | int32 | int | int |
| <div><h4 id="#int64" /></div><a name="int64" /> int64 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint64 instead. | int64 | long | int/long |
| <div><h4 id="#uint32" /></div><a name="uint32" /> uint32 | Uses variable-length encoding. | uint32 | int | int/long |
| <div><h4 id="#uint64" /></div><a name="uint64" /> uint64 | Uses variable-length encoding. | uint64 | long | int/long |
| <div><h4 id="#sint32" /></div><a name="sint32" /> sint32 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int32s. | int32 | int | int |
| <div><h4 id="#sint64" /></div><a name="sint64" /> sint64 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int64s. | int64 | long | int/long |
| <div><h4 id="#fixed32" /></div><a name="fixed32" /> fixed32 | Always four bytes. More efficient than uint32 if values are often greater than 2^28. | uint32 | int | int |
| <div><h4 id="#fixed64" /></div><a name="fixed64" /> fixed64 | Always eight bytes. More efficient than uint64 if values are often greater than 2^56. | uint64 | long | int/long |
| <div><h4 id="#sfixed32" /></div><a name="sfixed32" /> sfixed32 | Always four bytes. | int32 | int | int |
| <div><h4 id="#sfixed64" /></div><a name="sfixed64" /> sfixed64 | Always eight bytes. | int64 | long | int/long |
| <div><h4 id="#bool" /></div><a name="bool" /> bool |  | bool | boolean | boolean |
| <div><h4 id="#string" /></div><a name="string" /> string | A string must always contain UTF-8 encoded or 7-bit ASCII text. | string | String | str/unicode |
| <div><h4 id="#bytes" /></div><a name="bytes" /> bytes | May contain any arbitrary sequence of bytes. | string | ByteString | str |
