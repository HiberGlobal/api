# easypulse.proto

Easypulse specific view and services.

This file contains specific views and services for the easypulse feature set.
This feature set is only available to organizations with the easypulse feature enabled.

For Easypulse, we've introduced the concept of an Asset, which is a modem with some assumptions about the type of
data it sends. Additionally, aggregations can be requested of Asset history when requesting Assets, allowing for a
somewhat customized Asset model.

#### This file was generated from [easypulse.proto](https://github.com/HiberGlobal/api/blob/master/easypulse.proto).

## Table of Contents

- Services
  - [EasypulseService](#easypulseservice)

- Messages
  - [Easypulse](#easypulse)
  - [Easypulse.Asset](#easypulseasset)
  - [Easypulse.Asset.AggregationsEntry](#easypulseassetaggregationsentry)
  - [Easypulse.Asset.LastUpdate](#easypulseassetlastupdate)
  - [Easypulse.Asset.PeripheralsEntry](#easypulseassetperipheralsentry)
  - [Easypulse.AssetSelection](#easypulseassetselection)
  - [Easypulse.Fields](#easypulsefields)
  - [Easypulse.Fields.EasypulseField](#easypulsefieldseasypulsefield)
  - [Easypulse.Fields.PTOEngagement](#easypulsefieldsptoengagement)
  - [Easypulse.Fields.Request](#easypulsefieldsrequest)
  - [Easypulse.Fields.Response](#easypulsefieldsresponse)
  - [Easypulse.Fields.StateBasedFields](#easypulsefieldsstatebasedfields)
  - [Easypulse.History](#easypulsehistory)
  - [Easypulse.History.Request](#easypulsehistoryrequest)
  - [Easypulse.History.Response](#easypulsehistoryresponse)
  - [Easypulse.History.Response.Value](#easypulsehistoryresponsevalue)
  - [Easypulse.ListAssets](#easypulselistassets)
  - [Easypulse.ListAssets.Request](#easypulselistassetsrequest)
  - [Easypulse.ListAssets.Request.AggregationsEntry](#easypulselistassetsrequestaggregationsentry)
  - [Easypulse.ListAssets.Response](#easypulselistassetsresponse)
  - [Easypulse.TargetValues](#easypulsetargetvalues)
  - [Easypulse.TargetValues.DistanceTargetValue](#easypulsetargetvaluesdistancetargetvalue)
  - [Easypulse.TargetValues.DurationTargetValue](#easypulsetargetvaluesdurationtargetvalue)
  - [Easypulse.TargetValues.FuelEfficiencyTargetValue](#easypulsetargetvaluesfuelefficiencytargetvalue)
  - [Easypulse.TargetValues.List](#easypulsetargetvalueslist)
  - [Easypulse.TargetValues.List.Request](#easypulsetargetvalueslistrequest)
  - [Easypulse.TargetValues.List.Response](#easypulsetargetvalueslistresponse)
  - [Easypulse.TargetValues.SinarmasTargetValues](#easypulsetargetvaluessinarmastargetvalues)
  - [Easypulse.TargetValues.SinarmasTargetValues.TreeVolumeTargetValue](#easypulsetargetvaluessinarmastargetvaluestreevolumetargetvalue)
  - [Easypulse.TargetValues.SinarmasTargetValues.TreesTargetValue](#easypulsetargetvaluessinarmastargetvaluestreestargetvalue)
  - [Easypulse.TargetValues.Update](#easypulsetargetvaluesupdate)
  - [Easypulse.TargetValues.Update.Request](#easypulsetargetvaluesupdaterequest)
  - [Easypulse.TargetValues.VolumeTargetValue](#easypulsetargetvaluesvolumetargetvalue)
  - [Easypulse.TellTale](#easypulsetelltale)
  - [Easypulse.TellTale.Indicator](#easypulsetelltaleindicator)

- Enums
  - [Easypulse.EngineState](#easypulseenginestate)
  - [Easypulse.History.Request.Aggregation](#easypulsehistoryrequestaggregation)
  - [Easypulse.History.Request.Sort](#easypulsehistoryrequestsort)
  - [Easypulse.ListAssets.Request.Sort](#easypulselistassetsrequestsort)
  - [Easypulse.TellTale.Indicator.State](#easypulsetelltaleindicatorstate)

- Referenced messages from [health.proto](#referenced-messages-from-healthproto)
  - [hiber.health.HealthLevel](#hiberhealthhealthlevel)
  - [hiber.health.HealthLevelSelection](#hiberhealthhealthlevelselection)


- Referenced messages from [tag.proto](#referenced-messages-from-tagproto)
  - [hiber.tag.Tag](#hibertagtag)
  - [hiber.tag.Tag.Label](#hibertagtaglabel)
  - [hiber.tag.TagSelection](#hibertagtagselection)


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

- Referenced messages from [field.proto](#referenced-messages-from-fieldproto)
  - [hiber.field.Field](#hiberfieldfield)
  - [hiber.field.Field.Enum](#hiberfieldfieldenum)
  - [hiber.field.Field.Numeric](#hiberfieldfieldnumeric)
  - [hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat)
  - [hiber.field.Field.Numeric.Unit](#hiberfieldfieldnumericunit)

    - [hiber.field.Field.Numeric.Format.RoundingMode](#hiberfieldfieldnumericformatroundingmode)

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
  - [hiber.Filter.FieldEnumValues](#hiberfilterfieldenumvalues)
  - [hiber.Filter.Modems](#hiberfiltermodems)
  - [hiber.Filter.Modems.Update](#hiberfiltermodemsupdate)
  - [hiber.Filter.OrganizationPermissions](#hiberfilterorganizationpermissions)
  - [hiber.Filter.Organizations](#hiberfilterorganizations)
  - [hiber.Filter.Publishers](#hiberfilterpublishers)
  - [hiber.Filter.SupportPermissions](#hiberfiltersupportpermissions)
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


## EasypulseService
Service to list and manage Assets.

### Assets
> **rpc** Assets([Easypulse.ListAssets.Request](#easypulselistassetsrequest))
    [Easypulse.ListAssets.Response](#easypulselistassetsresponse)

List the Easypulse Assets in your organization.
Optionally, aggregated historical data can be added to the returned Assets, with a given name.

Fails when your organizations does not have the Easypulse feature.

### History
> **rpc** History([Easypulse.History.Request](#easypulsehistoryrequest))
    [Easypulse.History.Response](#easypulsehistoryresponse)

List the history for a single field, and optionally apply an aggregation and/or grouping to it.
Deprecated in favor of the ValueService.

### Fields
> **rpc** Fields([Easypulse.Fields.Request](#easypulsefieldsrequest))
    [Easypulse.Fields.Response](#easypulsefieldsresponse)

List the fields for Easypulse, so they can be used with other services.

### TargetValues
> **rpc** TargetValues([Easypulse.TargetValues.List.Request](#easypulsetargetvalueslistrequest))
    [Easypulse.TargetValues.List.Response](#easypulsetargetvalueslistresponse)

Manage the target values that are used to determine score values.

### UpdateTargetValues
> **rpc** UpdateTargetValues([Easypulse.TargetValues.Update.Request](#easypulsetargetvaluesupdaterequest))
    [Easypulse.TargetValues](#easypulsetargetvalues)




## Messages

### Easypulse




### Easypulse.Asset

Asset in your organization.
An asset is a view of a modem, with assumptions about message data fields handled in the API.

In addition, an Asset can be enriched with aggregations of the data fields when requested (for example,
fuel level average over the past month, or total run time in the past week).

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | The organization the asset is in. |
| number | [ string](#string) | The modem number for the Asset. |
| name | [ string](#string) | The custom name for the Asset, defaults to modem number. |
| external_identifier | [ string](#string) | Optional external identifier the Asset may have. |
| peripherals | [map Easypulse.Asset.PeripheralsEntry](#easypulseassetperipheralsentry) | A key value map of peripherals for the Assets. |
| notes | [ string](#string) | Add additional notes to an asset. |
| secure_notes | [ string](#string) | Add additional notes to an asset that only people with the permission can access. |
| time_zone | [ string](#string) | The timezone configured for the asset. |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | Health level based on the modem alarm and some always-present alarms. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | Tags (or groups, when used in Mission Control) this asset is in. |
| last_update | [ Easypulse.Asset.LastUpdate](#easypulseassetlastupdate) | When this asset was last updated. |
| odometer | [ hiber.value.Value.Numeric.Distance](#hibervaluevaluenumericdistance) | Current value of the odometer. |
| engine_runtime | [ hiber.Duration](#hiberduration) | Duration of total hours the engine has ran. |
| engine_idle_time | [ hiber.Duration](#hiberduration) | Duration of total hours the engine has idled. |
| fuel_used_running | [ hiber.value.Value.Numeric.Volume](#hibervaluevaluenumericvolume) | The total amount of fuel used by this vehicle. |
| fuel_used_idling | [ hiber.value.Value.Numeric.Volume](#hibervaluevaluenumericvolume) | The total amount of fuel used by this vehicle while idling. |
| power_take_off_engagement_count | [ int32](#int32) | The amount of times the power-take-off was engaged |
| power_take_off_engagement_duration | [ hiber.Duration](#hiberduration) | The duration the power-take-off was engaged for |
| engine_oil_temperature | [ hiber.value.Value.Numeric.Temperature](#hibervaluevaluenumerictemperature) | Engine temperature. |
| fuel_level | [ hiber.value.Value.Numeric.Percentage](#hibervaluevaluenumericpercentage) | The most recent fuel level. |
| temperature | [ hiber.value.Value.Numeric.Temperature](#hibervaluevaluenumerictemperature) | The most recent temperature in degrees Celsius. |
| speed | [ hiber.value.Value.Numeric.Speed](#hibervaluevaluenumericspeed) | The most recent speed measurement. |
| rpm | [ int32](#int32) | The most recent peak rpm measurement. |
| tire_pressure | [ hiber.value.Value.Numeric.Pressure](#hibervaluevaluenumericpressure) | The most recent tire pressure measurement. |
| battery_level | [ hiber.value.Value.Numeric.BatteryLevel](#hibervaluevaluenumericbatterylevel) | The most recent battery level. |
| location | [ hiber.Location](#hiberlocation) | The most recently reported location. |
| aggregations | [map Easypulse.Asset.AggregationsEntry](#easypulseassetaggregationsentry) | Any aggregations added when this asset was requested. |
| tell_tales | [repeated Easypulse.TellTale](#easypulsetelltale) | List of tell-tale status indicators. The order of the list is intentional. |

### Easypulse.Asset.AggregationsEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ Easypulse.History.Response](#easypulsehistoryresponse) | none |

### Easypulse.Asset.LastUpdate

Information about the last update we received from this asset.

| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ uint64](#uint64) | none |
| received_at | [ hiber.Timestamp](#hibertimestamp) | Time the server has received the last update. |
| sent_at | [ hiber.Timestamp](#hibertimestamp) | Time the asset sent the last update. |
| body | [ hiber.BytesOrHex](#hiberbytesorhex) | The body of the last update. |

### Easypulse.Asset.PeripheralsEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ string](#string) | none |

### Easypulse.AssetSelection

An AssetSelection is used to select which Assets should be affected:
- When listing Assets, it is used to determine which Assets are returned
- When updating Assets, it is used to determine which Assets are updated

| Field | Type | Description |
| ----- | ---- | ----------- |
| search | [ string](#string) | Search for assets by name, modem number, tag or notes. |
| assets | [ hiber.Filter.Modems](#hiberfiltermodems) | Select assets by modem number. |
| health_levels | [repeated string](#string) | Select assets by health level. |
| filter_by_tags | [ hiber.tag.TagSelection](#hibertagtagselection) | Select assets by tag. |

### Easypulse.Fields

List the fields for the easypulse organization, to be used with the value service, for example.

| Field | Type | Description |
| ----- | ---- | ----------- |
| odometer | [ Easypulse.Fields.EasypulseField](#easypulsefieldseasypulsefield) | none |
| max_rpm | [ Easypulse.Fields.EasypulseField](#easypulsefieldseasypulsefield) | none |
| max_speed | [ Easypulse.Fields.EasypulseField](#easypulsefieldseasypulsefield) | none |
| battery_level | [ Easypulse.Fields.EasypulseField](#easypulsefieldseasypulsefield) | none |
| fuel_level | [ Easypulse.Fields.EasypulseField](#easypulsefieldseasypulsefield) | none |
| fuel_used | [ Easypulse.Fields.StateBasedFields](#easypulsefieldsstatebasedfields) | Fuel usage while in different states of usage. |
| engine_time | [ Easypulse.Fields.StateBasedFields](#easypulsefieldsstatebasedfields) | Time spent in different states of usage. |
| engine_oil_temperature | [ Easypulse.Fields.EasypulseField](#easypulsefieldseasypulsefield) | none |
| pto_engagement | [ Easypulse.Fields.PTOEngagement](#easypulsefieldsptoengagement) | none |

### Easypulse.Fields.EasypulseField



| Field | Type | Description |
| ----- | ---- | ----------- |
| field | [ hiber.field.Field](#hiberfieldfield) | none |
| default_aggregation | [ hiber.value.ValueAggregation](#hibervaluevalueaggregation) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **_default_transformation**.default_transformation | [optional hiber.value.ValueTransformation](#hibervaluevaluetransformation) | none |
| default_partition | [ hiber.value.Value.Numeric.DurationUnit](#hibervaluevaluenumericdurationunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **target_value**.target_value_duration | [ Easypulse.TargetValues.DurationTargetValue](#easypulsetargetvaluesdurationtargetvalue) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **target_value**.target_value_distance | [ Easypulse.TargetValues.DistanceTargetValue](#easypulsetargetvaluesdistancetargetvalue) | none |

### Easypulse.Fields.PTOEngagement



| Field | Type | Description |
| ----- | ---- | ----------- |
| count | [ Easypulse.Fields.EasypulseField](#easypulsefieldseasypulsefield) | none |
| time | [ Easypulse.Fields.EasypulseField](#easypulsefieldseasypulsefield) | none |

### Easypulse.Fields.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **_modem**.modem | [optional string](#string) | Request the fields for a specific modem. The fields are always the same, but the defaults and target values may be different. |
| apply_unit_preferences | [ bool](#bool) | Whether to apply the unit preferences to the fields. This will convert any fields into your preferred unit, for convenience. |

### Easypulse.Fields.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| fields | [ Easypulse.Fields](#easypulsefields) | none |
| request | [ Easypulse.Fields.Request](#easypulsefieldsrequest) | none |

### Easypulse.Fields.StateBasedFields



| Field | Type | Description |
| ----- | ---- | ----------- |
| on | [ Easypulse.Fields.EasypulseField](#easypulsefieldseasypulsefield) | none |
| running | [ Easypulse.Fields.EasypulseField](#easypulsefieldseasypulsefield) | none |
| idle | [ Easypulse.Fields.EasypulseField](#easypulsefieldseasypulsefield) | none |
| off | [ Easypulse.Fields.EasypulseField](#easypulsefieldseasypulsefield) | none |

### Easypulse.History

List the history for a single field, and optionally apply an aggregation and/or grouping to it.
Deprecated in favor of the ValueService.


### Easypulse.History.Request

Request to get the history of a field, for the selected Assets in the organization.
Deprecated in favor of the ValueService.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ Easypulse.AssetSelection](#easypulseassetselection) | Select the asset(s) to get the history for. |
| pagination | [ hiber.Pagination](#hiberpagination) | Paginate the returned values. This may not be relevant, depending on the aggregation (which may result in a single value) and the time range. |
| time_range | [ hiber.TimeRange](#hibertimerange) | The time to view the history for. |
| aggregation | [ Easypulse.History.Request.Aggregation](#easypulsehistoryrequestaggregation) | How to aggregate the data. |
| sort | [ Easypulse.History.Request.Sort](#easypulsehistoryrequestsort) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **group**.split_by_duration | [ hiber.Duration](#hiberduration) | Split up the data in time block of the given size. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **group**.reduce_to_max_size | [ uint32](#uint32) | Limit the results to the given amount of data points, applying the function to each chunk. |
| fuel_level | [ bool](#bool) | Get the history for the fuel level. |
| tire_pressure | [ bool](#bool) | Get the history for the tire pressure. |
| battery_level | [ bool](#bool) | Get the history for the battery level. |
| temperature | [ bool](#bool) | Get the history for the temperature. |
| run_time | [ bool](#bool) | Get the history for the run time. |
| idle_time | [ bool](#bool) | Get the history for the idle time. |
| location | [ bool](#bool) | Get the history for the location. |
| speed | [ bool](#bool) | Get the history for the speed. |
| rpm | [ bool](#bool) | Get the history for the rpm of the engine |
| engine_state | [ bool](#bool) | Get the history for the engine state |
| fuel_efficiency | [ bool](#bool) | Get the fuel efficiency in ???. |
| distance_traveled | [ bool](#bool) | Get the distance traveled in ???. |
| odometer | [ bool](#bool) | Get the value of the odometer. (Total traveled distance by vehicle) |
| engine_runtime | [ bool](#bool) | Get the total amount of run-time hours for the engine. |
| engine_idle_time | [ bool](#bool) | Get the total amount of idle-time hours for the engine. |
| fuel_used_running | [ bool](#bool) | Get the total amount of fuel used by the engine while running. |
| fuel_used_idling | [ bool](#bool) | Get the total amount of fuel used by the engine while idling. |
| power_take_off_engagement_count | [ bool](#bool) | Get the total amount of times the power take of was engaged. |
| power_take_off_engagement_duration | [ bool](#bool) | Get the total duration of time the power take of was engaged. |
| engine_oil_temperature | [ bool](#bool) | Get the history for the engine oil temperature. |
| fuel_efficiency_score | [ bool](#bool) | Get the normalized score for the fuel efficiency, using a preconfigured baseline. |
| distance_traveled_score | [ bool](#bool) | Get the normalized score for the distance traveled, using a preconfigured baseline. |
| idle_time_score | [ bool](#bool) | Get the normalized score for the idle time, using a preconfigured baseline. |
| run_time_score | [ bool](#bool) | Get the normalized score for the run time, using a preconfigured baseline. |
| utilization_score | [ bool](#bool) | Get the average normalized score for the run time, idle time, distance traveled and fuel efficiency. |

### Easypulse.History.Response

Response with the (aggregated) history of a field, for the selected Assets in the organization.
Deprecated in favor of the ValueService.

| Field | Type | Description |
| ----- | ---- | ----------- |
| values | [repeated Easypulse.History.Response.Value](#easypulsehistoryresponsevalue) | The processed historical data points. For example, when applying the SUM aggregation to all data points, this list would only contains a single value, the sum of values. |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | The pagination result, containing information about amounts and pages. |
| request | [ Easypulse.History.Request](#easypulsehistoryrequest) | The request that was received, corrected and used to produce this result. |

### Easypulse.History.Response.Value

Processed historical data point. If this is a group, it will have a time range to denote the group.

| Field | Type | Description |
| ----- | ---- | ----------- |
| timestamp | [ hiber.Timestamp](#hibertimestamp) | When not grouping, time of the individual point. When grouping would return an exact data point (i.e. not an average), the time of that point. When grouping would not return an exact data point (i.e. average), the end of the time range. |
| time_range | [ hiber.TimeRange](#hibertimerange) | When grouping, the start and end time for the group. |
| fuel_level | [ float](#float) | The fuel level, as a percentage. |
| tire_pressure_deprecated | [ float](#float) | The tire pressure in bar. |
| battery_level_deprecated | [ float](#float) | The battery level, as a percentage. |
| temperature | [ float](#float) | The temperature in degrees Celsius. |
| run_time | [ hiber.Duration](#hiberduration) | The time the Asset was running. |
| idle_time | [ hiber.Duration](#hiberduration) | The time the Asset was idle. |
| location | [ hiber.Location](#hiberlocation) | The location of the asset at the timestamp, or the last location in the time range. |
| speed_deprecated | [ float](#float) | The speed of the asset in km/h. |
| rpm | [ int32](#int32) | none |
| fuel_efficiency | [ float](#float) | Fuel efficiency in ???. |
| distance_traveled | [ float](#float) | Distance traveled in ???. |
| engine_state | [ Easypulse.EngineState](#easypulseenginestate) | State of the engine |
| fuel_efficiency_score | [ float](#float) | Normalized score for the fuel efficiency, using a preconfigured baseline. |
| distance_traveled_score | [ float](#float) | Normalized score for the distance traveled, using a preconfigured baseline. |
| idle_time_score | [ float](#float) | Normalized score for the idle time, using a preconfigured baseline. |
| run_time_score | [ float](#float) | Normalized score for the run time, using a preconfigured baseline. |
| utilization_score | [ float](#float) | Average normalized score for the run time, idle time, distance traveled and fuel efficiency. |
| odometer | [ hiber.value.Value.Numeric.Distance](#hibervaluevaluenumericdistance) | Current value of the odometer. |
| engine_runtime | [ hiber.Duration](#hiberduration) | Duration of total hours the engine has ran. |
| engine_idle_time | [ hiber.Duration](#hiberduration) | Duration of total hours the engine has been idling. |
| fuel_used_running | [ hiber.value.Value.Numeric.Volume](#hibervaluevaluenumericvolume) | The total amount of fuel used by this vehicle. |
| fuel_used_idling | [ hiber.value.Value.Numeric.Volume](#hibervaluevaluenumericvolume) | The total amount of fuel used by this vehicle while idling. |
| power_take_off_engagement_count | [ int32](#int32) | none |
| power_take_off_engagement_duration | [ hiber.Duration](#hiberduration) | none |
| engine_oil_temperature | [ hiber.value.Value.Numeric.Temperature](#hibervaluevaluenumerictemperature) | Engine temperature. |
| speed | [ hiber.value.Value.Numeric.Speed](#hibervaluevaluenumericspeed) | Speed of the asset. |
| tire_pressure | [ hiber.value.Value.Numeric.Pressure](#hibervaluevaluenumericpressure) | The tire pressure of the asset. |
| battery_level | [ hiber.value.Value.Numeric.BatteryLevel](#hibervaluevaluenumericbatterylevel) | The battery level, as a percentage. |

### Easypulse.ListAssets

List the Easypulse Assets in your organization.
Optionally, aggregated historical data can be added to the returned Assets, with a given name.

Fails when your organizations does not have the Easypulse feature.


### Easypulse.ListAssets.Request

Request to list Assets in your organization.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ Easypulse.AssetSelection](#easypulseassetselection) | Select the Assets to return. |
| pagination | [ hiber.Pagination](#hiberpagination) | Paginate over the returned Assets. |
| aggregations | [map Easypulse.ListAssets.Request.AggregationsEntry](#easypulselistassetsrequestaggregationsentry) | Any aggregations to return with the assets, specified as a name and a History.Request. |
| sort | [ Easypulse.ListAssets.Request.Sort](#easypulselistassetsrequestsort) | Sort the returned assets using the given option. By default, Assets are sorted by name. |

### Easypulse.ListAssets.Request.AggregationsEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ Easypulse.History.Request](#easypulsehistoryrequest) | none |

### Easypulse.ListAssets.Response

Response with a list of Assets

| Field | Type | Description |
| ----- | ---- | ----------- |
| assets | [repeated Easypulse.Asset](#easypulseasset) | The selected Assets. |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | The applied pagination, including total results, page information, etc. |
| request | [ Easypulse.ListAssets.Request](#easypulselistassetsrequest) | The request that was received, corrected and used to produce this result. |

### Easypulse.TargetValues

Target values for a modem.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | The organization the asset is in. |
| number | [ string](#string) | The asset number these target values are for. |
| engine_run_time | [ Easypulse.TargetValues.DurationTargetValue](#easypulsetargetvaluesdurationtargetvalue) | none |
| engine_idle_time | [ Easypulse.TargetValues.DurationTargetValue](#easypulsetargetvaluesdurationtargetvalue) | none |
| engine_off_time | [ Easypulse.TargetValues.DurationTargetValue](#easypulsetargetvaluesdurationtargetvalue) | none |
| distance_travelled | [ Easypulse.TargetValues.DistanceTargetValue](#easypulsetargetvaluesdistancetargetvalue) | none |
| availability | [ Easypulse.TargetValues.DurationTargetValue](#easypulsetargetvaluesdurationtargetvalue) | none |
| sinarmas_specific | [ Easypulse.TargetValues.SinarmasTargetValues](#easypulsetargetvaluessinarmastargetvalues) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **fuel_efficiency**.fuel_efficiency_unit | [ Easypulse.TargetValues.FuelEfficiencyTargetValue](#easypulsetargetvaluesfuelefficiencytargetvalue) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **fuel_efficiency**.fuel_efficiency_as_volume | [ Easypulse.TargetValues.VolumeTargetValue](#easypulsetargetvaluesvolumetargetvalue) | none |

### Easypulse.TargetValues.DistanceTargetValue

A target value that measures distance per time, i.e. 12 kilometers per day.

| Field | Type | Description |
| ----- | ---- | ----------- |
| enabled | [ bool](#bool) | none |
| value | [ float](#float) | none |
| unit | [ hiber.value.Value.Numeric.Distance.Unit](#hibervaluevaluenumericdistanceunit) | none |
| per_time | [ hiber.value.Value.Numeric.DurationUnit](#hibervaluevaluenumericdurationunit) | none |

### Easypulse.TargetValues.DurationTargetValue

A target value that measures time per time, i.e. 12 hours per day.

| Field | Type | Description |
| ----- | ---- | ----------- |
| enabled | [ bool](#bool) | none |
| value | [ float](#float) | none |
| unit | [ hiber.value.Value.Numeric.DurationUnit](#hibervaluevaluenumericdurationunit) | none |
| per_time | [ hiber.value.Value.Numeric.DurationUnit](#hibervaluevaluenumericdurationunit) | none |

### Easypulse.TargetValues.FuelEfficiencyTargetValue

A target value that measures fuel efficiency.

| Field | Type | Description |
| ----- | ---- | ----------- |
| enabled | [ bool](#bool) | none |
| value | [ float](#float) | none |
| unit | [ hiber.value.Value.Numeric.FuelEfficiency.Unit](#hibervaluevaluenumericfuelefficiencyunit) | none |

### Easypulse.TargetValues.List




### Easypulse.TargetValues.List.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ Easypulse.AssetSelection](#easypulseassetselection) | Select the Assets to return. |
| pagination | [ hiber.Pagination](#hiberpagination) | Paginate over the returned Assets. |
| sort | [ Easypulse.ListAssets.Request.Sort](#easypulselistassetsrequestsort) | Sort the returned assets using the given option. By default, Assets are sorted by name. |
| apply_unit_preferences | [ bool](#bool) | Whether to apply the unit preferences to the fields. This will convert any fields into your preferred unit, for convenience. |

### Easypulse.TargetValues.List.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| asset_target_values | [repeated Easypulse.TargetValues](#easypulsetargetvalues) | The selected Assets. |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | The applied pagination, including total results, page information, etc. |
| request | [ Easypulse.TargetValues.List.Request](#easypulsetargetvalueslistrequest) | The request that was received, corrected and used to produce this result. |

### Easypulse.TargetValues.SinarmasTargetValues

A specific set of target values for Sinarmas.

| Field | Type | Description |
| ----- | ---- | ----------- |
| trees | [ Easypulse.TargetValues.SinarmasTargetValues.TreesTargetValue](#easypulsetargetvaluessinarmastargetvaluestreestargetvalue) | none |
| tree_volume | [ Easypulse.TargetValues.SinarmasTargetValues.TreeVolumeTargetValue](#easypulsetargetvaluessinarmastargetvaluestreevolumetargetvalue) | none |

### Easypulse.TargetValues.SinarmasTargetValues.TreeVolumeTargetValue



| Field | Type | Description |
| ----- | ---- | ----------- |
| enabled | [ bool](#bool) | none |
| value | [ float](#float) | none |
| unit | [ hiber.value.Value.Numeric.Volume.Unit](#hibervaluevaluenumericvolumeunit) | none |
| per_time | [ hiber.value.Value.Numeric.DurationUnit](#hibervaluevaluenumericdurationunit) | none |
| volume_per_tree | [ float](#float) | none |

### Easypulse.TargetValues.SinarmasTargetValues.TreesTargetValue



| Field | Type | Description |
| ----- | ---- | ----------- |
| enabled | [ bool](#bool) | none |
| value | [ uint32](#uint32) | none |
| per_time | [ hiber.value.Value.Numeric.DurationUnit](#hibervaluevaluenumericdurationunit) | none |

### Easypulse.TargetValues.Update




### Easypulse.TargetValues.Update.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| number | [ string](#string) | The asset number to update the target values for. |
| replace_engine_run_time | [ Easypulse.TargetValues.DurationTargetValue](#easypulsetargetvaluesdurationtargetvalue) | Replace the engine_run_time target value with this DurationTargetValue. |
| replace_engine_idle_time | [ Easypulse.TargetValues.DurationTargetValue](#easypulsetargetvaluesdurationtargetvalue) | Replace the engine_idle_time target value with this DurationTargetValue. |
| replace_engine_off_time | [ Easypulse.TargetValues.DurationTargetValue](#easypulsetargetvaluesdurationtargetvalue) | Replace the engine_off_time target value with this DurationTargetValue. |
| replace_distance_travelled | [ Easypulse.TargetValues.DistanceTargetValue](#easypulsetargetvaluesdistancetargetvalue) | Replace the distance_travelled target value with this DistanceTargetValue. |
| replace_availability | [ Easypulse.TargetValues.DurationTargetValue](#easypulsetargetvaluesdurationtargetvalue) | Replace the availability target value with this DurationTargetValue. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **replace_fuel_efficiency**.replace_fuel_efficiency_unit | [ Easypulse.TargetValues.FuelEfficiencyTargetValue](#easypulsetargetvaluesfuelefficiencytargetvalue) | Replace the fuel_efficiency target value with this FuelEfficiencyTargetValue. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **replace_fuel_efficiency**.replace_fuel_efficiency_as_volume | [ Easypulse.TargetValues.VolumeTargetValue](#easypulsetargetvaluesvolumetargetvalue) | Replace the fuel_efficiency target value with this VolumeTargetValue. |
| replace_sinarmas_specific | [ Easypulse.TargetValues.SinarmasTargetValues](#easypulsetargetvaluessinarmastargetvalues) | Replace the sinarmas_specific target values with this SinarmasTargetValues. |

### Easypulse.TargetValues.VolumeTargetValue

A target value that measures volume per time, i.e. 2 liters per day.

| Field | Type | Description |
| ----- | ---- | ----------- |
| enabled | [ bool](#bool) | none |
| value | [ float](#float) | none |
| unit | [ hiber.value.Value.Numeric.Volume.Unit](#hibervaluevaluenumericvolumeunit) | none |
| per_time | [ hiber.value.Value.Numeric.DurationUnit](#hibervaluevaluenumericdurationunit) | none |

### Easypulse.TellTale

A tell tale is an indicator of a part of the system.

| Field | Type | Description |
| ----- | ---- | ----------- |
| indicator | [ Easypulse.TellTale.Indicator](#easypulsetelltaleindicator) | none |
| name | [ string](#string) | none |
| label | [ string](#string) | none |
| description | [ string](#string) | none |
| enum_value | [ hiber.value.Value.Enum](#hibervaluevalueenum) | none |

### Easypulse.TellTale.Indicator



| Field | Type | Description |
| ----- | ---- | ----------- |
| state | [ Easypulse.TellTale.Indicator.State](#easypulsetelltaleindicatorstate) | none |
| color | [ string](#string) | none |
| label | [ string](#string) | none |


## Enums
### Easypulse.EngineState


| Name | Description | Number |
| ---- | ----------- | ------ |
| OFF | none | 0 |
| IDLING | none | 1 |
| RUNNING | none | 2 |
| RESERVED | none | 3 |

### Easypulse.History.Request.Aggregation
Options to aggregate the history data points (in a group).

| Name | Description | Number |
| ---- | ----------- | ------ |
| NONE | Do not aggregate the history data points, just list all of them. | 0 |
| AVERAGE | Average value of all history data points (in a group). | 1 |
| SUM | Sum all history data points (in a group). | 2 |
| LAST | Just take the last value (in a group). | 3 |
| MINIMUM | Take the lowest value (in a group). | 4 |
| MAXIMUM | Take the highest value (in a group). | 5 |

### Easypulse.History.Request.Sort
How to sort the returned values.

| Name | Description | Number |
| ---- | ----------- | ------ |
| TIME_DESCENDING | none | 0 |
| TIME_ASCENDING | none | 1 |

### Easypulse.ListAssets.Request.Sort


| Name | Description | Number |
| ---- | ----------- | ------ |
| NAME | none | 0 |
| NAME_DESC | none | 1 |
| LAST_UPDATED | none | 2 |
| INACTIVITY | none | 3 |
| NUMBER_ASC | none | 4 |
| NUMBER_DESC | none | 5 |
| LOWEST_FUEL_LEVEL | none | 6 |
| HIGHEST_FUEL_LEVEL | none | 7 |
| LOWEST_TIRE_PRESSURE | none | 8 |
| HIGHEST_TIRE_PRESSURE | none | 9 |
| LOWEST_BATTERY_LEVEL | none | 10 |
| HIGHEST_BATTERY_LEVEL | none | 11 |
| LOWEST_TEMPERATURE | none | 12 |
| HIGHEST_TEMPERATURE | none | 13 |
| HEALTH | Health sorted from least to most severe (i.e. OK, WARNING, ERROR). | 14 |
| HEALTH_DESC | Health sorted from most to least severe (i.e. ERROR, WARNING, OK). | 15 |

### Easypulse.TellTale.Indicator.State
The state of a tell-tale sensor. Ordinal numbers follow the spec of the CAN bus for states

| Name | Description | Number |
| ---- | ----------- | ------ |
| OFF | The tell-tale has not been triggered. This can be considered an OK state. | 0 |
| RED | The tell-tale indicates something is very wrong with the system it is monitoring. | 1 |
| YELLOW | The tell-tale indicates something is wrong with the system it is monitoring, but not broken yet. | 2 |
| INFO | The tell-tale indicates there is some information about the system it is monitoring. | 3 |
| NOT_AVAILABLE | The tell-tale sensor for this system is not available. | 4 |
| OTHER | Other, not part of the CAN-Bus spec. | 5 |



## Referenced messages from health.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [health.proto](https://github.com/HiberGlobal/api/blob/master/health.proto).


### hiber.health.HealthLevel

A health level in an organization.
Health can be customized depending on your need.

The default health levels are:
- OK (green): no problems detected
- WARNING (orange): unresolvable problems detected, for example delayed or skipped messages
- ERROR (red): significant problems detected (that typically can be resolved),
  for example inactivity or invalid messages (resolved on a successful message)

Health levels can be customized to as many as you need for your operations, for example:
- INTERVENTION
- DEFECT
- BATTERY
- HIGH
- LOW

Health levels are ordered by severity (low to high),
and of all things affecting a modem's health,
only the most severe level will be returned when retrieving a modem.

Health can be assigned using modems alarms, which specify the health level they will cause on a modem (and for how
long, if it does not resolve automatically).

Precisely one health level can be assigned as a catch-all for any unknown health levels from alarms (or Hiber systems),
which can happen when a device manufacturer has provided alarms to your device (e.g. a low battery alarm).
By default, any unknown health levels map to the level that is marked catch-all.

Health level have a set of named colors, represented by a map where the key is the name of the color
and the value is a string that represents a valid CSS3 color.
Simple examples are: green, red, orange, grey, #FF00FF for fuchsia, etc (Keep in mind that CSS3 allows for many
ways to define colors, see https://www.w3.org/TR/2003/WD-css3-color-20030214/).

All the following definitions also mean "red":
 - rgb(255, 0, 0)
 - rgb(100%, 0, 0)
 - rgba(100%, 0%, 0%, 100%)
 - hsl(0, 100%, 50%)
 - hsla(0, 100%, 50%, 1)

The client is responsible for rendering the correct color from the CSS3 color-space and for setting the colors and
their names. There is no verification on missing named colors, so the client must set sensible defaults when colors
are missing.

To assist with sorting, health levels have a numeric severity equal to their index in the sorted list of health
levels (starting at 1). This means higher numbers denote a more severe health.
Since these values are noting more than a list index, they should not be cached, compared to another organization or
compared to values retrieved from the API at another time.

For example, an organization using the default health would have:
- Ok: severity 1
- Warning: severity 2
- Error: severity 3

That organization could then add a new health level in between Ok and Warning, meaning the severity of Warning and
Error will change:
- Ok, severity 1
- ItsComplicated, severity 2
- Warning, severity 3
- Error, severity 4

| Field | Type | Description |
| ----- | ---- | ----------- |
| level | [ string](#string) | The name of this health level. Levels are identified by their name. The API does support renaming, where the rename is propagated to all the relevant parts of the system. |
| color | [ string](#string) | Default color for the health level, as a string that represents a valid CSS3 color. DEPRECATED: Maps to the color named "text" in color_data. |
| color_data | [map hiber.health.HealthLevel.ColorDataEntry](#hiberhealthhealthlevelcolordataentry) | Map of named colors, where key is the name and the value is a valid CSS3 color definition. |
| severity | [ int64](#int64) | A unique numeric value equal to the index of this health level in the list of health levels sorted by ascending severity (starting at 1). This means higher numbers denote a more severe health. This value cannot be used when creating or updating. To change the severity for a health level, reorder all health levels. |
| catch_all | [ bool](#bool) | Precisely one health level can be assigned as a catch-all for any unknown health levels from alarms (or Hiber systems), which can happen when a device manufacturer has provided alarms for your device (e.g. a low battery alarm). By default, unknown health levels map to the level of the highest severity, unless another level is marked as catch-all. |

### hiber.health.HealthLevelSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| search | [ string](#string) | Search for the given string in the levels and colors. |
| levels | [repeated string](#string) | Filter by exact levels. |


### Enums


## Referenced messages from tag.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [tag.proto](https://github.com/HiberGlobal/api/blob/master/tag.proto).


### hiber.tag.Tag



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) | none |
| label | [ hiber.tag.Tag.Label](#hibertagtaglabel) | none |

### hiber.tag.Tag.Label



| Field | Type | Description |
| ----- | ---- | ----------- |
| name | [ string](#string) | none |
| type | [ string](#string) | none |

### hiber.tag.TagSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| search | [repeated string](#string) | none |
| names | [repeated string](#string) | none |
| filter | [ hiber.Filter.Tags](#hiberfiltertags) | none |
| types | [repeated string](#string) | none |


### Enums


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


| Name | Description | Number |
| ---- | ----------- | ------ |
| PERCENT | Battery level as a percentage (technically not a unit).

other units will be added here later, like voltage | 0 |

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

### hiber.Filter.FieldEnumValues



| Field | Type | Description |
| ----- | ---- | ----------- |
| field | [ string](#string) | none |
| include | [repeated string](#string) | none |
| exclude | [repeated string](#string) | none |

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

### hiber.Filter.SupportPermissions



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated hiber.SupportPermission](#hibersupportpermission) | none |
| exclude | [repeated hiber.SupportPermission](#hibersupportpermission) | none |

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

This can be used with textual shortcuts for timestamp, and some additional duration textual shortcuts:
- a duration as an offset of now, i.e. "-10h" or "PT-10h": converted to now + offset, so start.textual -10h is
  10 hours before the end time (using the ISO 8601 duration format)
Examples:
- start "-10h" end "now": a time range from 10 hours before the request time, to the request time
- start "-10h" end "2022-01-01 20:00": becomes start 2022-01-01 10:00 end 2022-01-01 20:00

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

In addition, the textual field, when used as input, allows for a number of shortcuts that get converted into
timestamps:
- "now": converted to the current timestamp at the time of the request

| Field | Type | Description |
| ----- | ---- | ----------- |
| timestamp | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | none |
| time_zone | [ string](#string) | none |
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
| MODEM_MESSAGE_RECEIVED | none | 5 |
| MODEM_MESSAGE_BODY_PARSED | none | 39 |
| MODEM_MESSAGE_BODY_RECEIVED | none | 45 |
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
| DURATION_MILLISECONDS | none | 40 |
| DURATION_SECONDS | none | 1 |
| DURATION_MINUTES | none | 2 |
| DURATION_HOURS | none | 3 |
| DURATION_DAYS | none | 4 |
| DURATION_WEEKS | none | 41 |
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
| VOLUME_CUBIC_METER | none | 42 |
| VOLUME_CUBIC_FOOT | none | 43 |
| MASS_KILOGRAMS | none | 37 |
| MASS_POUNDS | none | 38 |
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

