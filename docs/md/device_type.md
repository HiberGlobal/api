# device_type.proto



#### This file was generated from [device_type.proto](https://github.com/HiberGlobal/api/blob/master/device_type.proto).

## Table of Contents



- Messages
  - [DeviceType](#devicetype)
  - [DeviceTypeSelection](#devicetypeselection)

- Enums

- [Scalar Value Types](#scalar-value-types)

## Messages

### DeviceType

Preconfigured device type.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) |  |
| brand | [ string](#string) | Brand that produces this device type. |
| application | [ string](#string) | What this devices is meant for, e.g. measuring pressure. |
| category | [ string](#string) | A category specific to this device type (for example, based on device configuration). |
| version | [ string](#string) | A version specific to this device type (typically based on firmware version). |
| description | [ string](#string) | Textual description of the device type, for display purposes. |
| gateway | [ bool](#bool) | Whether this device type represents a gateway or a device. |

### DeviceTypeSelection

Selection object for device types.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** search | [optional string](#string) | Search all the text of the device type (identifier, brand, application, category, version, description). |
|  **optional** only_gateways | [optional bool](#bool) | Limit the results to just device types where gateway is true. |
|  **optional** exclude_gateways | [optional bool](#bool) | Limit the results to just device types where gateway is false. |


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

