# transfer.proto

Service to transfer data from one organization to another.

To transfer data to another organization, you must have access to both organizations,
and must have the TRANSFERS permissions in the sender organization.

#### This file was generated from [transfer.proto](https://github.com/HiberGlobal/api/blob/master/transfer.proto).

## Table of Contents



- Messages
  - [Transfer](#transfer)
  - [Transfer.Devices](#transferdevices)

- Enums
  - [Transfer.Type](#transfertype)

- [Scalar Value Types](#scalar-value-types)

## Messages

### Transfer



| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) | The identifier for the transfer. |
| sender_organization | [ string](#string) | The organization that sent the transfer. |
| recipient_organization | [ string](#string) | The organization that received the transfer. |
| comment | [ string](#string) | Optional comment for the transfer (i.e. reason, tracking information, etc). |
| created_at | [ hiber.Timestamp](#hibertimestamp) |  |
| type | [ Transfer.Type](#transfertype) | The type of data transferred to the recipient organization. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed**.devices | [ Transfer.Devices](#transferdevices) | The devices that were transferred from the sender to the recipient organization. |

### Transfer.Devices

The devices that were transferred from the sender to the recipient organization.

| Field | Type | Description |
| ----- | ---- | ----------- |
| numbers | [repeated string](#string) | The numbers of the devices that were transferred from the sender to the recipient organization. |


## Enums
### Transfer.Type
The type of data transferred to the recipient organization.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEVICES |  | 0 |

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

