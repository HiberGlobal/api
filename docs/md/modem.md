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
  - [Modem](#modem)
  - [Modem.ConnectedDeviceInfo](#modemconnecteddeviceinfo)
  - [Modem.ConnectedDeviceInfo.SettingsEntry](#modemconnecteddeviceinfosettingsentry)
  - [Modem.GatewayInfo](#modemgatewayinfo)
  - [Modem.Peripherals](#modemperipherals)
  - [Modem.Peripherals.PeripheralsEntry](#modemperipheralsperipheralsentry)
  - [Modem.TechnicalData](#modemtechnicaldata)
  - [Modem.ValveInfo](#modemvalveinfo)
  - [ModemLifecycleInfo](#modemlifecycleinfo)
  - [ModemLifecycleInfo.Request](#modemlifecycleinforequest)
  - [ModemLifecycleInfo.Response](#modemlifecycleinforesponse)
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
  - [TagCount](#tagcount)
  - [TagCount.Request](#tagcountrequest)
  - [TagCount.Response](#tagcountresponse)
  - [UpdateModemTagsRequest](#updatemodemtagsrequest)
  - [UpdateModemTagsRequest.Response](#updatemodemtagsrequestresponse)

- Enums
  - [ListModemsRequest.Sort](#listmodemsrequestsort)
  - [Modem.ConnectedDeviceInfo.Frequency](#modemconnecteddeviceinfofrequency)
  - [Modem.Lifecycle](#modemlifecycle)
  - [Modem.Type](#modemtype)
  - [ModemMessage.Source](#modemmessagesource)

- Referenced messages from [file.proto](#referenced-messages-from-fileproto)
  - [hiber.file.File](#hiberfilefile)
  - [hiber.file.FileSelection](#hiberfilefileselection)


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
  - [hiber.organization.Organization.Avatar](#hiberorganizationorganizationavatar)
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

- Referenced messages from [process_point.proto](#referenced-messages-from-process_pointproto)
  - [hiber.processpoint.ProcessPoint](#hiberprocesspointprocesspoint)
  - [hiber.processpoint.ProcessPoint.AssignedDevice](#hiberprocesspointprocesspointassigneddevice)
  - [hiber.processpoint.ProcessPointSelection](#hiberprocesspointprocesspointselection)

    - [hiber.processpoint.ProcessPoint.Type](#hiberprocesspointprocesspointtype)

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
    - [hiber.value.ValueTransformation](#hibervaluevaluetransformation)

- Referenced messages from [valve.proto](#referenced-messages-from-valveproto)
  - [hiber.valve.Valve](#hibervalvevalve)
  - [hiber.valve.Valve.ValveProcess](#hibervalvevalvevalveprocess)
  - [hiber.valve.ValveSelection](#hibervalvevalveselection)

    - [hiber.valve.Valve.HighPressureLineStatus](#hibervalvevalvehighpressurelinestatus)
    - [hiber.valve.Valve.Operation](#hibervalvevalveoperation)

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

### Lifecycles
> **rpc** Lifecycles([ModemLifecycleInfo.Request](#modemlifecycleinforequest))
    [ModemLifecycleInfo.Response](#modemlifecycleinforesponse)

List possible lifecycles with additional information.

### Messages
> **rpc** Messages([ListModemMessagesRequest](#listmodemmessagesrequest))
    [ListModemMessagesRequest.Response](#listmodemmessagesrequestresponse)

<p class="deprecated deprecated-method">Deprecated</p> List messages for the selected modems.

### UpdateTags
> **rpc** UpdateTags([UpdateModemTagsRequest](#updatemodemtagsrequest))
    [UpdateModemTagsRequest.Response](#updatemodemtagsrequestresponse)

Add, remove and create new tags for the selected modems.

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
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| amount | [ uint32](#uint32) | The amount of modems to create. |
| names | [repeated string](#string) | The name(s) to give the new modem(s). Must not contain more values than the amount of modems to create. |
| external_device_identifiers | [repeated string](#string) | The external device identifiers for the new modems. Must not contain more values than the amount of modems to create. The order of this list matches the order of the name, values in the same index are applied to the same modem. |
|  **optional** device_type | [optional string](#string) | Device type for the modem(s) we will create. |
|  **optional** lifecycle | [optional Modem.Lifecycle](#modemlifecycle) | The status for the new modems. |
|  **optional** technical | [optional Modem.TechnicalData](#modemtechnicaldata) | The technical data, such as manufacturer and hardware information for the new modems. |
| peripherals | [map CreateModem.Request.PeripheralsEntry](#createmodemrequestperipheralsentry) | The peripherals for the new modems. |
|  **optional** notes | [optional string](#string) | Notes for all new modems. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **initial_location**.location | [ hiber.Location](#hiberlocation) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **initial_location**.random_location_in_area | [ hiber.Area](#hiberarea) |  |
|  **optional** tags | [optional hiber.tag.UpdateTagsForItem](#hibertagupdatetagsforitem) | The tags to set to the new modems, either existing or created by this call. |
|  **optional** include_modems_in_response | [optional bool](#bool) | Whether to return the full Modem in addition to the modem number and verification code. |
|  **optional** include_verification_code | [optional bool](#bool) | Whether to return the verification code for the modem. |

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
|  **optional** child_organizations | [optional hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | <span class="deprecated deprecated-field">Deprecated</span> Look for the modem in child organizations. DEPRECATED: use the in_organizations flag instead. |

### ListModemMessagesRequest

<p class="deprecated deprecated-message">Deprecated</p> 

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
|  **optional** allow_any_group_parent | [optional bool](#bool) | Set to true to allow group request to return modems that can never be the parent of a group. - If this flag is false, the modems for the groups are automatically filtered on being a parent of a group. Note that the group may still be empty, i.e. when a gateway has no connected devices. - If this flag is true, the group parents can include modems which cannot be a parent and for which the group can only be empty. |

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
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional ModemSelection](#modemselection) | Select which modems to return. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) | Paginate through results. |
| sort_by | [repeated ListModemsRequest.Sort](#listmodemsrequestsort) | Sort the modem with the given sort options. |
|  **optional** child_organizations | [optional hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | Include modems from the selected child organizations. |
|  **optional** location_selection | [optional hiber.LocationSelection](#hiberlocationselection) | Filter modems by location. |
|  **optional** include_missing_group_parents | [optional bool](#bool) | Set this to true to populate the group_parents field in the response. This will be populated with missing group parents (i.e. gateways) for the the modems on this page. Any group parent that is on the current page is not included in this list to avoid duplicate data. |

### ListModemsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [repeated Modem](#modem) |  |
| request | [ ListModemsRequest](#listmodemsrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |
| sorted_by | [repeated ListModemsRequest.Sort](#listmodemsrequestsort) |  |
| group_parents | [repeated Modem](#modem) | This will be populated with missing group parents (i.e. gateways) for the the modems on this page. Any group parent that is on the current page is not included in this list to avoid duplicate data. Only set when include_missing_group_parents is true in the request. |

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
| is_gateway | [ bool](#bool) | <span class="deprecated deprecated-field">Deprecated</span> Whether the modem is a gateway, it has been configured as a gateway and has connected devices. Use `type` instead. |
| is_device_connected_to_gateway | [ bool](#bool) | <span class="deprecated deprecated-field">Deprecated</span> Whether the modem is connected to a modem configured as a gateway. Use `type` instead. |
| connected_to_gateway | [ string](#string) | <span class="deprecated deprecated-field">Deprecated</span> The modem number that this modem is connected to, if any. Use `connected_device_info.connected_to_gateway` instead. |
| external_device_ids | [repeated string](#string) | External device ids for this sensor, gateway or valve. |
| device_type | [ string](#string) | Device type for this modem. |
| type | [ Modem.Type](#modemtype) | The type of modem. Used mainly to differentiate in the UI or to sort on. |
|  **optional** gateway_info | [optional Modem.GatewayInfo](#modemgatewayinfo) | Additional information when this modem is a gateway. |
|  **optional** connected_device_info | [optional Modem.ConnectedDeviceInfo](#modemconnecteddeviceinfo) | Additional information when this modem is a connected device. |
|  **optional** valve_info | [optional Modem.ValveInfo](#modemvalveinfo) | Additional information when this modem is a connected device. |
| metadata | [ google.protobuf.Struct](#googleprotobufstruct) | Modem metadata, typically extracted from messages. |
| time_zone | [ string](#string) | The timezone configured for the modem. |
| transmission_interval | [ hiber.Duration](#hiberduration) | The transmission interval for this modem, if configured. |
|  **optional** expected_transmission_rate | [optional hiber.value.Value.Numeric.Rate](#hibervaluevaluenumericrate) | The expected transmission rate for this modem. |
| numeric_value_types | [repeated hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype) | The numeric value types that this device produces. The device may produce other values (like battery level), but these are the primary value types. |
| files | [repeated hiber.file.File](#hiberfilefile) | Files for this tag. Typically an image of the device installation. See the File.media_type for more information. |
|  **optional** required_device_firmware_identifier | [optional string](#string) |  |
| process_points | [repeated hiber.processpoint.ProcessPoint](#hiberprocesspointprocesspoint) | List of process points that this device is connected to (if you have permission to access them). Some fields might be omitted in this inline view for compactness (like connected devices). |

### Modem.ConnectedDeviceInfo

Additional information when this modem is a connected device.

| Field | Type | Description |
| ----- | ---- | ----------- |
| connected_to_gateway | [ string](#string) | The gateways that this modem is connected to. This field reflects the gateway that processed the last message for this modem. If the modem is connected to multiple gateways, the last used gateway is tracked here. |
| external_device_ids | [repeated string](#string) | <span class="deprecated deprecated-field">Deprecated</span> External device ids for this modem. |
| device_type | [ string](#string) | <span class="deprecated deprecated-field">Deprecated</span> Device type for this modem. |
| sensor_brand | [ string](#string) | Brand for this modem's sensor. |
|  **optional** frequency | [optional Modem.ConnectedDeviceInfo.Frequency](#modemconnecteddeviceinfofrequency) | Frequency configured for this device. |
|  **optional** last_battery_replacement | [optional hiber.Timestamp](#hibertimestamp) | The last time the battery was replaced for this device. |
| settings | [map Modem.ConnectedDeviceInfo.SettingsEntry](#modemconnecteddeviceinfosettingsentry) | Map of numeric value to bytes that can be applied to the device. |

### Modem.ConnectedDeviceInfo.SettingsEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ hiber.BytesOrHex](#hiberbytesorhex) |  |

### Modem.GatewayInfo

Additional information when this modem is a gateway.

| Field | Type | Description |
| ----- | ---- | ----------- |
| number_of_connected_devices | [ int32](#int32) |  |
| device_type | [ string](#string) | <span class="deprecated deprecated-field">Deprecated</span> Device type for this gateway. |
| gateway_brand | [ string](#string) | Brand for this gateway. |
| external_device_ids | [repeated string](#string) | <span class="deprecated deprecated-field">Deprecated</span> External device ids for this gateway. |

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

### Modem.ValveInfo



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** open | [optional bool](#bool) |  |
|  **optional** high_pressure_line_status | [optional hiber.valve.Valve.HighPressureLineStatus](#hibervalvevalvehighpressurelinestatus) |  |

### ModemLifecycleInfo



| Field | Type | Description |
| ----- | ---- | ----------- |
| lifecycle | [ Modem.Lifecycle](#modemlifecycle) | The lifecycle with info. |
|  **optional** visibility_limited | [optional bool](#bool) | Whether this lifecycle is visible to everyone, or limited to specific permissions. For example, decommissioned devices are no longer visible to customers, but are visible to support staff. |
|  **optional** highlighted | [optional bool](#bool) | Whether this lifecycle should be highlighted to the users. Typically means that some interaction is required. |

### ModemLifecycleInfo.Request




### ModemLifecycleInfo.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| lifecycles | [repeated ModemLifecycleInfo](#modemlifecycleinfo) |  |

### ModemMessage

<p class="deprecated deprecated-message">Deprecated</p> Decrypted modem message. Messages are received encrypted and decrypted asynchronously, which adds the location
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
| sources | [repeated ModemMessage.Source](#modemmessagesource) | Message source(s) for this message (e.g. it was received through the satellite or directly to the server). |
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
| parser_id | [ int32](#int32) | <span class="deprecated deprecated-field">Deprecated</span> Id of the parser that was used, if the parser and modem are owned by the same organization. Deprecated in favour of the identifier, which is globally unique. |
| parser_identifier | [ string](#string) | Globally unique identifier of the parser that was used. |
| parser_name | [ string](#string) | Name of the parser that was used. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **parsed**.error | [ string](#string) | Error while parsing the message body. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **parsed**.result | [ google.protobuf.Struct](#googleprotobufstruct) | Result of parsing the body with this parser. |

### ModemMessageSelection

<p class="deprecated deprecated-message">Deprecated</p> Selection object for modem messages.
Filter messages by modem id, (child)organization, and time sent (note that this is not the time the message was received)

| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [ hiber.Filter.Modems](#hiberfiltermodems) | <span class="deprecated deprecated-field">Deprecated</span> Define the modems to return messages for, e.g. include = [AAAA AAAA, BBBB BBBB]. Deprecated in favor of using the ModemSelection. |
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
|  **optional** modems | [optional hiber.Filter.Modems](#hiberfiltermodems) |  |
|  **optional** free_text_search | [optional string](#string) |  |
|  **optional** only_active | [optional bool](#bool) | <span class="deprecated deprecated-field">Deprecated</span> Use lifecycle filter instead. |
|  **optional** activated_in | [optional hiber.TimeRange](#hibertimerange) | <span class="deprecated deprecated-field">Deprecated</span>  |
|  **optional** with_last_message_in | [optional hiber.TimeRange](#hibertimerange) |  |
| health_levels | [repeated string](#string) | Filter modems by health level. |
| lifecycles | [repeated Modem.Lifecycle](#modemlifecycle) | Filter modems by lifecycle(s). Defaults to nominal lifecycles, excluding disabled or decommissioned modems. |
|  **optional** transfers | [optional ModemSelection.Transfers](#modemselectiontransfers) |  |
| include_types | [repeated Modem.Type](#modemtype) | Only include modems that have a type listed in types. In other words, when providing multiple types, this is an "OR" relationship. |
| exclude_types | [repeated Modem.Type](#modemtype) | Exclude modems that have a type listed in types. |
|  **optional** device_types | [optional hiber.Filter.DeviceTypes](#hiberfilterdevicetypes) |  |
|  **optional** sensorBrands | [optional hiber.Filter.SensorBrands](#hiberfiltersensorbrands) |  |
|  **optional** identifiers | [optional hiber.Filter.ModemIdentifiers](#hiberfiltermodemidentifiers) |  |
|  **optional** only_gateways | [optional bool](#bool) | <span class="deprecated deprecated-field">Deprecated</span> Only list devices that are a gateway. Replaced by `types`. If you only want to have gateways in the result, create a selection with only `Modem.Type.GATEWAY` for `types`. |
|  **optional** only_has_external_device_ids | [optional bool](#bool) | <span class="deprecated deprecated-field">Deprecated</span> Only list devices that are a connected devices. Typically these are LoRaWAN sensors. Replaced by `types`. If you only want to have connected devices in the result, create a selection with only `Modem.Type.CONNECTED_DEVICE` for `types`. |
|  **optional** connected_to_gateways | [optional hiber.Filter.Modems](#hiberfiltermodems) |  |
| external_device_ids | [repeated string](#string) | <span class="deprecated deprecated-field">Deprecated</span>  |
|  **optional** filter_by_tags | [optional hiber.tag.TagSelection](#hibertagtagselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **peripheral_selection**.peripherals | [ ModemSelection.Peripherals](#modemselectionperipherals) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **peripheral_selection**.only_without_peripheral | [ bool](#bool) | When set to true, only modems that do not have any peripheral will be included in the result. |
|  **optional** only_connected_to_gateway | [optional bool](#bool) | Only select modems that are connected to a gateway (connected devices). |
|  **optional** not_connected_to_gateway | [optional bool](#bool) | Only select modems that are not connected to a gateway (i.e. gateways). |

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

### TagCount



| Field | Type | Description |
| ----- | ---- | ----------- |
| tag | [ hiber.tag.Tag](#hibertagtag) |  |
| modems | [ uint32](#uint32) |  |

### TagCount.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional ModemSelection](#modemselection) | Select the modems to count. Optional, when omitted or empty everything is included. |
|  **optional** tag_selection | [optional hiber.tag.TagSelection](#hibertagtagselection) | Select the tags to list. Optional, when omitted or empty everything is included. |

### TagCount.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| tags | [repeated TagCount](#tagcount) |  |
| request | [ TagCount.Request](#tagcountrequest) |  |

### UpdateModemTagsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| update | [ hiber.tag.UpdateTagsForItem](#hibertagupdatetagsforitem) |  |
| selection | [ ModemSelection](#modemselection) |  |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |

### UpdateModemTagsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [repeated Modem](#modem) |  |
| request | [ UpdateModemTagsRequest](#updatemodemtagsrequest) |  |
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
| PROCESS_POINT_ASC | Sort alphabetically on the name of the process point(s) assigned to the modem, in ascending order. | 26 |
| PROCESS_POINT_DESC | Sort alphabetically on the name of the process point(s) assigned to the modem, in descending order. | 27 |
| HEALTH | Health sorted from least to most severe (e.g. OK, WARNING, ERROR). | 10 |
| HEALTH_DESC | Health sorted from most to least severe (e.g. ERROR, WARNING, OK). | 11 |
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

### Modem.ConnectedDeviceInfo.Frequency
Frequency specified by LoRaWAN regional parameters.

| Name | Description | Number |
| ---- | ----------- | ------ |
| AS923 | AS923 | 0 |
| AS923_2 | AS923-2 | 10 |
| AU915 | AU915 | 1 |
| EU868 | EU868 | 5 |
| IN865 | IN865 | 6 |
| KR920 | KR920 | 7 |
| US915 | US915 | 8 |
| US915_HYBRID | US915-Hybrid | 9 |

### Modem.Lifecycle


| Name | Description | Number |
| ---- | ----------- | ------ |
| ACCEPTANCE_TESTING | Device is being tested by Hiber. Devices in this state are not visible to customers. | 0 |
| READY_TO_INSTALL | Device has passed Acceptance Testing and is ready be installed. When it sends it first message, it will automatically go to INSTALLED. | 8 |
| INSTALLED | Device is active and sending messages. | 1 |
| PAUSED | Device is paused and not sending messages. This should be of a temporary nature (e.g. a change to the installation is being made). On its next message, it will automatically go back to INSTALLED. Offline alarm checks will not be triggered for devices in this lifecycle. | 6 |
| DISABLED | Device is disabled and not sending messages. This is a more permanent version of PAUSED. Devices in this state are not visible to customers. | 5 |
| DECOMMISSIONED | Device is (going to be) removed from installation and will not return to installed status again. Devices in this state are not visible to customers. | 4 |
| DEFECTIVE | Device is defective and should not be used anymore. Devices in this state are typically RMA-ed and (should be) transferred to the RMA organization. Devices in this state are not visible to customers. | 7 |
| PENDING_MAINTENANCE | Device is defective in some way and needs maintenance to operate optimally. Devices in this state should be highlighted as they need to be acted upon. | 11 |
| PENDING_REPLACEMENT | Device is defective and needs to be replaced. Devices in this state should be highlighted as they need to be acted upon. | 12 |
| SPARE | Spare device sent to customer in case it is needed. | 9 |

### Modem.Type
The effective type of this modem.
Type can depend on the hardware itself as well as network topology.

| Name | Description | Number |
| ---- | ----------- | ------ |
| OTHER | A device of which the specific type is not known | 0 |
| GATEWAY | A device that can receive messages from sensors in the field and relay them (directly) to the satellite. Typically a LoRaWAN hub. Note that gateways also send messages themselves (e.g. a daily heartbeat). | 2 |
| SENSOR | A sensor that can (only) send data to a gateway. Typically using a LoRaWAN connection. | 3 |
| VALVE |  | 4 |

### ModemMessage.Source


| Name | Description | Number |
| ---- | ----------- | ------ |
| HIBERBAND | A real message from a modem or gateway, sent over Hiberband to the server. | 0 |
| DIRECT_TO_API | A real message from a modem or gateway, sent directly to the API using a persistent connection. | 1 |
| TEST | A test message sent to the testing API. | 2 |
| SIMULATION | A simulated message, generated by the server. | 3 |



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
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **content**.data | [ hiber.BytesOrHex](#hiberbytesorhex) | The binary payload that represents the file, in our standard binary wrapper. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **content**.data_formatted_hex | [ string](#string) | The binary payload that represents the file, formatted as a hexadecimal string. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **content**.data_formatted_base64 | [ string](#string) | The binary payload that represents the file, formatted as a base64 string. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **content**.data_uri | [ string](#string) | The binary payload that represents the file, formatted as a data uri string (e.g. data:image/png;base64,). |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **content**.data_raw | [ bytes](#bytes) | The binary payload that represents the file, raw bytes only. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **content**.file_service | [ bool](#bool) | This file's content can be fetched using the FileService, with this file identifier. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **content**.url | [ string](#string) | This file's content can be fetched at this url. |
| media_type | [ string](#string) | The media-type of the file, as defined by RFC 6838 or its extensions |
| name | [ string](#string) | A semantic name for this file. |
| link | [ string](#string) | A link to file in the Hiber Rest API. Note: the Hiber Rest API requires a token, for authenticated access to your files. If the content oneof of this file is a url, this link will return a HTTP 301 code to redirect to that url. |
| time | [ hiber.Timestamp](#hibertimestamp) | The time for this file, typically when it was created. |

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
| color | [ string](#string) | <span class="deprecated deprecated-field">Deprecated</span> Default color for the health level, as a string that represents a valid CSS3 color. DEPRECATED: Maps to the color named "text" in color_data. |
| color_data | [map hiber.health.HealthLevel.ColorDataEntry](#hiberhealthhealthlevelcolordataentry) | Map of named colors, where key is the name and the value is a valid CSS3 color definition. |
| severity | [ int64](#int64) | A unique numeric value equal to the index of this health level in the list of health levels sorted by ascending severity (starting at 1). This means higher numbers denote a more severe health. This value cannot be used when creating or updating. To change the severity for a health level, reorder all health levels. |
| catch_all | [ bool](#bool) | Precisely one health level can be assigned as a catch-all for any unknown health levels from alarms (or Hiber systems), which can happen when a device manufacturer has provided alarms for your device (e.g. a low battery alarm). By default, unknown health levels map to the level of the highest severity, unless another level is marked as catch-all. |

### hiber.health.HealthLevelSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** search | [optional string](#string) | Search for the given string in the levels and colors. |
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
|  **optional** display_name | [optional string](#string) | The name to display for your organization (i.e. capitalized, with spaces, etc.). Default to the name above. |
|  **optional** avatar | [optional hiber.organization.Organization.Avatar](#hiberorganizationorganizationavatar) | The avatar image representing this organization. Usually the logo. |
|  **optional** is_business | [optional bool](#bool) | Whether this organization is created for a business. |
|  **optional** vat_number | [optional string](#string) | Whether this organization is created for a business, provide a VAT number. |
|  **optional** address | [optional hiber.organization.Organization.Address](#hiberorganizationorganizationaddress) | Postal address for your organization. |
|  **optional** billing_name | [optional string](#string) | Billing information for your organization. Optional, but required if you want active modems. |
|  **optional** billing_address | [optional hiber.organization.Organization.Address](#hiberorganizationorganizationaddress) | Billing address for your organization. Optional, but required if you want active modems. |
| contact | [ hiber.organization.Organization.Contact](#hiberorganizationorganizationcontact) | Contact information for your organization. Required. |
|  **optional** organization_creation_token | [optional string](#string) | A token that allows you to create an organization without having an organization. |

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
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |

### hiber.organization.GetOrganizationAvatar.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| avatars | [map hiber.organization.GetOrganizationAvatar.Response.AvatarsEntry](#hiberorganizationgetorganizationavatarresponseavatarsentry) | Avatars, indexed by organization slug |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### hiber.organization.GetOrganizationAvatar.Response.AvatarsEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ hiber.organization.Organization.Avatar](#hiberorganizationorganizationavatar) |  |

### hiber.organization.GetOrganizationRequest

Get your current organization's data

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to get the details for. If unset, your default organization is used. |

### hiber.organization.ListChildOrganizationsRequest

List the child organizations for the given organization

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional hiber.organization.OrganizationSelection](#hiberorganizationorganizationselection) | Select the organizations to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |
|  **optional** include_details | [optional bool](#bool) |  |

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
|  **optional** defaults | [optional hiber.organization.Organization.Defaults](#hiberorganizationorganizationdefaults) |  |

### hiber.organization.Organization.Address



| Field | Type | Description |
| ----- | ---- | ----------- |
| lines | [repeated string](#string) |  |
| zip_code | [ string](#string) |  |
| city | [ string](#string) |  |
| state | [ string](#string) |  |
| country | [ string](#string) |  |

### hiber.organization.Organization.Avatar

An avatar is represented either by a (publicly) fetchable URL that serves an image,
xor a binary payload that knows its name and mime-type.

If it is a url, it must be obtainable without credentials, though this is not validated by the API.
Because the content behind URL's can change or become unavailable over time,
the client should make sure it properly caches the data fetched from the URL.
("Properly" means [among other things] respecting the response headers for this resource)

| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **url_or_image**.url | [ string](#string) | A URL that contains the location of avatar. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **url_or_image**.image | [ hiber.file.File](#hiberfilefile) | The data of the avatar as a Named File. |

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
|  **optional** expected_device_transmission_rate | [optional hiber.value.Value.Numeric.Rate](#hibervaluevaluenumericrate) | The default expected transmission interval for devices in this organization. |

### hiber.organization.OrganizationSelection

Selection object for child organizations.
User for child organization list and tree.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organizations | [optional hiber.Filter.Organizations](#hiberfilterorganizations) |  |
|  **optional** search | [optional string](#string) |  |

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
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate) for this call, overriding your default organization |
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
|  **optional** organization | [optional string](#string) |  |
| display_name | [ string](#string) |  |
| vat_number | [ string](#string) |  |
| address | [ hiber.organization.Organization.Address](#hiberorganizationorganizationaddress) |  |
| billing_name | [ string](#string) |  |
| billing_address | [ hiber.organization.Organization.Address](#hiberorganizationorganizationaddress) |  |
| contact | [ hiber.organization.Organization.Contact](#hiberorganizationorganizationcontact) |  |
| avatar | [ hiber.organization.Organization.Avatar](#hiberorganizationorganizationavatar) |  |

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
| MODEM_CREATION | Required to manually create modems using the ModemService. | 4 |
| EARLY_ACCESS | Used for organizations that get early access to features. | 5 |
| EXPERIMENTAL | Used for organizations that get access to experimental features. e.g. feature work in progress. | 6 |
| ASSETS | Access the list of assets in Mission Control. | 10 |
| PROCESS_POINTS | Access the list of process points in Mission Control. | 13 |
| ASSET_DASHBOARD | Use the new assets as primary data owner in Mission Control dashboards. | 11 |
| PROCESS_POINT_DASHBOARD | Use the new process points as primary data owner in Mission Control dashboards. | 14 |
| LOCATIONS | Display and use device and gateway locations in Mission Control. | 12 |



## Referenced messages from process_point.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [process_point.proto](https://github.com/HiberGlobal/api/blob/master/process_point.proto).


### hiber.processpoint.ProcessPoint

Process Points are things that collect the data produced by devices.
Devices are assigned to process points to handle data ownership.
When a device is replaced, the data flow for the process point continues with the data from the new device.
Multiple devices can be assigned to an process point, though it is advisable to only do so when they send
different type of data (e.g. one sensor for pressure and one for flow).

For example, if you have a Well, you might have process points for Annulus A and the tubing head.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) |  |
| name | [ string](#string) | Name of the process point |
|  **optional** type | [optional hiber.processpoint.ProcessPoint.Type](#hiberprocesspointprocesspointtype) | Type of the process point, if any of the predefined types applies. |
|  **optional** description | [optional string](#string) | Longer detailed description of the process point. |
|  **optional** notes | [optional string](#string) | Multiline notes field that can be used to add additional information to an process point. |
|  **optional** time_zone | [optional string](#string) | Optional time zone for the process point. This can, for example, be used to calculate SLAs on a daily basis, adjusted by time zone. |
|  **optional** expected_transmission_rate | [optional hiber.value.Value.Numeric.Rate](#hibervaluevaluenumericrate) | The expected transmission rate for this process point. |
| metadata | [ google.protobuf.Struct](#googleprotobufstruct) | Metadata for the process point. This can be automatically populated from linked devices or manually added. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | Tags assigned to this process point |
| devices | [repeated hiber.processpoint.ProcessPoint.AssignedDevice](#hiberprocesspointprocesspointassigneddevice) | Devices assigned to this process point |
| inactive_devices | [repeated hiber.processpoint.ProcessPoint.AssignedDevice](#hiberprocesspointprocesspointassigneddevice) | Devices that were assigned to this process point in the past |
| organization | [ string](#string) | The organization that owns this process point. Typically only relevant if child organizations are included. |
| location | [ hiber.Location](#hiberlocation) | Location for the process point. |
| files | [repeated hiber.file.File](#hiberfilefile) | Files for this process point. Typically an image of a place. See the File.media_type for more information. |

### hiber.processpoint.ProcessPoint.AssignedDevice

A device assigned to this process point.
Non-operational values that the device produces will be linked to this process point
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

### hiber.processpoint.ProcessPointSelection

Selection object for process points.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifiers | [repeated string](#string) | Select process points by identifier. |
| search | [repeated string](#string) | Search process points by (partial, case insensitive) identifier, name, description, notes and time zone. |
| types | [repeated hiber.processpoint.ProcessPoint.Type](#hiberprocesspointprocesspointtype) | Select process points by type. |
|  **optional** filter_by_tags | [optional hiber.tag.TagSelection](#hibertagtagselection) | Select process points by tags |


### Enums
#### hiber.processpoint.ProcessPoint.Type
Predefined process points types that can be used to say something about the data.
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



## Referenced messages from tag.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [tag.proto](https://github.com/HiberGlobal/api/blob/master/tag.proto).


### hiber.tag.Tag

Tag in your organization.
Tags can be assigned to devices and process points to group them together or mark a certain property.

A Tag has three parts: its id in your organization, a Label that describes how it should be displayed, and
Metadata (which is only included when using the TagService) with additional information.

| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) |  |
| label | [ hiber.tag.Tag.Label](#hibertagtaglabel) | The label to display for this tag. |
|  **optional** metadata | [optional hiber.tag.Tag.Metadata](#hibertagtagmetadata) | Metadata for this tag. This is typically not included in calls where the tag is repeated a lot, like the device list. Use the TagService.List call to get the tags with Metadata. |
|  **optional** priority | [optional int32](#int32) | Control tag sorting by setting a priority (sorted from high to low, where no priority is treated as 0). |

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
|  **optional** associated_with | [optional hiber.Filter.Tags](#hiberfiltertags) | Return all tags that are used in combination with the given tags (e.g. assigned to the same device). |


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
| formatted | [ string](#string) | Textual representation, excluding unit symbol, rounded based on the user preferences and field config. |
| textual | [ string](#string) | Textual representation, including unit symbol, rounded based on the user preferences and field config. |
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
| OIL_BARREL | bbl | 5 |

#### hiber.value.Value.Type
The type of value that is represented.

| Name | Description | Number |
| ---- | ----------- | ------ |
| OTHER |  | 0 |
| NUMERIC | This field contains numeric values, with an optional unit of measurement defined below. | 1 |
| TEXT | This field contains text to be displayed. | 2 |
| ENUM | This field switches between several predefined values. Typically used for status fields. | 3 |

#### hiber.value.ValueTransformation
Transform the values into a derived value.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DURATION | Instead of returning the value, return the amount of time a value was active. Aggregation (if applicable) is applied afterwards on the duration value. | 0 |
| DELTA | Instead of returning the value, return the difference between the value and the previous value. Aggregation (if applicable) is applied before the delta is calculated. | 1 |



## Referenced messages from valve.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [valve.proto](https://github.com/HiberGlobal/api/blob/master/valve.proto).


### hiber.valve.Valve



| Field | Type | Description |
| ----- | ---- | ----------- |
| number | [ string](#string) | An 8-character hexadecimal string |
| organization | [ string](#string) |  |
| external_device_id | [ string](#string) |  |
| name | [ string](#string) |  |
| device_type | [ string](#string) |  |
| open | [ bool](#bool) | Valve actuator status: open or closed. |
|  **optional** leak | [optional bool](#bool) |  |
|  **optional** fraud | [optional bool](#bool) |  |
|  **optional** remaining_battery_voltage | [optional int64](#int64) |  |
|  **optional** last_process | [optional hiber.valve.Valve.ValveProcess](#hibervalvevalvevalveprocess) |  |
| high_pressure_line_status | [ hiber.valve.Valve.HighPressureLineStatus](#hibervalvevalvehighpressurelinestatus) |  |

### hiber.valve.Valve.ValveProcess



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem_number | [ string](#string) | Modem valve actuator number. |
| operation | [ hiber.valve.Valve.Operation](#hibervalvevalveoperation) | Operation from technician. |
| operation_at | [ hiber.Timestamp](#hibertimestamp) | Time that the operation was executed. |
| high_pressure_line_status | [ hiber.valve.Valve.HighPressureLineStatus](#hibervalvevalvehighpressurelinestatus) | High pressure line status after the operation. |

### hiber.valve.ValveSelection

Selection object for valve.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** numbers | [optional hiber.Filter.Modems](#hiberfiltermodems) | Select by valve numbers. |
|  **optional** identifiers | [optional hiber.Filter.ModemIdentifiers](#hiberfiltermodemidentifiers) | Select by external device identifiers. |
|  **optional** search | [optional string](#string) |  |
| high_pressure_line_status | [repeated hiber.valve.Valve.HighPressureLineStatus](#hibervalvevalvehighpressurelinestatus) | Select by high pressure line status. |
|  **optional** only_opened_valve | [optional bool](#bool) | Select opened valves. |
|  **optional** only_closed_valve | [optional bool](#bool) | Select closed valves. |


### Enums
#### hiber.valve.Valve.HighPressureLineStatus


| Name | Description | Number |
| ---- | ----------- | ------ |
| NOT_PRESSURIZED | High pressure line = 0 bar. | 0 |
| PRESSURIZED | High pressure line pressurized. | 1 |
| READY_TO_BE_PRESSURIZED | High pressure line ready to be pressurized. High pressure line requires manual operation to change status to PRESSURIZED. | 2 |

#### hiber.valve.Valve.Operation


| Name | Description | Number |
| ---- | ----------- | ------ |
| NO_OPERATION | If no choice is made, fall back to no-operation | 0 |
| BLEED_HIGH_PRESSURE_LINE | Open valve to bleed high pressure line. Send a downlink command to LoRaWAN LNS to open the valve actuator. High pressure line status should be changed: PRESSURIZED -> ZERO | 1 |
| CONFIRM_HIGH_PRESSURE_LINE_IS_ZERO | Confirm high pressure line pressure is 0 bar. High pressure line status can only be updated after operator's confirmation: High pressure line status is confirmed: ZERO | 2 |
| RESET_VALVE | Reset valve. Send a downlink command to LoRaWAN LNS to close the valve actuator. High pressure line status should be changed: ZERO -> READY_TO_BE_PRESSURIZED | 3 |
| CONFIRM_VALVE_IS_RESET | Confirm valve is reset. High pressure line status can only be updated after operator's confirmation: High pressure line status is confirmed: READY_TO_BE_PRESSURIZED | 4 |
| CONFIRM_HIGH_PRESSURE_LINE_UNDER_PRESSURE | Confirm high pressure line under pressure. The operator is required to manually operate the high pressure line to make it PRESSURIZED High pressure line status can only be updated after operator confirmation: High pressure line status is confirmed: PRESSURIZED | 5 |



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
| PROCESS_POINT_CREATED | A new process point was created in your organization. | 73 |
| ASSET_UPDATED | An asset in your organization was updated (e.g. renamed, tagged). | 71 |
| PROCESS_POINT_UPDATED | An process point in your organization was updated (e.g. renamed, tagged). | 74 |
| ASSET_DELETED | An asset in your organization was deleted. | 72 |
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

