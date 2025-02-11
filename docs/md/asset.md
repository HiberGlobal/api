# asset.proto



#### This file was generated from [asset.proto](https://github.com/HiberGlobal/api/blob/master/asset.proto).

## Table of Contents



- Messages
  - [Asset](#asset)
  - [Asset.AssignedDevice](#assetassigneddevice)
  - [AssetSelection](#assetselection)

- Enums
  - [Asset.Type](#assettype)

- Referenced messages from [file.proto](#referenced-messages-from-fileproto)
  - [hiber.file.File](#hiberfilefile)
  - [hiber.file.FileSelection](#hiberfilefileselection)


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

## Messages

### Asset

Assets are things that collect the data produced by devices.
Devices are assigned to assets to handle data ownership.
When a device is replaced, the data flow for the asset continues with the data from the new device.
Multiple devices can be assigned to an asset, though it is advisable to only do so when they send
different type of data (e.g. one sensor for pressure and one for flow).

For example, if you have a Well, you might have assets for Annulus A and the tubing head.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) |  |
| name | [ string](#string) | Name of the asset |
|  **optional** type | [optional Asset.Type](#assettype) | Type of the asset, if any of the predefined types applies. |
|  **optional** description | [optional string](#string) | Longer detailed description of the asset. |
|  **optional** notes | [optional string](#string) | Multiline notes field that can be used to add additional information to an asset. |
|  **optional** time_zone | [optional string](#string) | Optional time zone for the asset. This can, for example, be used to calculate SLAs on a daily basis, adjusted by time zone. |
|  **optional** expected_transmission_rate | [optional hiber.value.Value.Numeric.Rate](#hibervaluevaluenumericrate) | The expected transmission rate for this asset. |
| metadata | [ google.protobuf.Struct](#googleprotobufstruct) | Metadata for the asset. This can be automatically populated from linked devices or manually added. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | Tags assigned to this asset |
| devices | [repeated Asset.AssignedDevice](#assetassigneddevice) | Devices assigned to this asset |
| inactive_devices | [repeated Asset.AssignedDevice](#assetassigneddevice) | Devices that were assigned to this asset in the past |
| organization | [ string](#string) | The organization that owns this asset. Typically only relevant if child organizations are included. |
| location | [ hiber.Location](#hiberlocation) | Location for the asset. |
| files | [repeated hiber.file.File](#hiberfilefile) | Files for this asset. Typically an image of a place. See the File.media_type for more information. |

### Asset.AssignedDevice

A device assigned to this asset.
Non-operational values that the device produces will be linked to this asset
(e.g. pressure, but not battery level).

| Field | Type | Description |
| ----- | ---- | ----------- |
| number | [ string](#string) |  |
| identifiers | [repeated string](#string) |  |
|  **optional** name | [optional string](#string) |  |
|  **optional** type | [optional string](#string) |  |
|  **optional** last_message_sent_at | [optional hiber.Timestamp](#hibertimestamp) |  |
|  **optional** last_message_received_at | [optional hiber.Timestamp](#hibertimestamp) |  |
|  **optional** assignment_time_range | [optional hiber.TimeRange](#hibertimerange) |  |
|  **optional** health | [optional hiber.health.HealthLevel](#hiberhealthhealthlevel) |  |
| numeric_value_types | [repeated hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype) |  |

### AssetSelection

Selection object for assets.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifiers | [repeated string](#string) | Select assets by identifier. |
| search | [repeated string](#string) | Search assets by (partial, case insensitive) identifier, name, description, notes and time zone. |
| types | [repeated Asset.Type](#assettype) | Select assets by type. |
|  **optional** filter_by_tags | [optional hiber.tag.TagSelection](#hibertagtagselection) | Select assets by tags |


## Enums
### Asset.Type
Predefined assets types that can be used to say something about the data.
Currently a limited list, but more may be added in the future.

| Name | Description | Number |
| ---- | ----------- | ------ |
| UNKNOWN |  | 0 |
| WELL_ANNULUS_A |  | 1 |
| WELL_ANNULUS_B |  | 2 |
| WELL_ANNULUS_C |  | 3 |
| WELL_ANNULUS_D |  | 4 |
| WELL_HEAD |  | 15 |
| WELL_TUBING_HEAD |  | 5 |
| WELL_TUBING |  | 6 |
| WELL_FLOW_LINE |  | 7 |
| WELL_CASING |  | 8 |
| WELL_PRODUCTION_CASING_PRESSURE |  | 9 |
| WELL_INTERMITTENT_CASING_PRESSURE |  | 10 |
| PIPELINE |  | 11 |
| PRODUCTION_LINE |  | 12 |
| GAS_MANIFOLD |  | 13 |
| PRODUCTION_MANIFOLD |  | 14 |



## Referenced messages from file.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [file.proto](https://github.com/HiberGlobal/api/blob/master/file.proto).


### hiber.file.File

A file in your organization, with its mime-type and name.
It can represent any file of any type.

Specific API calls may pur restrictions on the name or size of the file.

To avoid sending large amounts of binary data, File does not typically contain the file's content.
The content can be fetched at a url, or using the FileService.Get rpc.
For specific use cases, the data field might be set with binary data, avoiding the need for another lookup.

The file name should be interpreted as-is.
No hierarchical information is stored in the name, nor should you look at the "extension" to know its media-type.
It might not even have a file extension.
The file name may contain characters that cannot be a valid file name on certain systems.

When showing this as an image in a browser, one can make use of a `data` URI.
The client must convert the bytes to base64 and can then construct a data URI like this

    data:<media-type>;base64,<base64-encoded-bytes>

Other type clients should be able to sort-of-directly set the data bytes as the source for an image.

(Technical note: the indices are structured for binary backwards compatibility with the now-removed NamedFile.)

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) | This file's content can be fetched using the FileService, with this file identifier. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **content**.data | [ hiber.BytesOrHex](#hiberbytesorhex) | The binary payload that represents the file |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **content**.file_service | [ bool](#bool) | This file's content can be fetched using the FileService, with this file identifier. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **content**.url | [ string](#string) | This file's content can be fetched at this url. |
| media_type | [ string](#string) | The media-type of the file, as defined by RFC 6838 or its extensions |
| name | [ string](#string) | A semantic name for this file. |
| link | [ string](#string) | A link to file in the Hiber Rest API. Note: the Hiber Rest API requires a token, for authenticated access to your files. If the content oneof of this file is a url, this link will return a HTTP 301 code to redirect to that url. |

### hiber.file.FileSelection

Selection to use when listing files in your organization.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** search | [optional string](#string) | Search files in your organization by (partial) match on name, media type and (if present) url. |
| identifiers | [repeated string](#string) | List files in your organization with a specific identifier. |


### Enums


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
| color | [ string](#string) | <strong>Deprecated.</strong> Default color for the health level, as a string that represents a valid CSS3 color. DEPRECATED: Maps to the color named "text" in color_data. |
| color_data | [map hiber.health.HealthLevel.ColorDataEntry](#hiberhealthhealthlevelcolordataentry) | Map of named colors, where key is the name and the value is a valid CSS3 color definition. |
| severity | [ int64](#int64) | A unique numeric value equal to the index of this health level in the list of health levels sorted by ascending severity (starting at 1). This means higher numbers denote a more severe health. This value cannot be used when creating or updating. To change the severity for a health level, reorder all health levels. |
| catch_all | [ bool](#bool) | Precisely one health level can be assigned as a catch-all for any unknown health levels from alarms (or Hiber systems), which can happen when a device manufacturer has provided alarms for your device (e.g. a low battery alarm). By default, unknown health levels map to the level of the highest severity, unless another level is marked as catch-all. |

### hiber.health.HealthLevelSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** search | [optional string](#string) | Search for the given string in the levels and colors. |
| levels | [repeated string](#string) | Filter by exact levels. |


### Enums


## Referenced messages from tag.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [tag.proto](https://github.com/HiberGlobal/api/blob/master/tag.proto).


### hiber.tag.Tag

Tag in your organization.
Tags can be assigned to devices and assets to group them together or mark a certain property.

A Tag has three parts: its id in your organization, a Label that describes how it should be displayed, and
Metadata (which is only included when using the TagService) with additional information.

| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) |  |
| label | [ hiber.tag.Tag.Label](#hibertagtaglabel) | The label to display for this tag. |
|  **optional** metadata | [optional hiber.tag.Tag.Metadata](#hibertagtagmetadata) | Metadata for this tag. This is typically not included in calls where the tag is repeated a lot, like the device list. Use the TagService.List call to get the tags with Metadata. |

### hiber.tag.Tag.Label

Label for a tag, containing all the information needed to display it.

| Field | Type | Description |
| ----- | ---- | ----------- |
| name | [ string](#string) |  |
| type | [ string](#string) |  |

### hiber.tag.TagSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| search | [repeated string](#string) |  |
| names | [repeated string](#string) |  |
|  **optional** filter | [optional hiber.Filter.Tags](#hiberfiltertags) |  |
| types | [repeated string](#string) |  |
|  **optional** location | [optional hiber.LocationSelection](#hiberlocationselection) |  |


### Enums


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

<strong>Deprecated.</strong> 

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

<strong>Deprecated.</strong> Update object to update a Filter.ChildOrganizations field.

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

<strong>Deprecated.</strong> Update object to update a Filter.Events field.

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

<strong>Deprecated.</strong> Update object to update a Filter.Modems field.

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

<strong>Deprecated.</strong> Update object to update a Filter.Tags field.

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

<strong>Deprecated.</strong> Update object for a boolean.

Since false is the default value, we need to distinguish between an omitted value and setting the value to false,
in an update object.

To use this to update, set a value and set updated to true

DEPRECATED: use alternative optional fields in the relevant places instead.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ bool](#bool) |  |

### hiber.UpdateClearableString

<strong>Deprecated.</strong> Update object for a string that can be empty.

Since an empty string is also the default value, we need to distinguish between an omitted value and
setting the value to an empty string, in an update object.

To use this to update, set a value and set updated to true

DEPRECATED: use alternative optional fields in the relevant places instead.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ string](#string) |  |

### hiber.UpdateOptionalDuration

<strong>Deprecated.</strong> Update object for an optional Duration.

To use this to update, set a value and set updated to true.
To clear the duration, set updated to true, but set no value.

DEPRECATED: use alternative optional fields in the relevant places instead.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.Duration](#hiberduration) |  |

### hiber.UpdateOptionalId

<strong>Deprecated.</strong> Update object for an optional id.

To use this to update, set a value and set updated to true. To clear the id, set updated to true, but set no value.

DEPRECATED: use alternative optional fields in the relevant places instead.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ int64](#int64) |  |

### hiber.UpdateZeroableInt

<strong>Deprecated.</strong> Update object for an int that can be set to 0.

Since 0 is also the default value, we need to distinguish between an omitted value and setting the value to 0,
in an update object.

To use this to update, set a value and set updated to true

DEPRECATED: use alternative optional fields in the relevant places instead.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ uint32](#uint32) |  |


### Enums
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
| ASSET_CREATED | A new asset was created in your organization. | 70 |
| ASSET_UPDATED | An asset in your organization was updated (e.g. renamed, tagged). | 71 |
| ASSET_DELETED | An asset in your organization was deleted. | 72 |
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
| TOKEN_CREATED | A new token was created for your organization. | 31 |
| TOKEN_EXPIRY_WARNING | A token in your organization will expire within 2 weeks. | 25 |
| TOKEN_EXPIRED | A token in your organization has expired. | 26 |
| TOKEN_DELETED | A token in your organization was deleted. | 32 |
| EXPORT_CREATED | A new export was started for your organization, exporting data (e.g. messages) to a file. | 65 |
| EXPORT_READY | An export in your organization has completed and the resulting file with data (e.g. messages as CSV) is ready to be downloaded. | 66 |
| EXPORT_FAILED | An export in your organization has failed (typically because of incorrect data selection). | 67 |

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

