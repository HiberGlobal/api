# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [easypulse.proto](#easypulse.proto)
    - [Easypulse](#hiber.easypulse.Easypulse)
    - [Easypulse.Asset](#hiber.easypulse.Easypulse.Asset)
    - [Easypulse.Asset.AggregationsEntry](#hiber.easypulse.Easypulse.Asset.AggregationsEntry)
    - [Easypulse.Asset.LastUpdate](#hiber.easypulse.Easypulse.Asset.LastUpdate)
    - [Easypulse.Asset.PeripheralsEntry](#hiber.easypulse.Easypulse.Asset.PeripheralsEntry)
    - [Easypulse.AssetSelection](#hiber.easypulse.Easypulse.AssetSelection)
    - [Easypulse.History](#hiber.easypulse.Easypulse.History)
    - [Easypulse.History.Request](#hiber.easypulse.Easypulse.History.Request)
    - [Easypulse.History.Response](#hiber.easypulse.Easypulse.History.Response)
    - [Easypulse.History.Response.Value](#hiber.easypulse.Easypulse.History.Response.Value)
    - [Easypulse.ListAssets](#hiber.easypulse.Easypulse.ListAssets)
    - [Easypulse.ListAssets.Request](#hiber.easypulse.Easypulse.ListAssets.Request)
    - [Easypulse.ListAssets.Request.AggregationsEntry](#hiber.easypulse.Easypulse.ListAssets.Request.AggregationsEntry)
    - [Easypulse.ListAssets.Response](#hiber.easypulse.Easypulse.ListAssets.Response)
    - [Easypulse.UpdateAssets](#hiber.easypulse.Easypulse.UpdateAssets)
    - [Easypulse.UpdateAssets.Request](#hiber.easypulse.Easypulse.UpdateAssets.Request)
    - [Easypulse.UpdateAssets.Request.AddPeripheralsEntry](#hiber.easypulse.Easypulse.UpdateAssets.Request.AddPeripheralsEntry)
    - [Easypulse.UpdateAssets.Response](#hiber.easypulse.Easypulse.UpdateAssets.Response)
  
    - [Easypulse.History.Request.Aggregation](#hiber.easypulse.Easypulse.History.Request.Aggregation)
    - [Easypulse.ListAssets.Request.Sort](#hiber.easypulse.Easypulse.ListAssets.Request.Sort)
  
    - [EasypulseService](#hiber.easypulse.EasypulseService)
  
- [health.proto](#health.proto)
    - [AddHealthLevel](#hiber.health.AddHealthLevel)
    - [AddHealthLevel.Request](#hiber.health.AddHealthLevel.Request)
    - [AddHealthLevel.Response](#hiber.health.AddHealthLevel.Response)
    - [HealthLevel](#hiber.health.HealthLevel)
    - [HealthLevel.ColorDataEntry](#hiber.health.HealthLevel.ColorDataEntry)
    - [HealthLevelSelection](#hiber.health.HealthLevelSelection)
    - [ListHealthLevels](#hiber.health.ListHealthLevels)
    - [ListHealthLevels.Request](#hiber.health.ListHealthLevels.Request)
    - [ListHealthLevels.Response](#hiber.health.ListHealthLevels.Response)
    - [RemoveHealthLevel](#hiber.health.RemoveHealthLevel)
    - [RemoveHealthLevel.Request](#hiber.health.RemoveHealthLevel.Request)
    - [RemoveHealthLevel.Response](#hiber.health.RemoveHealthLevel.Response)
    - [ReorderHealthLevels](#hiber.health.ReorderHealthLevels)
    - [ReorderHealthLevels.Request](#hiber.health.ReorderHealthLevels.Request)
    - [ReorderHealthLevels.Response](#hiber.health.ReorderHealthLevels.Response)
    - [UpdateHealthLevel](#hiber.health.UpdateHealthLevel)
    - [UpdateHealthLevel.Request](#hiber.health.UpdateHealthLevel.Request)
    - [UpdateHealthLevel.Request.AddColorsEntry](#hiber.health.UpdateHealthLevel.Request.AddColorsEntry)
    - [UpdateHealthLevel.Response](#hiber.health.UpdateHealthLevel.Response)
  
    - [HealthService](#hiber.health.HealthService)
  
- [tag.proto](#tag.proto)
    - [CreateTagRequest](#hiber.tag.CreateTagRequest)
    - [DeleteTagRequest](#hiber.tag.DeleteTagRequest)
    - [DeleteTagRequest.Response](#hiber.tag.DeleteTagRequest.Response)
    - [ListTagsRequest](#hiber.tag.ListTagsRequest)
    - [ListTagsRequest.Response](#hiber.tag.ListTagsRequest.Response)
    - [ListTagsRequest.Response.TagModemCountEntry](#hiber.tag.ListTagsRequest.Response.TagModemCountEntry)
    - [ListTagsRequest.Response.TagWebhookCountEntry](#hiber.tag.ListTagsRequest.Response.TagWebhookCountEntry)
    - [Tag](#hiber.tag.Tag)
    - [Tag.Label](#hiber.tag.Tag.Label)
    - [TagSelection](#hiber.tag.TagSelection)
    - [UpdateTagRequest](#hiber.tag.UpdateTagRequest)
    - [UpdateTagsForItem](#hiber.tag.UpdateTagsForItem)
  
    - [TagService](#hiber.tag.TagService)
  
- [base.proto](#base.proto)
    - [Area](#hiber.Area)
    - [Avatar](#hiber.Avatar)
    - [BytesOrHex](#hiber.BytesOrHex)
    - [BytesOrHex.Update](#hiber.BytesOrHex.Update)
    - [Date](#hiber.Date)
    - [DoubleRange](#hiber.DoubleRange)
    - [Duration](#hiber.Duration)
    - [Filter](#hiber.Filter)
    - [Filter.ChildOrganizations](#hiber.Filter.ChildOrganizations)
    - [Filter.ChildOrganizations.Update](#hiber.Filter.ChildOrganizations.Update)
    - [Filter.Events](#hiber.Filter.Events)
    - [Filter.Events.Update](#hiber.Filter.Events.Update)
    - [Filter.Modems](#hiber.Filter.Modems)
    - [Filter.Modems.Update](#hiber.Filter.Modems.Update)
    - [Filter.OrganizationPermissions](#hiber.Filter.OrganizationPermissions)
    - [Filter.Organizations](#hiber.Filter.Organizations)
    - [Filter.Publishers](#hiber.Filter.Publishers)
    - [Filter.Tags](#hiber.Filter.Tags)
    - [Filter.Tags.Update](#hiber.Filter.Tags.Update)
    - [Filter.UserPermissions](#hiber.Filter.UserPermissions)
    - [Filter.Users](#hiber.Filter.Users)
    - [Filter.Webhooks](#hiber.Filter.Webhooks)
    - [Location](#hiber.Location)
    - [LocationSelection](#hiber.LocationSelection)
    - [NamedFile](#hiber.NamedFile)
    - [Pagination](#hiber.Pagination)
    - [Pagination.Result](#hiber.Pagination.Result)
    - [Shape](#hiber.Shape)
    - [TimeRange](#hiber.TimeRange)
    - [Timestamp](#hiber.Timestamp)
    - [UpdateBoolean](#hiber.UpdateBoolean)
    - [UpdateClearableString](#hiber.UpdateClearableString)
    - [UpdateOptionalDuration](#hiber.UpdateOptionalDuration)
    - [UpdateOptionalId](#hiber.UpdateOptionalId)
    - [UpdateZeroableInt](#hiber.UpdateZeroableInt)
  
    - [EventType](#hiber.EventType)
    - [Health](#hiber.Health)
  
- [Scalar Value Types](#scalar-value-types)



<a name="easypulse.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## easypulse.proto
Easypulse specific view and services.

This file contains specific views and services for the easypulse feature set.
This feature set is only available to organizations with the easypulse feature enabled.

For Easypulse, we&#39;ve introduced the concept of an Asset, which is a modem with some assumptions about the type of
data it sends. Additionally, aggregations can be requested of Asset history when requesting Assets, allowing for a
somewhat customized Asset model.


<a name="hiber.easypulse.Easypulse"></a>

### Easypulse







<a name="hiber.easypulse.Easypulse.Asset"></a>

### Easypulse.Asset
Asset in your organization.
An asset is a view of a modem, with assumptions about message data fields handled in the API.

In addition, an Asset can be enriched with aggregations of the data fields when requested (for example,
fuel level average over the past month, or total run time in the past week).


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| organization | [string](#string) |  | The organization the asset is in. |
| number | [string](#string) |  | The modem number for the Asset. |
| name | [string](#string) |  | The custom name for the Asset, defaults to modem number. |
| external_identifier | [string](#string) |  | Optional external identifier the Asset may have. |
| peripherals | [Easypulse.Asset.PeripheralsEntry](#hiber.easypulse.Easypulse.Asset.PeripheralsEntry) | repeated | A key value map of peripherals for the Assets. |
| notes | [string](#string) |  | Add additional notes to an asset. |
| secure_notes | [string](#string) |  | Add additional notes to an asset that only people with the permission can access. |
| health_level | [hiber.health.HealthLevel](#hiber.health.HealthLevel) |  | Health level based on the modem alarm and some always-present alarms. |
| tags | [hiber.tag.Tag](#hiber.tag.Tag) | repeated | Tags (or groups, when used in Mission Control) this asset is in. |
| last_update | [Easypulse.Asset.LastUpdate](#hiber.easypulse.Easypulse.Asset.LastUpdate) |  | When this asset was last updated. |
| fuel_level | [float](#float) |  | The most recent fuel level, as a percentage. |
| tire_pressure | [float](#float) |  | The most recent tire pressure in bar. |
| battery_level | [float](#float) |  | The most recent battery level, as a percentage. |
| temperature | [float](#float) |  | The most recent temperature in degrees Celsius. |
| location | [hiber.Location](#hiber.Location) |  | The most recently reported location. |
| aggregations | [Easypulse.Asset.AggregationsEntry](#hiber.easypulse.Easypulse.Asset.AggregationsEntry) | repeated | Any aggregations added when this asset was requested. |






<a name="hiber.easypulse.Easypulse.Asset.AggregationsEntry"></a>

### Easypulse.Asset.AggregationsEntry



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| key | [string](#string) |  |  |
| value | [Easypulse.History.Response](#hiber.easypulse.Easypulse.History.Response) |  |  |






<a name="hiber.easypulse.Easypulse.Asset.LastUpdate"></a>

### Easypulse.Asset.LastUpdate
Information about the last update we received from this asset.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [uint64](#uint64) |  |  |
| received_at | [hiber.Timestamp](#hiber.Timestamp) |  | Time the server has received the last update. |
| sent_at | [hiber.Timestamp](#hiber.Timestamp) |  | Time the asset sent the last update. |
| body | [hiber.BytesOrHex](#hiber.BytesOrHex) |  | The body of the last update. |






<a name="hiber.easypulse.Easypulse.Asset.PeripheralsEntry"></a>

### Easypulse.Asset.PeripheralsEntry



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| key | [string](#string) |  |  |
| value | [string](#string) |  |  |






<a name="hiber.easypulse.Easypulse.AssetSelection"></a>

### Easypulse.AssetSelection
An AssetSelection is used to select which Assets should be affected:
- When listing Assets, it is used to determine which Assets are returned
- When updating Assets, it is used to determine which Assets are updated


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| search | [string](#string) |  | Search for assets by name, modem number, tag or notes. |
| assets | [hiber.Filter.Modems](#hiber.Filter.Modems) |  | Select assets by modem number. |
| health_levels | [string](#string) | repeated | Select assets by health level. |
| filter_by_tags | [hiber.tag.TagSelection](#hiber.tag.TagSelection) |  | Select assets by tag. |






<a name="hiber.easypulse.Easypulse.History"></a>

### Easypulse.History
List the history for a single field, and optionally apply an aggregation and/or grouping to it.






<a name="hiber.easypulse.Easypulse.History.Request"></a>

### Easypulse.History.Request
Request to get the history of a field, for the selected Assets in the organization.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| organization | [string](#string) |  | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [Easypulse.AssetSelection](#hiber.easypulse.Easypulse.AssetSelection) |  | Select the asset(s) to update. |
| time_range | [hiber.TimeRange](#hiber.TimeRange) |  | The time to view the history for. |
| aggregation | [Easypulse.History.Request.Aggregation](#hiber.easypulse.Easypulse.History.Request.Aggregation) |  | How to aggregate the data. |
| split_by_duration | [hiber.Duration](#hiber.Duration) |  | Split up the data in time block of the given size. |
| reduce_to_max_size | [uint32](#uint32) |  | Limit the results to the given amount of data points, applying the function to each chunk. |
| fuel_level | [bool](#bool) |  | Get the history for the fuel level. Only one field can be chosen. |
| tire_pressure | [bool](#bool) |  | Get the history for the tire pressure. Only one field can be chosen. |
| battery_level | [bool](#bool) |  | Get the history for the battery level. Only one field can be chosen. |
| temperature | [bool](#bool) |  | Get the history for the temperature. Only one field can be chosen. |
| run_time | [bool](#bool) |  | Get the history for the run time. Only one field can be chosen. |
| idle_time | [bool](#bool) |  | Get the history for the idle time. Only one field can be chosen. |






<a name="hiber.easypulse.Easypulse.History.Response"></a>

### Easypulse.History.Response
Response with the (aggregated) history of a field, for the selected Assets in the organization.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| values | [Easypulse.History.Response.Value](#hiber.easypulse.Easypulse.History.Response.Value) | repeated | The processed historical data points. For example, when applying the SUM aggregation to all data points, this list would only contains a single value, the sum of values. |
| request | [Easypulse.History.Request](#hiber.easypulse.Easypulse.History.Request) |  | The request that was received, corrected and used to produce this result. |






<a name="hiber.easypulse.Easypulse.History.Response.Value"></a>

### Easypulse.History.Response.Value
Processed historical data point. If this is a group, it will have a time range to denote the group.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| timestamp | [hiber.Timestamp](#hiber.Timestamp) |  | When not grouping, time of the individual point. When grouping, the time at the end of the group (when the value was true). |
| time_range | [hiber.TimeRange](#hiber.TimeRange) |  | When grouping, the start and end time for the group. |
| fuel_level | [float](#float) |  | The fuel level, as a percentage. |
| tire_pressure | [float](#float) |  | The tire pressure in bar. |
| battery_level | [float](#float) |  | The battery level, as a percentage. |
| temperature | [float](#float) |  | The temperature in degrees Celsius. |
| run_time | [hiber.Duration](#hiber.Duration) |  | The time the Asset was running. |
| idle_time | [hiber.Duration](#hiber.Duration) |  | The time the Asset was idle. |






<a name="hiber.easypulse.Easypulse.ListAssets"></a>

### Easypulse.ListAssets
List the Easypulse Assets in your organization.
Optionally, aggregated historical data can be added to the returned Assets, with a given name.

Fails when your organizations does not have the Easypulse feature.






<a name="hiber.easypulse.Easypulse.ListAssets.Request"></a>

### Easypulse.ListAssets.Request
Request to list Assets in your organization.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| organization | [string](#string) |  | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [Easypulse.AssetSelection](#hiber.easypulse.Easypulse.AssetSelection) |  | Select the Assets to return. |
| pagination | [hiber.Pagination](#hiber.Pagination) |  | Paginate over the returned Assets. |
| aggregations | [Easypulse.ListAssets.Request.AggregationsEntry](#hiber.easypulse.Easypulse.ListAssets.Request.AggregationsEntry) | repeated | Any aggregations to return with the assets, specified as a name and a History.Request. |
| sort | [Easypulse.ListAssets.Request.Sort](#hiber.easypulse.Easypulse.ListAssets.Request.Sort) |  | Sort the returned assets using the given option. By default, Assets are sorted by name. |






<a name="hiber.easypulse.Easypulse.ListAssets.Request.AggregationsEntry"></a>

### Easypulse.ListAssets.Request.AggregationsEntry



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| key | [string](#string) |  |  |
| value | [Easypulse.History.Request](#hiber.easypulse.Easypulse.History.Request) |  |  |






<a name="hiber.easypulse.Easypulse.ListAssets.Response"></a>

### Easypulse.ListAssets.Response
Response with a list of Assets


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| assets | [Easypulse.Asset](#hiber.easypulse.Easypulse.Asset) | repeated | The selected Assets. |
| pagination | [hiber.Pagination.Result](#hiber.Pagination.Result) |  | The applied pagination, including total results, page information, etc. |
| request | [Easypulse.ListAssets.Request](#hiber.easypulse.Easypulse.ListAssets.Request) |  | The request that was received, corrected and used to produce this result. |






<a name="hiber.easypulse.Easypulse.UpdateAssets"></a>

### Easypulse.UpdateAssets
Update your Assets, renaming, updating tags, etc.

Produces a ModemUpdated event with the changed values.






<a name="hiber.easypulse.Easypulse.UpdateAssets.Request"></a>

### Easypulse.UpdateAssets.Request
Request to update your Assets, renaming, updating tags, etc.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| organization | [string](#string) |  | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [Easypulse.AssetSelection](#hiber.easypulse.Easypulse.AssetSelection) |  | Select the asset(s) to update. |
| result_pagination | [hiber.Pagination](#hiber.Pagination) |  | Pagination for the returned assets. Does not affect the amount of assets that are updated. |
| rename | [string](#string) |  | Change the asset name to the given value. Ignored if empty. |
| notes | [string](#string) |  | Update the notes for the selected assets. Expects the original notes to be identical, unless allow_override_existing_notes is set. |
| secure_notes | [string](#string) |  | Update the secure notes for the selected assets. Expects the original notes to be identical, unless allow_override_existing_notes is set. |
| update_tags | [hiber.tag.UpdateTagsForItem](#hiber.tag.UpdateTagsForItem) |  | Update the tags for the selected assets. |
| add_peripherals | [Easypulse.UpdateAssets.Request.AddPeripheralsEntry](#hiber.easypulse.Easypulse.UpdateAssets.Request.AddPeripheralsEntry) | repeated | Add or update peripherals for the selected assets. |
| remove_peripherals | [string](#string) | repeated | Remove peripherals from the selected assets. |
| allow_override_existing_notes | [bool](#bool) |  | When you try to set a new notes value to multiple assets, the API returns an error if their previous values were different. Set this to true to apply it anyway. |






<a name="hiber.easypulse.Easypulse.UpdateAssets.Request.AddPeripheralsEntry"></a>

### Easypulse.UpdateAssets.Request.AddPeripheralsEntry



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| key | [string](#string) |  |  |
| value | [string](#string) |  |  |






<a name="hiber.easypulse.Easypulse.UpdateAssets.Response"></a>

### Easypulse.UpdateAssets.Response
The updated Assets, paginated to limit the returned amount.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| assets | [Easypulse.Asset](#hiber.easypulse.Easypulse.Asset) | repeated | The (page of) updated Assets. |
| pagination | [hiber.Pagination.Result](#hiber.Pagination.Result) |  | The applied pagination, including total results, page information, etc. |
| request | [Easypulse.UpdateAssets.Request](#hiber.easypulse.Easypulse.UpdateAssets.Request) |  | The request that was received, corrected and used to produce this result. |





 


<a name="hiber.easypulse.Easypulse.History.Request.Aggregation"></a>

### Easypulse.History.Request.Aggregation
Options to aggregate the history data points (in a group).

| Name | Number | Description |
| ---- | ------ | ----------- |
| NONE | 0 | Do not aggregate the history data points, just list all of them. |
| AVERAGE | 1 | Average value of all history data points (in a group). |
| SUM | 2 | Sum all history data points (in a group). |



<a name="hiber.easypulse.Easypulse.ListAssets.Request.Sort"></a>

### Easypulse.ListAssets.Request.Sort


| Name | Number | Description |
| ---- | ------ | ----------- |
| NAME | 0 |  |
| NAME_DESC | 1 |  |
| LAST_UPDATED | 2 |  |
| INACTIVITY | 3 |  |
| NUMBER_ASC | 4 |  |
| NUMBER_DESC | 5 |  |
| LOWEST_FUEL_LEVEL | 6 |  |
| HIGHEST_FUEL_LEVEL | 7 |  |
| LOWEST_TIRE_PRESSURE | 8 |  |
| HIGHEST_TIRE_PRESSURE | 9 |  |
| LOWEST_BATTERY_LEVEL | 10 |  |
| HIGHEST_BATTERY_LEVEL | 11 |  |


 

 


<a name="hiber.easypulse.EasypulseService"></a>

### EasypulseService
Service to list and manage Assets.

| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| Assets | [Easypulse.ListAssets.Request](#hiber.easypulse.Easypulse.ListAssets.Request) | [Easypulse.ListAssets.Response](#hiber.easypulse.Easypulse.ListAssets.Response) |  |
| Update | [Easypulse.UpdateAssets.Request](#hiber.easypulse.Easypulse.UpdateAssets.Request) | [Easypulse.UpdateAssets.Response](#hiber.easypulse.Easypulse.UpdateAssets.Response) |  |
| History | [Easypulse.History.Request](#hiber.easypulse.Easypulse.History.Request) | [Easypulse.History.Response](#hiber.easypulse.Easypulse.History.Response) |  |

 



<a name="health.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## health.proto



<a name="hiber.health.AddHealthLevel"></a>

### AddHealthLevel







<a name="hiber.health.AddHealthLevel.Request"></a>

### AddHealthLevel.Request



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| organization | [string](#string) |  | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| new_health_level | [HealthLevel](#hiber.health.HealthLevel) |  | Add the given level to the organizations health levels. The new health level will be added with the highest severity (at the bottom of the health levels list). |






<a name="hiber.health.AddHealthLevel.Response"></a>

### AddHealthLevel.Response



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| health_levels | [HealthLevel](#hiber.health.HealthLevel) | repeated |  |






<a name="hiber.health.HealthLevel"></a>

### HealthLevel
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

Health levels are ordered by severity (low to high), and only the most severe level will be returned when
retrieving a modem.

Health can be assigned using modems alarms, which specify the health level they will cause on a modem (and for how
long, if it does not resolve automatically).

Precisely one health level can be assigned as a catch-all for any unknown health levels from alarms (or Hiber systems),
which can happen when a device manufacturer has provided alarms to your device (e.g. a low battery alarm).
By default, any unknown health levels map to the level that is marked catch-all.

Health level have a set of named colors, represented by a map where the key is the name of the color
and the value is a string that represents a valid CSS3 color.
Simple examples are: green, red, orange, grey, #FF00FF for fuchsia, etc (Keep in mind that CSS3 allows for many
ways to define colors, see https://www.w3.org/TR/2003/WD-css3-color-20030214/).

All the following definitions also mean &#34;red&#34;:
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


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| level | [string](#string) |  | The name of this health level. Levels are identified by their name. The API does support renaming, where the rename is propagated to all the relevant parts of the system. |
| color | [string](#string) |  | **Deprecated.** Default color for the health level, as a string that represents a valid CSS3 color. DEPRECATED: Maps to the color named &#34;text&#34; in color_data. |
| color_data | [HealthLevel.ColorDataEntry](#hiber.health.HealthLevel.ColorDataEntry) | repeated | Map of named colors, where key is the name and the value is a valid CSS3 color definition. |
| severity | [int64](#int64) |  | A numeric value equal to the index of this health level in the sorted list of health levels (starting at 1). This means higher numbers denote a more severe health. |
| catch_all | [bool](#bool) |  | Precisely one health level can be assigned as a catch-all for any unknown health levels from alarms (or Hiber systems), which can happen when a device manufacturer has provided alarms for your device (e.g. a low battery alarm). By default, unknown health levels map to the level of the highest severity, unless another level is marked as catch-all. |






<a name="hiber.health.HealthLevel.ColorDataEntry"></a>

### HealthLevel.ColorDataEntry



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| key | [string](#string) |  |  |
| value | [string](#string) |  |  |






<a name="hiber.health.HealthLevelSelection"></a>

### HealthLevelSelection



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| search | [string](#string) |  | Search for the given string in the levels and colors. |
| levels | [string](#string) | repeated | Filter by exact levels. |






<a name="hiber.health.ListHealthLevels"></a>

### ListHealthLevels







<a name="hiber.health.ListHealthLevels.Request"></a>

### ListHealthLevels.Request



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| organization | [string](#string) |  | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [HealthLevelSelection](#hiber.health.HealthLevelSelection) |  |  |






<a name="hiber.health.ListHealthLevels.Response"></a>

### ListHealthLevels.Response



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| health_levels | [HealthLevel](#hiber.health.HealthLevel) | repeated |  |
| request | [ListHealthLevels.Request](#hiber.health.ListHealthLevels.Request) |  |  |






<a name="hiber.health.RemoveHealthLevel"></a>

### RemoveHealthLevel







<a name="hiber.health.RemoveHealthLevel.Request"></a>

### RemoveHealthLevel.Request



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| organization | [string](#string) |  | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| level | [string](#string) |  |  |






<a name="hiber.health.RemoveHealthLevel.Response"></a>

### RemoveHealthLevel.Response



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| health_levels | [HealthLevel](#hiber.health.HealthLevel) | repeated |  |






<a name="hiber.health.ReorderHealthLevels"></a>

### ReorderHealthLevels
Re-order the health levels for your organization.






<a name="hiber.health.ReorderHealthLevels.Request"></a>

### ReorderHealthLevels.Request



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| organization | [string](#string) |  | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| levels | [string](#string) | repeated | The health levels for the organization, ordered by severity (low to high). This list must include _all_ health levels, or the call will fail. The implication is, that if someone adds, removes or renames a level just before this call is sent, then this call will fail to protect against strange results. |






<a name="hiber.health.ReorderHealthLevels.Response"></a>

### ReorderHealthLevels.Response



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| reordered_health_levels | [HealthLevel](#hiber.health.HealthLevel) | repeated |  |






<a name="hiber.health.UpdateHealthLevel"></a>

### UpdateHealthLevel







<a name="hiber.health.UpdateHealthLevel.Request"></a>

### UpdateHealthLevel.Request



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| organization | [string](#string) |  | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| level | [string](#string) |  |  |
| rename | [string](#string) |  | Optionally, rename this health level. NOTE! Don&#39;t use this to change the semantics of a health level. All historic events that have this health-level will change with it. (Unless you are very sure you want to change history, that is) |
| update_color | [hiber.UpdateClearableString](#hiber.UpdateClearableString) |  | **Deprecated.** Optionally, set or update the color for this health level. DEPRECATED, use add_colors with name &#34;text&#34;. Vice versa, this field will also update the &#34;text&#34; color in the color_data field of HealthLevel. |
| remove_colors | [string](#string) | repeated | Remove colors by name. Will remove the named color from the color_data field in HealthLevel. |
| add_colors | [UpdateHealthLevel.Request.AddColorsEntry](#hiber.health.UpdateHealthLevel.Request.AddColorsEntry) | repeated | Add colors by name. Will add the named color from the color_data field in HealthLevel. For backwards compatibility reasons, if add_colors contains a color named &#34;text&#34;, it will also update the field color in HealthLevel |
| update_catch_all | [hiber.UpdateBoolean](#hiber.UpdateBoolean) |  | Optionally, set or unset the catch all flag. |






<a name="hiber.health.UpdateHealthLevel.Request.AddColorsEntry"></a>

### UpdateHealthLevel.Request.AddColorsEntry



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| key | [string](#string) |  |  |
| value | [string](#string) |  |  |






<a name="hiber.health.UpdateHealthLevel.Response"></a>

### UpdateHealthLevel.Response



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| health_levels | [HealthLevel](#hiber.health.HealthLevel) | repeated |  |





 

 

 


<a name="hiber.health.HealthService"></a>

### HealthService


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| List | [ListHealthLevels.Request](#hiber.health.ListHealthLevels.Request) | [ListHealthLevels.Response](#hiber.health.ListHealthLevels.Response) | List the health levels. |
| Reorder | [ReorderHealthLevels.Request](#hiber.health.ReorderHealthLevels.Request) | [ReorderHealthLevels.Response](#hiber.health.ReorderHealthLevels.Response) | Reorder the health levels, changing the order of severity. |
| Add | [AddHealthLevel.Request](#hiber.health.AddHealthLevel.Request) | [AddHealthLevel.Response](#hiber.health.AddHealthLevel.Response) | Add a new health level at the end of the list (highest severity). |
| Update | [UpdateHealthLevel.Request](#hiber.health.UpdateHealthLevel.Request) | [UpdateHealthLevel.Response](#hiber.health.UpdateHealthLevel.Response) | Update or rename a health level. |
| Remove | [RemoveHealthLevel.Request](#hiber.health.RemoveHealthLevel.Request) | [RemoveHealthLevel.Response](#hiber.health.RemoveHealthLevel.Response) | Remove a health level. Any events with that level are redirected to the catch-all level. |

 



<a name="tag.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## tag.proto



<a name="hiber.tag.CreateTagRequest"></a>

### CreateTagRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| organization | [string](#string) |  | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| create | [Tag.Label](#hiber.tag.Tag.Label) |  |  |






<a name="hiber.tag.DeleteTagRequest"></a>

### DeleteTagRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| organization | [string](#string) |  | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| id | [int64](#int64) |  |  |






<a name="hiber.tag.DeleteTagRequest.Response"></a>

### DeleteTagRequest.Response







<a name="hiber.tag.ListTagsRequest"></a>

### ListTagsRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| organization | [string](#string) |  | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [TagSelection](#hiber.tag.TagSelection) |  |  |
| modem_count | [bool](#bool) |  |  |
| webhook_count | [bool](#bool) |  |  |






<a name="hiber.tag.ListTagsRequest.Response"></a>

### ListTagsRequest.Response



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tags | [Tag](#hiber.tag.Tag) | repeated |  |
| request | [ListTagsRequest](#hiber.tag.ListTagsRequest) |  |  |
| tag_modem_count | [ListTagsRequest.Response.TagModemCountEntry](#hiber.tag.ListTagsRequest.Response.TagModemCountEntry) | repeated |  |
| tag_webhook_count | [ListTagsRequest.Response.TagWebhookCountEntry](#hiber.tag.ListTagsRequest.Response.TagWebhookCountEntry) | repeated |  |






<a name="hiber.tag.ListTagsRequest.Response.TagModemCountEntry"></a>

### ListTagsRequest.Response.TagModemCountEntry



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| key | [int64](#int64) |  |  |
| value | [int32](#int32) |  |  |






<a name="hiber.tag.ListTagsRequest.Response.TagWebhookCountEntry"></a>

### ListTagsRequest.Response.TagWebhookCountEntry



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| key | [int64](#int64) |  |  |
| value | [int32](#int32) |  |  |






<a name="hiber.tag.Tag"></a>

### Tag



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [int64](#int64) |  |  |
| label | [Tag.Label](#hiber.tag.Tag.Label) |  |  |






<a name="hiber.tag.Tag.Label"></a>

### Tag.Label



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| name | [string](#string) |  |  |






<a name="hiber.tag.TagSelection"></a>

### TagSelection



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| search | [string](#string) | repeated |  |
| names | [string](#string) | repeated |  |
| filter | [hiber.Filter.Tags](#hiber.Filter.Tags) |  |  |






<a name="hiber.tag.UpdateTagRequest"></a>

### UpdateTagRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| organization | [string](#string) |  | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| id | [int64](#int64) |  |  |
| update | [Tag.Label](#hiber.tag.Tag.Label) |  |  |






<a name="hiber.tag.UpdateTagsForItem"></a>

### UpdateTagsForItem



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tag_ids_to_add | [int64](#int64) | repeated |  |
| tag_ids_to_remove | [int64](#int64) | repeated |  |
| new_tags_to_add | [Tag.Label](#hiber.tag.Tag.Label) | repeated |  |





 

 

 


<a name="hiber.tag.TagService"></a>

### TagService
Tag management api calls. You can already get tags for objects when you get their data, and even create new tags
when updating them, so these calls are meant for easier tag management if you need it.

| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| List | [ListTagsRequest](#hiber.tag.ListTagsRequest) | [ListTagsRequest.Response](#hiber.tag.ListTagsRequest.Response) |  |
| Create | [CreateTagRequest](#hiber.tag.CreateTagRequest) | [Tag](#hiber.tag.Tag) |  |
| Update | [UpdateTagRequest](#hiber.tag.UpdateTagRequest) | [Tag](#hiber.tag.Tag) |  |
| Delete | [DeleteTagRequest](#hiber.tag.DeleteTagRequest) | [DeleteTagRequest.Response](#hiber.tag.DeleteTagRequest.Response) |  |

 



<a name="base.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## base.proto



<a name="hiber.Area"></a>

### Area
Rectangular area between two locations, normalized to bottom-left and top-right points.
Center point is added for convenience; it&#39;s simple the point directly between the two corner points.
When sending an Area to the api, the center location is ignored.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| center | [Location](#hiber.Location) |  |  |
| bottom_left | [Location](#hiber.Location) |  |  |
| top_right | [Location](#hiber.Location) |  |  |






<a name="hiber.Avatar"></a>

### Avatar
An avatar is represented either by a (publicly) fetchable URL that serves an image,
xor a binary payload that knows its name and mime-type.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| url | [string](#string) |  | A URL that contains the location of avatar. It must be obtainable without credentials, though this is not validated by the API. Because the content behind URL&#39;s can change or become unavailable over time, the client should make sure it properly caches the data fetched from the URL. (&#34;Properly&#34; means [among other things] respecting the response headers for this resource) |
| image | [NamedFile](#hiber.NamedFile) |  | The data of the avatar as a Named File When showing this image in a browser, one can make use of a `data` URI. The client must convert the bytes to base64 and can then construct a data URI like this

data:&lt;media-type&gt;;base64,&lt;base64-encoded-bytes&gt;

Other type clients should be able to sort-of-directly set the data bytes as the source for an image. |






<a name="hiber.BytesOrHex"></a>

### BytesOrHex
Some clients may prefer direct binary data, while other prefer a hexadecimal string,
both for input and output. To support both methods, this object is used to represent binary data.
When you receive this from the api, both fields are set. When sending it to the api, only one field is required.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| bytes | [bytes](#bytes) |  |  |
| hex | [string](#string) |  |  |






<a name="hiber.BytesOrHex.Update"></a>

### BytesOrHex.Update



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| updated | [bool](#bool) |  |  |
| value | [BytesOrHex](#hiber.BytesOrHex) |  |  |






<a name="hiber.Date"></a>

### Date
Date type for convenience.
Some clients are better at parsing year, month and day of month as separate fields,
while others prefer a text-based format.
To accommodate this, this Date type supports both.
When used as API output, both the int fields and textual fields will be set.
The textual field has the commonly used ISO 8601 local date format (i.e. &#34;2018-01-01&#34;).
When used an API input, either specify the int fields or the textual field.
If both are specified, the textual field will be discarded.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| year | [uint32](#uint32) |  |  |
| month | [uint32](#uint32) |  |  |
| day | [uint32](#uint32) |  |  |
| textual | [string](#string) |  |  |






<a name="hiber.DoubleRange"></a>

### DoubleRange
Decimal range.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| start | [double](#double) |  |  |
| end | [double](#double) |  |  |






<a name="hiber.Duration"></a>

### Duration



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| duration | [google.protobuf.Duration](#google.protobuf.Duration) |  |  |
| textual | [string](#string) |  |  |






<a name="hiber.Filter"></a>

### Filter
Filters used in many api calls to filter the data sources, results, etc.

&#34;Include&#34; fields filter out anything not in the include set.
When not set, all items will be returned (except excluded items)
&#34;Exclude&#34; fields filter out anything in the exclude set.
When combined with include, exclude takes precedence when determining whether an item is filtered






<a name="hiber.Filter.ChildOrganizations"></a>

### Filter.ChildOrganizations
Specify which organizations to get data from. By default, data is only retrieved for the current organization, but
using ChildOrganizations we can specify to include a number of, or all, sub-organizations.

Note: ChildOrganization differs from other filters in that it defaults to not allowing anything, where the
other filters default to allowing everything


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| include_all | [bool](#bool) |  |  |
| include | [string](#string) | repeated |  |
| exclude | [string](#string) | repeated |  |






<a name="hiber.Filter.ChildOrganizations.Update"></a>

### Filter.ChildOrganizations.Update
Update object to update a Filter.ChildOrganizations field.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| updated | [bool](#bool) |  |  |
| value | [Filter.ChildOrganizations](#hiber.Filter.ChildOrganizations) |  |  |






<a name="hiber.Filter.Events"></a>

### Filter.Events



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| include | [EventType](#hiber.EventType) | repeated |  |
| exclude | [EventType](#hiber.EventType) | repeated |  |






<a name="hiber.Filter.Events.Update"></a>

### Filter.Events.Update
Update object to update a Filter.Events field.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| updated | [bool](#bool) |  |  |
| value | [Filter.Events](#hiber.Filter.Events) |  |  |






<a name="hiber.Filter.Modems"></a>

### Filter.Modems



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| include | [string](#string) | repeated | Include all modems with these modem numbers (HEX) |
| exclude | [string](#string) | repeated | Exclude all modems with these modem numbers (HEX). Exclude takes precedence over include. |






<a name="hiber.Filter.Modems.Update"></a>

### Filter.Modems.Update
Update object to update a Filter.Modems field.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| updated | [bool](#bool) |  |  |
| value | [Filter.Modems](#hiber.Filter.Modems) |  |  |






<a name="hiber.Filter.OrganizationPermissions"></a>

### Filter.OrganizationPermissions



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| include_all | [bool](#bool) |  |  |
| include | [OrganizationPermission](#hiber.OrganizationPermission) | repeated |  |
| exclude | [OrganizationPermission](#hiber.OrganizationPermission) | repeated |  |






<a name="hiber.Filter.Organizations"></a>

### Filter.Organizations



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| include | [string](#string) | repeated |  |
| exclude | [string](#string) | repeated |  |






<a name="hiber.Filter.Publishers"></a>

### Filter.Publishers



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| include | [int64](#int64) | repeated |  |
| exclude | [int64](#int64) | repeated |  |
| only_active | [bool](#bool) |  |  |






<a name="hiber.Filter.Tags"></a>

### Filter.Tags



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| include | [int64](#int64) | repeated |  |
| exclude | [int64](#int64) | repeated |  |






<a name="hiber.Filter.Tags.Update"></a>

### Filter.Tags.Update
Update object to update a Filter.Tags field.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| updated | [bool](#bool) |  |  |
| value | [Filter.Tags](#hiber.Filter.Tags) |  |  |






<a name="hiber.Filter.UserPermissions"></a>

### Filter.UserPermissions



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| include_all | [bool](#bool) |  |  |
| include | [UserPermission](#hiber.UserPermission) | repeated |  |
| exclude | [UserPermission](#hiber.UserPermission) | repeated |  |






<a name="hiber.Filter.Users"></a>

### Filter.Users



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| include | [string](#string) | repeated |  |
| exclude | [string](#string) | repeated |  |






<a name="hiber.Filter.Webhooks"></a>

### Filter.Webhooks



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| include | [int64](#int64) | repeated |  |
| exclude | [int64](#int64) | repeated |  |
| only_active | [bool](#bool) |  |  |






<a name="hiber.Location"></a>

### Location
Geographic latitude and longitude coordinates specified in decimal degrees.
For more information, see the WGS-84 coordinate system, which is used for most GPS systems.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| latitude | [double](#double) |  | Decimal degrees north. |
| longitude | [double](#double) |  | Decimal degrees east. |






<a name="hiber.LocationSelection"></a>

### LocationSelection
Selection object for map data. Filter modems on the map by id, (child)organization.
Also, filter the map data by level and area restriction, to only display a small area at a detailed map level,
for example


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| areas | [Area](#hiber.Area) | repeated | Rectangular areas, each defined by two locations, normalized to bottom-left and top-right points. |
| shapes | [Shape](#hiber.Shape) | repeated | Polygon shapes, each defined by a list of locations, which draw a shape on the map. |






<a name="hiber.NamedFile"></a>

### NamedFile
A NamedFile contains bytes with its mime-type and name.
It can represent any file of any type.
Note that depending on where in the API this is used,
the server might put restrictions on file size, media-type or name length.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| data | [BytesOrHex](#hiber.BytesOrHex) |  | The binary payload that represents the file |
| media_type | [string](#string) |  | The media-type of the file, as defined by RFC 6838 or its extensions |
| name | [string](#string) |  | A semantic name for this file. The name should be interpreted as-is. No hierarchical information is stored in the name, nor should you look at the &#34;extension&#34; to know its media-type. It might not even have a file extension.

Also note that this file may contain characters that cannot be a valid file name on certain systems.

Specific API calls may limit the validness of this field. For example setting a maximum length or disallowing certain characters. |






<a name="hiber.Pagination"></a>

### Pagination
Pagination is normalized across the api. Provide a pagination object to get a specific page or offset,
or limit your data.

Calls that have a pagination option automatically return a Pagination.Result, which contains
either the specified pagination options or the defaults, as well as total counts. It also contains Pagination
objects that can be used for the previous and next page.

This effectively means that an api user would never need to create their own pagination object; as long as they
start at the first page and continue to the next, they can use the provided Pagination object.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| size | [int32](#int32) |  |  |
| page | [int32](#int32) |  |  |






<a name="hiber.Pagination.Result"></a>

### Pagination.Result



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| size | [int32](#int32) |  |  |
| page | [int32](#int32) |  |  |
| total | [int32](#int32) |  |  |
| total_pages | [int32](#int32) |  |  |
| previous | [Pagination](#hiber.Pagination) |  |  |
| next | [Pagination](#hiber.Pagination) |  |  |
| approximated_total | [bool](#bool) |  | Indicates that the total is an approximation, and not an exact value. This can be set for data that changes often, or is generally only fetched in an infinite scrolling manner. For example, unbundled events are likely to return an approximated total, but not guaranteed to do so. |






<a name="hiber.Shape"></a>

### Shape
Polygon shape defined by a list of locations, which draw a shape on the map.
The last point is connected to the first to close the shape.
For example, the outline of a city would be defined using a Shape,
while a rectangular region is easier to define using Area.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| path | [Location](#hiber.Location) | repeated |  |






<a name="hiber.TimeRange"></a>

### TimeRange
Period of time between two timestamps. Typically used for filtering.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| start | [Timestamp](#hiber.Timestamp) |  |  |
| end | [Timestamp](#hiber.Timestamp) |  |  |






<a name="hiber.Timestamp"></a>

### Timestamp
Timestamp type for convenience.
Some clients are better at parsing Google&#39;s seconds/nanos based timestamp, while others prefer a text-based format.
To accommodate this, this Timestamp type supports both.
When used as API output, both the timestamp and textual fields will be set. The textual field has the commonly
used ISO 8601 format (i.e. &#34;2018-01-01T13:00:00Z&#34;).
When used an API input, only one of the fields is needed, there is no need to set both. When both are set, the
timestamp field will be used, the textual field will be discarded.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| timestamp | [google.protobuf.Timestamp](#google.protobuf.Timestamp) |  |  |
| textual | [string](#string) |  |  |






<a name="hiber.UpdateBoolean"></a>

### UpdateBoolean
Update object for a boolean.
Since false is the default value, we need to distinguish between an omitted value and setting the value to false,
in an update object.

To use this to update, set a value and set updated to true


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| updated | [bool](#bool) |  |  |
| value | [bool](#bool) |  |  |






<a name="hiber.UpdateClearableString"></a>

### UpdateClearableString
Update object for a string that can be empty.
Since an empty string is also the default value, we need to distinguish between an omitted value and
setting the value to an empty string, in an update object.

To use this to update, set a value and set updated to true


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| updated | [bool](#bool) |  |  |
| value | [string](#string) |  |  |






<a name="hiber.UpdateOptionalDuration"></a>

### UpdateOptionalDuration
Update object for an optional Duration.

To use this to update, set a value and set updated to true.
To clear the duration, set updated to true, but set no value.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| updated | [bool](#bool) |  |  |
| value | [Duration](#hiber.Duration) |  |  |






<a name="hiber.UpdateOptionalId"></a>

### UpdateOptionalId
Update object for an optional id.

To use this to update, set a value and set updated to true. To clear the id, set updated to true, but set no value.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| updated | [bool](#bool) |  |  |
| value | [int64](#int64) |  |  |






<a name="hiber.UpdateZeroableInt"></a>

### UpdateZeroableInt
Update object for an int that can be set to 0.
Since 0 is also the default value, we need to distinguish between an omitted value and setting the value to 0,
in an update object.

To use this to update, set a value and set updated to true


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| updated | [bool](#bool) |  |  |
| value | [uint32](#uint32) |  |  |





 


<a name="hiber.EventType"></a>

### EventType
Enum of api-accessible events.
The event types in this enum have a protobuf implementation, and can be used, for example, in the
api event stream and publishers.

| Name | Number | Description |
| ---- | ------ | ----------- |
| DEFAULT | 0 |  |
| ORGANIZATION_CREATED | 34 |  |
| ORGANIZATION_UPDATED | 12 |  |
| ORGANIZATION_DELETED | 35 |  |
| ORGANIZATION_EVENT_CONFIGURATION_UPDATED | 43 |  |
| MODEM_CREATED | 55 |  |
| MODEM_UPDATED | 36 |  |
| MODEM_LOCATION_UPDATED | 4 |  |
| MODEM_ACTIVATED | 33 |  |
| MODEM_STALE | 16 |  |
| MODEM_MESSAGE_RECEIVED | 5 |  |
| MODEM_MESSAGE_BODY_PARSED | 39 |  |
| MODEM_MESSAGE_BODY_RECEIVED | 45 |  |
| MODEM_MESSAGE_DROPPED | 13 |  |
| MODEM_MESSAGE_DELAYED | 14 |  |
| MODEM_MESSAGE_CANNOT_BE_PARSED | 15 |  |
| MODEM_MESSAGE_SUMMARY | 42 |  |
| MODEM_MESSAGE_BODY_PARSER_CREATED | 46 |  |
| MODEM_MESSAGE_BODY_PARSER_UPDATED | 47 |  |
| MODEM_MESSAGE_BODY_PARSER_DELETED | 48 |  |
| MODEM_MESSAGE_BODY_PARSER_AUTOMATIC_ASSIGNMENT_CREATED | 49 |  |
| MODEM_MESSAGE_BODY_PARSER_AUTOMATIC_ASSIGNMENT_UPDATED | 50 |  |
| MODEM_MESSAGE_BODY_PARSER_AUTOMATIC_ASSIGNMENT_DELETED | 51 |  |
| MODEM_MESSAGE_BODY_PARSER_ASSIGNED | 52 |  |
| MODEM_MESSAGE_BODY_PARSER_UNASSIGNED | 53 |  |
| MODEM_ALARM | 56 |  |
| MODEM_ALARM_CREATED | 57 |  |
| MODEM_ALARM_UPDATED | 58 |  |
| MODEM_ALARM_DELETED | 59 |  |
| DIRECT_ASSIGNMENT_ADDED | 63 |  |
| DIRECT_ASSIGNMENT_REMOVED | 64 |  |
| AUTOMATIC_MODEM_ASSIGNMENT_CREATED | 60 |  |
| AUTOMATIC_MODEM_ASSIGNMENT_UPDATED | 61 |  |
| AUTOMATIC_MODEM_ASSIGNMENT_DELETED | 62 |  |
| MODEM_TRANSFER_STARTED | 17 |  |
| MODEM_TRANSFER_RECEIVED | 18 |  |
| MODEM_TRANSFER_CANCELLED | 19 |  |
| MODEM_TRANSFER_NOT_RECEIVED | 20 |  |
| MODEM_TRANSFER_RETURN_TRANSFER_STARTED | 21 |  |
| MODEM_CLAIMED | 22 |  |
| PUBLISHER_CREATED | 1 |  |
| PUBLISHER_UPDATED | 2 |  |
| PUBLISHER_DELETED | 3 |  |
| PUBLISHER_AUTO_DISABLED | 37 |  |
| PUBLISHER_FAILED | 11 |  |
| USER_ACCESS_REQUEST | 8 |  |
| USER_INVITED | 38 |  |
| USER_ADDED | 9 |  |
| USER_REMOVED | 10 |  |
| USER_VALIDATION_UPDATED | 54 |  |
| TOKEN_CREATED | 31 |  |
| TOKEN_EXPIRY_WARNING | 25 |  |
| TOKEN_EXPIRED | 26 |  |
| TOKEN_DELETED | 32 |  |
| EXPORT_CREATED | 65 |  |
| EXPORT_READY | 66 |  |
| EXPORT_FAILED | 67 |  |



<a name="hiber.Health"></a>

### Health
Health is an indicator for issues. It is used for publishers to give a quick indication of issues.

| Name | Number | Description |
| ---- | ------ | ----------- |
| OK | 0 |  |
| WARNING | 1 |  |
| ERROR | 2 |  |


 

 

 



## Scalar Value Types

| .proto Type | Notes | C++ | Java | Python | Go | C# | PHP | Ruby |
| ----------- | ----- | --- | ---- | ------ | -- | -- | --- | ---- |
| <a name="double" /> double |  | double | double | float | float64 | double | float | Float |
| <a name="float" /> float |  | float | float | float | float32 | float | float | Float |
| <a name="int32" /> int32 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint32 instead. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="int64" /> int64 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint64 instead. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="uint32" /> uint32 | Uses variable-length encoding. | uint32 | int | int/long | uint32 | uint | integer | Bignum or Fixnum (as required) |
| <a name="uint64" /> uint64 | Uses variable-length encoding. | uint64 | long | int/long | uint64 | ulong | integer/string | Bignum or Fixnum (as required) |
| <a name="sint32" /> sint32 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int32s. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="sint64" /> sint64 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int64s. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="fixed32" /> fixed32 | Always four bytes. More efficient than uint32 if values are often greater than 2^28. | uint32 | int | int | uint32 | uint | integer | Bignum or Fixnum (as required) |
| <a name="fixed64" /> fixed64 | Always eight bytes. More efficient than uint64 if values are often greater than 2^56. | uint64 | long | int/long | uint64 | ulong | integer/string | Bignum |
| <a name="sfixed32" /> sfixed32 | Always four bytes. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="sfixed64" /> sfixed64 | Always eight bytes. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="bool" /> bool |  | bool | boolean | boolean | bool | bool | boolean | TrueClass/FalseClass |
| <a name="string" /> string | A string must always contain UTF-8 encoded or 7-bit ASCII text. | string | String | str/unicode | string | string | string | String (UTF-8) |
| <a name="bytes" /> bytes | May contain any arbitrary sequence of bytes. | string | ByteString | str | []byte | ByteString | string | String (ASCII-8BIT) |

