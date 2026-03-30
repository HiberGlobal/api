# device_type.proto



#### This file was generated from [device_type.proto](https://github.com/HiberGlobal/api/blob/master/device_type.proto).

## Table of Contents



- Messages
  - [DeviceType](#devicetype)
  - [DeviceTypeSelection](#devicetypeselection)

- Enums
  - [DeviceType.Class](#devicetypeclass)
  - [DeviceType.Identifier](#devicetypeidentifier)
  - [DeviceType.Implementation](#devicetypeimplementation)
  - [DeviceType.Infrastructure](#devicetypeinfrastructure)

- [Scalar Value Types](#scalar-value-types)

## Messages

### DeviceType

Preconfigured device type.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) | Identifier of this device type. |
| identifier_enum | [ DeviceType.Identifier](#devicetypeidentifier) | Identifier of this device type, as enum. |
| infrastructure | [ DeviceType.Infrastructure](#devicetypeinfrastructure) | Infrastructure purpose of this device type. |
| class | [ DeviceType.Class](#devicetypeclass) | Class of this device type. |
| implementation | [ DeviceType.Implementation](#devicetypeimplementation) | Implementation of the class of this device type. |
| brand | [ string](#string) | Brand that produces this device type. |
| application | [ string](#string) | What this devices is meant for, e.g. measuring pressure. |
| category | [ string](#string) | A category specific to this device type (for example, based on device configuration). |
| version | [ string](#string) | A version specific to this device type (typically based on firmware version). |
| description | [ string](#string) | Textual description of the device type, for display purposes. |
| gateway | [ bool](#bool) | <span class="deprecated deprecated-field">Deprecated</span> Whether this device type represents a gateway or a device. Deprecated in favor of infrastructure and class enums. |

### DeviceTypeSelection

Selection object for device types.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** search | [optional string](#string) | Search all the text of the device type (identifier, brand, application, category, version, description). |
|  **optional** only_gateways | [optional bool](#bool) | Limit the results to just device types where gateway is true. |
|  **optional** exclude_gateways | [optional bool](#bool) | Limit the results to just device types where gateway is false. |


## Enums
### DeviceType.Class


| Name | Description | Number |
| ---- | ----------- | ------ |
| GATEWAY_BGAN | This device is a gateway using BGAN for its data connection. | 0 |
| GATEWAY_CELLULAR | This device is a gateway using a cellular data connection (e.g. 4G). | 1 |
| SENSOR | This device is a sensor that measures data and sends it to the system. | 2 |
| RETROFITTER | This device is a retrofitter that is connected to a sensor and used to transmit its data. | 3 |
| ACTUATOR | This device is an actuator capable of operations that affect surrounding devices. | 4 |

### DeviceType.Identifier


| Name | Description | Number |
| ---- | ----------- | ------ |
| GATEWAY |  | 0 |
| PRESSURE_SENSOR_1 |  | 1 |
| PRESSURE_SENSOR_1_AS |  | 16 |
| PRESSURE_SENSOR_1_AU |  | 2 |
| PRESSURE_SENSOR_1_EU |  | 3 |
| PRESSURE_SENSOR_1_US |  | 4 |
| TEMPERATURE_SENSOR_1 |  | 17 |
| TEMPERATURE_SENSOR_1_AS |  | 5 |
| TEMPERATURE_SENSOR_1_AU |  | 6 |
| TEMPERATURE_SENSOR_1_EU |  | 7 |
| TEMPERATURE_SENSOR_1_US |  | 8 |
| PRESSURE_AND_TEMPERATURE_SENSOR_1 |  | 18 |
| PRESSURE_AND_TEMPERATURE_SENSOR_1_AS |  | 9 |
| PRESSURE_AND_TEMPERATURE_SENSOR_1_AU |  | 10 |
| PRESSURE_AND_TEMPERATURE_SENSOR_1_EU |  | 11 |
| PRESSURE_AND_TEMPERATURE_SENSOR_1_US |  | 12 |
| DEMO_ALL_VALUES |  | 13 |
| GATEWAY_V2_AC |  | 14 |
| GATEWAY_V2_DC |  | 26 |
| VALVE_ACTUATOR |  | 15 |
| GATEWAY_V2_AC_CELLULAR |  | 19 |
| GATEWAY_V2_DC_CELLULAR |  | 27 |
| VOBO_NUFLOW_MC_III_CHANNEL_1 |  | 20 |
| VOBO_SERTECPET_RPM_CHANNEL_1 |  | 21 |
| VOBO_HL_1 |  | 25 |
| ADEUNIS_MODBUS_EXPRO_FLOW_TOTALIZER_1_METER |  | 22 |
| ADEUNIS_MODBUS_EXPRO_FLOW_TOTALIZER_2_METERS |  | 23 |
| ADEUNIS_MODBUS_EXPRO_FLOW_TOTALIZER_3_METERS |  | 24 |

### DeviceType.Implementation


| Name | Description | Number |
| ---- | ----------- | ------ |
| GATEWAY_VERSION_1 | Original Hiber gateway, over BGAN. | 0 |
| GATEWAY_VERSION_2 | Improved Hiber gateway, capable of BGAN and cellular connections. | 3 |
| PRESSURE_SENSOR_VERSION_1 | Hiber Pressure Sensor. | 1 |
| TEMPERATURE_SENSOR_VERSION_1 | Hiber Temperature Sensor. | 2 |
| VALVE_VERSION_1 | Actuator capable of closing high pressure lines that affect surrounding devices. | 4 |
| RETROFITTER_4_20_MA | Retrofitter that reads 4 to 20 milliamps. | 5 |
| RETROFITTER_MODBUS | Retrofitter that connects to modbus. | 6 |
| RETROFITTER_MODBUS_2 | Different type of retrofitter that connects to modbus. | 7 |
| DEMO | Demo mode. | 8 |

### DeviceType.Infrastructure


| Name | Description | Number |
| ---- | ----------- | ------ |
| END_DEVICE | This device is an end device, like a sensor or actuator. | 0 |
| NETWORK | This device is a network node, facilitating connection and data transfer, like a gateway. | 1 |

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

