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
  - [hiber.value.Value.Numeric.Flow](#hibervaluevaluenumericflow)
  - [hiber.value.Value.Numeric.FuelEfficiency](#hibervaluevaluenumericfuelefficiency)
  - [hiber.value.Value.Numeric.Mass](#hibervaluevaluenumericmass)
  - [hiber.value.Value.Numeric.Percentage](#hibervaluevaluenumericpercentage)
  - [hiber.value.Value.Numeric.Pressure](#hibervaluevaluenumericpressure)
  - [hiber.value.Value.Numeric.Speed](#hibervaluevaluenumericspeed)
  - [hiber.value.Value.Numeric.Temperature](#hibervaluevaluenumerictemperature)
  - [hiber.value.Value.Numeric.Voltage](#hibervaluevaluenumericvoltage)
  - [hiber.value.Value.Numeric.Volume](#hibervaluevaluenumericvolume)
  - Enums
    - [hiber.value.Value.Numeric.BatteryLevel.Unit](#hibervaluevaluenumericbatterylevelunit)
    - [hiber.value.Value.Numeric.Distance.Unit](#hibervaluevaluenumericdistanceunit)
    - [hiber.value.Value.Numeric.DurationUnit](#hibervaluevaluenumericdurationunit)
    - [hiber.value.Value.Numeric.Flow.Unit](#hibervaluevaluenumericflowunit)
    - [hiber.value.Value.Numeric.FuelEfficiency.Unit](#hibervaluevaluenumericfuelefficiencyunit)
    - [hiber.value.Value.Numeric.Mass.Unit](#hibervaluevaluenumericmassunit)
    - [hiber.value.Value.Numeric.Percentage.Unit](#hibervaluevaluenumericpercentageunit)
    - [hiber.value.Value.Numeric.Pressure.Unit](#hibervaluevaluenumericpressureunit)
    - [hiber.value.Value.Numeric.Speed.Unit](#hibervaluevaluenumericspeedunit)
    - [hiber.value.Value.Numeric.Temperature.Unit](#hibervaluevaluenumerictemperatureunit)
    - [hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype)
    - [hiber.value.Value.Numeric.Voltage.Unit](#hibervaluevaluenumericvoltageunit)
    - [hiber.value.Value.Numeric.Volume.Unit](#hibervaluevaluenumericvolumeunit)
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
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **distance**.distance_preference | [ UnitPreferences.DistancePreference](#unitpreferencesdistancepreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **distance**.no_distance_preference | [ bool](#bool) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **flow**.flow_preference | [ UnitPreferences.FlowPreference](#unitpreferencesflowpreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **flow**.no_flow_preference | [ bool](#bool) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **fuel_efficiency**.fuel_efficiency_preference | [ UnitPreferences.FuelEfficiencyPreference](#unitpreferencesfuelefficiencypreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **fuel_efficiency**.no_fuel_efficiency_preference | [ bool](#bool) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **mass**.mass_preference | [ UnitPreferences.MassPreference](#unitpreferencesmasspreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **mass**.no_mass_preference | [ bool](#bool) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **percentage**.percentage_preference | [ UnitPreferences.PercentagePreference](#unitpreferencespercentagepreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **percentage**.no_percentage_preference | [ bool](#bool) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **pressure**.pressure_preference | [ UnitPreferences.PressurePreference](#unitpreferencespressurepreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **pressure**.no_pressure_preference | [ bool](#bool) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **speed**.speed_preference | [ UnitPreferences.SpeedPreference](#unitpreferencesspeedpreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **speed**.no_speed_preference | [ bool](#bool) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **temperature**.temperature_preference | [ UnitPreferences.TemperaturePreference](#unitpreferencestemperaturepreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **temperature**.no_temperature_preference | [ bool](#bool) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **voltage**.voltage_preference | [ UnitPreferences.VoltagePreference](#unitpreferencesvoltagepreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **voltage**.no_voltage_preference | [ bool](#bool) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **volume**.volume_preference | [ UnitPreferences.VolumePreference](#unitpreferencesvolumepreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **volume**.no_volume_preference | [ bool](#bool) | none |

### UnitPreferences.DistancePreference

User preferences for distance values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit_category | [ UnitPreferences.UnitCategory](#unitpreferencesunitcategory) | Unit category (metric / imperial) to convert distance values to. |
| format | [ hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.FlowPreference

User preferences for mass values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ Value.Numeric.Flow.Unit](#valuenumericflowunit) | none |
| format | [ hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.FuelEfficiencyPreference

User preferences for fuel efficiency values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ Value.Numeric.FuelEfficiency.Unit](#valuenumericfuelefficiencyunit) | none |
| format | [ hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.MassPreference

User preferences for mass values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit_category | [ UnitPreferences.UnitCategory](#unitpreferencesunitcategory) | Unit category (metric / imperial) to convert mass values to. |
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
| unit | [ Value.Numeric.Pressure.Unit](#valuenumericpressureunit) | none |
| format | [ hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **distance**.update_distance_preference | [ UnitPreferences.DistancePreference](#unitpreferencesdistancepreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **distance**.remove_distance_preference | [ bool](#bool) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **flow**.update_flow_preference | [ UnitPreferences.FlowPreference](#unitpreferencesflowpreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **flow**.remove_flow_preference | [ bool](#bool) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **fuel_efficiency**.update_fuel_efficiency_preference | [ UnitPreferences.FuelEfficiencyPreference](#unitpreferencesfuelefficiencypreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **fuel_efficiency**.remove_fuel_efficiency_preference | [ bool](#bool) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **mass**.update_mass_preference | [ UnitPreferences.MassPreference](#unitpreferencesmasspreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **mass**.remove_mass_preference | [ bool](#bool) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **percentage**.update_percentage_preference | [ UnitPreferences.PercentagePreference](#unitpreferencespercentagepreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **percentage**.remove_percentage_preference | [ bool](#bool) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **pressure**.update_pressure_preference | [ UnitPreferences.PressurePreference](#unitpreferencespressurepreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **pressure**.remove_pressure_preference | [ bool](#bool) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **speed**.update_speed_preference | [ UnitPreferences.SpeedPreference](#unitpreferencesspeedpreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **speed**.remove_speed_preference | [ bool](#bool) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **temperature**.update_temperature_preference | [ UnitPreferences.TemperaturePreference](#unitpreferencestemperaturepreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **temperature**.remove_temperature_preference | [ bool](#bool) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **voltage**.update_voltage_preference | [ UnitPreferences.VoltagePreference](#unitpreferencesvoltagepreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **voltage**.remove_voltage_preference | [ bool](#bool) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **volume**.update_volume_preference | [ UnitPreferences.VolumePreference](#unitpreferencesvolumepreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **volume**.remove_volume_preference | [ bool](#bool) | none |

### UnitPreferences.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| preferences | [ UnitPreferences](#unitpreferences) | none |

### UnitPreferences.SpeedPreference

User preferences for speed values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit_category | [ UnitPreferences.UnitCategory](#unitpreferencesunitcategory) | Unit category (metric / imperial) to convert speed values to. |
| format | [ hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.TemperaturePreference

User preferences for temperature values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ Value.Numeric.Temperature.Unit](#valuenumerictemperatureunit) | none |
| format | [ hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.VoltagePreference

User preferences for voltage values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ Value.Numeric.Voltage.Unit](#valuenumericvoltageunit) | none |
| format | [ hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.VolumePreference

User preferences for volume values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit_category | [ UnitPreferences.UnitCategory](#unitpreferencesunitcategory) | Unit category (metric / imperial) to convert volume values to. |
| format | [ hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat) | Optional formatting options for values (rounding, etc). |


## Enums
### UnitPreferences.UnitCategory


| Name | Description | Number |
| ---- | ----------- | ------ |
| METRIC | none | 0 |
| IMPERIAL | none | 1 |



## Referenced messages from field.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [field.proto](https://github.com/HiberGlobal/api/blob/master/field.proto).


### hiber.field.Field



| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) | Unique identifier for this field. |
| field | [ string](#string) | The name of the field (if in the root structure) or a JsonPath to the field. |
| display_name | [ string](#string) | An optional display name for the field. |
| priority | [ int32](#int32) | Priority of the field, typically used for ordering. |
| type | [ hiber.value.Value.Type](#hibervaluevaluetype) | The type of value the field contains. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **details**.numeric | [ hiber.field.Field.Numeric](#hiberfieldfieldnumeric) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **details**.enum | [ hiber.field.Field.Enum](#hiberfieldfieldenum) | none |
| encrypted | [ bool](#bool) | Whether this field should be stored encrypted or not. If it is, some processing options may be unavailable or slower. |
| optional | [ bool](#bool) | Whether this field should be validated from the parser output. |
| unit_of_measurement | [ hiber.UnitOfMeasurement](#hiberunitofmeasurement) | If numeric, the unit of the field. Deprecated: use numeric.numeric_unit oneof instead |
| unit_symbol | [ string](#string) | The symbol for the unit. Deprecated: use numeric.symbol instead |

### hiber.field.Field.Enum

If the field is an enum, this specifies the enum values for the field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| values | [repeated hiber.value.Value.Enum](#hibervaluevalueenum) | none |

### hiber.field.Field.Numeric

If the field is numeric, this specifies the unit and formatting details for the field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype) | The type of numeric value. |
| symbol | [ string](#string) | The symbol to use for the field's unit. |
| format | [ hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat) | How to format the values (number of decimals, rounding, etc.). |
| unit | [ hiber.field.Field.Numeric.Unit](#hiberfieldfieldnumericunit) | The unit for the field, depending on the type. |
| converted_from | [ hiber.field.Field.Numeric.Unit](#hiberfieldfieldnumericunit) | If the unit preferences were applied, and the unit is different, the field will be converted to the preferred unit, from the original unit specified in this field. |

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
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.battery_level | [ hiber.value.Value.Numeric.BatteryLevel.Unit](#hibervaluevaluenumericbatterylevelunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.distance | [ hiber.value.Value.Numeric.Distance.Unit](#hibervaluevaluenumericdistanceunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.duration | [ hiber.value.Value.Numeric.DurationUnit](#hibervaluevaluenumericdurationunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.fuel_efficiency | [ hiber.value.Value.Numeric.FuelEfficiency.Unit](#hibervaluevaluenumericfuelefficiencyunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.flow | [ hiber.value.Value.Numeric.Flow.Unit](#hibervaluevaluenumericflowunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.percentage | [ hiber.value.Value.Numeric.Percentage.Unit](#hibervaluevaluenumericpercentageunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.pressure | [ hiber.value.Value.Numeric.Pressure.Unit](#hibervaluevaluenumericpressureunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.speed | [ hiber.value.Value.Numeric.Speed.Unit](#hibervaluevaluenumericspeedunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.temperature | [ hiber.value.Value.Numeric.Temperature.Unit](#hibervaluevaluenumerictemperatureunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.voltage | [ hiber.value.Value.Numeric.Voltage.Unit](#hibervaluevaluenumericvoltageunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.volume | [ hiber.value.Value.Numeric.Volume.Unit](#hibervaluevaluenumericvolumeunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.mass | [ hiber.value.Value.Numeric.Mass.Unit](#hibervaluevaluenumericmassunit) | none |


### Enums
#### hiber.field.Field.Numeric.Format.RoundingMode
How to round the value when scale is applied.
For example, a value of 3.1415 with scale 3 could be
  4.141 (DOWN, HALF_DOWN, FLOOR) or
  4.142 (HALF_UP, UP, CEILING).

| Name | Description | Number |
| ---- | ----------- | ------ |
| HALF_UP | Round towards "nearest neighbor" unless both neighbors are equidistant, in which case round up Effectively round up when >= .5, otherwise round down. | 0 |
| HALF_DOWN | Round towards "nearest neighbor" unless both neighbors are equidistant, in which case round down. Effectively round up when > .5, otherwise round down. | 1 |
| UP | Round away from zero: 1.1 -> 2, while -1.1 -> -2. | 3 |
| DOWN | Round towards zero: 1.1 -> 1, while -1.1 -> -1. | 4 |
| CEILING | Round towards positive infinity. | 5 |
| FLOOR | Round towards negative infinity. | 6 |
| HALF_EVEN | Round towards the "nearest neighbor" unless both neighbors are equidistant, in which case, round towards the even neighbor. Effectively round up when >= .5 and next integer value is even, otherwise round down. | 7 |



## Referenced messages from value.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [value.proto](https://github.com/HiberGlobal/api/blob/master/value.proto).


### hiber.value.Value



| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.value.Value.Type](#hibervaluevaluetype) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.numeric | [ hiber.value.Value.Numeric](#hibervaluevaluenumeric) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.text | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.enum | [ hiber.value.Value.Enum](#hibervaluevalueenum) | none |

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
| type | [ hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.battery_level | [ hiber.value.Value.Numeric.BatteryLevel](#hibervaluevaluenumericbatterylevel) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.distance | [ hiber.value.Value.Numeric.Distance](#hibervaluevaluenumericdistance) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.duration | [ hiber.Duration](#hiberduration) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.fuel_efficiency | [ hiber.value.Value.Numeric.FuelEfficiency](#hibervaluevaluenumericfuelefficiency) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.percentage | [ hiber.value.Value.Numeric.Percentage](#hibervaluevaluenumericpercentage) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.pressure | [ hiber.value.Value.Numeric.Pressure](#hibervaluevaluenumericpressure) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.speed | [ hiber.value.Value.Numeric.Speed](#hibervaluevaluenumericspeed) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.temperature | [ hiber.value.Value.Numeric.Temperature](#hibervaluevaluenumerictemperature) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.voltage | [ hiber.value.Value.Numeric.Voltage](#hibervaluevaluenumericvoltage) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.volume | [ hiber.value.Value.Numeric.Volume](#hibervaluevaluenumericvolume) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.mass | [ hiber.value.Value.Numeric.Mass](#hibervaluevaluenumericmass) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.flow | [ hiber.value.Value.Numeric.Flow](#hibervaluevaluenumericflow) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.unknown | [ double](#double) | none |

### hiber.value.Value.Numeric.BatteryLevel

Special case for battery level, since it can be provided in many units.
Not included in the UnitPreferences, since it cannot be converted.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ hiber.value.Value.Numeric.BatteryLevel.Unit](#hibervaluevaluenumericbatterylevelunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.BatteryLevel.Unit](#hibervaluevaluenumericbatterylevelunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Distance

The value is a distance value, converted to your preferred distance unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ hiber.value.Value.Numeric.Distance.Unit](#hibervaluevaluenumericdistanceunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Distance.Unit](#hibervaluevaluenumericdistanceunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Flow



| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ hiber.value.Value.Numeric.Flow.Unit](#hibervaluevaluenumericflowunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Flow.Unit](#hibervaluevaluenumericflowunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.FuelEfficiency

The value is a distance value, converted to your preferred distance unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ hiber.value.Value.Numeric.FuelEfficiency.Unit](#hibervaluevaluenumericfuelefficiencyunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.FuelEfficiency.Unit](#hibervaluevaluenumericfuelefficiencyunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Mass

The value is a volume value, converted to your preferred volume unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ hiber.value.Value.Numeric.Mass.Unit](#hibervaluevaluenumericmassunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Mass.Unit](#hibervaluevaluenumericmassunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Percentage

The value is a percentage.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ float](#float) | none |
| unit | [ hiber.value.Value.Numeric.Percentage.Unit](#hibervaluevaluenumericpercentageunit) | none |
| textual | [ string](#string) | Textual representation with % symbol, rounded based on the user preferences and field config. |

### hiber.value.Value.Numeric.Pressure

The value is a pressure value, converted to your preferred pressure unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ hiber.value.Value.Numeric.Pressure.Unit](#hibervaluevaluenumericpressureunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Pressure.Unit](#hibervaluevaluenumericpressureunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Speed

The value is a speed value, converted to your preferred speed unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ hiber.value.Value.Numeric.Speed.Unit](#hibervaluevaluenumericspeedunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Speed.Unit](#hibervaluevaluenumericspeedunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Temperature

The value is a temperature, converted to your preferred temperature unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ hiber.value.Value.Numeric.Temperature.Unit](#hibervaluevaluenumerictemperatureunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Temperature.Unit](#hibervaluevaluenumerictemperatureunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Voltage

The value is a voltage, converted to your preferred voltage unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ hiber.value.Value.Numeric.Voltage.Unit](#hibervaluevaluenumericvoltageunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Voltage.Unit](#hibervaluevaluenumericvoltageunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Volume

The value is a volume value, converted to your preferred volume unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ hiber.value.Value.Numeric.Volume.Unit](#hibervaluevaluenumericvolumeunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Volume.Unit](#hibervaluevaluenumericvolumeunit) | The original unit, iff this value was converted from another unit because of user preferences. |


### Enums
#### hiber.value.Value.Numeric.BatteryLevel.Unit
other units will be added here later, like voltage

| Name | Description | Number |
| ---- | ----------- | ------ |
| PERCENT | Battery level as a percentage (technically not a unit). | 0 |

#### hiber.value.Value.Numeric.Distance.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| METER | none | 0 |
| MILLIMETER | none | 1 |
| CENTIMETER | none | 2 |
| KILOMETER | none | 3 |
| YARD | none | 5 |
| MILE | none | 4 |
| FOOT | none | 6 |
| INCH | none | 7 |
| NAUTICAL_MILE | This is a special case unit and may not be auto-converted to your UnitPreference. | 8 |

#### hiber.value.Value.Numeric.DurationUnit
The duration enum is not wrapped in Duration, since duration is always returned as a normalize Duration.
This unit is still used for fields, however.

| Name | Description | Number |
| ---- | ----------- | ------ |
| MILLISECONDS | none | 0 |
| SECONDS | none | 1 |
| MINUTES | none | 2 |
| HOURS | none | 3 |
| DAYS | none | 4 |
| WEEKS | none | 5 |

#### hiber.value.Value.Numeric.Flow.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| CUBIC_METER_PER_HOUR | none | 0 |

#### hiber.value.Value.Numeric.FuelEfficiency.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| LITER_PER_100_KILOMETER | none | 0 |
| KILOMETER_PER_LITER | none | 1 |
| KILOMETER_PER_GALLON | none | 2 |
| KILOMETER_PER_IMPERIAL_GALLON | none | 3 |
| MILE_PER_GALLON | none | 4 |
| MILE_PER_IMPERIAL_GALLON | none | 5 |
| MILE_PER_LITER | none | 6 |

#### hiber.value.Value.Numeric.Mass.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| KILOGRAMS | none | 0 |
| POUNDS | none | 1 |

#### hiber.value.Value.Numeric.Percentage.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| PERCENT | Technically not a unit, but for consistency, we've added it here. | 0 |

#### hiber.value.Value.Numeric.Pressure.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| BAR | none | 0 |
| PSI | none | 1 |
| K_PA | none | 2 |

#### hiber.value.Value.Numeric.Speed.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| KILOMETERS_PER_HOUR | none | 0 |
| KNOTS | This is a special case unit and may not be auto-converted to your UnitPreference. | 1 |
| METERS_PER_SECOND | none | 2 |
| MILES_PER_HOUR | none | 3 |

#### hiber.value.Value.Numeric.Temperature.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| KELVIN | none | 0 |
| DEGREES_CELSIUS | none | 1 |
| DEGREES_FAHRENHEIT | none | 2 |

#### hiber.value.Value.Numeric.Type
The type of numeric value that is represented.
Supported types will automatically convert to the preferred unit (based on the user settings).

| Name | Description | Number |
| ---- | ----------- | ------ |
| TYPE_UNKNOWN | none | 0 |
| PERCENTAGE | none | 1 |
| TEMPERATURE | none | 2 |
| DISTANCE | none | 3 |
| PRESSURE | none | 4 |
| VOLTAGE | none | 5 |
| SPEED | none | 6 |
| VOLUME | none | 7 |
| DURATION | none | 8 |
| FUEL_EFFICIENCY | none | 9 |
| MASS | none | 10 |
| BATTERY_LEVEL | none | 11 |
| FLOW | none | 12 |

#### hiber.value.Value.Numeric.Voltage.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| MILLIVOLT | none | 0 |

#### hiber.value.Value.Numeric.Volume.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| LITER | none | 0 |
| GALLON_US | none | 1 |
| GALLON_IMPERIAL | none | 2 |
| CUBIC_METER | none | 3 |
| CUBIC_FEET | none | 4 |

#### hiber.value.Value.Type
The type of value that is represented.

| Name | Description | Number |
| ---- | ----------- | ------ |
| OTHER | none | 0 |
| NUMERIC | This field contains numeric values, with an optional unit of measurement defined below. | 1 |
| TEXT | This field contains text to be displayed. | 2 |
| ENUM | This field switches between several predefined values. Typically used for status fields. | 3 |

#### hiber.value.ValueAggregation
Get the values for the selected field.

There are a few limitations here:
- text fields can only use the LAST aggregation.
- enum fields support a subset of aggregations:
  - DEFAULT and LAST return the last value.
  - MINIMUM and MAXIMUM return the lowest or highest value (respectively) based on the enum value order.
  - AVERAGE and SUM are not supported.

- enum duration

An enum example:
Field "status" with this timeline: 00:00 OK, 00:10 FAILED, 00:20 OK, 00:25 FAILED, 00:40 OK
- aggregation DEFAULT or LAST: OK, since it's OK at the end of the time range.
- aggregation SUM: OK: 35m, FAILED: 25m

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | none | 0 |
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

