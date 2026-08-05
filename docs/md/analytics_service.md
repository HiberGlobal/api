# analytics_service.proto



#### This file was generated from [analytics_service.proto](https://github.com/HiberGlobal/api/blob/master/analytics_service.proto).

## Table of Contents

- Services
  - [AnalyticsService](#analyticsservice)

- Messages
  - [Analytics](#analytics)
  - [Analytics.Request](#analyticsrequest)
  - [Analytics.Response](#analyticsresponse)
  - [Analytics.Result](#analyticsresult)

- Enums

- Referenced messages from [value_service.proto](#referenced-messages-from-value_serviceproto)
  - [hiber.value.AggregatedValues](#hibervalueaggregatedvalues)
  - [hiber.value.AggregatedValues.Aggregation](#hibervalueaggregatedvaluesaggregation)
  - [hiber.value.AggregatedValues.Aggregation.CountResult](#hibervalueaggregatedvaluesaggregationcountresult)
  - [hiber.value.AggregatedValues.Aggregation.PercentileAggregation](#hibervalueaggregatedvaluesaggregationpercentileaggregation)
  - [hiber.value.AggregatedValues.Request](#hibervalueaggregatedvaluesrequest)
  - [hiber.value.AggregatedValues.Response](#hibervalueaggregatedvaluesresponse)
  - [hiber.value.DownsampledValues](#hibervaluedownsampledvalues)
  - [hiber.value.DownsampledValues.Request](#hibervaluedownsampledvaluesrequest)
  - [hiber.value.DownsampledValues.Response](#hibervaluedownsampledvaluesresponse)
  - [hiber.value.LatestValues](#hibervaluelatestvalues)
  - [hiber.value.LatestValues.Request](#hibervaluelatestvaluesrequest)
  - [hiber.value.LatestValues.Response](#hibervaluelatestvaluesresponse)
  - [hiber.value.ListValues](#hibervaluelistvalues)
  - [hiber.value.ListValues.Request](#hibervaluelistvaluesrequest)
  - [hiber.value.ListValues.Request.TransformFieldsEntry](#hibervaluelistvaluesrequesttransformfieldsentry)
  - [hiber.value.ListValues.Response](#hibervaluelistvaluesresponse)
  - [hiber.value.ValueContext](#hibervaluevaluecontext)
  - [hiber.value.ValueContext.ValueDelta](#hibervaluevaluecontextvaluedelta)
  - [hiber.value.ValueContext.ValueDeviceContext](#hibervaluevaluecontextvaluedevicecontext)
  - [hiber.value.ValueContext.ValueDuration](#hibervaluevaluecontextvalueduration)
  - [hiber.value.ValueContext.ValueDurations](#hibervaluevaluecontextvaluedurations)
  - [hiber.value.ValueContext.ValueProcessPointContext](#hibervaluevaluecontextvalueprocesspointcontext)
  - [hiber.value.ValueSelection](#hibervaluevalueselection)
  - [hiber.value.ValueSelection.ByField](#hibervaluevalueselectionbyfield)
  - [hiber.value.ValueSelection.ByValueType](#hibervaluevalueselectionbyvaluetype)

    - [hiber.value.AggregatedValues.Aggregation.BasicAggregation](#hibervalueaggregatedvaluesaggregationbasicaggregation)
    - [hiber.value.AggregatedValues.Aggregation.PercentileAggregation.PercentileAggregationMethod](#hibervalueaggregatedvaluesaggregationpercentileaggregationpercentileaggregationmethod)
    - [hiber.value.ListValues.Sort](#hibervaluelistvaluessort)

- Referenced messages from [base.proto](#referenced-messages-from-baseproto)
  - [hiber.Area](#hiberarea)
  - [hiber.BytesOrHex](#hiberbytesorhex)
  - [hiber.BytesOrHex.Update](#hiberbytesorhexupdate)
  - [hiber.Date](#hiberdate)
  - [hiber.DoubleRange](#hiberdoublerange)
  - [hiber.Duration](#hiberduration)
  - [hiber.Filter](#hiberfilter)
  - [hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations)
  - [hiber.Filter.ChildOrganizations.Update](#hiberfilterchildorganizationsupdate)
  - [hiber.Filter.DeviceTypes](#hiberfilterdevicetypes)
  - [hiber.Filter.Events](#hiberfilterevents)
  - [hiber.Filter.Events.Update](#hiberfiltereventsupdate)
  - [hiber.Filter.FieldEnumValues](#hiberfilterfieldenumvalues)
  - [hiber.Filter.HealthLevels](#hiberfilterhealthlevels)
  - [hiber.Filter.ModemIdentifiers](#hiberfiltermodemidentifiers)
  - [hiber.Filter.Modems](#hiberfiltermodems)
  - [hiber.Filter.Modems.Update](#hiberfiltermodemsupdate)
  - [hiber.Filter.OrganizationPermissions](#hiberfilterorganizationpermissions)
  - [hiber.Filter.Organizations](#hiberfilterorganizations)
  - [hiber.Filter.Properties](#hiberfilterproperties)
  - [hiber.Filter.Publishers](#hiberfilterpublishers)
  - [hiber.Filter.Roles](#hiberfilterroles)
  - [hiber.Filter.SensorBrands](#hiberfiltersensorbrands)
  - [hiber.Filter.SupportPermissions](#hiberfiltersupportpermissions)
  - [hiber.Filter.Tags](#hiberfiltertags)
  - [hiber.Filter.Tags.Update](#hiberfiltertagsupdate)
  - [hiber.Filter.UserPermissions](#hiberfilteruserpermissions)
  - [hiber.Filter.Users](#hiberfilterusers)
  - [hiber.Filter.Webhooks](#hiberfilterwebhooks)
  - [hiber.IntRange](#hiberintrange)
  - [hiber.Location](#hiberlocation)
  - [hiber.LocationSelection](#hiberlocationselection)
  - [hiber.MapFilter](#hibermapfilter)
  - [hiber.MapFilter.ExcludeEntry](#hibermapfilterexcludeentry)
  - [hiber.MapFilter.IncludeAndEntry](#hibermapfilterincludeandentry)
  - [hiber.MapFilter.OneOfValues](#hibermapfilteroneofvalues)
  - [hiber.Pagination](#hiberpagination)
  - [hiber.Pagination.Result](#hiberpaginationresult)
  - [hiber.Shape](#hibershape)
  - [hiber.TimeRange](#hibertimerange)
  - [hiber.TimeWindow](#hibertimewindow)
  - [hiber.TimeWindow.CalendarWindow](#hibertimewindowcalendarwindow)
  - [hiber.TimeWindow.IntervalWindow](#hibertimewindowintervalwindow)
  - [hiber.Timestamp](#hibertimestamp)
  - [hiber.UpdateBoolean](#hiberupdateboolean)
  - [hiber.UpdateClearableString](#hiberupdateclearablestring)
  - [hiber.UpdateOptionalDuration](#hiberupdateoptionalduration)
  - [hiber.UpdateOptionalId](#hiberupdateoptionalid)
  - [hiber.UpdateZeroableInt](#hiberupdatezeroableint)
  - Enums
    - [hiber.CalendarPeriod](#hibercalendarperiod)
    - [hiber.EventType](#hibereventtype)
    - [hiber.Health](#hiberhealth)
    - [hiber.UnitOfMeasurement](#hiberunitofmeasurement)

- [Scalar Value Types](#scalar-value-types)


## AnalyticsService


### Analytics
> **rpc** Analytics([Analytics.Request](#analyticsrequest))
    [Analytics.Response](#analyticsresponse)




## Messages

### Analytics



| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.value_aggregation | [ hiber.value.AggregatedValues.Request](#hibervalueaggregatedvaluesrequest) |  |

### Analytics.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| analytics | [repeated Analytics](#analytics) |  |

### Analytics.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| results | [repeated Analytics.Result](#analyticsresult) |  |
| request | [ Analytics.Request](#analyticsrequest) |  |

### Analytics.Result



| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.value_aggregation | [ hiber.value.AggregatedValues.Response](#hibervalueaggregatedvaluesresponse) |  |


## Enums


## Referenced messages from value_service.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [value_service.proto](https://github.com/HiberGlobal/api/blob/master/value_service.proto).


### hiber.value.AggregatedValues



| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **result**.value | [ hiber.value.Value](#hibervaluevalue) | The value resulting from the aggregation. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **result**.count | [ hiber.value.AggregatedValues.Aggregation.CountResult](#hibervalueaggregatedvaluesaggregationcountresult) | The count resulting from a COUNT or COUNT_DISTINCT aggregation. |
| aggregation | [ hiber.value.AggregatedValues.Aggregation](#hibervalueaggregatedvaluesaggregation) | The aggregation applied to get this value. |
|  **optional** window | [optional hiber.TimeWindow](#hibertimewindow) | The windowing configuration used for this value. |
|  **optional** time_range | [optional hiber.TimeRange](#hibertimerange) | The actual time range used for this aggregated value (e.g. window when windowing). |
|  **optional** device | [optional hiber.value.ValueContext.ValueDeviceContext](#hibervaluevaluecontextvaluedevicecontext) | If the selected values all belonged to a single device, or group_by_owner was set, the device. |
|  **optional** process_point | [optional hiber.value.ValueContext.ValueProcessPointContext](#hibervaluevaluecontextvalueprocesspointcontext) | If the selected values all belonged to a single process point, or group_by_owner was set, the process point. |

### hiber.value.AggregatedValues.Aggregation

Aggregation operation, e.g. min, max, count, sum or percentiles.

| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **aggregation**.basic | [ hiber.value.AggregatedValues.Aggregation.BasicAggregation](#hibervalueaggregatedvaluesaggregationbasicaggregation) | Basic aggregation options, e.g. average, min, max, etc. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **aggregation**.percentile | [ hiber.value.AggregatedValues.Aggregation.PercentileAggregation](#hibervalueaggregatedvaluesaggregationpercentileaggregation) | Configurable percentile aggregation option. |

### hiber.value.AggregatedValues.Aggregation.CountResult

Counting does not return a value, just an integer, but we do want to know what we counted.

| Field | Type | Description |
| ----- | ---- | ----------- |
| amount | [ uint32](#uint32) | Counted amount. |
| type | [ hiber.value.Value.Type](#hibervaluevaluetype) | Type of values counted. |
|  **optional** numeric_value_type | [optional hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype) | Numeric type of values counted, if type is numeric. |

### hiber.value.AggregatedValues.Aggregation.PercentileAggregation

Configurable percentile aggregation option.

| Field | Type | Description |
| ----- | ---- | ----------- |
| percentile | [ double](#double) | The percentile to aggregate to, e.g. 75th, 90th, 99th, 99.999th. (really any number, e.g. 88.12345 since it is a double) Values between 0 and 1 are interpreted as using a range of 0 to 1, e.g. 0.995 -> 99.5th percentile. Values higher than 100.0 or below 0 are not supported. |
| method | [ hiber.value.AggregatedValues.Aggregation.PercentileAggregation.PercentileAggregationMethod](#hibervalueaggregatedvaluesaggregationpercentileaggregationpercentileaggregationmethod) | The method of calculation used for the percentile value: continuous or discrete. |

### hiber.value.AggregatedValues.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.value.ValueSelection](#hibervaluevalueselection) | Select the values to aggregate. |
| aggregation | [repeated hiber.value.AggregatedValues.Aggregation](#hibervalueaggregatedvaluesaggregation) | Aggregation operation, e.g. min, max, count, sum or percentiles. |
|  **optional** window | [optional hiber.TimeWindow](#hibertimewindow) | Time window to aggregate values, e.g. minimum per hour, maximum per day, average per week, etc. |
|  **optional** group_by_owner | [optional bool](#bool) | If true, groups the selected values by their owner (device or process point) before applying the aggregation. For example, if the selection includes data from both process point A and process point B, requesting MAXIMUM will return two separate results: the maximum for process point A and the maximum for process point B. If false, all data is aggregated into a single value (per aggregation). |

### hiber.value.AggregatedValues.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| results | [repeated hiber.value.AggregatedValues](#hibervalueaggregatedvalues) | The aggregated values, for each operation and window result. |
| request | [ hiber.value.AggregatedValues.Request](#hibervalueaggregatedvaluesrequest) | The original request, corrected and filled in with any defaults. |

### hiber.value.DownsampledValues

Downsampled values for a (set of) modem(s), filtering by field and time.


### hiber.value.DownsampledValues.Request

Request downsampled values, reducing the selected time range to a single value per field.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.value.ValueSelection](#hibervaluevalueselection) | The values to downsample. When multiple modems are given, the data is downsampled separately and merged together in the response, sorted by time. |
|  **optional** points | [optional uint32](#uint32) | Downsample the values to the given amount of data points. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) | Paginate the downsampled values, if needed. |
| sort | [ hiber.value.ListValues.Sort](#hibervaluelistvaluessort) | How to sort the downsampled values. |
|  **optional** determine_minimum_and_maximum_values | [optional bool](#bool) | Determine the lowest and highest values for each owner (device / process point). |

### hiber.value.DownsampledValues.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| downsampled_values | [repeated hiber.value.ValueContext](#hibervaluevaluecontext) | The downsampled values, mixed together and sorted by time (see sort in request). |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |
| request | [ hiber.value.DownsampledValues.Request](#hibervaluedownsampledvaluesrequest) |  |
| lowest | [repeated hiber.value.ValueContext](#hibervaluevaluecontext) | The lowest value for each owner (device / process point). |
| highest | [repeated hiber.value.ValueContext](#hibervaluevaluecontext) | The highest value for each owner (device / process point). |

### hiber.value.LatestValues

Latest values for a (set of) modem(s), filtering by field and time.


### hiber.value.LatestValues.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.value.ValueSelection](#hibervaluevalueselection) |  |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |

### hiber.value.LatestValues.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| values | [repeated hiber.value.ValueContext](#hibervaluevaluecontext) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |
| request | [ hiber.value.LatestValues.Request](#hibervaluelatestvaluesrequest) |  |

### hiber.value.ListValues

List values for a (set of) modem(s), filtering by field and time.


### hiber.value.ListValues.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.value.ValueSelection](#hibervaluevalueselection) |  |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |
| sort | [ hiber.value.ListValues.Sort](#hibervaluelistvaluessort) |  |
| transform_fields | [map hiber.value.ListValues.Request.TransformFieldsEntry](#hibervaluelistvaluesrequesttransformfieldsentry) | Transform the values for a field into a derived value. Fields specified here must have been specified in the selection. |

### hiber.value.ListValues.Request.TransformFieldsEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ hiber.value.ValueTransformation](#hibervaluevaluetransformation) |  |

### hiber.value.ListValues.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| values | [repeated hiber.value.ValueContext](#hibervaluevaluecontext) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |
| request | [ hiber.value.ListValues.Request](#hibervaluelistvaluesrequest) |  |

### hiber.value.ValueContext

A Value at a time, for a given modem and field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| device | [ hiber.value.ValueContext.ValueDeviceContext](#hibervaluevaluecontextvaluedevicecontext) | The device that produced this value. |
| device_number | [ string](#string) | <span class="deprecated deprecated-field">Deprecated</span> The device that produced this value. |
| process_point | [ hiber.value.ValueContext.ValueProcessPointContext](#hibervaluevaluecontextvalueprocesspointcontext) | The process point that owns this value, if any. Process points own this value if they were assigned to the device that produced this value at the time it was produced. If multiple process points were assigned at the same time, this value exists for each process point. |
| field | [ string](#string) | The field that this value was produced for. |
| time | [ hiber.Timestamp](#hibertimestamp) | The time for this value. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value_type**.value | [ hiber.value.Value](#hibervaluevalue) | The value at this time, if no ValueTransformation was specified for this field. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value_type**.value_durations | [ hiber.value.ValueContext.ValueDurations](#hibervaluevaluecontextvaluedurations) | The output of the DURATION ValueTransformation, if it was specified for this field. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value_type**.delta | [ hiber.value.ValueContext.ValueDelta](#hibervaluevaluecontextvaluedelta) | The output of the DELTA ValueTransformation, if it was specified for this field. |

### hiber.value.ValueContext.ValueDelta

The delta of a value: the difference between a value and the previous value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| delta | [ hiber.value.Value](#hibervaluevalue) | The delta of the two values. |
| current | [ hiber.value.Value](#hibervaluevalue) | The value at this time. |
| previous | [ hiber.value.Value](#hibervaluevalue) | The previous value to compare it with. |

### hiber.value.ValueContext.ValueDeviceContext

The device data for this value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| number | [ string](#string) |  |
| identifier | [ string](#string) |  |
| name | [ string](#string) |  |

### hiber.value.ValueContext.ValueDuration

The amount of time a field for a modem was in this value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ hiber.value.Value](#hibervaluevalue) | The value the duration is for. |
| duration | [ hiber.Duration](#hiberduration) | The aggregated duration the field was this value. |

### hiber.value.ValueContext.ValueDurations

The amount of time a field for a modem was at different values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| durations | [repeated hiber.value.ValueContext.ValueDuration](#hibervaluevaluecontextvalueduration) |  |

### hiber.value.ValueContext.ValueProcessPointContext

Information about the process point that owns the value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) |  |
| name | [ string](#string) |  |
| type | [ hiber.processpoint.ProcessPoint.Type](#hiberprocesspointprocesspointtype) |  |

### hiber.value.ValueSelection

Select the values to return.

| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **owner_selection**.devices | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | Select the devices(s) to get the values for. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **owner_selection**.process_points | [ hiber.processpoint.ProcessPointSelection](#hiberprocesspointprocesspointselection) | Select the process point(s) to get the values for. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data_selection**.value_type | [ hiber.value.ValueSelection.ByValueType](#hibervaluevalueselectionbyvaluetype) | Get the values that are of the given numeric value types. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data_selection**.field | [ hiber.value.ValueSelection.ByField](#hibervaluevalueselectionbyfield) | Get the values for the selected fields. |
| fields | [repeated string](#string) | <span class="deprecated deprecated-field">Deprecated</span> Get the values for the selected fields. |
|  **optional** time_range | [optional hiber.TimeRange](#hibertimerange) | The time to view the values for. |
|  **optional** include_location | [optional bool](#bool) | Include the location (which is not a field). |
| filter_enum_values | [repeated hiber.Filter.FieldEnumValues](#hiberfilterfieldenumvalues) | Filter the values for enum fields. |
|  **optional** include_operational_data | [optional bool](#bool) | Whether to include values that have been marked as operational (e.g. device status). Operational data is typically only available when selecting values for a device. |

### hiber.value.ValueSelection.ByField

Select the data by numeric value type.
If the list is empty, all fields are returned.

| Field | Type | Description |
| ----- | ---- | ----------- |
| fields | [repeated string](#string) |  |

### hiber.value.ValueSelection.ByValueType

Select the data by (numeric) value type.
If the selection is empty, all values with all types are returned.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value_type | [repeated hiber.value.Value.Type](#hibervaluevaluetype) |  |
| numeric_value_type | [repeated hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype) |  |


### Enums
#### hiber.value.AggregatedValues.Aggregation.BasicAggregation
Basic aggregation options, e.g. average, min, max, etc.
Options to be added in the future: MEDIAN, STANDARD_DEVIATION, etc

| Name | Description | Number |
| ---- | ----------- | ------ |
| COUNT | Counts the total number of selected values. | 0 |
| COUNT_DISTINCT | Counts the total number of UNIQUE values in the selected values. | 1 |
| SUM | Calculates the total sum of all values in the selection. | 2 |
| AVERAGE | Calculates the mathematical average of the selected values. Alias for MEAN. | 3 |
| MEAN | Calculates the mathematical mean of the selected values. Alias for AVERAGE. | 4 |
| MINIMUM | Finds the lowest value of the selected values. | 5 |
| MAXIMUM | Finds the highest value of the selected values. | 6 |
| MODE | Finds the most frequently occurring value of the selected values. | 7 |
| MEDIAN | Calculates the standard mathematical median (50th percentile). Uses continuous interpolation. If there is an even number of rows, it will return the average of the two middle values. | 8 |
| MEDIAN_DISCRETE | Calculates the discrete median (50th percentile). Unlike the standard median this will never interpolate. It guarantees returning an actual, existing value from the dataset (picking the lower of the middle values if even). | 9 |
| STANDARD_DEVIATION | Calculates the Sample Standard Deviation. Standard Deviation measures how spread out your data is from the Mean (average). A *low* standard deviation means the data is tightly clustered around the average (highly predictable). A *high* standard deviation means the data is widely spread out (highly volatile). Use this for sensor readings, like pressure, which are a sample of real pressures. | 10 |
| STANDARD_DEVIATION_POPULATION | Calculates the Population Standard Deviation. See STANDARD_DEVIATION. Use this ONLY when your data represents the entire population (all possible values). | 11 |

#### hiber.value.AggregatedValues.Aggregation.PercentileAggregation.PercentileAggregationMethod
The method of calculation used for the percentile value: continuous or discrete.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DISCRETE | Always return an existing value from the selected values. Do not interpolate. | 0 |
| CONTINUOUS | Interpolate between adjacent values if the target percentile falls between them. | 1 |

#### hiber.value.ListValues.Sort
How to sort the values.

| Name | Description | Number |
| ---- | ----------- | ------ |
| TIME_ASCENDING |  | 0 |
| TIME_DESCENDING |  | 1 |



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
| center | [ hiber.Location](#hiberlocation) |  |
| bottom_left | [ hiber.Location](#hiberlocation) |  |
| top_right | [ hiber.Location](#hiberlocation) |  |
|  **optional** textual | [optional string](#string) | Text representation. Can be used as an alternative input in a request, filled in by the API in responses. |

### hiber.BytesOrHex

Some clients may prefer direct binary data, while other prefer a hexadecimal string,
both for input and output. To support both methods, this object is used to represent binary data.

When you receive this from the api, both fields are set. When sending it to the api, only one field is required.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** bytes | [optional bytes](#bytes) |  |
|  **optional** hex | [optional string](#string) |  |

### hiber.BytesOrHex.Update

<p class="deprecated deprecated-message">Deprecated</p> 

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.BytesOrHex](#hiberbytesorhex) |  |

### hiber.Date

Date type for convenience.

Some clients are better at parsing year, month and day of month as separate fields,
while others prefer a text-based format.
To accommodate this, this Date type supports both.

When used as API output, both the int fields and textual fields will be set.
The textual field has the commonly used ISO 8601 local date format (e.g. "2018-01-01").
When used an API input, either specify the int fields or the textual field.
If both are specified, the textual field will be discarded.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** year | [optional uint32](#uint32) |  |
|  **optional** month | [optional uint32](#uint32) |  |
|  **optional** day | [optional uint32](#uint32) |  |
|  **optional** textual | [optional string](#string) |  |

### hiber.DoubleRange

Decimal range.

| Field | Type | Description |
| ----- | ---- | ----------- |
| start | [ double](#double) |  |
| end | [ double](#double) |  |

### hiber.Duration



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** duration | [optional google.protobuf.Duration](#googleprotobufduration) |  |
|  **optional** textual | [optional string](#string) |  |

### hiber.Filter

Filters used in many api calls to filter the data sources, results, etc.

"Include" fields filter out anything not in the include set.
When not set, all items will be returned (except excluded items)

"Exclude" fields filter out anything in the exclude set.
When combined with include, exclude takes precedence when determining whether an item is filtered


### hiber.Filter.ChildOrganizations

Specify which organizations to get data from. By default, data is only retrieved for the current organization,
but using ChildOrganizations we can specify to include a number of, or all, sub-organizations.

Note: ChildOrganization differs from other filters in that it defaults to not allowing anything, where the
other filters default to allowing everything

| Field | Type | Description |
| ----- | ---- | ----------- |
| include_all | [ bool](#bool) |  |
| include | [repeated string](#string) |  |
| exclude | [repeated string](#string) |  |

### hiber.Filter.ChildOrganizations.Update

<p class="deprecated deprecated-message">Deprecated</p> Update object to update a Filter.ChildOrganizations field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) |  |

### hiber.Filter.DeviceTypes



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) |  |
| exclude | [repeated string](#string) |  |

### hiber.Filter.Events



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated hiber.EventType](#hibereventtype) |  |
| exclude | [repeated hiber.EventType](#hibereventtype) |  |

### hiber.Filter.Events.Update

<p class="deprecated deprecated-message">Deprecated</p> Update object to update a Filter.Events field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.Filter.Events](#hiberfilterevents) |  |

### hiber.Filter.FieldEnumValues



| Field | Type | Description |
| ----- | ---- | ----------- |
| field | [ string](#string) |  |
| include | [repeated string](#string) |  |
| exclude | [repeated string](#string) |  |

### hiber.Filter.HealthLevels



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) |  |
| exclude | [repeated string](#string) |  |

### hiber.Filter.ModemIdentifiers



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) |  |
| exclude | [repeated string](#string) |  |

### hiber.Filter.Modems



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) | Include all modems with these modem numbers (HEX) |
| exclude | [repeated string](#string) | Exclude all modems with these modem numbers (HEX). Exclude takes precedence over include. |

### hiber.Filter.Modems.Update

<p class="deprecated deprecated-message">Deprecated</p> Update object to update a Filter.Modems field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.Filter.Modems](#hiberfiltermodems) |  |

### hiber.Filter.OrganizationPermissions



| Field | Type | Description |
| ----- | ---- | ----------- |
| include_all | [ bool](#bool) |  |
| include | [repeated hiber.OrganizationPermission](#hiberorganizationpermission) |  |
| exclude | [repeated hiber.OrganizationPermission](#hiberorganizationpermission) |  |

### hiber.Filter.Organizations



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) |  |
| exclude | [repeated string](#string) |  |

### hiber.Filter.Properties

Filter result on specific properties encoded in map-value pairs.

| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **selection**.properties | [ hiber.MapFilter](#hibermapfilter) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **selection**.include_only_empty | [ bool](#bool) | When set to true, match only empty property-sets. |

### hiber.Filter.Publishers



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated int64](#int64) |  |
| exclude | [repeated int64](#int64) |  |
| only_active | [ bool](#bool) |  |

### hiber.Filter.Roles



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) |  |
| exclude | [repeated string](#string) |  |

### hiber.Filter.SensorBrands



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) |  |
| exclude | [repeated string](#string) |  |

### hiber.Filter.SupportPermissions



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated hiber.SupportPermission](#hibersupportpermission) |  |
| exclude | [repeated hiber.SupportPermission](#hibersupportpermission) |  |

### hiber.Filter.Tags



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated int64](#int64) |  |
| exclude | [repeated int64](#int64) |  |

### hiber.Filter.Tags.Update

<p class="deprecated deprecated-message">Deprecated</p> Update object to update a Filter.Tags field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.Filter.Tags](#hiberfiltertags) |  |

### hiber.Filter.UserPermissions



| Field | Type | Description |
| ----- | ---- | ----------- |
| include_all | [ bool](#bool) |  |
| include | [repeated hiber.UserPermission](#hiberuserpermission) |  |
| exclude | [repeated hiber.UserPermission](#hiberuserpermission) |  |

### hiber.Filter.Users



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) |  |
| exclude | [repeated string](#string) |  |

### hiber.Filter.Webhooks



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated int64](#int64) |  |
| exclude | [repeated int64](#int64) |  |
| only_active | [ bool](#bool) |  |

### hiber.IntRange



| Field | Type | Description |
| ----- | ---- | ----------- |
| start | [ uint32](#uint32) |  |
| end | [ uint32](#uint32) |  |

### hiber.Location

Geographic latitude and longitude coordinates specified in decimal degrees.
For more information, see the WGS-84 coordinate system, which is used for most GPS systems.

| Field | Type | Description |
| ----- | ---- | ----------- |
| latitude | [ double](#double) | Decimal degrees north. |
| longitude | [ double](#double) | Decimal degrees east. |
|  **optional** textual | [optional string](#string) | Text representation. Can be used as an alternative input in a request, filled in by the API in responses. |

### hiber.LocationSelection

Selection object for map data.

Also, filter the map data by level and area restriction, to only display a small area at a detailed map level,
for example

| Field | Type | Description |
| ----- | ---- | ----------- |
| areas | [repeated hiber.Area](#hiberarea) | Rectangular areas, each defined by two locations, normalized to bottom-left and top-right points. |
| shapes | [repeated hiber.Shape](#hibershape) | Polygon shapes, each defined by a list of locations, which draw a shape on the map. |

### hiber.MapFilter

Some properties are stored as a name-value pair (e.g. bluetooth: 4.0, bluetooth: BLE).
This filter allows selecting a range of values for a specific name.
One could imagine wanting to include "all devices with bluetooth 4.0 or 4.1".

To select for multiple versions of a property,
add the name of the property as a map-key and add a repeated list of versions as the map-value.

For example:
- include { 'bluetooth' -> [ ] }
    returns all items that have any version of bluetooth,
- include { 'bluetooth' -> [ '4.0', '5.0' ] }
    will only return items that have bluetooth version 4.0 _or_ 5.0 (inclusive or),
- include { 'bluetooth' -> [ '' ] }
    would only select bluetooth peripherals that don't have any version set,
- include { 'bluetooth' -> [ ], 'LoRaWAN' -> [ ] }
    will only select items that have both bluetooth (any version) _and_ LoRaWAN (any version),
- include { 'bluetooth' -> [ ] }, exclude { 'bluetooth' -> [ ] }
    will return an empty list since exclude will take precedence, and
- include { 'bluetooth' -> [ ] }, exclude { 'bluetooth' -> [ '3.0' ] }
    returns only items that have bluetooth, but not version 3.0.

| Field | Type | Description |
| ----- | ---- | ----------- |
| include_and | [map hiber.MapFilter.IncludeAndEntry](#hibermapfilterincludeandentry) | Filter to only include items with all of the given set of properties. |
| exclude | [map hiber.MapFilter.ExcludeEntry](#hibermapfilterexcludeentry) | Filter to exclude items with any of the given set of properties. |

### hiber.MapFilter.ExcludeEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ hiber.MapFilter.OneOfValues](#hibermapfilteroneofvalues) |  |

### hiber.MapFilter.IncludeAndEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ hiber.MapFilter.OneOfValues](#hibermapfilteroneofvalues) |  |

### hiber.MapFilter.OneOfValues

Technical solution to make map<k, v> into a map<k, repeated v>,
which is not possible in protobuf without trickery.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [repeated string](#string) |  |

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
|  **optional** size | [optional int32](#int32) |  |
|  **optional** page | [optional int32](#int32) |  |

### hiber.Pagination.Result



| Field | Type | Description |
| ----- | ---- | ----------- |
| size | [ int32](#int32) |  |
| page | [ int32](#int32) |  |
| total | [ int32](#int32) |  |
| total_pages | [ int32](#int32) |  |
| previous | [ hiber.Pagination](#hiberpagination) |  |
| next | [ hiber.Pagination](#hiberpagination) |  |
| approximated_total | [ bool](#bool) | Indicates that the total is an approximation, and not an exact value. This can be set for data that changes often, or is generally only fetched in an infinite scrolling manner. For example, unbundled events are likely to return an approximated total, but not guaranteed to do so. |
|  **optional** items_on_page | [optional hiber.IntRange](#hiberintrange) | The indices of the first and last items on the page, if any. For example, on the second page of size 10, this is 11 - 20. |

### hiber.Shape

Polygon shape defined by a list of locations, which draw a shape on the map.
The last point is connected to the first to close the shape.

For example, the outline of a city would be defined using a Shape,
while a rectangular region is easier to define using Area.

| Field | Type | Description |
| ----- | ---- | ----------- |
| path | [repeated hiber.Location](#hiberlocation) |  |
|  **optional** textual | [optional string](#string) | Text representation. Can be used as an alternative input in a request, filled in by the API in responses. |

### hiber.TimeRange

Period of time between two timestamps. Typically used for filtering.

This can be used with textual shortcuts for timestamp, and some additional duration textual shortcuts:
- a duration as an offset of now, e.g. "-10h" or "PT-10h": converted to now + offset, so start.textual -10h is
  10 hours before the end time (using the ISO 8601 duration format)
Examples:
- start "-10h" end "now": a time range from 10 hours before the request time, to the request time
- start "-10h" end "2022-01-01 20:00": becomes start 2022-01-01 10:00 end 2022-01-01 20:00

| Field | Type | Description |
| ----- | ---- | ----------- |
| start | [ hiber.Timestamp](#hibertimestamp) |  |
| end | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.TimeWindow

Time window to split a time range, e.g. per hour, per day, per week, etc.

| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **window**.interval | [ hiber.TimeWindow.IntervalWindow](#hibertimewindowintervalwindow) | Simple interval to use for windowing, e.g. every 2 hours or 24 hours or 5 minutes. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **window**.calendar | [ hiber.TimeWindow.CalendarWindow](#hibertimewindowcalendarwindow) | Calendar-based time window to use for windowing, e.g. per day, week, month, etc, for a given time zone. |

### hiber.TimeWindow.CalendarWindow

Calendar-based time window to use for windowing, e.g. per day, week, month, etc, for a given time zone.

| Field | Type | Description |
| ----- | ---- | ----------- |
| window | [ hiber.CalendarPeriod](#hibercalendarperiod) | The calendar-based window to use, e.g. daily or monthly. |
| time_zone | [ string](#string) | The time zone to use for the calendar window. |

### hiber.TimeWindow.IntervalWindow

Interval-based time window to use for windowing, e.g. every 2 hours or 24 hours or 5 minutes.

| Field | Type | Description |
| ----- | ---- | ----------- |
| interval | [ hiber.Duration](#hiberduration) | Simple interval to use for windowing, e.g. every 2 hours or 24 hours or 5 minutes. |
|  **optional** align_to | [optional hiber.Timestamp](#hibertimestamp) | Alignment for the interval repetition, e.g. every 5 minutes from 12:03 (resulting in 12:08, 12:13, etc). Defaults to any given time in the request where this is used, or else midnight today in UTC. |

### hiber.Timestamp

Timestamp type for convenience.

Some clients are better at parsing Google's seconds/nanos based timestamp, while others prefer a text-based format.
To accommodate this, this Timestamp type supports both.

When used as API output, both the timestamp and textual fields will be set. The textual field has the commonly
used ISO 8601 format (e.g. "2018-01-01T13:00:00Z").
When used an API input, only one of the fields is needed, there is no need to set both. When both are set, the
timestamp field will be used, the textual field will be discarded.

In addition, the textual field, when used as input, allows for a number of shortcuts that get converted into
timestamps:
- "now": converted to the current timestamp at the time of the request

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** timestamp | [optional google.protobuf.Timestamp](#googleprotobuftimestamp) |  |
|  **optional** time_zone | [optional string](#string) |  |
|  **optional** textual | [optional string](#string) |  |

### hiber.UpdateBoolean

<p class="deprecated deprecated-message">Deprecated</p> Update object for a boolean.

Since false is the default value, we need to distinguish between an omitted value and setting the value to false,
in an update object.

To use this to update, set a value and set updated to true

DEPRECATED: use alternative optional fields in the relevant places instead.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ bool](#bool) |  |

### hiber.UpdateClearableString

<p class="deprecated deprecated-message">Deprecated</p> Update object for a string that can be empty.

Since an empty string is also the default value, we need to distinguish between an omitted value and
setting the value to an empty string, in an update object.

To use this to update, set a value and set updated to true

DEPRECATED: use alternative optional fields in the relevant places instead.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ string](#string) |  |

### hiber.UpdateOptionalDuration

<p class="deprecated deprecated-message">Deprecated</p> Update object for an optional Duration.

To use this to update, set a value and set updated to true.
To clear the duration, set updated to true, but set no value.

DEPRECATED: use alternative optional fields in the relevant places instead.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.Duration](#hiberduration) |  |

### hiber.UpdateOptionalId

<p class="deprecated deprecated-message">Deprecated</p> Update object for an optional id.

To use this to update, set a value and set updated to true. To clear the id, set updated to true, but set no value.

DEPRECATED: use alternative optional fields in the relevant places instead.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ int64](#int64) |  |

### hiber.UpdateZeroableInt

<p class="deprecated deprecated-message">Deprecated</p> Update object for an int that can be set to 0.

Since 0 is also the default value, we need to distinguish between an omitted value and setting the value to 0,
in an update object.

To use this to update, set a value and set updated to true

DEPRECATED: use alternative optional fields in the relevant places instead.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ uint32](#uint32) |  |


### Enums
#### hiber.CalendarPeriod
A period of time represented on a calendar, in a time zone.
Includes DST transitions, meaning that DAY can be 23 or 25 hours, etc.

| Name | Description | Number |
| ---- | ----------- | ------ |
| CALENDAR_PERIOD_UNSPECIFIED | Undefined period, raises an error. | 0 |
| DAY | A day on the calendar, in a given time zone. Not guaranteed to be 24 hours (e.g. around DST transitions). | 1 |
| WEEK | A week. Weeks begin on Monday, following [ISO 8601](https://en.wikipedia.org/wiki/ISO_week_date). For a week starting on Sunday, use WEEK_STARTING_SUNDAY. | 2 |
| WEEK_STARTING_SUNDAY | A week, starting on Sunday. For a week starting on Monday, use WEEK. | 3 |
| MONTH | A month. | 4 |
| QUARTER | A quarter. Quarters start on dates 1-Jan, 1-Apr, 1-Jul, and 1-Oct of each year. | 5 |
| HALF | A half-year. Half-years start on dates 1-Jan and 1-Jul. | 6 |
| YEAR | A year. | 7 |

#### hiber.EventType
Enum of api-accessible events.
The event types in this enum have a protobuf implementation, and can be used, for example, in the
api event stream and publishers.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT |  | 0 |
| ORGANIZATION_CREATED | A new organization was created under your organization. | 34 |
| ORGANIZATION_UPDATED | Your organization information was updated. This deals with things like display name and contact information, not users and devices. | 12 |
| ORGANIZATION_DELETED | An organization under your organization was deleted. | 35 |
| ORGANIZATION_EVENT_CONFIGURATION_UPDATED | Your organization's event configuration was updated. This refers to things like message summary configuration. | 43 |
| PROCESS_POINT_CREATED | A new process point was created in your organization. | 73 |
| PROCESS_POINT_UPDATED | An process point in your organization was updated (e.g. renamed, tagged). | 74 |
| PROCESS_POINT_DELETED | An process point in your organization was deleted. | 75 |
| DEVICE_CREATED | A new device was created in your organization, either manually or by a gateway. | 55 |
| DEVICE_UPDATED | A device in your organization was manually updated (e.g. renamed, tagged). | 36 |
| DEVICE_LOCATION_UPDATED | The location of a device in your organization was updated, either manually or by a message. | 4 |
| DEVICE_INSTALLED | A device in your organization was installed and should now be active. | 33 |
| MESSAGE_RECEIVED | A device in your organization sent a message. This event is the final output for the message, after any parsing and post-processing. | 5 |
| MESSAGE_BODY_PARSED | A device in your organization sent a message, and it was parsed by a message body parser. For the final event, with all applied parsers and post processing, use MESSAGE_RECEIVED instead. | 39 |
| MESSAGE_BODY_RECEIVED | A device in your organization sent a message, and it has been scheduled for parsing by message body parsers and post-processing. For the final event, with all applied parsers and post processing, use MESSAGE_RECEIVED instead. | 45 |
| MESSAGE_CANNOT_BE_PARSED | A device in your organization sent a message, and it could not be parsed by any assigned message body parser. This is typically a configuration issue. Please contact customer support if this is not resolved. | 15 |
| MESSAGE_SUMMARY | A summary of messages in your organization was created, based on your event configuration. | 42 |
| MESSAGE_BODY_PARSER_CREATED | A new message body parser was created in your organization. This typically only happens for custom solutions. | 46 |
| MESSAGE_BODY_PARSER_UPDATED | A message body parser in your organization was updated. This typically only happens for custom solutions. | 47 |
| MESSAGE_BODY_PARSER_DELETED | A message body parser in your organization was deleted. This typically only happens for custom solutions. | 48 |
| ALARM_TRIGGERED | An alarm was triggered in your organizations. Depending on the alarm, this may mean that a device sent a message with a value (e.g. pressure) outside of the expected range, or moved out of the expected area. | 56 |
| ALARM_CREATED | A new alarm was created in your organization. | 57 |
| ALARM_UPDATED | An alarm in your organization was updated. | 58 |
| ALARM_DELETED | An alarm in your organization was deleted. | 59 |
| ASSIGNED | An assignment was made in your organization. For example: assigning a tag or alarm to a modem. | 63 |
| UNASSIGNED | An assignment was removed in your organization. For example: removing a tag or alarm from a modem. | 64 |
| TRANSFER | A device was transferred into or out of your organization. Transferred device lose their data and are only used in the new organization if connected to a gateway in that organization. | 18 |
| PUBLISHER_CREATED | A new publisher was created in your organization. Publishers are any system that pushes data out of the system, like webhooks, MQTT integrations and even email preferences. | 1 |
| PUBLISHER_UPDATED | A publisher in your organization was updated. Publishers are any system that pushes data out of the system, like webhooks, MQTT integrations and even email preferences. | 2 |
| PUBLISHER_DELETED | A publisher in your organization was deleted. Publishers are any system that pushes data out of the system, like webhooks, MQTT integrations and even email preferences. | 3 |
| PUBLISHER_FAILED | A publisher in your organization failed to send its data. This can be a temporary issue (perhaps the webhook endpoint is down) or an indication of a configuration issue. Publishers are any system that pushes data out of the system, like webhooks, MQTT integrations and even email preferences. | 11 |
| PUBLISHER_AUTO_DISABLED | A publisher in your organization failed to send its data for a long enough period that is has been disabled. This means the failures were not a temporary issue, but there is something wrong with the configuration. Publishers are any system that pushes data out of the system, like webhooks, MQTT integrations and even email preferences. | 37 |
| USER_ACCESS_REQUEST | A user has requested access to your organization. You can review their request and approve or reject them. | 8 |
| USER_INVITED | A user was invited into your organization. They can review your invite and accept it or ignore it. | 38 |
| USER_ADDED | A user was granted access to your organization, by request, invite, or created by an organization admin. | 9 |
| USER_REMOVED | A user was removed from your organization by an organization admin. | 10 |
| USER_VALIDATION_UPDATED | The user validation (i.e. email domain) for your organization was updated. | 54 |
| USER_UPDATED | A user was updated | 60 |
| USER_PERMISSIONS_UPDATED | A user's permissions and/or roles were updated | 61 |
| TOKEN_CREATED | A new token was created for your organization. | 31 |
| TOKEN_EXPIRY_WARNING | A token in your organization will expire within 2 weeks. | 25 |
| TOKEN_EXPIRED | A token in your organization has expired. | 26 |
| TOKEN_DELETED | A token in your organization was deleted. | 32 |
| EXPORT_CREATED | A new export was started for your organization, exporting data (e.g. messages) to a file. | 65 |
| EXPORT_READY | An export in your organization has completed and the resulting file with data (e.g. messages as CSV) is ready to be downloaded. | 66 |
| EXPORT_FAILED | An export in your organization has failed (typically because of incorrect data selection). | 67 |
| VALUE | A new value. | 80 |

#### hiber.Health
Health is an indicator for issues. It is used for publishers to give a quick indication of issues.

| Name | Description | Number |
| ---- | ----------- | ------ |
| OK |  | 0 |
| WARNING |  | 1 |
| ERROR |  | 2 |

#### hiber.UnitOfMeasurement
Unit of measurement for a numeric value.

| Name | Description | Number |
| ---- | ----------- | ------ |
| UNIT_UNKNOWN |  | 0 |
| DURATION_MILLISECONDS |  | 40 |
| DURATION_SECONDS |  | 1 |
| DURATION_MINUTES |  | 2 |
| DURATION_HOURS |  | 3 |
| DURATION_DAYS |  | 4 |
| DURATION_WEEKS |  | 41 |
| FUEL_EFFICIENCY_LITER_PER_100_KILOMETER |  | 30 |
| FUEL_EFFICIENCY_KILOMETER_PER_LITER |  | 31 |
| FUEL_EFFICIENCY_KILOMETER_PER_US_GALLON |  | 32 |
| FUEL_EFFICIENCY_KILOMETER_PER_IMPERIAL_GALLON |  | 33 |
| FUEL_EFFICIENCY_MILE_PER_US_GALLON |  | 34 |
| FUEL_EFFICIENCY_MILE_PER_IMPERIAL_GALLON |  | 35 |
| FUEL_EFFICIENCY_MILE_PER_LITER |  | 36 |
| DISTANCE_METER |  | 8 |
| DISTANCE_MILLIMETER |  | 9 |
| DISTANCE_CENTIMETER |  | 10 |
| DISTANCE_KILOMETER |  | 11 |
| DISTANCE_NAUTICAL_MILE |  | 26 |
| DISTANCE_MILE |  | 21 |
| DISTANCE_YARD |  | 27 |
| DISTANCE_FOOT |  | 28 |
| DISTANCE_INCH |  | 29 |
| PERCENT |  | 16 |
| PRESSURE_BAR |  | 12 |
| PRESSURE_PSI |  | 14 |
| PRESSURE_K_PA |  | 17 |
| PRESSURE_KILOGRAM_PER_CENTIMETER_SQUARED |  | 53 |
| SPEED_KILOMETERS_PER_HOUR |  | 18 |
| SPEED_KNOTS |  | 19 |
| SPEED_METERS_PER_SECOND |  | 20 |
| SPEED_MILES_PER_HOUR |  | 22 |
| SPEED_FEET_PER_SECOND |  | 47 |
| TEMPERATURE_KELVIN |  | 5 |
| TEMPERATURE_DEGREES_CELSIUS |  | 6 |
| TEMPERATURE_DEGREES_FAHRENHEIT |  | 7 |
| VOLTAGE_MILLIVOLT |  | 15 |
| VOLUME_LITER |  | 23 |
| VOLUME_GALLON_US |  | 24 |
| VOLUME_GALLON_IMPERIAL |  | 25 |
| VOLUME_CUBIC_METER |  | 42 |
| VOLUME_CUBIC_FOOT |  | 43 |
| VOLUME_OIL_BARREL |  | 55 |
| MASS_KILOGRAMS |  | 37 |
| MASS_POUNDS |  | 38 |
| FLOW_BARRELS_PER_DAY |  | 46 |
| FLOW_CUBIC_METER_PER_HOUR |  | 39 |
| FLOW_CUBIC_METER_PER_SECOND |  | 49 |
| FLOW_LITER_PER_HOUR |  | 51 |
| FLOW_LITER_PER_SECOND |  | 52 |
| FLOW_CUBIC_FEET_PER_HOUR |  | 48 |
| FLOW_CUBIC_FEET_PER_SECOND |  | 50 |
| REVOLUTIONS_PER_MINUTE |  | 44 |
| ITEMS_PER_24_HOURS |  | 45 |
| OTHER |  | 54 |
| ANGLE_DEGREES_ARC |  | 56 |

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

