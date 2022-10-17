# base.proto



#### This file was generated from [base.proto](https://github.com/HiberGlobal/api/blob/master/base.proto).

## Table of Contents



- Messages
  - [Area](#area)
  - [Avatar](#avatar)
  - [BytesOrHex](#bytesorhex)
  - [BytesOrHex.Update](#bytesorhexupdate)
  - [Date](#date)
  - [DoubleRange](#doublerange)
  - [Duration](#duration)
  - [Filter](#filter)
  - [Filter.ChildOrganizations](#filterchildorganizations)
  - [Filter.ChildOrganizations.Update](#filterchildorganizationsupdate)
  - [Filter.Events](#filterevents)
  - [Filter.Events.Update](#filtereventsupdate)
  - [Filter.FieldEnumValues](#filterfieldenumvalues)
  - [Filter.Modems](#filtermodems)
  - [Filter.Modems.Update](#filtermodemsupdate)
  - [Filter.OrganizationPermissions](#filterorganizationpermissions)
  - [Filter.Organizations](#filterorganizations)
  - [Filter.Publishers](#filterpublishers)
  - [Filter.SupportPermissions](#filtersupportpermissions)
  - [Filter.Tags](#filtertags)
  - [Filter.Tags.Update](#filtertagsupdate)
  - [Filter.UserPermissions](#filteruserpermissions)
  - [Filter.Users](#filterusers)
  - [Filter.Webhooks](#filterwebhooks)
  - [Location](#location)
  - [LocationSelection](#locationselection)
  - [NamedFile](#namedfile)
  - [Pagination](#pagination)
  - [Pagination.Result](#paginationresult)
  - [Shape](#shape)
  - [TimeRange](#timerange)
  - [Timestamp](#timestamp)
  - [UpdateBoolean](#updateboolean)
  - [UpdateClearableString](#updateclearablestring)
  - [UpdateOptionalDuration](#updateoptionalduration)
  - [UpdateOptionalId](#updateoptionalid)
  - [UpdateZeroableInt](#updatezeroableint)

- Enums
  - [EventType](#eventtype)
  - [Health](#health)
  - [UnitOfMeasurement](#unitofmeasurement)


  - Enums
    - [hiber.OrganizationPermission](#hiberorganizationpermission)
    - [hiber.SupportPermission](#hibersupportpermission)
    - [hiber.UserPermission](#hiberuserpermission)

- [Scalar Value Types](#scalar-value-types)

## Messages

### Area

Rectangular area between two locations, normalized to bottom-left and top-right points.

Center point is added for convenience; it's simple the point directly between the two corner points.
When sending an Area to the api, the center location is ignored.

| Field | Type | Description |
| ----- | ---- | ----------- |
| center | [ Location](#location) | none |
| bottom_left | [ Location](#location) | none |
| top_right | [ Location](#location) | none |
| textual | [ string](#string) | Text representation. Can be used as an alternative input in a request, filled in by the API in responses. |

### Avatar

An avatar is represented either by a (publicly) fetchable URL that serves an image,
xor a binary payload that knows its name and mime-type.

If it is a url, it must be obtainable without credentials, though this is not validated by the API.
Because the content behind URL's can change or become unavailable over time,
the client should make sure it properly caches the data fetched from the URL.
("Properly" means [among other things] respecting the response headers for this resource)

| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **url_or_image**.url | [ string](#string) | A URL that contains the location of avatar. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **url_or_image**.image | [ NamedFile](#namedfile) | The data of the avatar as a Named File. |

### BytesOrHex

Some clients may prefer direct binary data, while other prefer a hexadecimal string,
both for input and output. To support both methods, this object is used to represent binary data.

When you receive this from the api, both fields are set. When sending it to the api, only one field is required.

| Field | Type | Description |
| ----- | ---- | ----------- |
| bytes | [ bytes](#bytes) | none |
| hex | [ string](#string) | none |

### BytesOrHex.Update



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ BytesOrHex](#bytesorhex) | none |

### Date

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

### DoubleRange

Decimal range.

| Field | Type | Description |
| ----- | ---- | ----------- |
| start | [ double](#double) | none |
| end | [ double](#double) | none |

### Duration



| Field | Type | Description |
| ----- | ---- | ----------- |
| duration | [ google.protobuf.Duration](#googleprotobufduration) | none |
| textual | [ string](#string) | none |

### Filter

Filters used in many api calls to filter the data sources, results, etc.

"Include" fields filter out anything not in the include set.
When not set, all items will be returned (except excluded items)

"Exclude" fields filter out anything in the exclude set.
When combined with include, exclude takes precedence when determining whether an item is filtered


### Filter.ChildOrganizations

Specify which organizations to get data from. By default, data is only retrieved for the current organization, but
using ChildOrganizations we can specify to include a number of, or all, sub-organizations.

Note: ChildOrganization differs from other filters in that it defaults to not allowing anything, where the
other filters default to allowing everything

| Field | Type | Description |
| ----- | ---- | ----------- |
| include_all | [ bool](#bool) | none |
| include | [repeated string](#string) | none |
| exclude | [repeated string](#string) | none |

### Filter.ChildOrganizations.Update

Update object to update a Filter.ChildOrganizations field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ Filter.ChildOrganizations](#filterchildorganizations) | none |

### Filter.Events



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated EventType](#eventtype) | none |
| exclude | [repeated EventType](#eventtype) | none |

### Filter.Events.Update

Update object to update a Filter.Events field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ Filter.Events](#filterevents) | none |

### Filter.FieldEnumValues



| Field | Type | Description |
| ----- | ---- | ----------- |
| field | [ string](#string) | none |
| include | [repeated string](#string) | none |
| exclude | [repeated string](#string) | none |

### Filter.Modems



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) | Include all modems with these modem numbers (HEX) |
| exclude | [repeated string](#string) | Exclude all modems with these modem numbers (HEX). Exclude takes precedence over include. |

### Filter.Modems.Update

Update object to update a Filter.Modems field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ Filter.Modems](#filtermodems) | none |

### Filter.OrganizationPermissions



| Field | Type | Description |
| ----- | ---- | ----------- |
| include_all | [ bool](#bool) | none |
| include | [repeated OrganizationPermission](#organizationpermission) | none |
| exclude | [repeated OrganizationPermission](#organizationpermission) | none |

### Filter.Organizations



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) | none |
| exclude | [repeated string](#string) | none |

### Filter.Publishers



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated int64](#int64) | none |
| exclude | [repeated int64](#int64) | none |
| only_active | [ bool](#bool) | none |

### Filter.SupportPermissions



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated SupportPermission](#supportpermission) | none |
| exclude | [repeated SupportPermission](#supportpermission) | none |

### Filter.Tags



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated int64](#int64) | none |
| exclude | [repeated int64](#int64) | none |

### Filter.Tags.Update

Update object to update a Filter.Tags field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ Filter.Tags](#filtertags) | none |

### Filter.UserPermissions



| Field | Type | Description |
| ----- | ---- | ----------- |
| include_all | [ bool](#bool) | none |
| include | [repeated UserPermission](#userpermission) | none |
| exclude | [repeated UserPermission](#userpermission) | none |

### Filter.Users



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) | none |
| exclude | [repeated string](#string) | none |

### Filter.Webhooks



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated int64](#int64) | none |
| exclude | [repeated int64](#int64) | none |
| only_active | [ bool](#bool) | none |

### Location

Geographic latitude and longitude coordinates specified in decimal degrees.
For more information, see the WGS-84 coordinate system, which is used for most GPS systems.

| Field | Type | Description |
| ----- | ---- | ----------- |
| latitude | [ double](#double) | Decimal degrees north. |
| longitude | [ double](#double) | Decimal degrees east. |
| textual | [ string](#string) | Text representation. Can be used as an alternative input in a request, filled in by the API in responses. |

### LocationSelection

Selection object for map data. Filter modems on the map by id, (child)organization.

Also, filter the map data by level and area restriction, to only display a small area at a detailed map level,
for example

| Field | Type | Description |
| ----- | ---- | ----------- |
| areas | [repeated Area](#area) | Rectangular areas, each defined by two locations, normalized to bottom-left and top-right points. |
| shapes | [repeated Shape](#shape) | Polygon shapes, each defined by a list of locations, which draw a shape on the map. |

### NamedFile

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
| data | [ BytesOrHex](#bytesorhex) | The binary payload that represents the file |
| media_type | [ string](#string) | The media-type of the file, as defined by RFC 6838 or its extensions |
| name | [ string](#string) | A semantic name for this file. |

### Pagination

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

### Pagination.Result



| Field | Type | Description |
| ----- | ---- | ----------- |
| size | [ int32](#int32) | none |
| page | [ int32](#int32) | none |
| total | [ int32](#int32) | none |
| total_pages | [ int32](#int32) | none |
| previous | [ Pagination](#pagination) | none |
| next | [ Pagination](#pagination) | none |
| approximated_total | [ bool](#bool) | Indicates that the total is an approximation, and not an exact value. This can be set for data that changes often, or is generally only fetched in an infinite scrolling manner. For example, unbundled events are likely to return an approximated total, but not guaranteed to do so. |

### Shape

Polygon shape defined by a list of locations, which draw a shape on the map.
The last point is connected to the first to close the shape.

For example, the outline of a city would be defined using a Shape,
while a rectangular region is easier to define using Area.

| Field | Type | Description |
| ----- | ---- | ----------- |
| path | [repeated Location](#location) | none |
| textual | [ string](#string) | Text representation. Can be used as an alternative input in a request, filled in by the API in responses. |

### TimeRange

Period of time between two timestamps. Typically used for filtering.

This can be used with textual shortcuts for timestamp, and some additional duration textual shortcuts:
- a duration as an offset of now, i.e. "-10h" or "PT-10h": converted to now + offset, so start.textual -10h is
  10 hours before the end time (using the ISO 8601 duration format)
Examples:
- start "-10h" end "now": a time range from 10 hours before the request time, to the request time
- start "-10h" end "2022-01-01 20:00": becomes start 2022-01-01 10:00 end 2022-01-01 20:00

| Field | Type | Description |
| ----- | ---- | ----------- |
| start | [ Timestamp](#timestamp) | none |
| end | [ Timestamp](#timestamp) | none |

### Timestamp

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

### UpdateBoolean

Update object for a boolean.

Since false is the default value, we need to distinguish between an omitted value and setting the value to false,
in an update object.

To use this to update, set a value and set updated to true

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ bool](#bool) | none |

### UpdateClearableString

Update object for a string that can be empty.

Since an empty string is also the default value, we need to distinguish between an omitted value and
setting the value to an empty string, in an update object.

To use this to update, set a value and set updated to true

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ string](#string) | none |

### UpdateOptionalDuration

Update object for an optional Duration.

To use this to update, set a value and set updated to true.
To clear the duration, set updated to true, but set no value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ Duration](#duration) | none |

### UpdateOptionalId

Update object for an optional id.

To use this to update, set a value and set updated to true. To clear the id, set updated to true, but set no value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ int64](#int64) | none |

### UpdateZeroableInt

Update object for an int that can be set to 0.

Since 0 is also the default value, we need to distinguish between an omitted value and setting the value to 0,
in an update object.

To use this to update, set a value and set updated to true

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ uint32](#uint32) | none |


## Enums
### EventType
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

### Health
Health is an indicator for issues. It is used for publishers to give a quick indication of issues.

| Name | Description | Number |
| ---- | ----------- | ------ |
| OK | none | 0 |
| WARNING | none | 1 |
| ERROR | none | 2 |

### UnitOfMeasurement
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



## Referenced messages from permission.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [permission.proto](https://github.com/HiberGlobal/api/blob/master/permission.proto).



### Enums
#### hiber.OrganizationPermission
OrganizationPermissions limit what a user can do in an Organization.
By default, everyone who has access to an organization, can access:
- organization data
- dashboard (including the map, and message count for the past days, and any events they have access to)
- tags
- deleting tags, but only if they are allowed to update the modems and webhooks the tag is assigned to

Events are filtered by permission, i.e. if you cannot access the users, you would not see user-related events.
Requesting user-related events explicitly if you cannot access the users will return an error.

| Name | Description | Number |
| ---- | ----------- | ------ |
| PERMISSION_DEFAULT | none | 0 |
| ORGANIZATION_CREATE | Create a new child organization. | 1 |
| ORGANIZATION_UPDATE | Update the organizations data, such as billing information, address, and contact. | 2 |
| ORGANIZATION_DELETE | Delete child organizations. You cannot delete your own organization. To delete your organization, contact support. | 3 |
| MODEMS | List modems, see their details and health | 10 |
| MODEMS_CREATE | Create new modems. Includes MODEMS permission. | 50 |
| MODEMS_UPDATE | Update modems, such as their peripherals, display name and tags. Includes MODEMS permission. | 11 |
| MODEMS_LICENSE_KEYS | Show and regenerate license keys. Includes MODEMS permission. | 12 |
| MODEMS_MESSAGE_BODY_PARSERS | Manage and assign message body parsers. Includes MODEMS permission. | 43 |
| MODEMS_SECURE_NOTES | Show and update secure notes. Includes MODEMS permission. | 42 |
| MODEMS_ALARMS | Manage and assign message alerts. Includes MODEMS permission. | 44 |
| MODEM_MESSAGES | Read modem messages. | 15 |
| MODEM_MESSAGES_SEND_TEST_MESSAGES | Send modem messages using the TestingService. Does not include MODEMS or MESSAGES permission. | 16 |
| MODEM_MESSAGES_SEND_REAL_MESSAGES | Send modem messages using real message sources (i.e. gateway). Does not include MODEMS or MESSAGES permission. | 41 |
| MODEM_DOWNLINK_MESSAGES | Send modem downlink messages. | 51 |
| MODEM_TRANSFERS | See modem transfers, inbound and outbound modems. Includes modems permission. | 20 |
| MODEM_TRANSFERS_SEND | Transfer modems to another organization, cancel open transfers and send return transfers. Includes modems_transfers permission. | 21 |
| MODEM_TRANSFERS_PROCESS | Mark transfers as received, prepare modems for return. This does not include actually sending the return transfer. Includes modems_transfers permission. | 22 |
| MODEM_CLAIM | Claiming modems. | 25 |
| USERS | List all users, see their names and email addresses. | 30 |
| USERS_MANAGE | Approve or create new users, remove users from the organization. Includes users permission. | 31 |
| PUBLISHERS | Manage publishers: webhooks, MQTT integration and custom email publishers. | 35 |
| TOKENS | Manage tokens. | 36 |
| CERTIFICATES | Read and use uploaded certificates (i.e. for publishers). | 38 |
| CERTIFICATES_MANAGE | Upload certificates, and update or delete uploaded certificates. | 39 |
| ASSIGNMENTS | Manage assignments using the assignment services and individual calls on, for example, ModemService. | 45 |
| SIMULATION_MANAGE | Manage simulations, like modem message simulation. | 46 |
| HEALTH_MANAGE | Manage custom health levels. | 47 |
| LOCATIONS_MANAGE | Manage saved locations using the OrganizationLocationService. | 48 |
| EXPORT | Create, access and download exports. | 49 |

#### hiber.SupportPermission
SupportPermissions are used for features typically reserved for customer support, or that behave differently
when used by a customer support operator.

| Name | Description | Number |
| ---- | ----------- | ------ |
| CUSTOMER_SUPPORT | Allow Customer Support functions. | 0 |

#### hiber.UserPermission
UserPermissions are generally used to limit what a token can do to its user.
By default, a user has all UserPermissions, which apply only to himself.
When creating a token, however, the token typically does not need permission to affect the user at all.

| Name | Description | Number |
| ---- | ----------- | ------ |
| READ | Read your name, email, linked organizations and mission-control settings. | 0 |
| UPDATE | Update your personal information, mission-control settings and default organization. Includes read permission. | 1 |
| REQUEST_ACCESS | Request access to an organization and cancel open requests. Does not include read permission. | 2 |
| DELETE | Delete your user account permanently. Includes read permission. | 3 |

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

