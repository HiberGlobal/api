# value.proto



#### This file was generated from [value.proto](https://github.com/HiberGlobal/api/blob/master/value.proto).

## Table of Contents

- Services
  - [UnitPreferencesService](#unitpreferencesservice)

- Messages
  - [Field](#field)
  - [Field.Numeric](#fieldnumeric)
  - [Field.Numeric.Format](#fieldnumericformat)
  - [UnitPreferences](#unitpreferences)
  - [UnitPreferences.DistancePreference](#unitpreferencesdistancepreference)
  - [UnitPreferences.FuelEfficiencyPreference](#unitpreferencesfuelefficiencypreference)
  - [UnitPreferences.PercentagePreference](#unitpreferencespercentagepreference)
  - [UnitPreferences.PressurePreference](#unitpreferencespressurepreference)
  - [UnitPreferences.Request](#unitpreferencesrequest)
  - [UnitPreferences.Response](#unitpreferencesresponse)
  - [UnitPreferences.SpeedPreference](#unitpreferencesspeedpreference)
  - [UnitPreferences.TemperaturePreference](#unitpreferencestemperaturepreference)
  - [UnitPreferences.VoltagePreference](#unitpreferencesvoltagepreference)
  - [UnitPreferences.VolumePreference](#unitpreferencesvolumepreference)
  - [UnitPreferences.WeightPreference](#unitpreferencesweightpreference)
  - [Value](#value)
  - [Value.Numeric](#valuenumeric)
  - [Value.Numeric.BatteryLevel](#valuenumericbatterylevel)
  - [Value.Numeric.Distance](#valuenumericdistance)
  - [Value.Numeric.Flow](#valuenumericflow)
  - [Value.Numeric.FuelEfficiency](#valuenumericfuelefficiency)
  - [Value.Numeric.Percentage](#valuenumericpercentage)
  - [Value.Numeric.Pressure](#valuenumericpressure)
  - [Value.Numeric.Speed](#valuenumericspeed)
  - [Value.Numeric.Temperature](#valuenumerictemperature)
  - [Value.Numeric.Voltage](#valuenumericvoltage)
  - [Value.Numeric.Volume](#valuenumericvolume)
  - [Value.Numeric.Weight](#valuenumericweight)

- Enums
  - [Field.Numeric.Format.RoundingMode](#fieldnumericformatroundingmode)
  - [UnitPreferences.UnitCategory](#unitpreferencesunitcategory)
  - [Value.Numeric.BatteryLevel.Unit](#valuenumericbatterylevelunit)
  - [Value.Numeric.Distance.Unit](#valuenumericdistanceunit)
  - [Value.Numeric.DurationUnit](#valuenumericdurationunit)
  - [Value.Numeric.Flow.Unit](#valuenumericflowunit)
  - [Value.Numeric.FuelEfficiency.Unit](#valuenumericfuelefficiencyunit)
  - [Value.Numeric.Pressure.Unit](#valuenumericpressureunit)
  - [Value.Numeric.Speed.Unit](#valuenumericspeedunit)
  - [Value.Numeric.Temperature.Unit](#valuenumerictemperatureunit)
  - [Value.Numeric.Type](#valuenumerictype)
  - [Value.Numeric.Voltage.Unit](#valuenumericvoltageunit)
  - [Value.Numeric.Volume.Unit](#valuenumericvolumeunit)
  - [Value.Numeric.Weight.Unit](#valuenumericweightunit)
  - [Value.Type](#valuetype)

- Referenced messages from [base.proto](#referenced-messages-from-baseproto)
  - [hiber.Area](#hiberarea)
  - [hiber.Avatar](#hiberavatar)
  - [hiber.BytesOrHex](#hiberbytesorhex)
  - [hiber.BytesOrHex.Update](#hiberbytesorhexupdate)
  - [hiber.Date](#hiberdate)
  - [hiber.DoubleRange](#hiberdoublerange)
  - [hiber.Duration](#hiberduration)
  - [hiber.Filter](#hiberfilter)
  - [hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations)
  - [hiber.Filter.ChildOrganizations.Update](#hiberfilterchildorganizationsupdate)
  - [hiber.Filter.Events](#hiberfilterevents)
  - [hiber.Filter.Events.Update](#hiberfiltereventsupdate)
  - [hiber.Filter.Modems](#hiberfiltermodems)
  - [hiber.Filter.Modems.Update](#hiberfiltermodemsupdate)
  - [hiber.Filter.OrganizationPermissions](#hiberfilterorganizationpermissions)
  - [hiber.Filter.Organizations](#hiberfilterorganizations)
  - [hiber.Filter.Publishers](#hiberfilterpublishers)
  - [hiber.Filter.Tags](#hiberfiltertags)
  - [hiber.Filter.Tags.Update](#hiberfiltertagsupdate)
  - [hiber.Filter.UserPermissions](#hiberfilteruserpermissions)
  - [hiber.Filter.Users](#hiberfilterusers)
  - [hiber.Filter.Webhooks](#hiberfilterwebhooks)
  - [hiber.Location](#hiberlocation)
  - [hiber.LocationSelection](#hiberlocationselection)
  - [hiber.NamedFile](#hibernamedfile)
  - [hiber.Pagination](#hiberpagination)
  - [hiber.Pagination.Result](#hiberpaginationresult)
  - [hiber.Shape](#hibershape)
  - [hiber.TimeRange](#hibertimerange)
  - [hiber.Timestamp](#hibertimestamp)
  - [hiber.UpdateBoolean](#hiberupdateboolean)
  - [hiber.UpdateClearableString](#hiberupdateclearablestring)
  - [hiber.UpdateOptionalDuration](#hiberupdateoptionalduration)
  - [hiber.UpdateOptionalId](#hiberupdateoptionalid)
  - [hiber.UpdateZeroableInt](#hiberupdatezeroableint)
  - Enums
    - [hiber.EventType](#hibereventtype)
    - [hiber.Health](#hiberhealth)
    - [hiber.UnitOfMeasurement](#hiberunitofmeasurement)

- [Scalar Value Types](#scalar-value-types)


## UnitPreferencesService


### UnitPreferences
> **rpc** UnitPreferences([UnitPreferences.Request](#unitpreferencesrequest))
    [UnitPreferences.Response](#unitpreferencesresponse)




## Messages

### Field



| Field | Type | Description |
| ----- | ---- | ----------- |
| field | [ string](#string) | The name of the field (if in the root structure) or a JsonPath to the field. |
| display_name | [ string](#string) | An optional display name for the field. |
| priority | [ int32](#int32) | Priority of the field, typically used for ordering. |
| type | [ Value.Type](#valuetype) | The type of value the field contains. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **details**.numeric | [ Field.Numeric](#fieldnumeric) | none |
| encrypted | [ bool](#bool) | Whether this field should be stored encrypted or not. If it is, some processing options may be unavailable or slower. |
| unit_of_measurement | [ UnitOfMeasurement](#unitofmeasurement) | If numeric, the unit of the field. Deprecated: use numeric.numeric_unit oneof instead |
| unit_symbol | [ string](#string) | The symbol for the unit. Deprecated: use numeric.symbol instead |

### Field.Numeric

If the field is numeric, this specifies the details for the field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ Value.Numeric.Type](#valuenumerictype) | The type of numeric value. |
| symbol | [ string](#string) | The symbol to use for the field's unit. |
| format | [ Field.Numeric.Format](#fieldnumericformat) | How to format the values (number of decimals, rounding, etc.). |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **numeric_unit**.battery_level_unit | [ Value.Numeric.BatteryLevel.Unit](#valuenumericbatterylevelunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **numeric_unit**.distance_unit | [ Value.Numeric.Distance.Unit](#valuenumericdistanceunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **numeric_unit**.duration_unit | [ Value.Numeric.DurationUnit](#valuenumericdurationunit) | The duration unit the field is in. Note that duration is mapped to a normalized Duration object for convenience, so the unit is only used to convert from the field value to Duration. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **numeric_unit**.fuel_efficiency_unit | [ Value.Numeric.FuelEfficiency.Unit](#valuenumericfuelefficiencyunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **numeric_unit**.pressure_unit | [ Value.Numeric.Pressure.Unit](#valuenumericpressureunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **numeric_unit**.speed_unit | [ Value.Numeric.Speed.Unit](#valuenumericspeedunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **numeric_unit**.temperature_unit | [ Value.Numeric.Temperature.Unit](#valuenumerictemperatureunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **numeric_unit**.voltage_unit | [ Value.Numeric.Voltage.Unit](#valuenumericvoltageunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **numeric_unit**.volume_unit | [ Value.Numeric.Volume.Unit](#valuenumericvolumeunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **numeric_unit**.weight_unit | [ Value.Numeric.Weight.Unit](#valuenumericweightunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **numeric_unit**.flow_unit | [ Value.Numeric.Flow.Unit](#valuenumericflowunit) | none |

### Field.Numeric.Format

Formatting options for the field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **round**.round_to_integer | [ bool](#bool) | Round to an integer. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **round**.round_to_scale | [ uint32](#uint32) | Round to a number of decimals (at least 1). |
| rounding_mode | [ Field.Numeric.Format.RoundingMode](#fieldnumericformatroundingmode) | How to round the value when scale is applied. |

### UnitPreferences

The preferred units for the current user.

| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **distance**.distance_preference | [ UnitPreferences.DistancePreference](#unitpreferencesdistancepreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **distance**.no_distance_preference | [ bool](#bool) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **fuel_efficiency**.fuel_efficiency_preference | [ UnitPreferences.FuelEfficiencyPreference](#unitpreferencesfuelefficiencypreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **fuel_efficiency**.no_fuel_efficiency_preference | [ bool](#bool) | none |
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
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **weight**.weight_preference | [ UnitPreferences.WeightPreference](#unitpreferencesweightpreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **weight**.no_weight_preference | [ bool](#bool) | none |

### UnitPreferences.DistancePreference

User preferences for distance values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit_category | [ UnitPreferences.UnitCategory](#unitpreferencesunitcategory) | Unit category (metric / imperial) to convert distance values to. |
| format | [ Field.Numeric.Format](#fieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.FuelEfficiencyPreference

User preferences for fuel efficiency values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ Value.Numeric.FuelEfficiency.Unit](#valuenumericfuelefficiencyunit) | none |
| format | [ Field.Numeric.Format](#fieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.PercentagePreference

User preferences for percentage values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| format | [ Field.Numeric.Format](#fieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.PressurePreference

User preferences for pressure values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ Value.Numeric.Pressure.Unit](#valuenumericpressureunit) | none |
| format | [ Field.Numeric.Format](#fieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **distance**.update_distance_preference | [ UnitPreferences.DistancePreference](#unitpreferencesdistancepreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **distance**.remove_distance_preference | [ bool](#bool) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **fuel_efficiency**.update_fuel_efficiency_preference | [ UnitPreferences.FuelEfficiencyPreference](#unitpreferencesfuelefficiencypreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **fuel_efficiency**.remove_fuel_efficiency_preference | [ bool](#bool) | none |
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
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **weight**.update_weight_preference | [ UnitPreferences.WeightPreference](#unitpreferencesweightpreference) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **weight**.remove_weight_preference | [ bool](#bool) | none |

### UnitPreferences.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| preferences | [ UnitPreferences](#unitpreferences) | none |

### UnitPreferences.SpeedPreference

User preferences for speed values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit_category | [ UnitPreferences.UnitCategory](#unitpreferencesunitcategory) | Unit category (metric / imperial) to convert speed values to. |
| format | [ Field.Numeric.Format](#fieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.TemperaturePreference

User preferences for temperature values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ Value.Numeric.Temperature.Unit](#valuenumerictemperatureunit) | none |
| format | [ Field.Numeric.Format](#fieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.VoltagePreference

User preferences for voltage values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ Value.Numeric.Voltage.Unit](#valuenumericvoltageunit) | none |
| format | [ Field.Numeric.Format](#fieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.VolumePreference

User preferences for volume values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit_category | [ UnitPreferences.UnitCategory](#unitpreferencesunitcategory) | Unit category (metric / imperial) to convert volume values to. |
| format | [ Field.Numeric.Format](#fieldnumericformat) | Optional formatting options for values (rounding, etc). |

### UnitPreferences.WeightPreference

User preferences for weight values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit_category | [ UnitPreferences.UnitCategory](#unitpreferencesunitcategory) | Unit category (metric / imperial) to convert weight values to. |
| format | [ Field.Numeric.Format](#fieldnumericformat) | Optional formatting options for values (rounding, etc). |

### Value



| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ Value.Type](#valuetype) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.numeric | [ Value.Numeric](#valuenumeric) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.text | [ string](#string) | none |

### Value.Numeric



| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ Value.Numeric.Type](#valuenumerictype) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.battery_level | [ Value.Numeric.BatteryLevel](#valuenumericbatterylevel) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.distance | [ Value.Numeric.Distance](#valuenumericdistance) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.duration | [ Duration](#duration) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.percentage | [ Value.Numeric.Percentage](#valuenumericpercentage) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.pressure | [ Value.Numeric.Pressure](#valuenumericpressure) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.speed | [ Value.Numeric.Speed](#valuenumericspeed) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.temperature | [ Value.Numeric.Temperature](#valuenumerictemperature) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.voltage | [ Value.Numeric.Voltage](#valuenumericvoltage) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.volume | [ Value.Numeric.Volume](#valuenumericvolume) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.flow | [ Value.Numeric.Flow](#valuenumericflow) | none |

### Value.Numeric.BatteryLevel

Special case for battery level, since it can be provided in many units.
Not included in the UnitPreferences, since it cannot be converted.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ Value.Numeric.BatteryLevel.Unit](#valuenumericbatterylevelunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ Value.Numeric.BatteryLevel.Unit](#valuenumericbatterylevelunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### Value.Numeric.Distance

The value is a distance value, converted to your preferred distance unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ Value.Numeric.Distance.Unit](#valuenumericdistanceunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ Value.Numeric.Distance.Unit](#valuenumericdistanceunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### Value.Numeric.Flow



| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ Value.Numeric.Flow.Unit](#valuenumericflowunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ Value.Numeric.Flow.Unit](#valuenumericflowunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### Value.Numeric.FuelEfficiency

The value is a distance value, converted to your preferred distance unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ Value.Numeric.FuelEfficiency.Unit](#valuenumericfuelefficiencyunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ Value.Numeric.FuelEfficiency.Unit](#valuenumericfuelefficiencyunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### Value.Numeric.Percentage

The value is a percentage.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ float](#float) | none |
| textual | [ string](#string) | Textual representation with % symbol, rounded based on the user preferences and field config. |

### Value.Numeric.Pressure

The value is a pressure value, converted to your preferred pressure unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ Value.Numeric.Pressure.Unit](#valuenumericpressureunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ Value.Numeric.Pressure.Unit](#valuenumericpressureunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### Value.Numeric.Speed

The value is a speed value, converted to your preferred speed unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ Value.Numeric.Speed.Unit](#valuenumericspeedunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ Value.Numeric.Speed.Unit](#valuenumericspeedunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### Value.Numeric.Temperature

The value is a temperature, converted to your preferred temperature unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ Value.Numeric.Temperature.Unit](#valuenumerictemperatureunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ Value.Numeric.Temperature.Unit](#valuenumerictemperatureunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### Value.Numeric.Voltage

The value is a voltage, converted to your preferred voltage unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ Value.Numeric.Voltage.Unit](#valuenumericvoltageunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ Value.Numeric.Voltage.Unit](#valuenumericvoltageunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### Value.Numeric.Volume

The value is a volume value, converted to your preferred volume unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ Value.Numeric.Volume.Unit](#valuenumericvolumeunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ Value.Numeric.Volume.Unit](#valuenumericvolumeunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### Value.Numeric.Weight

The value is a volume value, converted to your preferred volume unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ Value.Numeric.Weight.Unit](#valuenumericweightunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ Value.Numeric.Weight.Unit](#valuenumericweightunit) | The original unit, iff this value was converted from another unit because of user preferences. |


## Enums
### Field.Numeric.Format.RoundingMode
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

### UnitPreferences.UnitCategory


| Name | Description | Number |
| ---- | ----------- | ------ |
| METRIC | none | 0 |
| IMPERIAL | none | 1 |

### Value.Numeric.BatteryLevel.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| PERCENT | Battery level as a percentage (technically not a unit).

other units will be added here later, like voltage | 0 |

### Value.Numeric.Distance.Unit


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

### Value.Numeric.DurationUnit
The duration enum is not wrapped in Duration, since duration is always returned as a normalize Duration.
This unit is still used for fields, however.

| Name | Description | Number |
| ---- | ----------- | ------ |
| MILLISECONDS | none | 0 |
| SECONDS | none | 1 |
| MINUTES | none | 2 |
| HOURS | none | 3 |
| DAYS | none | 4 |

### Value.Numeric.Flow.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| CUBIC_METER_PER_HOUR | none | 0 |

### Value.Numeric.FuelEfficiency.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| LITER_PER_100_KILOMETER | none | 0 |
| KILOMETER_PER_LITER | none | 1 |
| KILOMETER_PER_GALLON | none | 2 |
| KILOMETER_PER_IMPERIAL_GALLON | none | 3 |
| MILE_PER_GALLON | none | 4 |
| MILE_PER_IMPERIAL_GALLON | none | 5 |
| MILE_PER_LITER | none | 6 |

### Value.Numeric.Pressure.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| BAR | none | 0 |
| PSI | none | 1 |
| K_PA | none | 2 |

### Value.Numeric.Speed.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| KILOMETERS_PER_HOUR | none | 0 |
| KNOTS | This is a special case unit and may not be auto-converted to your UnitPreference. | 1 |
| METERS_PER_SECOND | none | 2 |
| MILES_PER_HOUR | none | 3 |

### Value.Numeric.Temperature.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| KELVIN | none | 0 |
| DEGREES_CELSIUS | none | 1 |
| DEGREES_FAHRENHEIT | none | 2 |

### Value.Numeric.Type
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
| WEIGHT | none | 10 |
| BATTERY_LEVEL | none | 11 |
| FLOW | none | 12 |

### Value.Numeric.Voltage.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| MILLIVOLT | none | 0 |

### Value.Numeric.Volume.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| LITER | none | 0 |
| GALLON_US | none | 1 |
| GALLON_IMPERIAL | none | 2 |

### Value.Numeric.Weight.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| KILOGRAMS | none | 0 |
| POUNDS | none | 1 |

### Value.Type
The type of value that is represented.

| Name | Description | Number |
| ---- | ----------- | ------ |
| OTHER | none | 0 |
| NUMERIC | This field contains numeric values, with an optional unit of measurement defined below. | 1 |
| TEXT | This field contains text to be displayed. | 2 |



## Referenced messages from base.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [base.proto](https://github.com/HiberGlobal/api/blob/master/base.proto).


### hiber.Area

Rectangular area between two locations, normalized to bottom-left and top-right points.

Center point is added for convenience; it's simple the point directly between the two corner points.
When sending an Area to the api, the center location is ignored.

| Field | Type | Description |
| ----- | ---- | ----------- |
| center | [ hiber.Location](#hiberlocation) | none |
| bottom_left | [ hiber.Location](#hiberlocation) | none |
| top_right | [ hiber.Location](#hiberlocation) | none |
| textual | [ string](#string) | Text representation. Can be used as an alternative input in a request, filled in by the API in responses. |

### hiber.Avatar

An avatar is represented either by a (publicly) fetchable URL that serves an image,
xor a binary payload that knows its name and mime-type.

If it is a url, it must be obtainable without credentials, though this is not validated by the API.
Because the content behind URL's can change or become unavailable over time,
the client should make sure it properly caches the data fetched from the URL.
("Properly" means [among other things] respecting the response headers for this resource)

| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **url_or_image**.url | [ string](#string) | A URL that contains the location of avatar. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **url_or_image**.image | [ hiber.NamedFile](#hibernamedfile) | The data of the avatar as a Named File. |

### hiber.BytesOrHex

Some clients may prefer direct binary data, while other prefer a hexadecimal string,
both for input and output. To support both methods, this object is used to represent binary data.

When you receive this from the api, both fields are set. When sending it to the api, only one field is required.

| Field | Type | Description |
| ----- | ---- | ----------- |
| bytes | [ bytes](#bytes) | none |
| hex | [ string](#string) | none |

### hiber.BytesOrHex.Update



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ hiber.BytesOrHex](#hiberbytesorhex) | none |

### hiber.Date

Date type for convenience.

Some clients are better at parsing year, month and day of month as separate fields,
while others prefer a text-based format.
To accommodate this, this Date type supports both.

When used as API output, both the int fields and textual fields will be set.
The textual field has the commonly used ISO 8601 local date format (i.e. "2018-01-01").
When used an API input, either specify the int fields or the textual field.
If both are specified, the textual field will be discarded.

| Field | Type | Description |
| ----- | ---- | ----------- |
| year | [ uint32](#uint32) | none |
| month | [ uint32](#uint32) | none |
| day | [ uint32](#uint32) | none |
| textual | [ string](#string) | none |

### hiber.DoubleRange

Decimal range.

| Field | Type | Description |
| ----- | ---- | ----------- |
| start | [ double](#double) | none |
| end | [ double](#double) | none |

### hiber.Duration



| Field | Type | Description |
| ----- | ---- | ----------- |
| duration | [ google.protobuf.Duration](#googleprotobufduration) | none |
| textual | [ string](#string) | none |

### hiber.Filter

Filters used in many api calls to filter the data sources, results, etc.

"Include" fields filter out anything not in the include set.
When not set, all items will be returned (except excluded items)

"Exclude" fields filter out anything in the exclude set.
When combined with include, exclude takes precedence when determining whether an item is filtered


### hiber.Filter.ChildOrganizations

Specify which organizations to get data from. By default, data is only retrieved for the current organization, but
using ChildOrganizations we can specify to include a number of, or all, sub-organizations.

Note: ChildOrganization differs from other filters in that it defaults to not allowing anything, where the
other filters default to allowing everything

| Field | Type | Description |
| ----- | ---- | ----------- |
| include_all | [ bool](#bool) | none |
| include | [repeated string](#string) | none |
| exclude | [repeated string](#string) | none |

### hiber.Filter.ChildOrganizations.Update

Update object to update a Filter.ChildOrganizations field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | none |

### hiber.Filter.Events



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated hiber.EventType](#hibereventtype) | none |
| exclude | [repeated hiber.EventType](#hibereventtype) | none |

### hiber.Filter.Events.Update

Update object to update a Filter.Events field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ hiber.Filter.Events](#hiberfilterevents) | none |

### hiber.Filter.Modems



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) | Include all modems with these modem numbers (HEX) |
| exclude | [repeated string](#string) | Exclude all modems with these modem numbers (HEX). Exclude takes precedence over include. |

### hiber.Filter.Modems.Update

Update object to update a Filter.Modems field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ hiber.Filter.Modems](#hiberfiltermodems) | none |

### hiber.Filter.OrganizationPermissions



| Field | Type | Description |
| ----- | ---- | ----------- |
| include_all | [ bool](#bool) | none |
| include | [repeated hiber.OrganizationPermission](#hiberorganizationpermission) | none |
| exclude | [repeated hiber.OrganizationPermission](#hiberorganizationpermission) | none |

### hiber.Filter.Organizations



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) | none |
| exclude | [repeated string](#string) | none |

### hiber.Filter.Publishers



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated int64](#int64) | none |
| exclude | [repeated int64](#int64) | none |
| only_active | [ bool](#bool) | none |

### hiber.Filter.Tags



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated int64](#int64) | none |
| exclude | [repeated int64](#int64) | none |

### hiber.Filter.Tags.Update

Update object to update a Filter.Tags field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ hiber.Filter.Tags](#hiberfiltertags) | none |

### hiber.Filter.UserPermissions



| Field | Type | Description |
| ----- | ---- | ----------- |
| include_all | [ bool](#bool) | none |
| include | [repeated hiber.UserPermission](#hiberuserpermission) | none |
| exclude | [repeated hiber.UserPermission](#hiberuserpermission) | none |

### hiber.Filter.Users



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) | none |
| exclude | [repeated string](#string) | none |

### hiber.Filter.Webhooks



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated int64](#int64) | none |
| exclude | [repeated int64](#int64) | none |
| only_active | [ bool](#bool) | none |

### hiber.Location

Geographic latitude and longitude coordinates specified in decimal degrees.
For more information, see the WGS-84 coordinate system, which is used for most GPS systems.

| Field | Type | Description |
| ----- | ---- | ----------- |
| latitude | [ double](#double) | Decimal degrees north. |
| longitude | [ double](#double) | Decimal degrees east. |
| textual | [ string](#string) | Text representation. Can be used as an alternative input in a request, filled in by the API in responses. |

### hiber.LocationSelection

Selection object for map data. Filter modems on the map by id, (child)organization.

Also, filter the map data by level and area restriction, to only display a small area at a detailed map level,
for example

| Field | Type | Description |
| ----- | ---- | ----------- |
| areas | [repeated hiber.Area](#hiberarea) | Rectangular areas, each defined by two locations, normalized to bottom-left and top-right points. |
| shapes | [repeated hiber.Shape](#hibershape) | Polygon shapes, each defined by a list of locations, which draw a shape on the map. |

### hiber.NamedFile

A NamedFile contains bytes with its mime-type and name.
It can represent any file of any type.

Note that depending on where in the API this is used,
the server might put restrictions on file size, media-type or name length.

The file name should be interpreted as-is.
No hierarchical information is stored in the name, nor should you look at the "extension" to know its media-type.
It might not even have a file extension.
The file name may contain characters that cannot be a valid file name on certain systems.

Specific API calls may pur restrictions on the name or size of the file.

When showing this as an image in a browser, one can make use of a `data` URI.
The client must convert the bytes to base64 and can then construct a data URI like this

    data:<media-type>;base64,<base64-encoded-bytes>

Other type clients should be able to sort-of-directly set the data bytes as the source for an image.

| Field | Type | Description |
| ----- | ---- | ----------- |
| data | [ hiber.BytesOrHex](#hiberbytesorhex) | The binary payload that represents the file |
| media_type | [ string](#string) | The media-type of the file, as defined by RFC 6838 or its extensions |
| name | [ string](#string) | A semantic name for this file. |

### hiber.Pagination

Pagination is normalized across the api. Provide a pagination object to get a specific page or offset,
or limit your data.

Calls that have a pagination option automatically return a Pagination.Result, which contains
either the specified pagination options or the defaults, as well as total counts. It also contains Pagination
objects that can be used for the previous and next page.

This effectively means that an api user would never need to create their own pagination object; as long as they
start at the first page and continue to the next, they can use the provided Pagination object.

| Field | Type | Description |
| ----- | ---- | ----------- |
| size | [ int32](#int32) | none |
| page | [ int32](#int32) | none |

### hiber.Pagination.Result



| Field | Type | Description |
| ----- | ---- | ----------- |
| size | [ int32](#int32) | none |
| page | [ int32](#int32) | none |
| total | [ int32](#int32) | none |
| total_pages | [ int32](#int32) | none |
| previous | [ hiber.Pagination](#hiberpagination) | none |
| next | [ hiber.Pagination](#hiberpagination) | none |
| approximated_total | [ bool](#bool) | Indicates that the total is an approximation, and not an exact value. This can be set for data that changes often, or is generally only fetched in an infinite scrolling manner. For example, unbundled events are likely to return an approximated total, but not guaranteed to do so. |

### hiber.Shape

Polygon shape defined by a list of locations, which draw a shape on the map.
The last point is connected to the first to close the shape.

For example, the outline of a city would be defined using a Shape,
while a rectangular region is easier to define using Area.

| Field | Type | Description |
| ----- | ---- | ----------- |
| path | [repeated hiber.Location](#hiberlocation) | none |
| textual | [ string](#string) | Text representation. Can be used as an alternative input in a request, filled in by the API in responses. |

### hiber.TimeRange

Period of time between two timestamps. Typically used for filtering.

| Field | Type | Description |
| ----- | ---- | ----------- |
| start | [ hiber.Timestamp](#hibertimestamp) | none |
| end | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.Timestamp

Timestamp type for convenience.

Some clients are better at parsing Google's seconds/nanos based timestamp, while others prefer a text-based format.
To accommodate this, this Timestamp type supports both.

When used as API output, both the timestamp and textual fields will be set. The textual field has the commonly
used ISO 8601 format (i.e. "2018-01-01T13:00:00Z").
When used an API input, only one of the fields is needed, there is no need to set both. When both are set, the
timestamp field will be used, the textual field will be discarded.

| Field | Type | Description |
| ----- | ---- | ----------- |
| timestamp | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | none |
| textual | [ string](#string) | none |

### hiber.UpdateBoolean

Update object for a boolean.

Since false is the default value, we need to distinguish between an omitted value and setting the value to false,
in an update object.

To use this to update, set a value and set updated to true

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ bool](#bool) | none |

### hiber.UpdateClearableString

Update object for a string that can be empty.

Since an empty string is also the default value, we need to distinguish between an omitted value and
setting the value to an empty string, in an update object.

To use this to update, set a value and set updated to true

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ string](#string) | none |

### hiber.UpdateOptionalDuration

Update object for an optional Duration.

To use this to update, set a value and set updated to true.
To clear the duration, set updated to true, but set no value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ hiber.Duration](#hiberduration) | none |

### hiber.UpdateOptionalId

Update object for an optional id.

To use this to update, set a value and set updated to true. To clear the id, set updated to true, but set no value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ int64](#int64) | none |

### hiber.UpdateZeroableInt

Update object for an int that can be set to 0.

Since 0 is also the default value, we need to distinguish between an omitted value and setting the value to 0,
in an update object.

To use this to update, set a value and set updated to true

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ uint32](#uint32) | none |


### Enums
#### hiber.EventType
Enum of api-accessible events.

The event types in this enum have a protobuf implementation, and can be used, for example, in the
api event stream and publishers.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | none | 0 |
| ORGANIZATION_CREATED | none | 34 |
| ORGANIZATION_UPDATED | none | 12 |
| ORGANIZATION_DELETED | none | 35 |
| ORGANIZATION_EVENT_CONFIGURATION_UPDATED | none | 43 |
| MODEM_CREATED | none | 55 |
| MODEM_UPDATED | none | 36 |
| MODEM_LOCATION_UPDATED | none | 4 |
| MODEM_ACTIVATED | none | 33 |
| MODEM_STALE | none | 16 |
| MODEM_MESSAGE_RECEIVED | none | 5 |
| MODEM_MESSAGE_BODY_PARSED | none | 39 |
| MODEM_MESSAGE_BODY_RECEIVED | none | 45 |
| MODEM_MESSAGE_DELAYED | none | 14 |
| MODEM_MESSAGE_CANNOT_BE_PARSED | none | 15 |
| MODEM_MESSAGE_SUMMARY | none | 42 |
| MODEM_MESSAGE_BODY_PARSER_CREATED | none | 46 |
| MODEM_MESSAGE_BODY_PARSER_UPDATED | none | 47 |
| MODEM_MESSAGE_BODY_PARSER_DELETED | none | 48 |
| MODEM_ALARM | none | 56 |
| MODEM_ALARM_CREATED | none | 57 |
| MODEM_ALARM_UPDATED | none | 58 |
| MODEM_ALARM_DELETED | none | 59 |
| ASSIGNED | none | 63 |
| UNASSIGNED | none | 64 |
| MODEM_TRANSFER_STARTED | none | 17 |
| MODEM_TRANSFER_RECEIVED | none | 18 |
| MODEM_TRANSFER_CANCELLED | none | 19 |
| MODEM_TRANSFER_NOT_RECEIVED | none | 20 |
| MODEM_TRANSFER_RETURN_TRANSFER_STARTED | none | 21 |
| MODEM_CLAIMED | none | 22 |
| PUBLISHER_CREATED | none | 1 |
| PUBLISHER_UPDATED | none | 2 |
| PUBLISHER_DELETED | none | 3 |
| PUBLISHER_AUTO_DISABLED | none | 37 |
| PUBLISHER_FAILED | none | 11 |
| USER_ACCESS_REQUEST | none | 8 |
| USER_INVITED | none | 38 |
| USER_ADDED | none | 9 |
| USER_REMOVED | none | 10 |
| USER_VALIDATION_UPDATED | none | 54 |
| TOKEN_CREATED | none | 31 |
| TOKEN_EXPIRY_WARNING | none | 25 |
| TOKEN_EXPIRED | none | 26 |
| TOKEN_DELETED | none | 32 |
| EXPORT_CREATED | none | 65 |
| EXPORT_READY | none | 66 |
| EXPORT_FAILED | none | 67 |

#### hiber.Health
Health is an indicator for issues. It is used for publishers to give a quick indication of issues.

| Name | Description | Number |
| ---- | ----------- | ------ |
| OK | none | 0 |
| WARNING | none | 1 |
| ERROR | none | 2 |

#### hiber.UnitOfMeasurement
Unit of measurement for a numeric value.

| Name | Description | Number |
| ---- | ----------- | ------ |
| UNIT_UNKNOWN | none | 0 |
| DURATION_SECONDS | none | 1 |
| DURATION_MINUTES | none | 2 |
| DURATION_HOURS | none | 3 |
| DURATION_DAYS | none | 4 |
| FUEL_EFFICIENCY_LITER_PER_100_KILOMETER | none | 30 |
| FUEL_EFFICIENCY_KILOMETER_PER_LITER | none | 31 |
| FUEL_EFFICIENCY_KILOMETER_PER_US_GALLON | none | 32 |
| FUEL_EFFICIENCY_KILOMETER_PER_IMPERIAL_GALLON | none | 33 |
| FUEL_EFFICIENCY_MILE_PER_US_GALLON | none | 34 |
| FUEL_EFFICIENCY_MILE_PER_IMPERIAL_GALLON | none | 35 |
| FUEL_EFFICIENCY_MILE_PER_LITER | none | 36 |
| DISTANCE_METER | none | 8 |
| DISTANCE_MILLIMETER | none | 9 |
| DISTANCE_CENTIMETER | none | 10 |
| DISTANCE_KILOMETER | none | 11 |
| DISTANCE_NAUTICAL_MILE | none | 26 |
| DISTANCE_MILE | none | 21 |
| DISTANCE_YARD | none | 27 |
| DISTANCE_FOOT | none | 28 |
| DISTANCE_INCH | none | 29 |
| PERCENT | none | 16 |
| PRESSURE_BAR | none | 12 |
| PRESSURE_PSI | none | 14 |
| PRESSURE_K_PA | none | 17 |
| SPEED_KILOMETERS_PER_HOUR | none | 18 |
| SPEED_KNOTS | none | 19 |
| SPEED_METERS_PER_SECOND | none | 20 |
| SPEED_MILES_PER_HOUR | none | 22 |
| TEMPERATURE_KELVIN | none | 5 |
| TEMPERATURE_DEGREES_CELSIUS | none | 6 |
| TEMPERATURE_DEGREES_FAHRENHEIT | none | 7 |
| VOLTAGE_MILLIVOLT | none | 15 |
| VOLUME_LITER | none | 23 |
| VOLUME_GALLON_US | none | 24 |
| VOLUME_GALLON_IMPERIAL | none | 25 |
| WEIGHT_KILOGRAMS | none | 37 |
| WEIGHT_POUNDS | none | 38 |
| FLOW_CUBIC_METERS_PER_HOUR | none | 39 |

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

