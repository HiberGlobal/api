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
  - [ListModemsGrouped.Response.Total](#listmodemsgroupedresponsetotal)
  - [ListModemsRequest](#listmodemsrequest)
  - [ListModemsRequest.Response](#listmodemsrequestresponse)
  - [MessageCountRequest](#messagecountrequest)
  - [MessageCountRequest.Response](#messagecountrequestresponse)
  - [MessageCountRequest.Response.MessageCount](#messagecountrequestresponsemessagecount)
  - [Modem](#modem)
  - [Modem.ConnectedDeviceInfo](#modemconnecteddeviceinfo)
  - [Modem.GatewayInfo](#modemgatewayinfo)
  - [Modem.Peripherals](#modemperipherals)
  - [Modem.Peripherals.PeripheralsEntry](#modemperipheralsperipheralsentry)
  - [Modem.TechnicalData](#modemtechnicaldata)
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
  - [TagCount](#tagcount)
  - [TagCount.Request](#tagcountrequest)
  - [TagCount.Response](#tagcountresponse)
  - [UpdateModemLifecycleRequest](#updatemodemlifecyclerequest)
  - [UpdateModemLifecycleRequest.Response](#updatemodemlifecyclerequestresponse)
  - [UpdateModemNotesRequest](#updatemodemnotesrequest)
  - [UpdateModemNotesRequest.Response](#updatemodemnotesrequestresponse)
  - [UpdateModemSecureNotesRequest](#updatemodemsecurenotesrequest)
  - [UpdateModemSecureNotesRequest.Response](#updatemodemsecurenotesrequestresponse)
  - [UpdateModemTagsRequest](#updatemodemtagsrequest)
  - [UpdateModemTagsRequest.Response](#updatemodemtagsrequestresponse)
  - [UpdatePeripheralsRequest](#updateperipheralsrequest)
  - [UpdatePeripheralsRequest.AddPeripheralsEntry](#updateperipheralsrequestaddperipheralsentry)
  - [UpdatePeripheralsRequest.Response](#updateperipheralsrequestresponse)

- Enums
  - [ListModemsRequest.Sort](#listmodemsrequestsort)
  - [Modem.Lifecycle](#modemlifecycle)
  - [Modem.Type](#modemtype)
  - [ModemMessage.Source](#modemmessagesource)

- Referenced messages from [health.proto](#referenced-messages-from-healthproto)
  - [hiber.health.HealthLevel](#hiberhealthhealthlevel)
  - [hiber.health.HealthLevelSelection](#hiberhealthhealthlevelselection)


- Referenced messages from [organization.proto](#referenced-messages-from-organizationproto)
  - [hiber.organization.CreateOrganizationRequest](#hiberorganizationcreateorganizationrequest)
  - [hiber.organization.DeleteOrganizationRequest](#hiberorganizationdeleteorganizationrequest)
  - [hiber.organization.DeleteOrganizationRequest.Response](#hiberorganizationdeleteorganizationrequestresponse)
  - [hiber.organization.GetOrganizationAvatar](#hiberorganizationgetorganizationavatar)
  - [hiber.organization.GetOrganizationAvatar.Request](#hiberorganizationgetorganizationavatarrequest)
  - [hiber.organization.GetOrganizationAvatar.Response](#hiberorganizationgetorganizationavatarresponse)
  - [hiber.organization.GetOrganizationAvatar.Response.AvatarsEntry](#hiberorganizationgetorganizationavatarresponseavatarsentry)
  - [hiber.organization.GetOrganizationRequest](#hiberorganizationgetorganizationrequest)
  - [hiber.organization.ListChildOrganizationsRequest](#hiberorganizationlistchildorganizationsrequest)
  - [hiber.organization.ListChildOrganizationsRequest.Response](#hiberorganizationlistchildorganizationsrequestresponse)
  - [hiber.organization.Organization](#hiberorganizationorganization)
  - [hiber.organization.Organization.Address](#hiberorganizationorganizationaddress)
  - [hiber.organization.Organization.Contact](#hiberorganizationorganizationcontact)
  - [hiber.organization.Organization.Defaults](#hiberorganizationorganizationdefaults)
  - [hiber.organization.OrganizationSelection](#hiberorganizationorganizationselection)
  - [hiber.organization.OrganizationTree](#hiberorganizationorganizationtree)
  - [hiber.organization.OrganizationTreeRequest](#hiberorganizationorganizationtreerequest)
  - [hiber.organization.OrganizationTreeRequest.Response](#hiberorganizationorganizationtreerequestresponse)
  - [hiber.organization.UpdateOrganizationRequest](#hiberorganizationupdateorganizationrequest)
  - [hiber.organization.ValidateOrganizationCreationTokenRequest](#hiberorganizationvalidateorganizationcreationtokenrequest)
  - [hiber.organization.ValidateOrganizationCreationTokenRequest.Response](#hiberorganizationvalidateorganizationcreationtokenrequestresponse)

    - [hiber.organization.Organization.Feature](#hiberorganizationorganizationfeature)

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
  - [hiber.value.Value.Numeric.Percentage](#hibervaluevaluenumericpercentage)
  - [hiber.value.Value.Numeric.Pressure](#hibervaluevaluenumericpressure)
  - [hiber.value.Value.Numeric.Rate](#hibervaluevaluenumericrate)
  - [hiber.value.Value.Numeric.RotationSpeed](#hibervaluevaluenumericrotationspeed)
  - [hiber.value.Value.Numeric.Speed](#hibervaluevaluenumericspeed)
  - [hiber.value.Value.Numeric.Temperature](#hibervaluevaluenumerictemperature)
  - [hiber.value.Value.Numeric.Voltage](#hibervaluevaluenumericvoltage)
  - [hiber.value.Value.Numeric.Volume](#hibervaluevaluenumericvolume)
  - Enums
    - [hiber.value.Value.Numeric.BatteryLevel.Unit](#hibervaluevaluenumericbatterylevelunit)
    - [hiber.value.Value.Numeric.Distance.Unit](#hibervaluevaluenumericdistanceunit)
    - [hiber.value.Value.Numeric.Duration.Unit](#hibervaluevaluenumericdurationunit)
    - [hiber.value.Value.Numeric.Flow.Unit](#hibervaluevaluenumericflowunit)
    - [hiber.value.Value.Numeric.FuelEfficiency.Unit](#hibervaluevaluenumericfuelefficiencyunit)
    - [hiber.value.Value.Numeric.Mass.Unit](#hibervaluevaluenumericmassunit)
    - [hiber.value.Value.Numeric.Percentage.Unit](#hibervaluevaluenumericpercentageunit)
    - [hiber.value.Value.Numeric.Pressure.Unit](#hibervaluevaluenumericpressureunit)
    - [hiber.value.Value.Numeric.Rate.Unit](#hibervaluevaluenumericrateunit)
    - [hiber.value.Value.Numeric.RotationSpeed.Unit](#hibervaluevaluenumericrotationspeedunit)
    - [hiber.value.Value.Numeric.Speed.Unit](#hibervaluevaluenumericspeedunit)
    - [hiber.value.Value.Numeric.Temperature.Unit](#hibervaluevaluenumerictemperatureunit)
    - [hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype)
    - [hiber.value.Value.Numeric.Voltage.Unit](#hibervaluevaluenumericvoltageunit)
    - [hiber.value.Value.Numeric.Volume.Unit](#hibervaluevaluenumericvolumeunit)
    - [hiber.value.Value.Type](#hibervaluevaluetype)
    - [hiber.value.ValueAggregation](#hibervaluevalueaggregation)
    - [hiber.value.ValueTransformation](#hibervaluevaluetransformation)

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

<strong>Deprecated.</strong> List messages for the selected modems.

### MessageCount
> **rpc** MessageCount([MessageCountRequest](#messagecountrequest))
    [MessageCountRequest.Response](#messagecountrequestresponse)

<strong>Deprecated.</strong> Count messages for the selected modems.

### Rename
> **rpc** Rename([RenameModemRequest](#renamemodemrequest))
    [Modem](#modem)

<strong>Deprecated.</strong> Change the name of a modem to the given value.

### UpdateTags
> **rpc** UpdateTags([UpdateModemTagsRequest](#updatemodemtagsrequest))
    [UpdateModemTagsRequest.Response](#updatemodemtagsrequestresponse)

Add, remove and create new tags for the selected modems.

### UpdateNotes
> **rpc** UpdateNotes([UpdateModemNotesRequest](#updatemodemnotesrequest))
    [UpdateModemNotesRequest.Response](#updatemodemnotesrequestresponse)

<strong>Deprecated.</strong> Change the notes for the selected modems to the given value.

### UpdateSecureNotes
> **rpc** UpdateSecureNotes([UpdateModemSecureNotesRequest](#updatemodemsecurenotesrequest))
    [UpdateModemSecureNotesRequest.Response](#updatemodemsecurenotesrequestresponse)

<strong>Deprecated.</strong> Change the secure notes for the selected modems to the given value, if you have permission.

### UpdateStatus
> **rpc** UpdateStatus([UpdateModemLifecycleRequest](#updatemodemlifecyclerequest))
    [UpdateModemLifecycleRequest.Response](#updatemodemlifecyclerequestresponse)

<strong>Deprecated.</strong> Change the status of the selected modems to the given value.

### UpdatePeripherals
> **rpc** UpdatePeripherals([UpdatePeripheralsRequest](#updateperipheralsrequest))
    [UpdatePeripheralsRequest.Response](#updateperipheralsrequestresponse)

<strong>Deprecated.</strong> Add and remove peripherals for the selected modems.

### HealthCount
> **rpc** HealthCount([ModemHealthCount.Request](#modemhealthcountrequest))
    [ModemHealthCount.Response](#modemhealthcountresponse)

<strong>Deprecated.</strong> Count the modems in your organization by health.

### TagCount
> **rpc** TagCount([TagCount.Request](#tagcountrequest))
    [TagCount.Response](#tagcountresponse)




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
| lifecycle | [ Modem.Lifecycle](#modemlifecycle) | The status for the new modems. |
| technical | [ Modem.TechnicalData](#modemtechnicaldata) | The technical data, such as manufacturer and hardware information for the new modems. |
| peripherals | [map CreateModem.Request.PeripheralsEntry](#createmodemrequestperipheralsentry) | The peripherals for the new modems. |
| notes | [ string](#string) | Notes for all new modems. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **initial_location**.location | [ hiber.Location](#hiberlocation) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **initial_location**.random_location_in_area | [ hiber.Area](#hiberarea) |  |
| tags | [ hiber.tag.UpdateTagsForItem](#hibertagupdatetagsforitem) | The tags to set to the new modems, either existing or created by this call. |
| include_modems_in_response | [ bool](#bool) | Whether to return the full Modem in addition to the modem number and verification code. |
| include_verification_code | [ bool](#bool) | Whether to return the verification code for the modem. |

### CreateModem.Request.PeripheralsEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ string](#string) |  |

### CreateModem.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [repeated CreateModem.Response.CreatedModem](#createmodemresponsecreatedmodem) |  |
| request | [ CreateModem.Request](#createmodemrequest) |  |

### CreateModem.Response.CreatedModem



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem_number | [ string](#string) | The modem number that was created. |
| verification_code | [ string](#string) | The verification code for this modem number, used to, for example, claim modems. Only available when include_verification_code was set to true. |
| modem | [ Modem](#modem) | Only available when include_modems_in_response was set to true. |

### GetModemRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **where**.organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **where**.in_organizations | [ hiber.organization.OrganizationSelection](#hiberorganizationorganizationselection) | If set, look up the modem in multiple organizations, instead of in the given or default organization. This can be used to find a modem if you do not know in which organization it is. Since this is a selection object, an empty selection searches in all accessible organizations, but the organizations can be limited using the fields in the OrganizationSelection. |
| modem_number | [ string](#string) | The modem to get. |
| child_organizations | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | <strong>Deprecated.</strong> Look for the modem in child organizations. DEPRECATED: use the in_organizations flag instead. |

### ListModemMessagesRequest

<strong>Deprecated.</strong> 

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ ModemMessageSelection](#modemmessageselection) |  |
| pagination | [ hiber.Pagination](#hiberpagination) |  |

### ListModemMessagesRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| messages | [repeated ModemMessage](#modemmessage) |  |
| request | [ ListModemMessagesRequest](#listmodemmessagesrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### ListModemsGrouped

Lists all modems the given criteria, grouped by gateway.
Pagination is applied to modems in a group, not to the groups themselves.


### ListModemsGrouped.Request

The usage of ListModemsRequest and ListModemsRequest.Response in the Response.Group was intentionally
chosen to simplify pagination withing a group, since the response contains the request
(which will be updated with the group it is in) and pagination to select the next page using the
list method.

| Field | Type | Description |
| ----- | ---- | ----------- |
| group_content | [ ListModemsRequest](#listmodemsrequest) | The modems you want to display in the groups. This is a ListModemsRequest that is used to fetch the modems for each group, with the added limitation that the modems must be in the group. |
| groups | [ ListModemsRequest](#listmodemsrequest) | Select the parents for the groups to display. Anything selected here that cannot have any connected modems (i.e. a direct modem) wil be omitted unless allow_any_group_parent is set to true. Only gateways will have connected devices, so unless allow_any_group_parent is true, type is replaced with GATEWAY. This may change in the future if more grouping options are introduced. |
| allow_any_group_parent | [ bool](#bool) | Set to true to allow group request to return modems that can never be the parent of a group. - If this flag is false, the modems for the groups are automatically filtered on being a parent of a group. Note that the group may still be empty, i.e. when a gateway has no connected devices. - If this flag is true, the group parents can include modems which cannot be a parent and for which the group can only be empty. |

### ListModemsGrouped.Response

The usage of ListModemsRequest and ListModemsRequest.Response in the Response.Group was intentionally
chosen to simplify pagination withing a group, since the response contains the request
(which will be updated with the group it is in) and pagination to select the next page using the
list method.

| Field | Type | Description |
| ----- | ---- | ----------- |
| groups | [repeated ListModemsRequest.Response](#listmodemsrequestresponse) | The groups, based on a parent (typically a gateway unless allow_any_group_parent was set). This is a ListModemsRequest.Response, with the selection updated with its parent and includes the group parent in the group_parents field. |
| request | [ ListModemsGrouped.Request](#listmodemsgroupedrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |
| sorted_by | [repeated ListModemsRequest.Sort](#listmodemsrequestsort) |  |
| total | [ ListModemsGrouped.Response.Total](#listmodemsgroupedresponsetotal) |  |

### ListModemsGrouped.Response.Total



| Field | Type | Description |
| ----- | ---- | ----------- |
| groups | [ uint32](#uint32) |  |
| content | [ uint32](#uint32) |  |
| all | [ uint32](#uint32) |  |

### ListModemsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ ModemSelection](#modemselection) | Select which modems to return. |
| pagination | [ hiber.Pagination](#hiberpagination) | Paginate through results. |
| sort_by | [repeated ListModemsRequest.Sort](#listmodemsrequestsort) | Sort the modem with the given sort options. |
| child_organizations | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | Include modems from the selected child organizations. |
| location_selection | [ hiber.LocationSelection](#hiberlocationselection) | Filter modems by location. |
| include_missing_group_parents | [ bool](#bool) | Set this to true to populate the group_parents field in the response. This will be populated with missing group parents (i.e. gateways) for the the modems on this page. Any group parent that is on the current page is not included in this list to avoid duplicate data. |

### ListModemsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [repeated Modem](#modem) |  |
| request | [ ListModemsRequest](#listmodemsrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |
| sorted_by | [repeated ListModemsRequest.Sort](#listmodemsrequestsort) |  |
| group_parents | [repeated Modem](#modem) | This will be populated with missing group parents (i.e. gateways) for the the modems on this page. Any group parent that is on the current page is not included in this list to avoid duplicate data. Only set when include_missing_group_parents is true in the request. |

### MessageCountRequest

<strong>Deprecated.</strong> 

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ ModemMessageSelection](#modemmessageselection) |  |
| time_zone_offset | [ int32](#int32) | Numeric timezone offset for day grouping. Optional. |
| time_zone | [ string](#string) | Timezone string for day grouping. Optional. |

### MessageCountRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| message_count_per_day | [repeated MessageCountRequest.Response.MessageCount](#messagecountrequestresponsemessagecount) |  |
| request | [ MessageCountRequest](#messagecountrequest) |  |

### MessageCountRequest.Response.MessageCount



| Field | Type | Description |
| ----- | ---- | ----------- |
| date | [ hiber.Date](#hiberdate) |  |
| count | [ int32](#int32) |  |

### Modem

Modem data, including location and last message (if available).
Location, last message and firmware version can be updated by messages, the rest is typically either set
when the modem is registered into the system or when a subscription is authorized.

| Field | Type | Description |
| ----- | ---- | ----------- |
| number | [ string](#string) | An 8-character hexadecimal string |
| organization | [ string](#string) |  |
| name | [ string](#string) | An optional descriptor given to the modem |
| location | [ hiber.Location](#hiberlocation) |  |
| last_message_id | [ uint64](#uint64) |  |
| last_message_received_at | [ hiber.Timestamp](#hibertimestamp) | Time the server has received the last message. |
| last_message_sent_at | [ hiber.Timestamp](#hibertimestamp) | Time the modem has sent the last message. |
| last_message_body | [ hiber.BytesOrHex](#hiberbytesorhex) | The body of the last message. |
| inactivity | [ hiber.Duration](#hiberduration) | The amount of time since the last message from this modem was received on the server. |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | Health level based on the modem alarm and some always-present alarms. |
| lifecycle | [ Modem.Lifecycle](#modemlifecycle) |  |
| technical | [ Modem.TechnicalData](#modemtechnicaldata) | additional information |
| peripherals | [ Modem.Peripherals](#modemperipherals) |  |
| notes | [ string](#string) | Notes field that can be used to add additional information to a modem. |
| secure_notes | [ string](#string) | Secure notes field that can be used to add additional information to a modem, with limited accessibility. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| is_gateway | [ bool](#bool) | <strong>Deprecated.</strong> [DEPRECATED] Whether the modem is a gateway, it has been configured as a gateway and has connected devices. Use `type` instead. |
| is_device_connected_to_gateway | [ bool](#bool) | <strong>Deprecated.</strong> [DEPRECATED] Whether the modem is connected to a modem configured as a gateway. Use `type` instead. |
| connected_to_gateway | [ string](#string) | <strong>Deprecated.</strong> [DEPRECATED] The modem number that this modem is connected to, if any. Use `connected_device_info.connected_to_gateway` instead. |
| external_device_ids | [repeated string](#string) | <strong>Deprecated.</strong> [DEPRECATED] External device ids, if any. Use `connected_device_info.external_device_ids` instead. |
| type | [ Modem.Type](#modemtype) | The type of modem. Used mainly to differentiate in the UI or to sort on. |
| gateway_info | [ Modem.GatewayInfo](#modemgatewayinfo) | Additional information when this modem is a gateway. |
| connected_device_info | [ Modem.ConnectedDeviceInfo](#modemconnecteddeviceinfo) | Additional information when this modem is a connected device. |
| metadata | [ google.protobuf.Struct](#googleprotobufstruct) | Modem metadata, typically extracted from messages. |
| time_zone | [ string](#string) | The timezone configured for the modem. |
| transmission_interval | [ hiber.Duration](#hiberduration) | The transmission interval for this modem, if configured. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **_expected_transmission_rate**.expected_transmission_rate | [optional hiber.value.Value.Numeric.Rate](#hibervaluevaluenumericrate) | The expected transmission rate for this modem. |

### Modem.ConnectedDeviceInfo

Additional information when this modem is a connected device.

| Field | Type | Description |
| ----- | ---- | ----------- |
| connected_to_gateway | [ string](#string) | The gateways that this modem is connected to. This field reflects the gateway that processed the last message for this modem. If the modem is connected to multiple gateways, the last used gateway is tracked here. |
| external_device_ids | [repeated string](#string) | External device ids for this modem. |
| device_type | [ string](#string) | Device type for this modem. |
| sensor_brand | [ string](#string) | Brand for this modem's sensor. |

### Modem.GatewayInfo

Additional information when this modem is a gateway.

| Field | Type | Description |
| ----- | ---- | ----------- |
| number_of_connected_devices | [ int32](#int32) |  |
| device_type | [ string](#string) | Device type for this gateway. |
| gateway_brand | [ string](#string) | Brand for this gateway. |

### Modem.Peripherals

Peripherals attached to the modem, including antenna, whether it has a gps antenna and an
open field for peripherals like battery, sensors, etc.

| Field | Type | Description |
| ----- | ---- | ----------- |
| gps | [ bool](#bool) |  |
| peripherals | [map Modem.Peripherals.PeripheralsEntry](#modemperipheralsperipheralsentry) |  |
| custom_antenna | [ string](#string) |  |

### Modem.Peripherals.PeripheralsEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ string](#string) |  |

### Modem.TechnicalData



| Field | Type | Description |
| ----- | ---- | ----------- |
| hardware_production_batch | [ string](#string) |  |
| manufacturer | [ string](#string) |  |

### ModemHealthCount

<strong>Deprecated.</strong> Deprecated: replaced with simpler calls in TagService.TagHealth and ModemService.TagCount.


### ModemHealthCount.HealthCount

<strong>Deprecated.</strong> 

| Field | Type | Description |
| ----- | ---- | ----------- |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | Health level based on the modem alarm and some always-present alarms. |
| count | [ uint32](#uint32) | The number of modems matching the modem selection with this health level |

### ModemHealthCount.HealthCountGroupedPerTag

<strong>Deprecated.</strong> 

| Field | Type | Description |
| ----- | ---- | ----------- |
| tag | [ hiber.tag.Tag](#hibertagtag) | The tag this count is for. |
| health_counts | [repeated ModemHealthCount.HealthCount](#modemhealthcounthealthcount) |  |

### ModemHealthCount.Request

<strong>Deprecated.</strong> 

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| modem_selection | [ ModemSelection](#modemselection) | Selection of modems to count. If default, all modems are counted. |
| include_tag_count | [ bool](#bool) | Whether to return specific counts for tags, selected using the tag_count_selection. |
| tag_count_selection | [ hiber.tag.TagSelection](#hibertagtagselection) | Selection of tags to return specific counts for. If default, count is calculated for all tags. |

### ModemHealthCount.Response

<strong>Deprecated.</strong> 

| Field | Type | Description |
| ----- | ---- | ----------- |
| health_totals | [repeated ModemHealthCount.HealthCount](#modemhealthcounthealthcount) |  |
| health_grouped_per_tag | [repeated ModemHealthCount.HealthCountGroupedPerTag](#modemhealthcounthealthcountgroupedpertag) |  |
| request | [ ModemHealthCount.Request](#modemhealthcountrequest) |  |

### ModemMessage

<strong>Deprecated.</strong> Decrypted modem message. Messages are received encrypted and decrypted asynchronously, which adds the location
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
| body_fields | [ google.protobuf.Struct](#googleprotobufstruct) | Flattened results of all successful body parsers. This is a convenience to access the fields from body_parsed, but if any fields are present in multiple body_parsed results, it is not defined which field will be used in this Struct. This may change in the future. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | The tags of the modem that sent the message. |
| tag_names | [repeated string](#string) | The names of the tags of the modem that sent the message. |

### ModemMessage.ParsedBody

Parsed message body.
If any parsers are configured for the modem, they are applied to the message.
The result is stored either as a json object or an error string.

| Field | Type | Description |
| ----- | ---- | ----------- |
| parser_id | [ int32](#int32) | <strong>Deprecated.</strong> Id of the parser that was used, if the parser and modem are owned by the same organization. [DEPRECATED] Deprecated in favour of the identifier, which is globally unique. |
| parser_identifier | [ string](#string) | Globally unique identifier of the parser that was used. |
| parser_name | [ string](#string) | Name of the parser that was used. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **parsed**.error | [ string](#string) | Error while parsing the message body. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **parsed**.result | [ google.protobuf.Struct](#googleprotobufstruct) | Result of parsing the body with this parser. |

### ModemMessageSelection

<strong>Deprecated.</strong> Selection object for modem messages.
Filter messages by modem id, (child)organization, and time sent (note that this is not the time the message was received)

| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [ hiber.Filter.Modems](#hiberfiltermodems) | <strong>Deprecated.</strong> Define the modems to return messages for, i.e. include = [AAAA AAAA, BBBB BBBB]. Deprecated in favor of using the ModemSelection. |
| modem_selection | [ ModemSelection](#modemselection) | Select the modems to return messages for. |
| time_range | [ hiber.TimeRange](#hibertimerange) | Filter message by time range. This field is required, to limit the amount of messages. |
| filter_by_sources | [ ModemMessageSelection.ModemMessageSourceFilter](#modemmessageselectionmodemmessagesourcefilter) | Filter messages by the given source filter. For example, to exclude test and simulated messages, use exclude = [TEST, SIMULATED] or to only return Hiberband messages, use include = [HIBERBAND]. Note that if a message has sources [HIBERBAND, DIRECT_TO_API], including [HIBERBAND] will include the message, and excluding [HIBERBAND] will filter out the message, even though it also has DIRECT_TO_API. |

### ModemMessageSelection.ModemMessageSourceFilter



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated ModemMessage.Source](#modemmessagesource) |  |
| exclude | [repeated ModemMessage.Source](#modemmessagesource) |  |

### ModemSelection

Selection object for modems.
Filter modems by modem id, (child)organization, tags, activation status and time, service type and last message time.

| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [ hiber.Filter.Modems](#hiberfiltermodems) |  |
| free_text_search | [ string](#string) |  |
| only_active | [ bool](#bool) | <strong>Deprecated.</strong> Use lifecycle filter instead. |
| activated_in | [ hiber.TimeRange](#hibertimerange) | <strong>Deprecated.</strong>  |
| with_last_message_in | [ hiber.TimeRange](#hibertimerange) |  |
| health_levels | [repeated string](#string) | Filter modems by health level. |
| lifecycles | [repeated Modem.Lifecycle](#modemlifecycle) | Filter modems by lifecycle(s). Defaults to nominal lifecycles, excluding disabled or decommissioned modems. |
| transfers | [ ModemSelection.Transfers](#modemselectiontransfers) |  |
| include_types | [repeated Modem.Type](#modemtype) | Only include modems that have a type listed in types. In other words, when providing multiple types, this is an "OR" relationship. |
| exclude_types | [repeated Modem.Type](#modemtype) | Exclude modems that have a type listed in types. |
| device_types | [ hiber.Filter.DeviceTypes](#hiberfilterdevicetypes) |  |
| sensorBrands | [ hiber.Filter.SensorBrands](#hiberfiltersensorbrands) |  |
| identifiers | [ hiber.Filter.ModemIdentifiers](#hiberfiltermodemidentifiers) |  |
| only_gateways | [ bool](#bool) | <strong>Deprecated.</strong> [DEPRECATED] Only list devices that are a gateway. Replaced by `types`. If you only want to have gateways in the result, create a selection with only `Modem.Type.GATEWAY` for `types`. |
| only_has_external_device_ids | [ bool](#bool) | <strong>Deprecated.</strong> [DEPRECATED] Only list devices that are a connected devices. Typically these are LoRaWAN sensors. Replaced by `types`. If you only want to have connected devices in the result, create a selection with only `Modem.Type.CONNECTED_DEVICE` for `types`. |
| connected_to_gateways | [ hiber.Filter.Modems](#hiberfiltermodems) |  |
| external_device_ids | [repeated string](#string) | <strong>Deprecated.</strong>  |
| filter_by_tags | [ hiber.tag.TagSelection](#hibertagtagselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **peripheral_selection**.peripherals | [ ModemSelection.Peripherals](#modemselectionperipherals) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **peripheral_selection**.only_without_peripheral | [ bool](#bool) | When set to true, only modems that do not have any peripheral will be included in the result. |
| only_connected_to_gateway | [ bool](#bool) | Only select modems that are connected to a gateway (connected devices). |
| not_connected_to_gateway | [ bool](#bool) | Only select modems that are not connected to a gateway (i.e. gateways). |

### ModemSelection.Peripherals

Filter to (de)select modems based on their peripherals.

For example:
- include { 'bluetooth' -> [ ] }
    returns all modems that have any version of bluetooth,
- include { 'bluetooth' -> [ '4.0', '5.0' ] }
    will only return modems that have bluetooth version 4.0 _or_ 5.0,
- include { 'bluetooth' -> [ '' ] }
    would only select bluetooth peripherals that don't have any version set,
- include { 'bluetooth' -> [ ], 'LoRaWAN' -> [ ] }
    will only select modems that have both bluetooth (any version) _and_ LoRaWAN (any version),
- include { 'bluetooth' -> [ ] }, exclude { 'bluetooth' -> [ ] }
    will return an empty list since exclude will take precedence, and
- include { 'bluetooth' -> [ ] }, exclude { 'bluetooth' -> [ '3.0' ] }
    returns modems that have bluetooth, but not version 3.0.
- exclude { 'bluetooth' -> [ ] }
    returns only modems that do not have any version of bluetooth,
- exclude { 'bluetooth' -> [ '4.0', '5.0' ] }
    returns modems that might have bluetooth as long as it's not versions 4.0 or 5.0,
- exclude { 'bluetooth' -> [ '' ] }
    returns modems that might have bluetooth as long as it's version is set to a specific value,
- exclude { 'bluetooth' -> [ ], 'LoRaWAN' -> [ ] }
    returns modems that don't have bluetooth and/or LoRaWAN.
- include { 'bluetooth' -> [ ] }, exclude { bluetooth' -> [ ] }
    will return an empty list, since exclusion takes precedence, and
- include { 'bluetooth' -> [ ] }, exclude { bluetooth' -> [ '3.0' ] }
    returns only modems that have bluetooth, but not version 3.0

| Field | Type | Description |
| ----- | ---- | ----------- |
| include_and | [map ModemSelection.Peripherals.IncludeAndEntry](#modemselectionperipheralsincludeandentry) | Filter to only include modems with all of the given set of peripherals. Peripherals are stored as a name-value pair (e.g. bluetooth, 4.0 / bluetooth, BLE). To select for multiple versions of a peripheral, add the name of the peripheral as a map-key and add a repeated list of versions as the map-value. |
| exclude | [map ModemSelection.Peripherals.ExcludeEntry](#modemselectionperipheralsexcludeentry) | Filter to exclude modems with any of the given set of peripherals. Peripherals are stored as a name-value pair (e.g. bluetooth, 4.0 / bluetooth, BLE). To select for multiple versions of a peripheral, add the name of the peripheral as a map-key and add a repeated list of versions as the map-value. |

### ModemSelection.Peripherals.ExcludeEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ ModemSelection.Peripherals.OneOfValues](#modemselectionperipheralsoneofvalues) |  |

### ModemSelection.Peripherals.IncludeAndEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ ModemSelection.Peripherals.OneOfValues](#modemselectionperipheralsoneofvalues) |  |

### ModemSelection.Peripherals.OneOfValues



| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [repeated string](#string) |  |

### ModemSelection.Transfers



| Field | Type | Description |
| ----- | ---- | ----------- |
| transfers_identifiers | [repeated string](#string) |  |

### RenameModemRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| modem_number | [ string](#string) |  |
| name | [ string](#string) |  |

### TagCount



| Field | Type | Description |
| ----- | ---- | ----------- |
| tag | [ hiber.tag.Tag](#hibertagtag) |  |
| modems | [ uint32](#uint32) |  |

### TagCount.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ ModemSelection](#modemselection) |  |
| tag_selection | [ hiber.tag.TagSelection](#hibertagtagselection) |  |

### TagCount.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| tags | [repeated TagCount](#tagcount) |  |
| request | [ TagCount.Request](#tagcountrequest) |  |

### UpdateModemLifecycleRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| modem_number | [ string](#string) | <strong>Deprecated.</strong> Either pick a single modem to update. DEPRECATED, since ModemSelection is more flexible. |
| modem_selection | [ ModemSelection](#modemselection) | Or a modem selection. |
| update_lifecycle | [ Modem.Lifecycle](#modemlifecycle) | The new status for the modem(s). |
| pagination | [ hiber.Pagination](#hiberpagination) | Pagination for the modems in the Response. |

### UpdateModemLifecycleRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem | [ Modem](#modem) | <strong>Deprecated.</strong>  |
| modems | [repeated Modem](#modem) |  |
| request | [ UpdateModemLifecycleRequest](#updatemodemlifecyclerequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### UpdateModemNotesRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ ModemSelection](#modemselection) |  |
| pagination | [ hiber.Pagination](#hiberpagination) |  |
| notes | [ string](#string) | Notes content |
| allow_override_existing_notes | [ bool](#bool) | When you try to set a new notes value to multiple modems, the API returns an error if their previous values were different. Set this to true to apply it anyway. |

### UpdateModemNotesRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [repeated Modem](#modem) |  |
| request | [ UpdateModemNotesRequest](#updatemodemnotesrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### UpdateModemSecureNotesRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| modem_number | [ string](#string) |  |
| secure_notes | [ string](#string) |  |

### UpdateModemSecureNotesRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem | [ Modem](#modem) |  |
| request | [ UpdateModemSecureNotesRequest](#updatemodemsecurenotesrequest) |  |

### UpdateModemTagsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| update | [ hiber.tag.UpdateTagsForItem](#hibertagupdatetagsforitem) |  |
| selection | [ ModemSelection](#modemselection) |  |
| pagination | [ hiber.Pagination](#hiberpagination) |  |

### UpdateModemTagsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [repeated Modem](#modem) |  |
| request | [ UpdateModemTagsRequest](#updatemodemtagsrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### UpdatePeripheralsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ ModemSelection](#modemselection) |  |
| gps | [ hiber.UpdateBoolean](#hiberupdateboolean) |  |
| hardcoded_gps_location | [ hiber.Location](#hiberlocation) |  |
| add_peripherals | [map UpdatePeripheralsRequest.AddPeripheralsEntry](#updateperipheralsrequestaddperipheralsentry) |  |
| remove_peripherals | [repeated string](#string) |  |
| pagination | [ hiber.Pagination](#hiberpagination) |  |
| custom_antenna | [ string](#string) |  |
| time_zone | [ hiber.UpdateClearableString](#hiberupdateclearablestring) |  |
| update_transmission_interval | [ hiber.Duration](#hiberduration) |  |
| remove_transmission_interval | [ bool](#bool) |  |

### UpdatePeripheralsRequest.AddPeripheralsEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ string](#string) |  |

### UpdatePeripheralsRequest.Response

The result is paginated if affecting more than 100 modems. Use the list call to paginate further.

| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ UpdatePeripheralsRequest](#updateperipheralsrequest) |  |
| modems | [repeated Modem](#modem) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |


## Enums
### ListModemsRequest.Sort
Sorting options for the results.

| Name | Description | Number |
| ---- | ----------- | ------ |
| LAST_MESSAGE_RECEIVED | Sorts messages in descending time order. | 0 |
| LAST_MESSAGE_RECEIVED_INVERTED | Sorts messages in ascending time order. | 1 |
| MODEM_NUMBER_ASC | Sort numerically on the number of the modem, in ascending order. | 2 |
| MODEM_NUMBER_DESC | Sort numerically on the number of the modem, in descending order. | 3 |
| STATUS_ASC | Sort modem on its Status. | 4 |
| STATUS_DESC | Sort modem on its Status in reverse order. | 5 |
| STATUS_ASC_ALPHABETICAL | Status sorted alphabetically by Status name. | 14 |
| STATUS_DESC_ALPHABETICAL | Status sorted alphabetically by Status name, descending order. | 15 |
| MODEM_NAME_ASC | Sort alphabetically on the name of the modem. De default name of the modem is its HEX number, in ascending order. | 6 |
| MODEM_NAME_DESC | Sort alphabetically on the name of the modem. De default name of the modem is its HEX number, in descending order. | 7 |
| ORGANIZATION_ASC | Sort alphabetically on the name of the organization that owns the modem, in ascending order. | 8 |
| ORGANIZATION_DESC | Sort alphabetically on the name of the organization that owns the modem, in descending order. | 9 |
| HEALTH | Health sorted from least to most severe (i.e. OK, WARNING, ERROR). | 10 |
| HEALTH_DESC | Health sorted from most to least severe (i.e. ERROR, WARNING, OK). | 11 |
| HEALTH_ASC_ALPHABETICAL | Health sorted alphabetically by health level name. | 12 |
| HEALTH_DESC_ALPHABETICAL | Health sorted alphabetically by health level name, descending order. | 13 |
| SENSOR_BRAND_ASC | Sort alphabetically on the brand of the sensor, in ascending order. | 16 |
| SENSOR_BRAND_DESC | Sort alphabetically on the brand of the sensor, in descending order. | 17 |
| DEVICE_TYPE_ASC | Sort alphabetically on the device type, in ascending order. | 18 |
| DEVICE_TYPE_DESC | Sort alphabetically on the device type, in descending order. | 19 |
| TAG_TYPE_WELL_ASC | Sort alphabetically on any tags of type 'well', in ascending order. | 20 |
| TAG_TYPE_WELL_DESC | Sort alphabetically on any tags of type 'well', in descending order. | 21 |
| TAG_TYPE_SITE_ASC | Sort alphabetically on any tags of type 'site', in ascending order. | 22 |
| TAG_TYPE_SITE_DESC | Sort alphabetically on any tags of type 'site', in descending order. | 23 |
| TAG_TYPE_PRODUCTION_AREA_ASC | Sort alphabetically on any tags of type 'production_area', in ascending order. | 24 |
| TAG_TYPE_PRODUCTION_AREA_DESC | Sort alphabetically on any tags of type 'production_area', in descending order. | 25 |

### Modem.Lifecycle


| Name | Description | Number |
| ---- | ----------- | ------ |
| ACCEPTANCE_TESTING | Device is deployed, but not active yet. Invisible for customer. | 0 |
| INSTALLED | Device is active and sending messages. See health for more details on its health, based on the past messages. | 1 |
| PAUSED | Device is paused and not sending messages. This should be of a temporary nature. (e.g. a change to the installation is being made) | 6 |
| DISABLED | Device is disabled and not sending messages. Invisible for customer. This could be either temporary or become permanent. Used for cases where devices is being serviced and customer should not be burdened with the health of this device. | 5 |
| DECOMMISSIONED | Device is (going to be) removed from installation and will not return to installed status again. | 4 |
| DEFECTIVE | Device is defective and should not be used anymore. | 7 |

### Modem.Type
The effective type of this modem.
Type can depend on the hardware itself as well as network topology.

| Name | Description | Number |
| ---- | ----------- | ------ |
| OTHER | A device of which the specific type is not known | 0 |
| DISCONNECTED_SENSOR | A device that is not currently connected to a gateway. | 1 |
| GATEWAY | A device that can receive messages from sensors in the field and relay them (directly) to the satellite. Typically a LoRaWAN hub. Note that gateways also send messages themselves (e.g. a daily heartbeat). | 2 |
| SENSOR | A sensor that can (only) send data to a gateway. Typically using a LoRaWAN connection. | 3 |

### ModemMessage.Source


| Name | Description | Number |
| ---- | ----------- | ------ |
| HIBERBAND | A real message from a modem or gateway, sent over Hiberband to the server. | 0 |
| DIRECT_TO_API | A real message from a modem or gateway, sent directly to the API using a persistent connection. | 1 |
| TEST | A test message sent to the testing API. | 2 |
| SIMULATION | A simulated message, generated by the server. | 3 |



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
| search | [ string](#string) | Search for the given string in the levels and colors. |
| levels | [repeated string](#string) | Filter by exact levels. |


### Enums


## Referenced messages from organization.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [organization.proto](https://github.com/HiberGlobal/api/blob/master/organization.proto).


### hiber.organization.CreateOrganizationRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| parent_organization | [ string](#string) | Pick the organization to use as parent. If unset, your default organization is used. If you have no organization, an organization_creation_token is required. |
| new_organization | [ string](#string) | The name for the new organization. Lowercase, letters, numbers, dashes and underscores only. Required. Used as an identifier for the organization. |
| display_name | [ string](#string) | The name to display for your organization (i.e. capitalized, with spaces, etc.). Default to the name above. |
| avatar | [ hiber.Avatar](#hiberavatar) | The avatar image representing this organization. Usually the logo. |
| is_business | [ bool](#bool) | Whether this organization is created for a business. |
| vat_number | [ string](#string) | Whether this organization is created for a business, provide a VAT number. |
| address | [ hiber.organization.Organization.Address](#hiberorganizationorganizationaddress) | Postal address for your organization. |
| billing_name | [ string](#string) | Billing information for your organization. Optional, but required if you want active modems. |
| billing_address | [ hiber.organization.Organization.Address](#hiberorganizationorganizationaddress) | Billing address for your organization. Optional, but required if you want active modems. |
| contact | [ hiber.organization.Organization.Contact](#hiberorganizationorganizationcontact) | Contact information for your organization. Required. |
| organization_creation_token | [ string](#string) | A token that allows you to create an organization without having an organization. |

### hiber.organization.DeleteOrganizationRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| parent_organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| organization_to_delete | [ string](#string) | The organization to delete. Required. |

### hiber.organization.DeleteOrganizationRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization_to_delete | [ string](#string) |  |
| organizations_deleted | [ hiber.organization.OrganizationTree](#hiberorganizationorganizationtree) | The organizations that were deleted. |

### hiber.organization.GetOrganizationAvatar




### hiber.organization.GetOrganizationAvatar.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organizations | [repeated string](#string) | The slug for this organization, used to identify organizations |
| pagination | [ hiber.Pagination](#hiberpagination) |  |

### hiber.organization.GetOrganizationAvatar.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| avatars | [map hiber.organization.GetOrganizationAvatar.Response.AvatarsEntry](#hiberorganizationgetorganizationavatarresponseavatarsentry) | Avatars, indexed by organization slug |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### hiber.organization.GetOrganizationAvatar.Response.AvatarsEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ hiber.Avatar](#hiberavatar) |  |

### hiber.organization.GetOrganizationRequest

Get your current organization's data

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to get the details for. If unset, your default organization is used. |

### hiber.organization.ListChildOrganizationsRequest

List the child organizations for the given organization

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.organization.OrganizationSelection](#hiberorganizationorganizationselection) |  |
| pagination | [ hiber.Pagination](#hiberpagination) |  |
| include_details | [ bool](#bool) |  |

### hiber.organization.ListChildOrganizationsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| child_organizations | [repeated hiber.organization.Organization](#hiberorganizationorganization) |  |
| request | [ hiber.organization.ListChildOrganizationsRequest](#hiberorganizationlistchildorganizationsrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### hiber.organization.Organization

Organization data. An Organization can have many linked users, but the organization is the owner
of any modems and related data.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | The slug for this organization, used to identify organizations |
| display_name | [ string](#string) | The name of the organization to display to the end-user |
| address | [ hiber.organization.Organization.Address](#hiberorganizationorganizationaddress) |  |
| contact | [ hiber.organization.Organization.Contact](#hiberorganizationorganizationcontact) |  |
| vat_number | [ string](#string) |  |
| billing_name | [ string](#string) |  |
| billing_address | [ hiber.organization.Organization.Address](#hiberorganizationorganizationaddress) |  |
| contract_signature_date | [ hiber.Timestamp](#hibertimestamp) |  |
| created_at | [ hiber.Timestamp](#hibertimestamp) |  |
| updated_at | [ hiber.Timestamp](#hibertimestamp) |  |
| features | [repeated hiber.organization.Organization.Feature](#hiberorganizationorganizationfeature) |  |
| database_info | [ string](#string) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **_defaults**.defaults | [optional hiber.organization.Organization.Defaults](#hiberorganizationorganizationdefaults) |  |

### hiber.organization.Organization.Address



| Field | Type | Description |
| ----- | ---- | ----------- |
| lines | [repeated string](#string) |  |
| zip_code | [ string](#string) |  |
| city | [ string](#string) |  |
| state | [ string](#string) |  |
| country | [ string](#string) |  |

### hiber.organization.Organization.Contact



| Field | Type | Description |
| ----- | ---- | ----------- |
| name | [ string](#string) |  |
| email | [ string](#string) |  |
| phone | [ string](#string) |  |

### hiber.organization.Organization.Defaults

Default settings for this organization.

| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **_expected_device_transmission_rate**.expected_device_transmission_rate | [optional hiber.value.Value.Numeric.Rate](#hibervaluevaluenumericrate) | The default expected transmission interval for devices in this organization. |

### hiber.organization.OrganizationSelection

Selection object for child organizations.
User for child organization list and tree.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organizations | [ hiber.Filter.Organizations](#hiberfilterorganizations) |  |
| search | [ string](#string) |  |

### hiber.organization.OrganizationTree



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ hiber.organization.Organization](#hiberorganizationorganization) |  |
| children | [repeated hiber.organization.OrganizationTree](#hiberorganizationorganizationtree) |  |

### hiber.organization.OrganizationTreeRequest

Get your current organization's organization tree.
The organization tree contains your current organization as the root of the tree, with all child organizations ordered below it.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate) for this call, overriding your default organization |
| selection | [ hiber.organization.OrganizationSelection](#hiberorganizationorganizationselection) |  |

### hiber.organization.OrganizationTreeRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ hiber.organization.OrganizationTreeRequest](#hiberorganizationorganizationtreerequest) |  |
| tree | [ hiber.organization.OrganizationTree](#hiberorganizationorganizationtree) |  |

### hiber.organization.UpdateOrganizationRequest

Update organization data.
All fields are effectively optional, though address, billing_address, contact and features are assumed to be complete objects,
not partial updates.
Note that the organization field specifies the organization, it is not used to update the current organization identifier.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| display_name | [ string](#string) |  |
| vat_number | [ string](#string) |  |
| address | [ hiber.organization.Organization.Address](#hiberorganizationorganizationaddress) |  |
| billing_name | [ string](#string) |  |
| billing_address | [ hiber.organization.Organization.Address](#hiberorganizationorganizationaddress) |  |
| contact | [ hiber.organization.Organization.Contact](#hiberorganizationorganizationcontact) |  |
| avatar | [ hiber.Avatar](#hiberavatar) |  |

### hiber.organization.ValidateOrganizationCreationTokenRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization_creation_token | [ string](#string) | A token that allows you to create an organization without having an organization. |

### hiber.organization.ValidateOrganizationCreationTokenRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| valid | [ bool](#bool) |  |


### Enums
#### hiber.organization.Organization.Feature


| Name | Description | Number |
| ---- | ----------- | ------ |
| UNKNOWN |  | 0 |
| HIBER | The default Hiber set of features including Mission Control and the API | 1 |
| HILO | A limited set of features corresponding to the HiberHilo product. | 2 |
| MODEM_CREATION | Required to manually create modems using the ModemService. | 4 |
| EARLY_ACCESS | Used for organizations that get early access to features. | 5 |
| EXPERIMENTAL | Used for organizations that get access to experimental features. e.g. feature work in progress. | 6 |
| BI_TOOLING_BETA | Integrate BI tooling in the Mission Control interface. | 8 |



## Referenced messages from tag.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [tag.proto](https://github.com/HiberGlobal/api/blob/master/tag.proto).


### hiber.tag.Tag



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) |  |
| label | [ hiber.tag.Tag.Label](#hibertagtaglabel) |  |

### hiber.tag.Tag.Label



| Field | Type | Description |
| ----- | ---- | ----------- |
| name | [ string](#string) |  |
| type | [ string](#string) |  |

### hiber.tag.TagSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| search | [repeated string](#string) |  |
| names | [repeated string](#string) |  |
| filter | [ hiber.Filter.Tags](#hiberfiltertags) |  |
| types | [repeated string](#string) |  |


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
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.battery_level | [ hiber.value.Value.Numeric.BatteryLevel](#hibervaluevaluenumericbatterylevel) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.distance | [ hiber.value.Value.Numeric.Distance](#hibervaluevaluenumericdistance) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.duration | [ hiber.value.Value.Numeric.Duration](#hibervaluevaluenumericduration) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.fuel_efficiency | [ hiber.value.Value.Numeric.FuelEfficiency](#hibervaluevaluenumericfuelefficiency) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.percentage | [ hiber.value.Value.Numeric.Percentage](#hibervaluevaluenumericpercentage) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.pressure | [ hiber.value.Value.Numeric.Pressure](#hibervaluevaluenumericpressure) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.speed | [ hiber.value.Value.Numeric.Speed](#hibervaluevaluenumericspeed) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.temperature | [ hiber.value.Value.Numeric.Temperature](#hibervaluevaluenumerictemperature) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.voltage | [ hiber.value.Value.Numeric.Voltage](#hibervaluevaluenumericvoltage) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.volume | [ hiber.value.Value.Numeric.Volume](#hibervaluevaluenumericvolume) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.mass | [ hiber.value.Value.Numeric.Mass](#hibervaluevaluenumericmass) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.flow | [ hiber.value.Value.Numeric.Flow](#hibervaluevaluenumericflow) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.rotation_speed | [ hiber.value.Value.Numeric.RotationSpeed](#hibervaluevaluenumericrotationspeed) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.rate | [ hiber.value.Value.Numeric.Rate](#hibervaluevaluenumericrate) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.unknown | [ double](#double) |  |

### hiber.value.Value.Numeric.BatteryLevel

Special case for battery level, since it can be provided in many units.
Not included in the UnitPreferences, since it cannot be converted.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) |  |
| unit | [ hiber.value.Value.Numeric.BatteryLevel.Unit](#hibervaluevaluenumericbatterylevelunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.BatteryLevel.Unit](#hibervaluevaluenumericbatterylevelunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Distance

The value is a distance value, converted to your preferred distance unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) |  |
| unit | [ hiber.value.Value.Numeric.Distance.Unit](#hibervaluevaluenumericdistanceunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Distance.Unit](#hibervaluevaluenumericdistanceunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Duration



| Field | Type | Description |
| ----- | ---- | ----------- |
| duration | [ google.protobuf.Duration](#googleprotobufduration) |  |
| value | [ double](#double) |  |
| unit | [ hiber.value.Value.Numeric.Duration.Unit](#hibervaluevaluenumericdurationunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Duration.Unit](#hibervaluevaluenumericdurationunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Flow



| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) |  |
| unit | [ hiber.value.Value.Numeric.Flow.Unit](#hibervaluevaluenumericflowunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Flow.Unit](#hibervaluevaluenumericflowunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.FuelEfficiency

The value is a distance value, converted to your preferred distance unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) |  |
| unit | [ hiber.value.Value.Numeric.FuelEfficiency.Unit](#hibervaluevaluenumericfuelefficiencyunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.FuelEfficiency.Unit](#hibervaluevaluenumericfuelefficiencyunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Mass

The value is a volume value, converted to your preferred volume unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) |  |
| unit | [ hiber.value.Value.Numeric.Mass.Unit](#hibervaluevaluenumericmassunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Mass.Unit](#hibervaluevaluenumericmassunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Percentage

The value is a percentage.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ float](#float) |  |
| unit | [ hiber.value.Value.Numeric.Percentage.Unit](#hibervaluevaluenumericpercentageunit) |  |
| textual | [ string](#string) | Textual representation with % symbol, rounded based on the user preferences and field config. |

### hiber.value.Value.Numeric.Pressure

The value is a pressure value, converted to your preferred pressure unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) |  |
| unit | [ hiber.value.Value.Numeric.Pressure.Unit](#hibervaluevaluenumericpressureunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Pressure.Unit](#hibervaluevaluenumericpressureunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Rate



| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ uint32](#uint32) |  |
| unit | [ hiber.value.Value.Numeric.Rate.Unit](#hibervaluevaluenumericrateunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Rate.Unit](#hibervaluevaluenumericrateunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.RotationSpeed

The value for rotation speed. The only value is revolutions per minute (RPM), therefore it is not included in
unit preferences.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) |  |
| unit | [ hiber.value.Value.Numeric.RotationSpeed.Unit](#hibervaluevaluenumericrotationspeedunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.RotationSpeed.Unit](#hibervaluevaluenumericrotationspeedunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Speed

The value is a speed value, converted to your preferred speed unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) |  |
| unit | [ hiber.value.Value.Numeric.Speed.Unit](#hibervaluevaluenumericspeedunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Speed.Unit](#hibervaluevaluenumericspeedunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Temperature

The value is a temperature, converted to your preferred temperature unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) |  |
| unit | [ hiber.value.Value.Numeric.Temperature.Unit](#hibervaluevaluenumerictemperatureunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Temperature.Unit](#hibervaluevaluenumerictemperatureunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Voltage

The value is a voltage, converted to your preferred voltage unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) |  |
| unit | [ hiber.value.Value.Numeric.Voltage.Unit](#hibervaluevaluenumericvoltageunit) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Voltage.Unit](#hibervaluevaluenumericvoltageunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Volume

The value is a volume value, converted to your preferred volume unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) |  |
| unit | [ hiber.value.Value.Numeric.Volume.Unit](#hibervaluevaluenumericvolumeunit) |  |
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
| METER |  | 0 |
| MILLIMETER |  | 1 |
| CENTIMETER |  | 2 |
| KILOMETER |  | 3 |
| YARD |  | 5 |
| MILE |  | 4 |
| FOOT |  | 6 |
| INCH |  | 7 |
| NAUTICAL_MILE | This is a special case unit and may not be auto-converted to your UnitPreference. | 8 |

#### hiber.value.Value.Numeric.Duration.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| MILLISECONDS |  | 0 |
| SECONDS |  | 1 |
| MINUTES |  | 2 |
| HOURS |  | 3 |
| DAYS |  | 4 |
| WEEKS |  | 5 |

#### hiber.value.Value.Numeric.Flow.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| CUBIC_METER_PER_HOUR |  | 0 |
| BARRELS_PER_DAY |  | 1 |

#### hiber.value.Value.Numeric.FuelEfficiency.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| LITER_PER_100_KILOMETER |  | 0 |
| KILOMETER_PER_LITER |  | 1 |
| KILOMETER_PER_GALLON |  | 2 |
| KILOMETER_PER_IMPERIAL_GALLON |  | 3 |
| MILE_PER_GALLON |  | 4 |
| MILE_PER_IMPERIAL_GALLON |  | 5 |
| MILE_PER_LITER |  | 6 |

#### hiber.value.Value.Numeric.Mass.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| KILOGRAMS |  | 0 |
| POUNDS |  | 1 |

#### hiber.value.Value.Numeric.Percentage.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| PERCENT | Technically not a unit, but for consistency, we've added it here. | 0 |

#### hiber.value.Value.Numeric.Pressure.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| BAR |  | 0 |
| PSI |  | 1 |
| K_PA |  | 2 |

#### hiber.value.Value.Numeric.Rate.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| ITEMS_PER_24_HOURS | The amount of items counted in a 24 hour window. | 0 |

#### hiber.value.Value.Numeric.RotationSpeed.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| REVOLUTIONS_PER_MINUTE |  | 0 |

#### hiber.value.Value.Numeric.Speed.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| KILOMETERS_PER_HOUR |  | 0 |
| KNOTS | This is a special case unit and may not be auto-converted to your UnitPreference. | 1 |
| METERS_PER_SECOND |  | 2 |
| MILES_PER_HOUR |  | 3 |

#### hiber.value.Value.Numeric.Temperature.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| KELVIN |  | 0 |
| DEGREES_CELSIUS |  | 1 |
| DEGREES_FAHRENHEIT |  | 2 |

#### hiber.value.Value.Numeric.Type
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

#### hiber.value.Value.Numeric.Voltage.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| MILLIVOLT |  | 0 |

#### hiber.value.Value.Numeric.Volume.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| LITER |  | 0 |
| GALLON_US |  | 1 |
| GALLON_IMPERIAL |  | 2 |
| CUBIC_METER |  | 3 |
| CUBIC_FEET |  | 4 |

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
| bytes | [ bytes](#bytes) |  |
| hex | [ string](#string) |  |

### hiber.BytesOrHex.Update



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
The textual field has the commonly used ISO 8601 local date format (i.e. "2018-01-01").
When used an API input, either specify the int fields or the textual field.
If both are specified, the textual field will be discarded.

| Field | Type | Description |
| ----- | ---- | ----------- |
| year | [ uint32](#uint32) |  |
| month | [ uint32](#uint32) |  |
| day | [ uint32](#uint32) |  |
| textual | [ string](#string) |  |

### hiber.DoubleRange

Decimal range.

| Field | Type | Description |
| ----- | ---- | ----------- |
| start | [ double](#double) |  |
| end | [ double](#double) |  |

### hiber.Duration



| Field | Type | Description |
| ----- | ---- | ----------- |
| duration | [ google.protobuf.Duration](#googleprotobufduration) |  |
| textual | [ string](#string) |  |

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

Update object to update a Filter.ChildOrganizations field.

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

Update object to update a Filter.Events field.

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

Update object to update a Filter.Modems field.

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

Update object to update a Filter.Tags field.

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
| textual | [ string](#string) | Text representation. Can be used as an alternative input in a request, filled in by the API in responses. |

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
| size | [ int32](#int32) |  |
| page | [ int32](#int32) |  |

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
| start | [ hiber.Timestamp](#hibertimestamp) |  |
| end | [ hiber.Timestamp](#hibertimestamp) |  |

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
| timestamp | [ google.protobuf.Timestamp](#googleprotobuftimestamp) |  |
| time_zone | [ string](#string) |  |
| textual | [ string](#string) |  |

### hiber.UpdateBoolean

Update object for a boolean.

Since false is the default value, we need to distinguish between an omitted value and setting the value to false,
in an update object.

To use this to update, set a value and set updated to true

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ bool](#bool) |  |

### hiber.UpdateClearableString

Update object for a string that can be empty.

Since an empty string is also the default value, we need to distinguish between an omitted value and
setting the value to an empty string, in an update object.

To use this to update, set a value and set updated to true

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ string](#string) |  |

### hiber.UpdateOptionalDuration

Update object for an optional Duration.

To use this to update, set a value and set updated to true.
To clear the duration, set updated to true, but set no value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.Duration](#hiberduration) |  |

### hiber.UpdateOptionalId

Update object for an optional id.

To use this to update, set a value and set updated to true. To clear the id, set updated to true, but set no value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ int64](#int64) |  |

### hiber.UpdateZeroableInt

Update object for an int that can be set to 0.

Since 0 is also the default value, we need to distinguish between an omitted value and setting the value to 0,
in an update object.

To use this to update, set a value and set updated to true

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
| DEVICE_CREATED | A new device was created in your organization, either manually or by a gateway. | 55 |
| DEVICE_UPDATED | A device in your organization was manually updated (i.e. renamed, tagged). | 36 |
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
| EXPORT_CREATED | A new export was started for your organization, exporting data (i.e. messages) to a file. | 65 |
| EXPORT_READY | An export in your organization has completed and the resulting file with data (i.e. messages as CSV) is ready to be downloaded. | 66 |
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
| SPEED_KILOMETERS_PER_HOUR |  | 18 |
| SPEED_KNOTS |  | 19 |
| SPEED_METERS_PER_SECOND |  | 20 |
| SPEED_MILES_PER_HOUR |  | 22 |
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
| FLOW_CUBIC_METERS_PER_HOUR |  | 39 |
| FLOW_BARRELS_PER_DAY |  | 46 |
| REVOLUTIONS_PER_MINUTE |  | 44 |
| ITEMS_PER_24_HOURS |  | 45 |

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

