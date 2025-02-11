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

- Referenced messages from [transfer.proto](#referenced-messages-from-transferproto)
  - [hiber.transfer.Transfer](#hibertransfertransfer)
  - [hiber.transfer.Transfer.Devices](#hibertransfertransferdevices)

    - [hiber.transfer.Transfer.Type](#hibertransfertransfertype)

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
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **recipient_organization_or_create**.recipient_organization | [ string](#string) | Existing organization to receive the transfer. You must have access to the recipient organization to transfer data to it. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **recipient_organization_or_create**.new_organization | [ hiber.organization.CreateOrganizationRequest](#hiberorganizationcreateorganizationrequest) | Create a new organization to receive the transfer. |
|  **optional** comment | [optional string](#string) | Optional comment for the transfer (e.g. reason, tracking information, etc). |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.devices | [ hiber.device.DeviceSelection](#hiberdevicedeviceselection) | Transfer a number of selected devices to the recipient organization. |

### PerformTransfer.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| transfer | [ Transfer](#transfer) |  |
| request | [ PerformTransfer.Request](#performtransferrequest) |  |

### TransferHistory




### TransferHistory.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional TransferHistory.Request.TransferSelection](#transferhistoryrequesttransferselection) | Select the transfers to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |

### TransferHistory.Request.TransferSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** search | [optional string](#string) | Search transfers by identifier, organizations, device, etc. |
| identifiers | [repeated string](#string) | Select transfers by transfer identifier. |
|  **optional** time_range | [optional hiber.TimeRange](#hibertimerange) | Select transfers that were performed within this time. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **selection**.devices | [ hiber.device.DeviceSelection](#hiberdevicedeviceselection) | Select device transfers with specific devices. |
|  **optional** received_only | [optional bool](#bool) | Only show transfer that your organization received. |
|  **optional** sent_only | [optional bool](#bool) | Only show transfer that your organization sent. |

### TransferHistory.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| transfer_history | [repeated Transfer](#transfer) |  |
| request | [ TransferHistory.Request](#transferhistoryrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |


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
| location | [ hiber.Location](#hiberlocation) |  |
|  **optional** inactivity | [optional hiber.Duration](#hiberduration) | The amount of time since the last message from this modem was received on the server. |
| health | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | Health based on the modem alarm and some always-present alarms. |
| lifecycle | [ hiber.modem.Modem.Lifecycle](#hibermodemmodemlifecycle) | The current lifecycle the modem is in. |
| peripherals | [map hiber.device.Device.PeripheralsEntry](#hiberdevicedeviceperipheralsentry) | additional information |
| notes | [ string](#string) | Notes field that can be used to add additional information to a modem. |
|  **optional** secure_notes | [optional string](#string) | Secure notes field that can be used to add additional information to a modem, with limited accessibility. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
|  **optional** link | [optional hiber.device.Device.Links](#hiberdevicedevicelinks) | Optional information about what other devices this devices is linked to. |
| metadata | [ google.protobuf.Struct](#googleprotobufstruct) | Modem metadata, typically extracted from messages. |
|  **optional** time_zone | [optional string](#string) | The timezone configured for the modem. |
|  **optional** transmission_interval | [optional hiber.Duration](#hiberduration) | The transmission interval for this modem, if configured. |
|  **optional** expected_transmission_rate | [optional hiber.value.Value.Numeric.Rate](#hibervaluevaluenumericrate) | The expected transmission rate for this device. |
| type | [ string](#string) | The DeviceType for this device. See DeviceType for more information. |
| sensor_brand | [ string](#string) | The DeviceType for this device. See DeviceType for more information. |
| numeric_value_types | [repeated hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype) | The numeric value types that this device produces. The device may produce other values (like battery level), but these are the primary value types. |

### hiber.device.Device.Links

Collection of data about the devices it is connected to.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifiers | [repeated string](#string) | Other identifiers for this devices. Could include data like its MAC-address or otherwise unique identifier. |
|  **optional** gateway | [optional string](#string) | The gateway directly upstream from this device (in the direction of Mission Control). This device sends its data directly to its gateway, which in turn relays it to Mission Control. |

### hiber.device.Device.PeripheralsEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ string](#string) |  |

### hiber.device.DeviceSelection

Selection object for devices.
Filter devices by device number, tags, etc.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** free_text_search | [optional string](#string) |  |
|  **optional** modems | [optional hiber.Filter.Modems](#hiberfiltermodems) |  |
|  **optional** identifiers | [optional hiber.Filter.ModemIdentifiers](#hiberfiltermodemidentifiers) |  |
|  **optional** health_level | [optional hiber.Filter.HealthLevels](#hiberfilterhealthlevels) |  |
|  **optional** lifecycles | [optional hiber.device.ModemFilter.Lifecycles](#hiberdevicemodemfilterlifecycles) |  |
|  **optional** with_gateways | [optional hiber.Filter.Modems](#hiberfiltermodems) |  |
|  **optional** peripherals | [optional hiber.Filter.Properties](#hiberfilterproperties) |  |
|  **optional** device_types | [optional hiber.Filter.DeviceTypes](#hiberfilterdevicetypes) |  |
|  **optional** sensorBrands | [optional hiber.Filter.SensorBrands](#hiberfiltersensorbrands) |  |
|  **optional** filter_by_tags | [optional hiber.tag.TagSelection](#hibertagtagselection) |  |
|  **optional** with_last_message_in | [optional hiber.TimeRange](#hibertimerange) |  |

### hiber.device.ModemFilter




### hiber.device.ModemFilter.Lifecycles



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated hiber.modem.Modem.Lifecycle](#hibermodemmodemlifecycle) |  |
| exclude | [repeated hiber.modem.Modem.Lifecycle](#hibermodemmodemlifecycle) |  |


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
| HEALTH_ASC | Health sorted from least to most severe (e.g. OK, WARNING, ERROR). | 12 |
| HEALTH_DESC | Health sorted from most to least severe (e.g. ERROR, WARNING, OK). | 13 |
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
| database_info | [ string](#string) |  |
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
| ASSET_DASHBOARD | Use the new assets as primary data owner in Mission Control dashboards. | 11 |
| LOCATIONS | Display and use device and gateway locations in Mission Control. | 12 |



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
| comment | [ string](#string) | Optional comment for the transfer (e.g. reason, tracking information, etc). |
| created_at | [ hiber.Timestamp](#hibertimestamp) |  |
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
| DEVICES |  | 0 |



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

