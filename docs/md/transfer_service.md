# transfer_service.proto

Service to transfer data from one organization to another.

To transfer data to another organization, you must have access to both organizations,
and must have the TRANSFERS permissions in the sender organization.

#### This file was generated from [transfer_service.proto](https://github.com/HiberGlobal/api/blob/master/transfer_service.proto).

## Table of Contents

- Services
  - [TransferService](#transferservice)

- Messages
  - [PerformTransfer](#performtransfer)
  - [PerformTransfer.Request](#performtransferrequest)
  - [PerformTransfer.Response](#performtransferresponse)
  - [TransferHistory](#transferhistory)
  - [TransferHistory.Request](#transferhistoryrequest)
  - [TransferHistory.Request.TransferSelection](#transferhistoryrequesttransferselection)
  - [TransferHistory.Response](#transferhistoryresponse)

- Enums

- Referenced messages from [device.proto](#referenced-messages-from-deviceproto)
  - [hiber.device.Device](#hiberdevicedevice)
  - [hiber.device.Device.Links](#hiberdevicedevicelinks)
  - [hiber.device.Device.PeripheralsEntry](#hiberdevicedeviceperipheralsentry)
  - [hiber.device.DeviceSelection](#hiberdevicedeviceselection)
  - [hiber.device.ModemFilter](#hiberdevicemodemfilter)
  - [hiber.device.ModemFilter.Lifecycles](#hiberdevicemodemfilterlifecycles)
  - Enums
    - [hiber.device.Sort](#hiberdevicesort)

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

- Referenced messages from [transfer.proto](#referenced-messages-from-transferproto)
  - [hiber.transfer.Transfer](#hibertransfertransfer)
  - [hiber.transfer.Transfer.Devices](#hibertransfertransferdevices)

    - [hiber.transfer.Transfer.Type](#hibertransfertransfertype)

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


## TransferService


### Transfer
> **rpc** Transfer([PerformTransfer.Request](#performtransferrequest))
    [PerformTransfer.Response](#performtransferresponse)



### History
> **rpc** History([TransferHistory.Request](#transferhistoryrequest))
    [TransferHistory.Response](#transferhistoryresponse)




## Messages

### PerformTransfer




### PerformTransfer.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **recipient_organization_or_create**.recipient_organization | [ string](#string) | Existing organization to receive the transfer. You must have access to the recipient organization to transfer data to it. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **recipient_organization_or_create**.new_organization | [ hiber.organization.CreateOrganizationRequest](#hiberorganizationcreateorganizationrequest) | Create a new organization to receive the transfer. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **_comment**.comment | [optional string](#string) | Optional comment for the transfer (i.e. reason, tracking information, etc). |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.devices | [ hiber.device.DeviceSelection](#hiberdevicedeviceselection) | Transfer a number of selected devices to the recipient organization. |

### PerformTransfer.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| transfer | [ Transfer](#transfer) | none |
| request | [ PerformTransfer.Request](#performtransferrequest) | none |

### TransferHistory




### TransferHistory.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ TransferHistory.Request.TransferSelection](#transferhistoryrequesttransferselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |

### TransferHistory.Request.TransferSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| search | [ string](#string) | Search transfers by identifier, organizations, device, etc. |
| identifiers | [repeated string](#string) | Select transfers by transfer identifier. |
| time_range | [ hiber.TimeRange](#hibertimerange) | Select transfers that were performed within this time. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **selection**.devices | [ hiber.device.DeviceSelection](#hiberdevicedeviceselection) | Select device transfers with specific devices. |
| received_only | [ bool](#bool) | Only show transfer that your organization received. |
| sent_only | [ bool](#bool) | Only show transfer that your organization sent. |

### TransferHistory.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| transfer_history | [repeated Transfer](#transfer) | none |
| request | [ TransferHistory.Request](#transferhistoryrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |


## Enums


## Referenced messages from device.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [device.proto](https://github.com/HiberGlobal/api/blob/master/device.proto).


### hiber.device.Device

Information about a device.
A device is anything in the Hiber network that can send data to our systems.
They have a unique device number in our system, used to identify them.

| Field | Type | Description |
| ----- | ---- | ----------- |
| number | [ string](#string) | An 8-character hexadecimal string, formatted for human readability. System ignores spaces. |
| organization | [ string](#string) | The organization that owns this device |
| name | [ string](#string) | A descriptor given to the device, defaults to it's number. |
| location | [ hiber.Location](#hiberlocation) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **_inactivity**.inactivity | [optional hiber.Duration](#hiberduration) | The amount of time since the last message from this modem was received on the server. |
| health | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | Health based on the modem alarm and some always-present alarms. |
| lifecycle | [ hiber.modem.Modem.Lifecycle](#hibermodemmodemlifecycle) | The current lifecycle the modem is in. |
| peripherals | [map hiber.device.Device.PeripheralsEntry](#hiberdevicedeviceperipheralsentry) | additional information |
| notes | [ string](#string) | Notes field that can be used to add additional information to a modem. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **_secure_notes**.secure_notes | [optional string](#string) | Secure notes field that can be used to add additional information to a modem, with limited accessibility. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **_link**.link | [optional hiber.device.Device.Links](#hiberdevicedevicelinks) | Optional information about what other devices this devices is linked to. |
| metadata | [ google.protobuf.Struct](#googleprotobufstruct) | Modem metadata, typically extracted from messages. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **_time_zone**.time_zone | [optional string](#string) | The timezone configured for the modem. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **_transmission_interval**.transmission_interval | [optional hiber.Duration](#hiberduration) | The transmission interval for this modem, if configured. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **_expected_transmission_rate**.expected_transmission_rate | [optional hiber.value.Value.Numeric.Rate](#hibervaluevaluenumericrate) | The expected transmission rate for this device. |
| type | [ string](#string) | The DeviceType for this device. See DeviceType for more information. |
| sensor_brand | [ string](#string) | The DeviceType for this device. See DeviceType for more information. |

### hiber.device.Device.Links

Collection of data about the devices it is connected to.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifiers | [repeated string](#string) | Other identifiers for this devices. Could include data like its MAC-address or otherwise unique identifier. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **_gateway**.gateway | [optional string](#string) | The gateway directly upstream from this device (in the direction of Mission Control). This device sends its data directly to its gateway, which in turn relays it to Mission Control. |

### hiber.device.Device.PeripheralsEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ string](#string) | none |

### hiber.device.DeviceSelection

Selection object for devices.
Filter devices by device number, tags, etc.

| Field | Type | Description |
| ----- | ---- | ----------- |
| free_text_search | [ string](#string) | none |
| modems | [ hiber.Filter.Modems](#hiberfiltermodems) | none |
| identifiers | [ hiber.Filter.ModemIdentifiers](#hiberfiltermodemidentifiers) | none |
| health_level | [ hiber.Filter.HealthLevels](#hiberfilterhealthlevels) | none |
| lifecycles | [ hiber.device.ModemFilter.Lifecycles](#hiberdevicemodemfilterlifecycles) | none |
| with_gateways | [ hiber.Filter.Modems](#hiberfiltermodems) | none |
| peripherals | [ hiber.Filter.Properties](#hiberfilterproperties) | none |
| device_types | [ hiber.Filter.DeviceTypes](#hiberfilterdevicetypes) | none |
| sensorBrands | [ hiber.Filter.SensorBrands](#hiberfiltersensorbrands) | none |
| filter_by_tags | [ hiber.tag.TagSelection](#hibertagtagselection) | none |
| with_last_message_in | [ hiber.TimeRange](#hibertimerange) | none |

### hiber.device.ModemFilter




### hiber.device.ModemFilter.Lifecycles



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated hiber.modem.Modem.Lifecycle](#hibermodemmodemlifecycle) | none |
| exclude | [repeated hiber.modem.Modem.Lifecycle](#hibermodemmodemlifecycle) | none |


### Enums
#### hiber.device.Sort
Sorting options for the results.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEVICE_NAME_ASC | Sort alphabetically on the name of the device. De default name of the device is its HEX number, in ascending order. | 0 |
| DEVICE_NAME_DESC | Sort alphabetically on the name of the device. De default name of the device is its HEX number, in descending order. | 1 |
| DEVICE_NUMBER_ASC | Sort numerically on the number of the device, in ascending order. | 2 |
| DEVICE_NUMBER_DESC | Sort numerically on the number of the device, in descending order. | 3 |
| ACTIVITY | Sort devices on most recent activity first (e.g. newest message received). | 4 |
| INACTIVITY | Sort devices on least recent activity first (e.g. longest no message received). | 5 |
| LIFECYCLE_ASC | Sort device on its lifecycle state. | 6 |
| LIFECYCLE_DESC | Sort device on its lifecycle state in reverse order. | 7 |
| LIFECYCLE_ALPHABETICAL_ASC | Sort device on lifecycle name, alphabetically. | 8 |
| LIFECYCLE_ALPHABETICAL_DESC | Sort device on lifecycle name, alphabetically in reverse order. | 9 |
| ORGANIZATION_ASC | Sort alphabetically on the name of the organization that owns the device, in ascending order. | 10 |
| ORGANIZATION_DESC | Sort alphabetically on the name of the organization that owns the device, in descending order. | 11 |
| HEALTH_ASC | Health sorted from least to most severe (i.e. OK, WARNING, ERROR). | 12 |
| HEALTH_DESC | Health sorted from most to least severe (i.e. ERROR, WARNING, OK). | 13 |
| HEALTH_ALPHABETICAL_ASC | Health sorted alphabetically by health level name. | 14 |
| HEALTH_ALPHABETICAL_DESC | Health sorted alphabetically by health level name, descending order. | 15 |
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
| avatar | [ hiber.Avatar](#hiberavatar) | The avatar image representing this organisation. Usually the logo. |
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
| organization_to_delete | [ string](#string) | none |
| organizations_deleted | [ hiber.organization.OrganizationTree](#hiberorganizationorganizationtree) | The organizations that were deleted. |

### hiber.organization.GetOrganizationAvatar




### hiber.organization.GetOrganizationAvatar.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organizations | [repeated string](#string) | The slug for this organization, used to identify organizations |
| pagination | [ hiber.Pagination](#hiberpagination) | none |

### hiber.organization.GetOrganizationAvatar.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| avatars | [map hiber.organization.GetOrganizationAvatar.Response.AvatarsEntry](#hiberorganizationgetorganizationavatarresponseavatarsentry) | Avatars, indexed by organization slug |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### hiber.organization.GetOrganizationAvatar.Response.AvatarsEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ hiber.Avatar](#hiberavatar) | none |

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
| selection | [ hiber.organization.OrganizationSelection](#hiberorganizationorganizationselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |
| include_details | [ bool](#bool) | none |

### hiber.organization.ListChildOrganizationsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| child_organizations | [repeated hiber.organization.Organization](#hiberorganizationorganization) | none |
| request | [ hiber.organization.ListChildOrganizationsRequest](#hiberorganizationlistchildorganizationsrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### hiber.organization.Organization

Organization data. An Organization can have many linked users, but the organization is the owner
of any modems and related data.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | The slug for this organization, used to identify organizations |
| display_name | [ string](#string) | The name of the organization to display to the end-user |
| address | [ hiber.organization.Organization.Address](#hiberorganizationorganizationaddress) | none |
| contact | [ hiber.organization.Organization.Contact](#hiberorganizationorganizationcontact) | none |
| vat_number | [ string](#string) | none |
| billing_name | [ string](#string) | none |
| billing_address | [ hiber.organization.Organization.Address](#hiberorganizationorganizationaddress) | none |
| contract_signature_date | [ hiber.Timestamp](#hibertimestamp) | none |
| created_at | [ hiber.Timestamp](#hibertimestamp) | none |
| updated_at | [ hiber.Timestamp](#hibertimestamp) | none |
| features | [repeated hiber.organization.Organization.Feature](#hiberorganizationorganizationfeature) | none |
| database_info | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **_defaults**.defaults | [optional hiber.organization.Organization.Defaults](#hiberorganizationorganizationdefaults) | none |

### hiber.organization.Organization.Address



| Field | Type | Description |
| ----- | ---- | ----------- |
| lines | [repeated string](#string) | none |
| zip_code | [ string](#string) | none |
| city | [ string](#string) | none |
| state | [ string](#string) | none |
| country | [ string](#string) | none |

### hiber.organization.Organization.Contact



| Field | Type | Description |
| ----- | ---- | ----------- |
| name | [ string](#string) | none |
| email | [ string](#string) | none |
| phone | [ string](#string) | none |

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
| organizations | [ hiber.Filter.Organizations](#hiberfilterorganizations) | none |
| search | [ string](#string) | none |

### hiber.organization.OrganizationTree



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ hiber.organization.Organization](#hiberorganizationorganization) | none |
| children | [repeated hiber.organization.OrganizationTree](#hiberorganizationorganizationtree) | none |

### hiber.organization.OrganizationTreeRequest

Get your current organization's organization tree.
The organization tree contains your current organization as the root of the tree, with all child organizations ordered below it.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate) for this call, overriding your default organization |
| selection | [ hiber.organization.OrganizationSelection](#hiberorganizationorganizationselection) | none |

### hiber.organization.OrganizationTreeRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ hiber.organization.OrganizationTreeRequest](#hiberorganizationorganizationtreerequest) | none |
| tree | [ hiber.organization.OrganizationTree](#hiberorganizationorganizationtree) | none |

### hiber.organization.UpdateOrganizationRequest

Update organization data.
All fields are effectively optional, though address, billing_address, contact and features are assumed to be complete objects,
not partial updates.
Note that the organization field specifies the organization, it is not used to update the current organization identifier.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| display_name | [ string](#string) | none |
| vat_number | [ string](#string) | none |
| address | [ hiber.organization.Organization.Address](#hiberorganizationorganizationaddress) | none |
| billing_name | [ string](#string) | none |
| billing_address | [ hiber.organization.Organization.Address](#hiberorganizationorganizationaddress) | none |
| contact | [ hiber.organization.Organization.Contact](#hiberorganizationorganizationcontact) | none |
| avatar | [ hiber.Avatar](#hiberavatar) | none |

### hiber.organization.ValidateOrganizationCreationTokenRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization_creation_token | [ string](#string) | A token that allows you to create an organization without having an organization. |

### hiber.organization.ValidateOrganizationCreationTokenRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| valid | [ bool](#bool) | none |


### Enums
#### hiber.organization.Organization.Feature


| Name | Description | Number |
| ---- | ----------- | ------ |
| UNKNOWN | none | 0 |
| HIBER | The default Hiber set of features including Mission Control and the API | 1 |
| HILO | A limited set of features corresponding to the HiberHilo product. | 2 |
| MODEM_CREATION | Required to manually create modems using the ModemService. | 4 |
| EARLY_ACCESS | Used for organizations that get early access to features. | 5 |
| EXPERIMENTAL | Used for organizations that get access to experimental features. e.g. feature work in progress. | 6 |
| BI_TOOLING_BETA | Integrate BI tooling in the Mission Control interface. | 8 |



## Referenced messages from transfer.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [transfer.proto](https://github.com/HiberGlobal/api/blob/master/transfer.proto).


### hiber.transfer.Transfer



| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) | The identifier for the transfer. |
| sender_organization | [ string](#string) | The organization that sent the transfer. |
| recipient_organization | [ string](#string) | The organization that received the transfer. |
| comment | [ string](#string) | Optional comment for the transfer (i.e. reason, tracking information, etc). |
| created_at | [ hiber.Timestamp](#hibertimestamp) | none |
| type | [ hiber.transfer.Transfer.Type](#hibertransfertransfertype) | The type of data transferred to the recipient organization. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed**.devices | [ hiber.transfer.Transfer.Devices](#hibertransfertransferdevices) | The devices that were transferred from the sender to the recipient organization. |

### hiber.transfer.Transfer.Devices

The devices that were transferred from the sender to the recipient organization.

| Field | Type | Description |
| ----- | ---- | ----------- |
| numbers | [repeated string](#string) | The numbers of the devices that were transferred from the sender to the recipient organization. |


### Enums
#### hiber.transfer.Transfer.Type
The type of data transferred to the recipient organization.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEVICES | none | 0 |



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

Specify which organizations to get data from. By default, data is only retrieved for the current organization,
but using ChildOrganizations we can specify to include a number of, or all, sub-organizations.

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

### hiber.Filter.DeviceTypes



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) | none |
| exclude | [repeated string](#string) | none |

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

### hiber.Filter.HealthLevels



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) | none |
| exclude | [repeated string](#string) | none |

### hiber.Filter.ModemIdentifiers



| Field | Type | Description |
| ----- | ---- | ----------- |
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

### hiber.Filter.Properties

Filter result on specific properties encoded in map-value pairs.

| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **selection**.properties | [ hiber.MapFilter](#hibermapfilter) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **selection**.include_only_empty | [ bool](#bool) | When set to true, match only empty property-sets. |

### hiber.Filter.Publishers



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated int64](#int64) | none |
| exclude | [repeated int64](#int64) | none |
| only_active | [ bool](#bool) | none |

### hiber.Filter.Roles



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) | none |
| exclude | [repeated string](#string) | none |

### hiber.Filter.SensorBrands



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) | none |
| exclude | [repeated string](#string) | none |

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
| key | [ string](#string) | none |
| value | [ hiber.MapFilter.OneOfValues](#hibermapfilteroneofvalues) | none |

### hiber.MapFilter.IncludeAndEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ hiber.MapFilter.OneOfValues](#hibermapfilteroneofvalues) | none |

### hiber.MapFilter.OneOfValues

Technical solution to make map<k, v> into a map<k, repeated v>,
which is not possible in protobuf without trickery.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [repeated string](#string) | none |

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
| TRANSFER | none | 18 |
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
| FLOW_BARRELS_PER_DAY | none | 46 |
| REVOLUTIONS_PER_MINUTE | none | 44 |
| ITEMS_PER_24_HOURS | none | 45 |

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

