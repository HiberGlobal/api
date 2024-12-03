# unit_preferences_service.proto



#### This file was generated from [unit_preferences_service.proto](https://github.com/HiberGlobal/api/blob/master/unit_preferences_service.proto).

## Table of Contents

- Services
  - [UnitPreferencesService](#unitpreferencesservice)

- Messages
  - [UnitPreferences](#unitpreferences)
  - [UnitPreferences.DistancePreference](#unitpreferencesdistancepreference)
  - [UnitPreferences.FlowPreference](#unitpreferencesflowpreference)
  - [UnitPreferences.FuelEfficiencyPreference](#unitpreferencesfuelefficiencypreference)
  - [UnitPreferences.MassPreference](#unitpreferencesmasspreference)
  - [UnitPreferences.PercentagePreference](#unitpreferencespercentagepreference)
  - [UnitPreferences.PressurePreference](#unitpreferencespressurepreference)
  - [UnitPreferences.Request](#unitpreferencesrequest)
  - [UnitPreferences.Response](#unitpreferencesresponse)
  - [UnitPreferences.RotationSpeedPreference](#unitpreferencesrotationspeedpreference)
  - [UnitPreferences.SpeedPreference](#unitpreferencesspeedpreference)
  - [UnitPreferences.TemperaturePreference](#unitpreferencestemperaturepreference)
  - [UnitPreferences.VoltagePreference](#unitpreferencesvoltagepreference)
  - [UnitPreferences.VolumePreference](#unitpreferencesvolumepreference)

- Enums
  - [UnitPreferences.UnitCategory](#unitpreferencesunitcategory)

- Referenced messages from [field.proto](#referenced-messages-from-fieldproto)
  - [hiber.field.Field](#hiberfieldfield)
  - [hiber.field.Field.Enum](#hiberfieldfieldenum)
  - [hiber.field.Field.Numeric](#hiberfieldfieldnumeric)
  - [hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat)
  - [hiber.field.Field.Numeric.Unit](#hiberfieldfieldnumericunit)

    - [hiber.field.Field.Numeric.Format.RoundingMode](#hiberfieldfieldnumericformatroundingmode)

- Referenced messages from [value.proto](#referenced-messages-from-valueproto)
  - [hiber.value.Value](#hibervaluevalue)
  - [hiber.value.Value.Enum](#hibervaluevalueenum)
  - [hiber.value.Value.Numeric](#hibervaluevaluenumeric)
  - [hiber.value.Value.Numeric.BatteryLevel](#hibervaluevaluenumericbatterylevel)
  - [hiber.value.Value.Numeric.Distance](#hibervaluevaluenumericdistance)
  - [hiber.value.Value.Numeric.Duration](#hibervaluevaluenumericduration)
  - [hiber.value.Value.Numeric.Flow](#hibervaluevaluenumericflow)
  - [hiber.value.Value.Numeric.FuelEfficiency](#hibervaluevaluenumericfuelefficiency)
  - [hiber.value.Value.Numeric.Mass](#hibervaluevaluenumericmass)
  - [hiber.value.Value.Numeric.Other](#hibervaluevaluenumericother)
  - [hiber.value.Value.Numeric.Percentage](#hibervaluevaluenumericpercentage)
  - [hiber.value.Value.Numeric.Pressure](#hibervaluevaluenumericpressure)
  - [hiber.value.Value.Numeric.Rate](#hibervaluevaluenumericrate)
  - [hiber.value.Value.Numeric.RotationSpeed](#hibervaluevaluenumericrotationspeed)
  - [hiber.value.Value.Numeric.Speed](#hibervaluevaluenumericspeed)
  - [hiber.value.Value.Numeric.Temperature](#hibervaluevaluenumerictemperature)
  - [hiber.value.Value.Numeric.Voltage](#hibervaluevaluenumericvoltage)
  - [hiber.value.Value.Numeric.Volume](#hibervaluevaluenumericvolume)
  - Enums
    - [hiber.value.Value.Numeric.BatteryLevel.BatteryLevelUnit](#hibervaluevaluenumericbatterylevelbatterylevelunit)
    - [hiber.value.Value.Numeric.Distance.DistanceUnit](#hibervaluevaluenumericdistancedistanceunit)
    - [hiber.value.Value.Numeric.Duration.DurationUnit](#hibervaluevaluenumericdurationdurationunit)
    - [hiber.value.Value.Numeric.Flow.FlowUnit](#hibervaluevaluenumericflowflowunit)
    - [hiber.value.Value.Numeric.FuelEfficiency.FuelEfficiencyUnit](#hibervaluevaluenumericfuelefficiencyfuelefficiencyunit)
    - [hiber.value.Value.Numeric.Mass.MassUnit](#hibervaluevaluenumericmassmassunit)
    - [hiber.value.Value.Numeric.Percentage.PercentageUnit](#hibervaluevaluenumericpercentagepercentageunit)
    - [hiber.value.Value.Numeric.Pressure.PressureUnit](#hibervaluevaluenumericpressurepressureunit)
    - [hiber.value.Value.Numeric.Rate.RateUnit](#hibervaluevaluenumericraterateunit)
    - [hiber.value.Value.Numeric.RotationSpeed.RotationSpeedUnit](#hibervaluevaluenumericrotationspeedrotationspeedunit)
    - [hiber.value.Value.Numeric.Speed.SpeedUnit](#hibervaluevaluenumericspeedspeedunit)
    - [hiber.value.Value.Numeric.Temperature.TemperatureUnit](#hibervaluevaluenumerictemperaturetemperatureunit)
    - [hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype)
    - [hiber.value.Value.Numeric.Voltage.VoltageUnit](#hibervaluevaluenumericvoltagevoltageunit)
    - [hiber.value.Value.Numeric.Volume.VolumeUnit](#hibervaluevaluenumericvolumevolumeunit)
    - [hiber.value.Value.Type](#hibervaluevaluetype)
    - [hiber.value.ValueAggregation](#hibervaluevalueaggregation)
    - [hiber.value.ValueTransformation](#hibervaluevaluetransformation)

- [Scalar Value Types](#scalar-value-types)


## UnitPreferencesService


### UnitPreferences
> **rpc** UnitPreferences([UnitPreferences.Request](#unitpreferencesrequest))
    [UnitPreferences.Response](#unitpreferencesresponse)




## Messages

### UnitPreferences

The preferred units for the current user.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** distance_preference | [optional UnitPreferences.DistancePreference](#unitpreferencesdistancepreference) | Optional distance preference for the current user. |
|  **optional** flow_preference | [optional UnitPreferences.FlowPreference](#unitpreferencesflowpreference) | Optional mass preference for the current user. |
|  **optional** fuel_efficiency_preference | [optional UnitPreferences.FuelEfficiencyPreference](#unitpreferencesfuelefficiencypreference) | Optional fuel efficiency preference for the current user. |
|  **optional** mass_preference | [optional UnitPreferences.MassPreference](#unitpreferencesmasspreference) | Optional mass preference for the current user. |
|  **optional** percentage_preference | [optional UnitPreferences.PercentagePreference](#unitpreferencespercentagepreference) | Optional percentage preference for the current user. |
|  **optional** pressure_preference | [optional UnitPreferences.PressurePreference](#unitpreferencespressurepreference) | Optional pressure preference for the current user. |
|  **optional** speed_preference | [optional UnitPreferences.SpeedPreference](#unitpreferencesspeedpreference) | Optional speed preference for the current user. |
|  **optional** temperature_preference | [optional UnitPreferences.TemperaturePreference](#unitpreferencestemperaturepreference) | Optional temperature preference for the current user. |
|  **optional** voltage_preference | [optional UnitPreferences.VoltagePreference](#unitpreferencesvoltagepreference) | Optional voltage preference for the current user. |
|  **optional** volume_preference | [optional UnitPreferences.VolumePreference](#unitpreferencesvolumepreference) | Optional volume preference for the current user. |
|  **optional** rotation_speed_preference | [optional UnitPreferences.RotationSpeedPreference](#unitpreferencesrotationspeedpreference) |  |

### UnitPreferences.DistancePreference

User preferences for distance values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| preference | [ UnitPreferences.UnitCategory](#unitpreferencesunitcategory) | Unit category (metric / imperial) to convert distance values to. |
| format | [ hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.FlowPreference

User preferences for mass values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| preference | [ Value.Numeric.Flow.FlowUnit](#valuenumericflowflowunit) |  |
| format | [ hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.FuelEfficiencyPreference

User preferences for fuel efficiency values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| preference | [ Value.Numeric.FuelEfficiency.FuelEfficiencyUnit](#valuenumericfuelefficiencyfuelefficiencyunit) |  |
| format | [ hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.MassPreference

User preferences for mass values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| preference | [ UnitPreferences.UnitCategory](#unitpreferencesunitcategory) | Unit category (metric / imperial) to convert mass values to. |
| format | [ hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.PercentagePreference

User preferences for percentage values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| format | [ hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.PressurePreference

User preferences for pressure values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| preference | [ Value.Numeric.Pressure.PressureUnit](#valuenumericpressurepressureunit) |  |
| format | [ hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **distance**.update_distance_preference | [ UnitPreferences.DistancePreference](#unitpreferencesdistancepreference) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **distance**.remove_distance_preference | [ bool](#bool) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **flow**.update_flow_preference | [ UnitPreferences.FlowPreference](#unitpreferencesflowpreference) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **flow**.remove_flow_preference | [ bool](#bool) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **fuel_efficiency**.update_fuel_efficiency_preference | [ UnitPreferences.FuelEfficiencyPreference](#unitpreferencesfuelefficiencypreference) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **fuel_efficiency**.remove_fuel_efficiency_preference | [ bool](#bool) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **mass**.update_mass_preference | [ UnitPreferences.MassPreference](#unitpreferencesmasspreference) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **mass**.remove_mass_preference | [ bool](#bool) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **percentage**.update_percentage_preference | [ UnitPreferences.PercentagePreference](#unitpreferencespercentagepreference) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **percentage**.remove_percentage_preference | [ bool](#bool) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **pressure**.update_pressure_preference | [ UnitPreferences.PressurePreference](#unitpreferencespressurepreference) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **pressure**.remove_pressure_preference | [ bool](#bool) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **speed**.update_speed_preference | [ UnitPreferences.SpeedPreference](#unitpreferencesspeedpreference) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **speed**.remove_speed_preference | [ bool](#bool) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **temperature**.update_temperature_preference | [ UnitPreferences.TemperaturePreference](#unitpreferencestemperaturepreference) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **temperature**.remove_temperature_preference | [ bool](#bool) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **voltage**.update_voltage_preference | [ UnitPreferences.VoltagePreference](#unitpreferencesvoltagepreference) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **voltage**.remove_voltage_preference | [ bool](#bool) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **volume**.update_volume_preference | [ UnitPreferences.VolumePreference](#unitpreferencesvolumepreference) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **volume**.remove_volume_preference | [ bool](#bool) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **rotation_speed**.update_rotation_speed_preference | [ UnitPreferences.RotationSpeedPreference](#unitpreferencesrotationspeedpreference) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **rotation_speed**.remove_rotation_speed_preference | [ bool](#bool) |  |

### UnitPreferences.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| preferences | [ UnitPreferences](#unitpreferences) |  |

### UnitPreferences.RotationSpeedPreference

User preferences for rotation speed values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| preference | [ Value.Numeric.RotationSpeed.RotationSpeedUnit](#valuenumericrotationspeedrotationspeedunit) |  |
| format | [ hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.SpeedPreference

User preferences for speed values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| preference | [ UnitPreferences.UnitCategory](#unitpreferencesunitcategory) | Unit category (metric / imperial) to convert speed values to. |
| format | [ hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.TemperaturePreference

User preferences for temperature values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| preference | [ Value.Numeric.Temperature.TemperatureUnit](#valuenumerictemperaturetemperatureunit) |  |
| format | [ hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.VoltagePreference

User preferences for voltage values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| preference | [ Value.Numeric.Voltage.VoltageUnit](#valuenumericvoltagevoltageunit) |  |
| format | [ hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.VolumePreference

User preferences for volume values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| preference | [ UnitPreferences.UnitCategory](#unitpreferencesunitcategory) | Unit category (metric / imperial) to convert volume values to. |
| format | [ hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat) | Optional formatting options for values (rounding, etc). |


## Enums
### UnitPreferences.UnitCategory


| Name | Description | Number |
| ---- | ----------- | ------ |
| METRIC |  | 0 |
| IMPERIAL |  | 1 |



## Referenced messages from field.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [field.proto](https://github.com/HiberGlobal/api/blob/master/field.proto).


### hiber.field.Field



| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) | Unique identifier for this field. |
| field | [ string](#string) | The name of the field (if in the root structure) or a JsonPath to the field. |
|  **optional** display_name | [optional string](#string) | An optional display name for the field. |
| priority | [ int32](#int32) | Priority of the field, typically used for ordering. |
| type | [ hiber.value.Value.Type](#hibervaluevaluetype) | The type of value the field contains. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **details**.numeric | [ hiber.field.Field.Numeric](#hiberfieldfieldnumeric) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **details**.enum | [ hiber.field.Field.Enum](#hiberfieldfieldenum) |  |
| encrypted | [ bool](#bool) | Whether this field should be stored encrypted or not. If it is, some processing options may be unavailable or slower. |
| optional | [ bool](#bool) | Whether this field should be validated from the parser output. |
| operational | [ bool](#bool) | Field contains values relevant for operating the device. |
|  **optional** unit_of_measurement | [optional hiber.UnitOfMeasurement](#hiberunitofmeasurement) | <strong>Deprecated.</strong> If numeric, the unit of the field. Deprecated: use numeric.numeric_unit oneof instead |
|  **optional** unit_symbol | [optional string](#string) | <strong>Deprecated.</strong> The symbol for the unit. Deprecated: use numeric.symbol instead |

### hiber.field.Field.Enum

If the field is an enum, this specifies the enum values for the field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| values | [repeated hiber.value.Value.Enum](#hibervaluevalueenum) |  |

### hiber.field.Field.Numeric

If the field is numeric, this specifies the unit and formatting details for the field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype) | The type of numeric value. |
| symbol | [ string](#string) | The symbol to use for the field's unit. |
| format | [ hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat) | How to format the values (number of decimals, rounding, etc.). |
| unit | [ hiber.field.Field.Numeric.Unit](#hiberfieldfieldnumericunit) | The unit for the field, depending on the type. |
|  **optional** converted_from | [optional hiber.field.Field.Numeric.Unit](#hiberfieldfieldnumericunit) | If the unit preferences were applied, and the unit is different, the field will be converted to the preferred unit, from the original unit specified in this field. |

### hiber.field.Field.Numeric.Format

Formatting options for the field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **round**.round_to_integer | [ bool](#bool) | Round to an integer. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **round**.round_to_scale | [ uint32](#uint32) | Round to a number of decimals (at least 1). |
| rounding_mode | [ hiber.field.Field.Numeric.Format.RoundingMode](#hiberfieldfieldnumericformatroundingmode) | How to round the value when scale is applied. |

### hiber.field.Field.Numeric.Unit



| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.battery_level | [ hiber.value.Value.Numeric.BatteryLevel.BatteryLevelUnit](#hibervaluevaluenumericbatterylevelbatterylevelunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.distance | [ hiber.value.Value.Numeric.Distance.DistanceUnit](#hibervaluevaluenumericdistancedistanceunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.duration | [ hiber.value.Value.Numeric.Duration.DurationUnit](#hibervaluevaluenumericdurationdurationunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.fuel_efficiency | [ hiber.value.Value.Numeric.FuelEfficiency.FuelEfficiencyUnit](#hibervaluevaluenumericfuelefficiencyfuelefficiencyunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.flow | [ hiber.value.Value.Numeric.Flow.FlowUnit](#hibervaluevaluenumericflowflowunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.percentage | [ hiber.value.Value.Numeric.Percentage.PercentageUnit](#hibervaluevaluenumericpercentagepercentageunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.pressure | [ hiber.value.Value.Numeric.Pressure.PressureUnit](#hibervaluevaluenumericpressurepressureunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.speed | [ hiber.value.Value.Numeric.Speed.SpeedUnit](#hibervaluevaluenumericspeedspeedunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.temperature | [ hiber.value.Value.Numeric.Temperature.TemperatureUnit](#hibervaluevaluenumerictemperaturetemperatureunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.voltage | [ hiber.value.Value.Numeric.Voltage.VoltageUnit](#hibervaluevaluenumericvoltagevoltageunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.volume | [ hiber.value.Value.Numeric.Volume.VolumeUnit](#hibervaluevaluenumericvolumevolumeunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.mass | [ hiber.value.Value.Numeric.Mass.MassUnit](#hibervaluevaluenumericmassmassunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.rotation_speed | [ hiber.value.Value.Numeric.RotationSpeed.RotationSpeedUnit](#hibervaluevaluenumericrotationspeedrotationspeedunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.rate | [ hiber.value.Value.Numeric.Rate.RateUnit](#hibervaluevaluenumericraterateunit) |  |


### Enums
#### hiber.field.Field.Numeric.Format.RoundingMode
How to round the value when scale is applied.
For example, a value of 3.1415 with scale 3 could be
  4.141 (DOWN, HALF_DOWN, FLOOR) or
  4.142 (HALF_UP, UP, CEILING).

| Name | Description | Number |
| ---- | ----------- | ------ |
| HALF_UP | Round towards nearest neighbor unless both neighbors are equidistant, in which case round up Effectively round up when >= .5, otherwise round down. | 0 |
| HALF_DOWN | Round towards nearest neighbor unless both neighbors are equidistant, in which case round down. Effectively round up when > .5, otherwise round down. | 1 |
| UP | Round away from zero: 1.1 -> 2, while -1.1 -> -2. | 3 |
| DOWN | Round towards zero: 1.1 -> 1, while -1.1 -> -1. | 4 |
| CEILING | Round towards positive infinity. | 5 |
| FLOOR | Round towards negative infinity. | 6 |
| HALF_EVEN | Round towards the nearest neighbor unless both neighbors are equidistant, in which case, round towards the even neighbor. Effectively round up when >= .5 and next integer value is even, otherwise round down. | 7 |



## Referenced messages from value.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [value.proto](https://github.com/HiberGlobal/api/blob/master/value.proto).


### hiber.value.Value



| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.value.Value.Type](#hibervaluevaluetype) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.numeric | [ hiber.value.Value.Numeric](#hibervaluevaluenumeric) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.text | [ string](#string) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.enum | [ hiber.value.Value.Enum](#hibervaluevalueenum) |  |

### hiber.value.Value.Enum

If this value is an enum, this specifies the value, display name and color for this enum value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ string](#string) | The enum value. This might be a cryptic value, see the display_name and description for more information. |
| display_name | [ string](#string) | User-facing name for this value. |
| description | [ string](#string) | More details for this enum value. |
| color | [ string](#string) | (Optional) color for this enum value. |
| priority | [ int32](#int32) | Priority of the value, typically used for ordering. |

### hiber.value.Value.Numeric

If the value is numeric, this specifies the unit, value, etc.

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.battery_level | [ hiber.value.Value.Numeric.BatteryLevel](#hibervaluevaluenumericbatterylevel) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.distance | [ hiber.value.Value.Numeric.Distance](#hibervaluevaluenumericdistance) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.duration | [ hiber.value.Value.Numeric.Duration](#hibervaluevaluenumericduration) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.fuel_efficiency | [ hiber.value.Value.Numeric.FuelEfficiency](#hibervaluevaluenumericfuelefficiency) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.percentage | [ hiber.value.Value.Numeric.Percentage](#hibervaluevaluenumericpercentage) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.pressure | [ hiber.value.Value.Numeric.Pressure](#hibervaluevaluenumericpressure) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.speed | [ hiber.value.Value.Numeric.Speed](#hibervaluevaluenumericspeed) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.temperature | [ hiber.value.Value.Numeric.Temperature](#hibervaluevaluenumerictemperature) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.voltage | [ hiber.value.Value.Numeric.Voltage](#hibervaluevaluenumericvoltage) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.volume | [ hiber.value.Value.Numeric.Volume](#hibervaluevaluenumericvolume) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.mass | [ hiber.value.Value.Numeric.Mass](#hibervaluevaluenumericmass) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.flow | [ hiber.value.Value.Numeric.Flow](#hibervaluevaluenumericflow) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.rotation_speed | [ hiber.value.Value.Numeric.RotationSpeed](#hibervaluevaluenumericrotationspeed) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.rate | [ hiber.value.Value.Numeric.Rate](#hibervaluevaluenumericrate) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.other | [ hiber.value.Value.Numeric.Other](#hibervaluevaluenumericother) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.unknown | [ double](#double) |  |
| value | [ double](#double) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| unit | [ hiber.UnitOfMeasurement](#hiberunitofmeasurement) | Unit of the value, based on the user preferences. |
| unit_symbol | [ string](#string) | Display string of the unit symbol, based on the unit of the value (which is based on user preferences). |
|  **optional** converted_from | [optional hiber.UnitOfMeasurement](#hiberunitofmeasurement) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.BatteryLevel

Special case for battery level, since it can be provided in many units.
Not included in the UnitPreferences, since it cannot be converted.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.BatteryLevel.BatteryLevelUnit](#hibervaluevaluenumericbatterylevelbatterylevelunit) |  |

### hiber.value.Value.Numeric.Distance

The value is a distance value, converted to your preferred distance unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.Distance.DistanceUnit](#hibervaluevaluenumericdistancedistanceunit) |  |

### hiber.value.Value.Numeric.Duration



| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.Duration.DurationUnit](#hibervaluevaluenumericdurationdurationunit) |  |
| duration | [ google.protobuf.Duration](#googleprotobufduration) |  |

### hiber.value.Value.Numeric.Flow



| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.Flow.FlowUnit](#hibervaluevaluenumericflowflowunit) |  |

### hiber.value.Value.Numeric.FuelEfficiency

The value is a fuel efficiency value, converted to your preferred fuel efficiency unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.FuelEfficiency.FuelEfficiencyUnit](#hibervaluevaluenumericfuelefficiencyfuelefficiencyunit) |  |

### hiber.value.Value.Numeric.Mass

The value is a mass value, converted to your preferred mass unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.Mass.MassUnit](#hibervaluevaluenumericmassmassunit) |  |

### hiber.value.Value.Numeric.Other

Known unit that is not (yet) supported.
This could be a very specific value, like a counter,
or something like energy in joules that is not available.


### hiber.value.Value.Numeric.Percentage

The value is a percentage.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.Percentage.PercentageUnit](#hibervaluevaluenumericpercentagepercentageunit) |  |

### hiber.value.Value.Numeric.Pressure

The value is a pressure value, converted to your preferred pressure unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.Pressure.PressureUnit](#hibervaluevaluenumericpressurepressureunit) |  |

### hiber.value.Value.Numeric.Rate



| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.Rate.RateUnit](#hibervaluevaluenumericraterateunit) |  |
| value | [ uint32](#uint32) |  |

### hiber.value.Value.Numeric.RotationSpeed

The value for rotation speed. The only value is revolutions per minute (RPM), therefore it is not included in
unit preferences.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.RotationSpeed.RotationSpeedUnit](#hibervaluevaluenumericrotationspeedrotationspeedunit) |  |

### hiber.value.Value.Numeric.Speed

The value is a speed value, converted to your preferred speed unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.Speed.SpeedUnit](#hibervaluevaluenumericspeedspeedunit) |  |

### hiber.value.Value.Numeric.Temperature

The value is a temperature, converted to your preferred temperature unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.Temperature.TemperatureUnit](#hibervaluevaluenumerictemperaturetemperatureunit) |  |

### hiber.value.Value.Numeric.Voltage

The value is a voltage, converted to your preferred voltage unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.Voltage.VoltageUnit](#hibervaluevaluenumericvoltagevoltageunit) |  |

### hiber.value.Value.Numeric.Volume

The value is a volume value, converted to your preferred volume unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.Volume.VolumeUnit](#hibervaluevaluenumericvolumevolumeunit) |  |


### Enums
#### hiber.value.Value.Numeric.BatteryLevel.BatteryLevelUnit
Convenience type for battery level. Other units may be added here later, like voltage.

| Name | Description | Number |
| ---- | ----------- | ------ |
| PERCENT | Battery level as a percentage (technically not a unit). | 0 |

#### hiber.value.Value.Numeric.Distance.DistanceUnit
Unit of distance

| Name | Description | Number |
| ---- | ----------- | ------ |
| METER | m | 0 |
| MILLIMETER | mm | 1 |
| CENTIMETER | cm | 2 |
| KILOMETER | km | 3 |
| YARD | yd | 5 |
| MILE | mi | 4 |
| FOOT | ' | 6 |
| INCH | ″ | 7 |
| NAUTICAL_MILE | NM. This is a special case unit and may not be auto-converted to your UnitPreference. | 8 |

#### hiber.value.Value.Numeric.Duration.DurationUnit
Unit of duration.

| Name | Description | Number |
| ---- | ----------- | ------ |
| MILLISECONDS | ms | 0 |
| SECONDS | s | 1 |
| MINUTES | min | 2 |
| HOURS | h | 3 |
| DAYS | d | 4 |
| WEEKS | w | 5 |

#### hiber.value.Value.Numeric.Flow.FlowUnit
Unit of volume per time.

| Name | Description | Number |
| ---- | ----------- | ------ |
| CUBIC_METER_PER_HOUR | m³/h | 0 |
| BARRELS_PER_DAY | bbl/d | 1 |
| CUBIC_METER_PER_SECOND | m³/s | 2 |
| CUBIC_FEET_PER_HOUR | ft³/h | 3 |
| CUBIC_FEET_PER_SECOND | ft³/s | 4 |
| LITER_PER_HOUR | l/h | 5 |
| LITER_PER_SECOND | l/s | 6 |

#### hiber.value.Value.Numeric.FuelEfficiency.FuelEfficiencyUnit
Unit of fuel efficiency

| Name | Description | Number |
| ---- | ----------- | ------ |
| LITER_PER_100_KILOMETER | l/100km | 0 |
| KILOMETER_PER_LITER | km/l | 1 |
| KILOMETER_PER_GALLON | km/gal (US) | 2 |
| KILOMETER_PER_IMPERIAL_GALLON | km/gal (imp) | 3 |
| MILES_PER_GALLON | mpg (US) | 4 |
| MILES_PER_IMPERIAL_GALLON | mpg (imp) | 5 |
| MILES_PER_LITER | mpl | 6 |

#### hiber.value.Value.Numeric.Mass.MassUnit
Unit of mass.

| Name | Description | Number |
| ---- | ----------- | ------ |
| KILOGRAMS | kg | 0 |
| POUNDS | lb | 1 |

#### hiber.value.Value.Numeric.Percentage.PercentageUnit
Convenience type for percentage. Technically not a unit, but for consistency, we've added it here.

| Name | Description | Number |
| ---- | ----------- | ------ |
| PERCENT | % | 0 |

#### hiber.value.Value.Numeric.Pressure.PressureUnit
Unit of pressure.

| Name | Description | Number |
| ---- | ----------- | ------ |
| BAR | bar | 0 |
| PSI | psi | 1 |
| K_PA | kPa | 2 |
| KILOGRAM_PER_CENTIMETER_SQUARED | kg/cm² | 3 |

#### hiber.value.Value.Numeric.Rate.RateUnit


| Name | Description | Number |
| ---- | ----------- | ------ |
| ITEMS_PER_24_HOURS | The amount of items counted in a 24 hour window. | 0 |

#### hiber.value.Value.Numeric.RotationSpeed.RotationSpeedUnit


| Name | Description | Number |
| ---- | ----------- | ------ |
| REVOLUTIONS_PER_MINUTE | rpm | 0 |

#### hiber.value.Value.Numeric.Speed.SpeedUnit
Unit of speed.

| Name | Description | Number |
| ---- | ----------- | ------ |
| KILOMETERS_PER_HOUR | km/h | 0 |
| KNOTS | kn. This is a special case unit and may not be auto-converted to your UnitPreference. | 1 |
| METERS_PER_SECOND | m/s | 2 |
| MILES_PER_HOUR | mph | 3 |
| FEET_PER_SECOND | ft/s | 4 |

#### hiber.value.Value.Numeric.Temperature.TemperatureUnit
Unit of temperature.

| Name | Description | Number |
| ---- | ----------- | ------ |
| KELVIN | K | 0 |
| DEGREES_CELSIUS | °C | 1 |
| DEGREES_FAHRENHEIT | °F | 2 |

#### hiber.value.Value.Numeric.Type
The type of numeric value that is represented.
Supported types will automatically convert to the preferred unit (based on the user settings).

| Name | Description | Number |
| ---- | ----------- | ------ |
| TYPE_UNKNOWN |  | 0 |
| BATTERY_LEVEL | Battery level, as a percentage. | 11 |
| DISTANCE | Distance in metric or imperial units. | 3 |
| DURATION | Time period. | 8 |
| FLOW | Volume per time period. | 12 |
| FUEL_EFFICIENCY | Fuel efficiency, e.g. mpg or l/100km. | 9 |
| MASS | Mass. | 10 |
| OTHER | Known unit that is not (yet) supported. This could be a very specific value, like a counter, or something like energy in joules that is not available. | 15 |
| PERCENTAGE | A percentage, typically 0-100%. | 1 |
| PRESSURE | Pressure. | 4 |
| RATE | Count per time period, e.g. the amount of items counted in a 24 hour window. | 14 |
| ROTATION_SPEED | Speed that something rotates per time period, typically in revolutions per minute. | 13 |
| TEMPERATURE | Temperature. | 2 |
| SPEED | Speed, e.g. km/h. | 6 |
| VOLTAGE | Voltage, e.g. mV. | 5 |
| VOLUME | Volume, e.g. m³. | 7 |

#### hiber.value.Value.Numeric.Voltage.VoltageUnit
Unit of voltage.

| Name | Description | Number |
| ---- | ----------- | ------ |
| MILLIVOLT | mV | 0 |

#### hiber.value.Value.Numeric.Volume.VolumeUnit
Unit of volume.

| Name | Description | Number |
| ---- | ----------- | ------ |
| LITER | l | 0 |
| GALLON_US | gal (US) | 1 |
| GALLON_IMPERIAL | gal (imp) | 2 |
| CUBIC_METER | m³ | 3 |
| CUBIC_FEET | ft³ | 4 |

#### hiber.value.Value.Type
The type of value that is represented.

| Name | Description | Number |
| ---- | ----------- | ------ |
| OTHER |  | 0 |
| NUMERIC | This field contains numeric values, with an optional unit of measurement defined below. | 1 |
| TEXT | This field contains text to be displayed. | 2 |
| ENUM | This field switches between several predefined values. Typically used for status fields. | 3 |

#### hiber.value.ValueAggregation
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

#### hiber.value.ValueTransformation
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

