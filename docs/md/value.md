# value.proto



#### This file was generated from [value.proto](https://github.com/HiberGlobal/api/blob/master/value.proto).

## Table of Contents



- Messages
  - [Value](#value)
  - [Value.Enum](#valueenum)
  - [Value.Numeric](#valuenumeric)
  - [Value.Numeric.BatteryLevel](#valuenumericbatterylevel)
  - [Value.Numeric.Distance](#valuenumericdistance)
  - [Value.Numeric.Duration](#valuenumericduration)
  - [Value.Numeric.Flow](#valuenumericflow)
  - [Value.Numeric.FuelEfficiency](#valuenumericfuelefficiency)
  - [Value.Numeric.Mass](#valuenumericmass)
  - [Value.Numeric.Percentage](#valuenumericpercentage)
  - [Value.Numeric.Pressure](#valuenumericpressure)
  - [Value.Numeric.Rate](#valuenumericrate)
  - [Value.Numeric.RotationSpeed](#valuenumericrotationspeed)
  - [Value.Numeric.Speed](#valuenumericspeed)
  - [Value.Numeric.Temperature](#valuenumerictemperature)
  - [Value.Numeric.Voltage](#valuenumericvoltage)
  - [Value.Numeric.Volume](#valuenumericvolume)

- Enums
  - [Value.Numeric.BatteryLevel.Unit](#valuenumericbatterylevelunit)
  - [Value.Numeric.Distance.Unit](#valuenumericdistanceunit)
  - [Value.Numeric.Duration.Unit](#valuenumericdurationunit)
  - [Value.Numeric.Flow.Unit](#valuenumericflowunit)
  - [Value.Numeric.FuelEfficiency.Unit](#valuenumericfuelefficiencyunit)
  - [Value.Numeric.Mass.Unit](#valuenumericmassunit)
  - [Value.Numeric.Percentage.Unit](#valuenumericpercentageunit)
  - [Value.Numeric.Pressure.Unit](#valuenumericpressureunit)
  - [Value.Numeric.Rate.Unit](#valuenumericrateunit)
  - [Value.Numeric.RotationSpeed.Unit](#valuenumericrotationspeedunit)
  - [Value.Numeric.Speed.Unit](#valuenumericspeedunit)
  - [Value.Numeric.Temperature.Unit](#valuenumerictemperatureunit)
  - [Value.Numeric.Type](#valuenumerictype)
  - [Value.Numeric.Voltage.Unit](#valuenumericvoltageunit)
  - [Value.Numeric.Volume.Unit](#valuenumericvolumeunit)
  - [Value.Type](#valuetype)
  - [ValueAggregation](#valueaggregation)
  - [ValueTransformation](#valuetransformation)

- [Scalar Value Types](#scalar-value-types)

## Messages

### Value



| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ Value.Type](#valuetype) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.numeric | [ Value.Numeric](#valuenumeric) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.text | [ string](#string) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.enum | [ Value.Enum](#valueenum) |  |

### Value.Enum

If this value is an enum, this specifies the value, display name and color for this enum value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ string](#string) | The enum value. This might be a cryptic value, see the display_name and description for more information. |
| display_name | [ string](#string) | User-facing name for this value. |
| description | [ string](#string) | More details for this enum value. |
| color | [ string](#string) | (Optional) color for this enum value. |
| priority | [ int32](#int32) | Priority of the value, typically used for ordering. |

### Value.Numeric

If the value is numeric, this specifies the unit, value, etc.

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ Value.Numeric.Type](#valuenumerictype) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.battery_level | [ Value.Numeric.BatteryLevel](#valuenumericbatterylevel) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.distance | [ Value.Numeric.Distance](#valuenumericdistance) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.duration | [ Value.Numeric.Duration](#valuenumericduration) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.fuel_efficiency | [ Value.Numeric.FuelEfficiency](#valuenumericfuelefficiency) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.percentage | [ Value.Numeric.Percentage](#valuenumericpercentage) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.pressure | [ Value.Numeric.Pressure](#valuenumericpressure) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.speed | [ Value.Numeric.Speed](#valuenumericspeed) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.temperature | [ Value.Numeric.Temperature](#valuenumerictemperature) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.voltage | [ Value.Numeric.Voltage](#valuenumericvoltage) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.volume | [ Value.Numeric.Volume](#valuenumericvolume) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.mass | [ Value.Numeric.Mass](#valuenumericmass) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.flow | [ Value.Numeric.Flow](#valuenumericflow) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.rotation_speed | [ Value.Numeric.RotationSpeed](#valuenumericrotationspeed) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.rate | [ Value.Numeric.Rate](#valuenumericrate) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.unknown | [ double](#double) |  |

### Value.Numeric.BatteryLevel

Special case for battery level, since it can be provided in many units.
Not included in the UnitPreferences, since it cannot be converted.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) |  |
| unit | [ Value.Numeric.BatteryLevel.Unit](#valuenumericbatterylevelunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ Value.Numeric.BatteryLevel.Unit](#valuenumericbatterylevelunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### Value.Numeric.Distance

The value is a distance value, converted to your preferred distance unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) |  |
| unit | [ Value.Numeric.Distance.Unit](#valuenumericdistanceunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ Value.Numeric.Distance.Unit](#valuenumericdistanceunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### Value.Numeric.Duration



| Field | Type | Description |
| ----- | ---- | ----------- |
| duration | [ google.protobuf.Duration](#googleprotobufduration) |  |
| value | [ double](#double) |  |
| unit | [ Value.Numeric.Duration.Unit](#valuenumericdurationunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ Value.Numeric.Duration.Unit](#valuenumericdurationunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### Value.Numeric.Flow



| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) |  |
| unit | [ Value.Numeric.Flow.Unit](#valuenumericflowunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ Value.Numeric.Flow.Unit](#valuenumericflowunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### Value.Numeric.FuelEfficiency

The value is a distance value, converted to your preferred distance unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) |  |
| unit | [ Value.Numeric.FuelEfficiency.Unit](#valuenumericfuelefficiencyunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ Value.Numeric.FuelEfficiency.Unit](#valuenumericfuelefficiencyunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### Value.Numeric.Mass

The value is a volume value, converted to your preferred volume unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) |  |
| unit | [ Value.Numeric.Mass.Unit](#valuenumericmassunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ Value.Numeric.Mass.Unit](#valuenumericmassunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### Value.Numeric.Percentage

The value is a percentage.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ float](#float) |  |
| unit | [ Value.Numeric.Percentage.Unit](#valuenumericpercentageunit) |  |
| textual | [ string](#string) | Textual representation with % symbol, rounded based on the user preferences and field config. |

### Value.Numeric.Pressure

The value is a pressure value, converted to your preferred pressure unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) |  |
| unit | [ Value.Numeric.Pressure.Unit](#valuenumericpressureunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ Value.Numeric.Pressure.Unit](#valuenumericpressureunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### Value.Numeric.Rate



| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ uint32](#uint32) |  |
| unit | [ Value.Numeric.Rate.Unit](#valuenumericrateunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ Value.Numeric.Rate.Unit](#valuenumericrateunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### Value.Numeric.RotationSpeed

The value for rotation speed. The only value is revolutions per minute (RPM), therefore it is not included in
unit preferences.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) |  |
| unit | [ Value.Numeric.RotationSpeed.Unit](#valuenumericrotationspeedunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ Value.Numeric.RotationSpeed.Unit](#valuenumericrotationspeedunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### Value.Numeric.Speed

The value is a speed value, converted to your preferred speed unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) |  |
| unit | [ Value.Numeric.Speed.Unit](#valuenumericspeedunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ Value.Numeric.Speed.Unit](#valuenumericspeedunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### Value.Numeric.Temperature

The value is a temperature, converted to your preferred temperature unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) |  |
| unit | [ Value.Numeric.Temperature.Unit](#valuenumerictemperatureunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ Value.Numeric.Temperature.Unit](#valuenumerictemperatureunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### Value.Numeric.Voltage

The value is a voltage, converted to your preferred voltage unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) |  |
| unit | [ Value.Numeric.Voltage.Unit](#valuenumericvoltageunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ Value.Numeric.Voltage.Unit](#valuenumericvoltageunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### Value.Numeric.Volume

The value is a volume value, converted to your preferred volume unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) |  |
| unit | [ Value.Numeric.Volume.Unit](#valuenumericvolumeunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ Value.Numeric.Volume.Unit](#valuenumericvolumeunit) | The original unit, iff this value was converted from another unit because of user preferences. |


## Enums
### Value.Numeric.BatteryLevel.Unit
other units will be added here later, like voltage

| Name | Description | Number |
| ---- | ----------- | ------ |
| PERCENT | Battery level as a percentage (technically not a unit). | 0 |

### Value.Numeric.Distance.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| METER |  | 0 |
| MILLIMETER |  | 1 |
| CENTIMETER |  | 2 |
| KILOMETER |  | 3 |
| YARD |  | 5 |
| MILE |  | 4 |
| FOOT |  | 6 |
| INCH |  | 7 |
| NAUTICAL_MILE | This is a special case unit and may not be auto-converted to your UnitPreference. | 8 |

### Value.Numeric.Duration.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| MILLISECONDS |  | 0 |
| SECONDS |  | 1 |
| MINUTES |  | 2 |
| HOURS |  | 3 |
| DAYS |  | 4 |
| WEEKS |  | 5 |

### Value.Numeric.Flow.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| CUBIC_METER_PER_HOUR |  | 0 |
| BARRELS_PER_DAY |  | 1 |

### Value.Numeric.FuelEfficiency.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| LITER_PER_100_KILOMETER |  | 0 |
| KILOMETER_PER_LITER |  | 1 |
| KILOMETER_PER_GALLON |  | 2 |
| KILOMETER_PER_IMPERIAL_GALLON |  | 3 |
| MILE_PER_GALLON |  | 4 |
| MILE_PER_IMPERIAL_GALLON |  | 5 |
| MILE_PER_LITER |  | 6 |

### Value.Numeric.Mass.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| KILOGRAMS |  | 0 |
| POUNDS |  | 1 |

### Value.Numeric.Percentage.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| PERCENT | Technically not a unit, but for consistency, we've added it here. | 0 |

### Value.Numeric.Pressure.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| BAR |  | 0 |
| PSI |  | 1 |
| K_PA |  | 2 |

### Value.Numeric.Rate.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| ITEMS_PER_24_HOURS | The amount of items counted in a 24 hour window. | 0 |

### Value.Numeric.RotationSpeed.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| REVOLUTIONS_PER_MINUTE |  | 0 |

### Value.Numeric.Speed.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| KILOMETERS_PER_HOUR |  | 0 |
| KNOTS | This is a special case unit and may not be auto-converted to your UnitPreference. | 1 |
| METERS_PER_SECOND |  | 2 |
| MILES_PER_HOUR |  | 3 |

### Value.Numeric.Temperature.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| KELVIN |  | 0 |
| DEGREES_CELSIUS |  | 1 |
| DEGREES_FAHRENHEIT |  | 2 |

### Value.Numeric.Type
The type of numeric value that is represented.
Supported types will automatically convert to the preferred unit (based on the user settings).

| Name | Description | Number |
| ---- | ----------- | ------ |
| TYPE_UNKNOWN |  | 0 |
| PERCENTAGE |  | 1 |
| TEMPERATURE |  | 2 |
| DISTANCE |  | 3 |
| PRESSURE |  | 4 |
| VOLTAGE |  | 5 |
| SPEED |  | 6 |
| VOLUME |  | 7 |
| DURATION |  | 8 |
| FUEL_EFFICIENCY |  | 9 |
| MASS |  | 10 |
| BATTERY_LEVEL |  | 11 |
| FLOW |  | 12 |
| ROTATION_SPEED |  | 13 |
| RATE |  | 14 |

### Value.Numeric.Voltage.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| MILLIVOLT |  | 0 |

### Value.Numeric.Volume.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| LITER |  | 0 |
| GALLON_US |  | 1 |
| GALLON_IMPERIAL |  | 2 |
| CUBIC_METER |  | 3 |
| CUBIC_FEET |  | 4 |

### Value.Type
The type of value that is represented.

| Name | Description | Number |
| ---- | ----------- | ------ |
| OTHER |  | 0 |
| NUMERIC | This field contains numeric values, with an optional unit of measurement defined below. | 1 |
| TEXT | This field contains text to be displayed. | 2 |
| ENUM | This field switches between several predefined values. Typically used for status fields. | 3 |

### ValueAggregation
Get an aggregated value for the selected data (e.g. average).
Text fields can only use the LAST aggregation.
Enum fields support a subset of aggregations:
  - DEFAULT and LAST return the last value;
  - MINIMUM and MAXIMUM return the lowest or highest value (respectively) based on the enum value order;
  - AVERAGE and SUM are not supported.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT |  | 0 |
| AVERAGE | Return the average value. Not supported for textual and enum fields. When used with these fields, LAST is used instead. | 1 |
| SUM | Return the sum all values. Not supported for textual and enum fields. When used with these fields, LAST is used instead. | 2 |
| LAST | Just take the last value. | 3 |
| MINIMUM | Return the lowest value. For enum fields, the order of values is used to determine the MINIMUM. Not supported for textual fields. When used with these fields, LAST is used instead. | 4 |
| MAXIMUM | Return the highest value. For enum fields, the order of values is used to determine the MAXIMUM. Not supported for textual fields. When used with these fields, LAST is used instead. | 5 |

### ValueTransformation
Transform the values into a derived value.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DURATION | Instead of returning the value, return the amount of time a value was active. Aggregation (if applicable) is applied afterwards on the duration value. | 0 |
| DELTA | Instead of returning the value, return the difference between the value and the previous value. Aggregation (if applicable) is applied before the delta is calculated. | 1 |

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

