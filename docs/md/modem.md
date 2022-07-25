# modem.proto

Modem and message management.

Modems are anything capable of sending messages to the system. They have a unique modem number,
used to identify them.

#### This file was generated from [modem.proto](https://github.com/HiberGlobal/api/blob/master/modem.proto).

## Table of Contents

- Services
  - [ModemService](#modemservice)

- Messages
  - [CreateModem](#createmodem)
  - [CreateModem.Request](#createmodemrequest)
  - [CreateModem.Request.PeripheralsEntry](#createmodemrequestperipheralsentry)
  - [CreateModem.Response](#createmodemresponse)
  - [CreateModem.Response.CreatedModem](#createmodemresponsecreatedmodem)
  - [GetModemRequest](#getmodemrequest)
  - [ListModemMessagesRequest](#listmodemmessagesrequest)
  - [ListModemMessagesRequest.Response](#listmodemmessagesrequestresponse)
  - [ListModemsGrouped](#listmodemsgrouped)
  - [ListModemsGrouped.Request](#listmodemsgroupedrequest)
  - [ListModemsGrouped.Response](#listmodemsgroupedresponse)
  - [ListModemsRequest](#listmodemsrequest)
  - [ListModemsRequest.Response](#listmodemsrequestresponse)
  - [MessageCountRequest](#messagecountrequest)
  - [MessageCountRequest.Response](#messagecountrequestresponse)
  - [MessageCountRequest.Response.MessageCount](#messagecountrequestresponsemessagecount)
  - [Modem](#modem)
  - [Modem.ActiveSubscription](#modemactivesubscription)
  - [Modem.ConnectedDeviceInfo](#modemconnecteddeviceinfo)
  - [Modem.GatewayInfo](#modemgatewayinfo)
  - [Modem.Peripherals](#modemperipherals)
  - [Modem.Peripherals.PeripheralsEntry](#modemperipheralsperipheralsentry)
  - [Modem.TechnicalData](#modemtechnicaldata)
  - [Modem.Transfer](#modemtransfer)
  - [ModemHealthCount](#modemhealthcount)
  - [ModemHealthCount.HealthCount](#modemhealthcounthealthcount)
  - [ModemHealthCount.HealthCountGroupedPerTag](#modemhealthcounthealthcountgroupedpertag)
  - [ModemHealthCount.Request](#modemhealthcountrequest)
  - [ModemHealthCount.Response](#modemhealthcountresponse)
  - [ModemMessage](#modemmessage)
  - [ModemMessage.ParsedBody](#modemmessageparsedbody)
  - [ModemMessageSelection](#modemmessageselection)
  - [ModemMessageSelection.ModemMessageSourceFilter](#modemmessageselectionmodemmessagesourcefilter)
  - [ModemSelection](#modemselection)
  - [ModemSelection.Peripherals](#modemselectionperipherals)
  - [ModemSelection.Peripherals.ExcludeEntry](#modemselectionperipheralsexcludeentry)
  - [ModemSelection.Peripherals.IncludeAndEntry](#modemselectionperipheralsincludeandentry)
  - [ModemSelection.Peripherals.OneOfValues](#modemselectionperipheralsoneofvalues)
  - [ModemSelection.Transfers](#modemselectiontransfers)
  - [RenameModemRequest](#renamemodemrequest)
  - [UpdateModemNotesRequest](#updatemodemnotesrequest)
  - [UpdateModemNotesRequest.Response](#updatemodemnotesrequestresponse)
  - [UpdateModemSecureNotesRequest](#updatemodemsecurenotesrequest)
  - [UpdateModemSecureNotesRequest.Response](#updatemodemsecurenotesrequestresponse)
  - [UpdateModemStatusRequest](#updatemodemstatusrequest)
  - [UpdateModemStatusRequest.Response](#updatemodemstatusrequestresponse)
  - [UpdateModemTagsRequest](#updatemodemtagsrequest)
  - [UpdateModemTagsRequest.Response](#updatemodemtagsrequestresponse)
  - [UpdatePeripheralsRequest](#updateperipheralsrequest)
  - [UpdatePeripheralsRequest.AddPeripheralsEntry](#updateperipheralsrequestaddperipheralsentry)
  - [UpdatePeripheralsRequest.Response](#updateperipheralsrequestresponse)

- Enums
  - [ListModemsRequest.Sort](#listmodemsrequestsort)
  - [Modem.Peripherals.HiberAntenna](#modemperipheralshiberantenna)
  - [Modem.Status](#modemstatus)
  - [Modem.Transfer.Status](#modemtransferstatus)
  - [Modem.Type](#modemtype)
  - [ModemMessage.Source](#modemmessagesource)

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


## ModemService
The core of the Hiber system, modems are the network nodes that send information and user data.
This service contains calls to list and manage them, as well as list their messages.

### Get
> **rpc** Get([GetModemRequest](#getmodemrequest))
    [Modem](#modem)

Get a single modem.

### Create
> **rpc** Create([CreateModem.Request](#createmodemrequest))
    [CreateModem.Response](#createmodemresponse)

Create new modem(s). This is only available if your organization can create modems.

### List
> **rpc** List([ListModemsRequest](#listmodemsrequest))
    [ListModemsRequest.Response](#listmodemsrequestresponse)

List the modems in your organization, and, optionally, its child organizations.

### Grouped
> **rpc** Grouped([ListModemsGrouped.Request](#listmodemsgroupedrequest))
    [ListModemsGrouped.Response](#listmodemsgroupedresponse)

List the modems in your organization, and, optionally, its child organizations, grouped by dependency.
For example, a modem that sends it messages through a gateway (like Hilo) would be grouped under that gateway.

### Messages
> **rpc** Messages([ListModemMessagesRequest](#listmodemmessagesrequest))
    [ListModemMessagesRequest.Response](#listmodemmessagesrequestresponse)

List messages for the selected modems.

### MessageCount
> **rpc** MessageCount([MessageCountRequest](#messagecountrequest))
    [MessageCountRequest.Response](#messagecountrequestresponse)

Count messages for the selected modems.

### Rename
> **rpc** Rename([RenameModemRequest](#renamemodemrequest))
    [Modem](#modem)

Change the name of a modem to the given value.

### UpdateTags
> **rpc** UpdateTags([UpdateModemTagsRequest](#updatemodemtagsrequest))
    [UpdateModemTagsRequest.Response](#updatemodemtagsrequestresponse)

Add, remove and create new tags for the selected modems.

### UpdateNotes
> **rpc** UpdateNotes([UpdateModemNotesRequest](#updatemodemnotesrequest))
    [UpdateModemNotesRequest.Response](#updatemodemnotesrequestresponse)

Change the notes for the selected modems to the given value.

### UpdateSecureNotes
> **rpc** UpdateSecureNotes([UpdateModemSecureNotesRequest](#updatemodemsecurenotesrequest))
    [UpdateModemSecureNotesRequest.Response](#updatemodemsecurenotesrequestresponse)

Change the secure notes for the selected modems to the given value, if you have permission.

### UpdateStatus
> **rpc** UpdateStatus([UpdateModemStatusRequest](#updatemodemstatusrequest))
    [UpdateModemStatusRequest.Response](#updatemodemstatusrequestresponse)

Change the status of the selected modems to the given value.

### UpdatePeripherals
> **rpc** UpdatePeripherals([UpdatePeripheralsRequest](#updateperipheralsrequest))
    [UpdatePeripheralsRequest.Response](#updateperipheralsrequestresponse)

Add and remove peripherals for the selected modems.

### HealthCount
> **rpc** HealthCount([ModemHealthCount.Request](#modemhealthcountrequest))
    [ModemHealthCount.Response](#modemhealthcountresponse)

Count the modems in your organization by health.


## Messages

### CreateModem

Create modems for your organization.
This call is not available to all organizations, and is typically used to create modems for testing or
when you want to connect a device to the API using just the API calls in the TestingService.


### CreateModem.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| amount | [ uint32](#uint32) | The amount of modems to create. |
| names | [repeated string](#string) | The name(s) to give the new modem(s). Must not contain more values than the amount of modems to create. |
| external_device_identifiers | [repeated string](#string) | The external device identifiers for the new modems. Must not contain more values than the amount of modems to create. The order of this list matches the order of the name, values in the same index are applied to the same modem. |
| status | [ Modem.Status](#modemstatus) | The status for the new modems. |
| technical | [ Modem.TechnicalData](#modemtechnicaldata) | The technical data, such as manufacturer and hardware information for the new modems. |
| peripherals | [map CreateModem.Request.PeripheralsEntry](#createmodemrequestperipheralsentry) | The peripherals for the new modems. |
| notes | [ string](#string) | Notes for all new modems. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **initial_location**.location | [ hiber.Location](#hiberlocation) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **initial_location**.random_location_in_area | [ hiber.Area](#hiberarea) | none |
| tags | [ hiber.tag.UpdateTagsForItem](#hibertagupdatetagsforitem) | The tags to set to the new modems, either existing or created by this call. |
| include_modems_in_response | [ bool](#bool) | Whether to return the full Modem in addition to the modem number and verification code. |
| include_verification_code | [ bool](#bool) | Whether to return the verification code for the modem. |

### CreateModem.Request.PeripheralsEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ string](#string) | none |

### CreateModem.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [repeated CreateModem.Response.CreatedModem](#createmodemresponsecreatedmodem) | none |
| request | [ CreateModem.Request](#createmodemrequest) | none |

### CreateModem.Response.CreatedModem



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem_number | [ string](#string) | The modem number that was created. |
| verification_code | [ string](#string) | The verification code for this modem number, used to, for example, claim modems. Only available when include_verification_code was set to true. |
| modem | [ Modem](#modem) | Only available when include_modems_in_response was set to true. |

### GetModemRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| modem_number | [ string](#string) | none |
| child_organizations | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | none |

### ListModemMessagesRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ ModemMessageSelection](#modemmessageselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |

### ListModemMessagesRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| messages | [repeated ModemMessage](#modemmessage) | none |
| request | [ ListModemMessagesRequest](#listmodemmessagesrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### ListModemsGrouped

Lists all modems the given criteria, grouped by gateway.
Pagination is applied to modems in a group, not to the groups themselves.


### ListModemsGrouped.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| group_content | [ ListModemsRequest](#listmodemsrequest) | The modems you want to display in the groups. This is a ListModemsRequest that is used to fetch the modems for each group, with the added limitation that the modems must be in the group.

The usage of ListModemsRequest and ListModemsRequest.Response in the Response.Group was intentionally chosen to simplify pagination withing a group, since the response contains the request (which will be updated with the group it is in) and pagination to select the next page using the list method. |
| groups | [ ListModemsRequest](#listmodemsrequest) | Select the parents for the groups to display.

Anything selected here that cannot have any connected modems (i.e. a direct modem) wil be omitted unless allow_any_group_parent is set to true. Only gateways will have connected devices, so unless allow_any_group_parent is true, type is replaced with GATEWAY. This may change in the future if more grouping options are introduced. |
| allow_any_group_parent | [ bool](#bool) | Set to true to allow group request to return modems that can never be the parent of a group. - If this flag is false, the modems for the groups are automatically filtered on being a parent of a group. Note that the group may still be empty, i.e. when a gateway has no connected devices. - If this flag is true, the group parents can include modems which cannot be a parent and for which the group can only be empty. |

### ListModemsGrouped.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| groups | [repeated ListModemsRequest.Response](#listmodemsrequestresponse) | The groups, based on a parent (typically a gateway unless allow_any_group_parent was set). This is a ListModemsRequest.Response, with the selection updated with its parent and includes the group parent in the group_parents field.

The usage of ListModemsRequest and ListModemsRequest.Response in the Response.Group was intentionally chosen to simplify pagination withing a group, since the response contains the request (which will be updated with the group it is in) and pagination to select the next page using the list method. |
| request | [ ListModemsGrouped.Request](#listmodemsgroupedrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |
| sorted_by | [repeated ListModemsRequest.Sort](#listmodemsrequestsort) | none |

### ListModemsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ ModemSelection](#modemselection) | Select which modems to return. |
| pagination | [ hiber.Pagination](#hiberpagination) | Paginate through results. |
| sort_by | [repeated ListModemsRequest.Sort](#listmodemsrequestsort) | Sort the modem with the given sort options. |
| include_inbound_modems | [ bool](#bool) | Whether to include inbound modems in the results. Inbound modems are modems that are in a transfer that has been sent *to* your organization, but that has not been marked as received yet. |
| include_outbound_modems | [ bool](#bool) | Whether to include outbound modems in the results. Inbound modems are modems that are in a transfer that has been sent *from* your organization, but that has not been marked as received yet. |
| child_organizations | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | Include modems from the selected child organizations. |
| location_selection | [ hiber.LocationSelection](#hiberlocationselection) | Filter modems by location. |
| include_missing_group_parents | [ bool](#bool) | Set this to true to populate the group_parents field in the response. This will be populated with missing group parents (i.e. gateways) for the the modems on this page. Any group parent that is on the current page is not included in this list to avoid duplicate data. |

### ListModemsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [repeated Modem](#modem) | none |
| request | [ ListModemsRequest](#listmodemsrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |
| sorted_by | [repeated ListModemsRequest.Sort](#listmodemsrequestsort) | none |
| group_parents | [repeated Modem](#modem) | This will be populated with missing group parents (i.e. gateways) for the the modems on this page. Any group parent that is on the current page is not included in this list to avoid duplicate data. Only set when include_missing_group_parents is true in the request. |

### MessageCountRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ ModemMessageSelection](#modemmessageselection) | none |
| time_zone_offset | [ int32](#int32) | Numeric timezone offset for day grouping. Optional. |
| time_zone | [ string](#string) | Timezone string for day grouping. Optional. |

### MessageCountRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| message_count_per_day | [repeated MessageCountRequest.Response.MessageCount](#messagecountrequestresponsemessagecount) | none |
| request | [ MessageCountRequest](#messagecountrequest) | none |

### MessageCountRequest.Response.MessageCount



| Field | Type | Description |
| ----- | ---- | ----------- |
| date | [ hiber.Date](#hiberdate) | none |
| count | [ int32](#int32) | none |

### Modem

Modem data, including location and last message (if available).
Location, last message and firmware version can be updated by messages, the rest is typically either set
when the modem is registered into the system or when a subscription is authorized.

| Field | Type | Description |
| ----- | ---- | ----------- |
| number | [ string](#string) | An 8-character hexadecimal string |
| organization | [ string](#string) | none |
| name | [ string](#string) | An optional descriptor given to the modem |
| location | [ hiber.Location](#hiberlocation) | none |
| last_message_id | [ uint64](#uint64) | none |
| last_message_received_at | [ hiber.Timestamp](#hibertimestamp) | Time the server has received the last message. |
| last_message_sent_at | [ hiber.Timestamp](#hibertimestamp) | Time the modem has sent the last message. |
| last_message_body | [ hiber.BytesOrHex](#hiberbytesorhex) | The body of the last message. |
| inactivity | [ hiber.Duration](#hiberduration) | The amount of time since the last message from this modem was received on the server. |
| health | [ hiber.Health](#hiberhealth) | Deprecated health based on the number of error and warning events this modem has received in the past 30 days Uses the OK, WARNING, ERROR format. |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | Health level based on the modem alarm and some always-present alarms. |
| status | [ Modem.Status](#modemstatus) | none |
| active_subscription | [ Modem.ActiveSubscription](#modemactivesubscription) | additional information |
| technical | [ Modem.TechnicalData](#modemtechnicaldata) | none |
| peripherals | [ Modem.Peripherals](#modemperipherals) | none |
| in_transfer | [ Modem.Transfer](#modemtransfer) | none |
| notes | [ string](#string) | Notes field that can be used to add additional information to a modem. |
| secure_notes | [ string](#string) | Secure notes field that can be used to add additional information to a modem, with limited accessibility. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| is_gateway | [ bool](#bool) | [DEPRECATED] Whether the modem is a gateway, it has been configured as a gateway and has connected devices. Use `type` instead. |
| is_device_connected_to_gateway | [ bool](#bool) | [DEPRECATED] Whether the modem is connected to a modem configured as a gateway. Use `type` instead. |
| connected_to_gateway | [ string](#string) | [DEPRECATED] The modem number that this modem is connected to, if any. Use `connected_device_info.connected_to_gateway` instead. |
| external_device_ids | [repeated string](#string) | [DEPRECATED] External device ids, if any. Use `connected_device_info.external_device_ids` instead. |
| type | [ Modem.Type](#modemtype) | The type of modem. Used mainly to differentiate in the UI or to sort on. |
| gateway_info | [ Modem.GatewayInfo](#modemgatewayinfo) | Additional information when this modem is a gateway. |
| connected_device_info | [ Modem.ConnectedDeviceInfo](#modemconnecteddeviceinfo) | Additional information when this modem is a connected device. |
| metadata | [ google.protobuf.Struct](#googleprotobufstruct) | Modem metadata, typically extracted from messages. |
| time_zone | [ string](#string) | The timezone configured for the modem. |

### Modem.ActiveSubscription



| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.organization.subscription.ServiceType](#hiberorganizationsubscriptionservicetype) | none |
| start_date | [ hiber.Timestamp](#hibertimestamp) | none |
| end_date | [ hiber.Timestamp](#hibertimestamp) | none |

### Modem.ConnectedDeviceInfo

Additional information when this modem is a connected device.

| Field | Type | Description |
| ----- | ---- | ----------- |
| connected_to_gateway | [ string](#string) | The gateways that this modem is connected to. This field reflects the gateway that processed the last message for this modem. If the modem is connected to multiple gateways, the last used gateway is tracked here. |
| external_device_ids | [repeated string](#string) | External device ids for this modem. |

### Modem.GatewayInfo

Additional information when this modem is a gateway.

| Field | Type | Description |
| ----- | ---- | ----------- |
| number_of_connected_devices | [ int32](#int32) | none |

### Modem.Peripherals

Peripherals attached to the modem, including antenna, whether it has a gps antenna and an
open field for peripherals like battery, sensors, etc.

| Field | Type | Description |
| ----- | ---- | ----------- |
| hiber_antenna | [ Modem.Peripherals.HiberAntenna](#modemperipheralshiberantenna) | none |
| gps | [ bool](#bool) | none |
| peripherals | [map Modem.Peripherals.PeripheralsEntry](#modemperipheralsperipheralsentry) | none |
| custom_antenna | [ string](#string) | none |

### Modem.Peripherals.PeripheralsEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ string](#string) | none |

### Modem.TechnicalData



| Field | Type | Description |
| ----- | ---- | ----------- |
| hardware_name | [ string](#string) | none |
| firmware_version_name | [ string](#string) | none |
| hardware_production_batch | [ string](#string) | none |
| manufacturer | [ string](#string) | none |

### Modem.Transfer



| Field | Type | Description |
| ----- | ---- | ----------- |
| status | [ Modem.Transfer.Status](#modemtransferstatus) | none |
| identifier | [ string](#string) | none |

### ModemHealthCount




### ModemHealthCount.HealthCount



| Field | Type | Description |
| ----- | ---- | ----------- |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | Health level based on the modem alarm and some always-present alarms. |
| count | [ uint32](#uint32) | The number of modems matching the modem selection with this health level |
| health | [ hiber.Health](#hiberhealth) | Deprecated health based on the number of error and warning events this modem has received in the past 30 days Uses the OK, WARNING, ERROR format. |

### ModemHealthCount.HealthCountGroupedPerTag



| Field | Type | Description |
| ----- | ---- | ----------- |
| tag | [ hiber.tag.Tag](#hibertagtag) | The tag this count is for. |
| health_counts | [repeated ModemHealthCount.HealthCount](#modemhealthcounthealthcount) | none |

### ModemHealthCount.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| modem_selection | [ ModemSelection](#modemselection) | Selection of modems to count. If default, all modems are counted. |
| include_tag_count | [ bool](#bool) | Whether to return specific counts for tags, selected using the tag_count_selection. |
| tag_count_selection | [ hiber.tag.TagSelection](#hibertagtagselection) | Selection of tags to return specific counts for. If default, count is calculated for all tags. |

### ModemHealthCount.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| health_totals | [repeated ModemHealthCount.HealthCount](#modemhealthcounthealthcount) | none |
| health_grouped_per_tag | [repeated ModemHealthCount.HealthCountGroupedPerTag](#modemhealthcounthealthcountgroupedpertag) | none |
| request | [ ModemHealthCount.Request](#modemhealthcountrequest) | none |

### ModemMessage

Decrypted modem message. Messages are received encrypted and decrypted asynchronously, which adds the location
data and message body. (Your message body is, of course, still encrypted if you've encrypted it yourself)

| Field | Type | Description |
| ----- | ---- | ----------- |
| message_id | [ uint64](#uint64) | Unique message identifier. |
| modem_number | [ string](#string) | Modem number of the modem that sent the message. |
| modem_name | [ string](#string) | The name of the modem that sent the message. |
| modem_identifier | [ string](#string) | The device identifier for the modem that sent the message (e.g. a MAC address). |
| sent_at | [ hiber.Timestamp](#hibertimestamp) | Time the message was sent from the modem. |
| received_at | [ hiber.Timestamp](#hibertimestamp) | Time the message was received on the server. |
| location | [ hiber.Location](#hiberlocation) | Modem location when the message was sent. |
| body | [ bytes](#bytes) | Message body. |
| body_bytes | [ hiber.BytesOrHex](#hiberbytesorhex) | Message body convenience object. |
| body_parsed | [repeated ModemMessage.ParsedBody](#modemmessageparsedbody) | A list of applied body parsers and their results. |
| body_parsed_successfully | [ bool](#bool) | Convenience flag marking whether the body was parsed successfully by at least one parser. |
| sources | [repeated ModemMessage.Source](#modemmessagesource) | Message source(s) for this message (i.e. it was received through the satellite or directly to the server). |
| is_test | [ bool](#bool) | True if the the TEST source is in the sources. |
| is_gateway_message | [ bool](#bool) | Whether this message contains other messages. |
| via_gateway_message | [ uint64](#uint64) | The gateway message this message was sent in. |
| metadata | [ google.protobuf.Struct](#googleprotobufstruct) | Message metadata, defined by the modem or gateway. |
| body_fields | [ google.protobuf.Struct](#googleprotobufstruct) | Flattened results of all successful body parsers.

This is a convenience to access the fields from body_parsed, but if any fields are present in multiple body_parsed results, it is not defined which field will be used in this Struct. This may change in the future. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | The tags of the modem that sent the message. |
| tag_names | [repeated string](#string) | The names of the tags of the modem that sent the message. |

### ModemMessage.ParsedBody

Parsed message body.
If any parsers are configured for the modem, they are applied to the message.
The result is stored either as a json object or an error string.

| Field | Type | Description |
| ----- | ---- | ----------- |
| parser_id | [ int32](#int32) | Id of the parser that was used, if the parser and modem are owned by the same organization. [DEPRECATED] Deprecated in favour of the identifier, which is globally unique. |
| parser_identifier | [ string](#string) | Globally unique identifier of the parser that was used. |
| parser_name | [ string](#string) | Name of the parser that was used. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **parsed**.error | [ string](#string) | Error while parsing the message body. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **parsed**.result | [ google.protobuf.Struct](#googleprotobufstruct) | Result of parsing the body with this parser. |

### ModemMessageSelection

Selection object for modem messages.
Filter messages by modem id, (child)organization, and time sent (note that this is not the time the message was received)

| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [ hiber.Filter.Modems](#hiberfiltermodems) | Define the modems to return messages for, i.e. include = [AAAA AAAA, BBBB BBBB]. Deprecated in favor of using the ModemSelection. |
| modem_selection | [ ModemSelection](#modemselection) | Select the modems to return messages for. |
| time_range | [ hiber.TimeRange](#hibertimerange) | Filter message by time range. This field is required, to limit the amount of messages. |
| filter_by_sources | [ ModemMessageSelection.ModemMessageSourceFilter](#modemmessageselectionmodemmessagesourcefilter) | Filter messages by the given source filter. For example, to exclude test and simulated messages, use exclude = [TEST, SIMULATED] or to only return Hiberband messages, use include = [HIBERBAND]. Note that if a message has sources [HIBERBAND, DIRECT_TO_API], including [HIBERBAND] will include the message, and excluding [HIBERBAND] will filter out the message, even though it also has DIRECT_TO_API. |

### ModemMessageSelection.ModemMessageSourceFilter



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated ModemMessage.Source](#modemmessagesource) | none |
| exclude | [repeated ModemMessage.Source](#modemmessagesource) | none |

### ModemSelection

Selection object for modems.
Filter modems by modem id, (child)organization, tags, activation status and time, service type and last message time.

| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [ hiber.Filter.Modems](#hiberfiltermodems) | none |
| free_text_search | [ string](#string) | none |
| only_active | [ bool](#bool) | none |
| activated_in | [ hiber.TimeRange](#hibertimerange) | none |
| with_last_message_in | [ hiber.TimeRange](#hibertimerange) | none |
| with_service_type | [repeated hiber.organization.subscription.ServiceType](#hiberorganizationsubscriptionservicetype) | none |
| health | [repeated hiber.Health](#hiberhealth) | Deprecated health that uses the OK, WARNING, ERROR format. |
| health_levels | [repeated string](#string) | Filter modems by health level. |
| status | [repeated Modem.Status](#modemstatus) | Filter modems by status(es). Defaults to nominal statuses, excluding disabled, dead, lost or damaged modems. |
| transfers | [ ModemSelection.Transfers](#modemselectiontransfers) | none |
| include_types | [repeated Modem.Type](#modemtype) | Only include modems that have a type listed in types. In other words, when providing multiple types, this is an "OR" relationship. |
| exclude_types | [repeated Modem.Type](#modemtype) | Exclude modems that have a type listed in types. |
| only_gateways | [ bool](#bool) | [DEPRECATED] Only list devices that are a gateway. Replaced by `types`. If you only want to have gateways in the result, create a selection with only `Modem.Type.GATEWAY` for `types`. |
| only_has_external_device_ids | [ bool](#bool) | [DEPRECATED] Only list devices that are a connected devices. Typically these are LoRaWAN sensors. Replaced by `types`. If you only want to have connected devices in the result, create a selection with only `Modem.Type.CONNECTED_DEVICE` for `types`. |
| connected_to_gateways | [ hiber.Filter.Modems](#hiberfiltermodems) | none |
| external_device_ids | [repeated string](#string) | none |
| filter_by_tags | [ hiber.tag.TagSelection](#hibertagtagselection) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **peripheral_selection**.peripherals | [ ModemSelection.Peripherals](#modemselectionperipherals) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **peripheral_selection**.only_without_peripheral | [ bool](#bool) | When set to true, only modems that do not have any peripheral will be included in the result. |

### ModemSelection.Peripherals

Filter to (de)select modems based on their peripherals.

| Field | Type | Description |
| ----- | ---- | ----------- |
| include_and | [map ModemSelection.Peripherals.IncludeAndEntry](#modemselectionperipheralsincludeandentry) | Filter to only include modems with all of the given set of peripherals. Peripherals are stored as a name-value pair (e.g. bluetooth, 4.0 / bluetooth, BLE). To select for multiple versions of a peripheral, add the name of the peripheral as a map-key and add a repeated list of versions as the map-value.

For example: - include { 'bluetooth' -> [ ] } returns all modems that have any version of bluetooth, - include { 'bluetooth' -> [ '4.0', '5.0' ] } will only return modems that have bluetooth version 4.0 _or_ 5.0, - include { 'bluetooth' -> [ '' ] } would only select bluetooth peripherals that don't have any version set, - include { 'bluetooth' -> [ ], 'LoRaWAN' -> [ ] } will only select modems that have both bluetooth (any version) _and_ LoRaWAN (any version), - include { 'bluetooth' -> [ ] }, exclude { 'bluetooth' -> [ ] } will return an empty list since exclude will take precedence, and - include { 'bluetooth' -> [ ] }, exclude { 'bluetooth' -> [ '3.0' ] } returns modems that have bluetooth, but not version 3.0. |
| exclude | [map ModemSelection.Peripherals.ExcludeEntry](#modemselectionperipheralsexcludeentry) | Filter to exclude modems with any of the given set of peripherals. Peripherals are stored as a name-value pair (e.g. bluetooth, 4.0 / bluetooth, BLE). To select for multiple versions of a peripheral, add the name of the peripheral as a map-key and add a repeated list of versions as the map-value.

For example: - exclude { 'bluetooth' -> [ ] } returns only modems that do not have any version of bluetooth, - exclude { 'bluetooth' -> [ '4.0', '5.0' ] } returns modems that might have bluetooth as long as it's not versions 4.0 or 5.0, - exclude { 'bluetooth' -> [ '' ] } returns modems that might have bluetooth as long as it's version is set to a specific value, - exclude { 'bluetooth' -> [ ], 'LoRaWAN' -> [ ] } returns modems that don't have bluetooth and/or LoRaWAN. - include { 'bluetooth' -> [ ] }, exclude { bluetooth' -> [ ] } will return an empty list, since exclusion takes precedence, and - include { 'bluetooth' -> [ ] }, exclude { bluetooth' -> [ '3.0' ] } returns only modems that have bluetooth, but not version 3.0 |

### ModemSelection.Peripherals.ExcludeEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ ModemSelection.Peripherals.OneOfValues](#modemselectionperipheralsoneofvalues) | none |

### ModemSelection.Peripherals.IncludeAndEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ ModemSelection.Peripherals.OneOfValues](#modemselectionperipheralsoneofvalues) | none |

### ModemSelection.Peripherals.OneOfValues



| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [repeated string](#string) | none |

### ModemSelection.Transfers



| Field | Type | Description |
| ----- | ---- | ----------- |
| transfers_identifiers | [repeated string](#string) | none |

### RenameModemRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| modem_number | [ string](#string) | none |
| name | [ string](#string) | none |

### UpdateModemNotesRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ ModemSelection](#modemselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |
| notes | [ string](#string) | Notes content |
| allow_override_existing_notes | [ bool](#bool) | When you try to set a new notes value to multiple modems, the API returns an error if their previous values were different. Set this to true to apply it anyway. |

### UpdateModemNotesRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [repeated Modem](#modem) | none |
| request | [ UpdateModemNotesRequest](#updatemodemnotesrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### UpdateModemSecureNotesRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| modem_number | [ string](#string) | none |
| secure_notes | [ string](#string) | none |

### UpdateModemSecureNotesRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem | [ Modem](#modem) | none |
| request | [ UpdateModemSecureNotesRequest](#updatemodemsecurenotesrequest) | none |

### UpdateModemStatusRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| modem_number | [ string](#string) | Either pick a single modem to update. DEPRECATED, since ModemSelection is more flexible. |
| modem_selection | [ ModemSelection](#modemselection) | Or a modem selection. |
| update_status | [ Modem.Status](#modemstatus) | The new status for the modem(s). |
| pagination | [ hiber.Pagination](#hiberpagination) | Pagination for the modems in the Response. |

### UpdateModemStatusRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem | [ Modem](#modem) | none |
| modems | [repeated Modem](#modem) | none |
| request | [ UpdateModemStatusRequest](#updatemodemstatusrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### UpdateModemTagsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| update | [ hiber.tag.UpdateTagsForItem](#hibertagupdatetagsforitem) | none |
| selection | [ ModemSelection](#modemselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |

### UpdateModemTagsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [repeated Modem](#modem) | none |
| request | [ UpdateModemTagsRequest](#updatemodemtagsrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### UpdatePeripheralsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ ModemSelection](#modemselection) | none |
| hiber_antenna | [ Modem.Peripherals.HiberAntenna](#modemperipheralshiberantenna) | none |
| gps | [ hiber.UpdateBoolean](#hiberupdateboolean) | none |
| hardcoded_gps_location | [ hiber.Location](#hiberlocation) | none |
| add_peripherals | [map UpdatePeripheralsRequest.AddPeripheralsEntry](#updateperipheralsrequestaddperipheralsentry) | none |
| remove_peripherals | [repeated string](#string) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |
| custom_antenna | [ string](#string) | none |
| time_zone | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |

### UpdatePeripheralsRequest.AddPeripheralsEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ string](#string) | none |

### UpdatePeripheralsRequest.Response

The result is paginated if affecting more than 100 modems. Use the list call to paginate further.

| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ UpdatePeripheralsRequest](#updateperipheralsrequest) | none |
| modems | [repeated Modem](#modem) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |


## Enums
### ListModemsRequest.Sort
Sorting options for the results.

| Name | Description | Number |
| ---- | ----------- | ------ |
| LAST_MESSAGE_RECEIVED | none | 0 |
| LAST_MESSAGE_RECEIVED_INVERTED | none | 1 |
| MODEM_NUMBER_ASC | Sort numerically on the number of the modem. | 2 |
| MODEM_NUMBER_DESC | none | 3 |
| STATUS_ASC | none | 4 |
| STATUS_DESC | none | 5 |
| MODEM_NAME_ASC | Sort alphabetically on the name of the modem. De default name of the modem is its HEX number | 6 |
| MODEM_NAME_DESC | none | 7 |
| ORGANIZATION_ASC | Sort alphabetically on the name of the organization that owns the modem | 8 |
| ORGANIZATION_DESC | none | 9 |
| HEALTH | Health sorted from least to most severe (i.e. OK, WARNING, ERROR). | 10 |
| HEALTH_DESC | Health sorted from most to least severe (i.e. ERROR, WARNING, OK). | 11 |

### Modem.Peripherals.HiberAntenna
A Hiber antenna is required for the modem to function.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | none | 0 |
| HIBER_PANDA | none | 1 |
| HIBER_GRIZZLY | none | 2 |
| HIBER_BLACK | none | 3 |
| CUSTOM | none | 4 |

### Modem.Status
Modem statuses for its lifecycle.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | Modem is in your inventory, but not deployed or active. | 0 |
| ACTIVE | Modem is active and sending messages. See health for more details on its health, based on the past messages. | 1 |
| DAMAGED | none | 2 |
| LOST | none | 3 |
| DEAD | none | 4 |
| DISABLED | none | 5 |

### Modem.Transfer.Status


| Name | Description | Number |
| ---- | ----------- | ------ |
| NONE | none | 0 |
| INBOUND | Modem has been shipped or transferred to you and is inbound. When you mark the transfer as received, the modems are added to your organization. If you encounter any issues, you can mark modems for return using the ModemTransferReturnService. | 1 |
| OUTBOUND | Modem has been shipped or transferred by you and is outbound. When the transfer is received, the modems are removed from your organization, though the recipient may still return them later. | 2 |
| RETURNING | You shipped this modem to another organization, but they are returning it. When you mark the transfer as received, the modems are added back to your organization. | 3 |

### Modem.Type
The effective type of this modem.
Type can depend on the hardware itself as well as network topology.

| Name | Description | Number |
| ---- | ----------- | ------ |
| OTHER | A device of which the specific type is not known | 0 |
| DIRECT | A devices that directly connects to the satellite | 1 |
| GATEWAY | A device that can receive messages from sensors in the field and relay them (directly) to the satellite. Typically a LoRaWAN hub. Note that gateways also send messages themselves (e.g. a daily heartbeat). | 2 |
| CONNECTED_DEVICE | A sensor that can (only) send data to a gateway. Typically using a LoRaWAN connection. | 3 |

### ModemMessage.Source


| Name | Description | Number |
| ---- | ----------- | ------ |
| HIBERBAND | A real message from a modem or gateway, sent over Hiberband to the server. | 0 |
| DIRECT_TO_API | A real message from a modem or gateway, sent directly to the API using a persistent connection. | 1 |
| TEST | A test message sent to the testing API. | 2 |
| SIMULATION | A simulated message, generated by the server. | 3 |



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

