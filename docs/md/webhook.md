# webhook.proto



#### This file was generated from [webhook.proto](https://github.com/HiberGlobal/api/blob/master/webhook.proto).

## Table of Contents

- Services
  - [WebhookService](#webhookservice)

- Messages
  - [CreateWebhookRequest](#createwebhookrequest)
  - [DeleteWebhookRequest](#deletewebhookrequest)
  - [DeleteWebhookRequest.Response](#deletewebhookrequestresponse)
  - [DisableWebhookRequest](#disablewebhookrequest)
  - [EnableWebhookRequest](#enablewebhookrequest)
  - [GetWebhookRequest](#getwebhookrequest)
  - [ListWebhooksRequest](#listwebhooksrequest)
  - [ListWebhooksRequest.Response](#listwebhooksrequestresponse)
  - [UpdateWebhookFilterRequest](#updatewebhookfilterrequest)
  - [UpdateWebhookFilterRequest.UpdateEvents](#updatewebhookfilterrequestupdateevents)
  - [UpdateWebhookFilterRequest.UpdateModems](#updatewebhookfilterrequestupdatemodems)
  - [UpdateWebhookFilterRequest.UpdateTags](#updatewebhookfilterrequestupdatetags)
  - [UpdateWebhookRequest](#updatewebhookrequest)
  - [UpdateWebhookRequest.UpdateWebhook](#updatewebhookrequestupdatewebhook)
  - [UpdateWebhookRequest.UpdateWebhook.AddCustomHeadersEntry](#updatewebhookrequestupdatewebhookaddcustomheadersentry)
  - [UpdateWebhookRequest.UpdateWebhook.ReplaceCustomHeadersEntry](#updatewebhookrequestupdatewebhookreplacecustomheadersentry)
  - [UpdateWebhookRequest.UpdateWebhook.UpdateEvents](#updatewebhookrequestupdatewebhookupdateevents)
  - [UpdateWebhookRequest.UpdateWebhook.UpdateModems](#updatewebhookrequestupdatewebhookupdatemodems)
  - [UpdateWebhookRequest.UpdateWebhook.UpdateTags](#updatewebhookrequestupdatewebhookupdatetags)
  - [UpdateWebhookTagsRequest](#updatewebhooktagsrequest)
  - [UpdateWebhookTagsRequest.Response](#updatewebhooktagsrequestresponse)
  - [UpdateWebhooksRequest](#updatewebhooksrequest)
  - [UpdateWebhooksRequest.Response](#updatewebhooksrequestresponse)
  - [UpdateWebhooksRequest.Update](#updatewebhooksrequestupdate)
  - [Webhook](#webhook)
  - [Webhook.HealthConfig](#webhookhealthconfig)
  - [Webhook.WebhookData](#webhookwebhookdata)
  - [Webhook.WebhookData.CustomHeadersEntry](#webhookwebhookdatacustomheadersentry)
  - [Webhook.WebhookFilters](#webhookwebhookfilters)
  - [WebhookCall](#webhookcall)
  - [WebhookCall.HeadersEntry](#webhookcallheadersentry)
  - [WebhookHistoryRequest](#webhookhistoryrequest)
  - [WebhookHistoryRequest.Response](#webhookhistoryrequestresponse)
  - [WebhookHistorySelection](#webhookhistoryselection)
  - [WebhookSelection](#webhookselection)

- Enums
  - [ListWebhooksRequest.Sort](#listwebhooksrequestsort)
  - [Webhook.ContentType](#webhookcontenttype)

- Referenced messages from [tag.proto](#referenced-messages-from-tagproto)
  - [hiber.tag.Tag](#hibertagtag)
  - [hiber.tag.Tag.Label](#hibertagtaglabel)
  - [hiber.tag.TagSelection](#hibertagtagselection)


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


## WebhookService


### List
> **rpc** List([ListWebhooksRequest](#listwebhooksrequest))
    [ListWebhooksRequest.Response](#listwebhooksrequestresponse)



### History
> **rpc** History([WebhookHistoryRequest](#webhookhistoryrequest))
    [WebhookHistoryRequest.Response](#webhookhistoryrequestresponse)



### Create
> **rpc** Create([CreateWebhookRequest](#createwebhookrequest))
    [Webhook](#webhook)



### Enable
> **rpc** Enable([EnableWebhookRequest](#enablewebhookrequest))
    [Webhook](#webhook)



### Disable
> **rpc** Disable([DisableWebhookRequest](#disablewebhookrequest))
    [Webhook](#webhook)



### UpdateFilter
> **rpc** UpdateFilter([UpdateWebhookFilterRequest](#updatewebhookfilterrequest))
    [Webhook](#webhook)



### Update
> **rpc** Update([UpdateWebhookRequest](#updatewebhookrequest))
    [Webhook](#webhook)



### UpdateWebhooks
> **rpc** UpdateWebhooks([UpdateWebhooksRequest](#updatewebhooksrequest))
    [UpdateWebhooksRequest.Response](#updatewebhooksrequestresponse)



### UpdateTags
> **rpc** UpdateTags([UpdateWebhookTagsRequest](#updatewebhooktagsrequest))
    [UpdateWebhookTagsRequest.Response](#updatewebhooktagsrequestresponse)



### Get
> **rpc** Get([GetWebhookRequest](#getwebhookrequest))
    [Webhook](#webhook)



### Delete
> **rpc** Delete([DeleteWebhookRequest](#deletewebhookrequest))
    [DeleteWebhookRequest.Response](#deletewebhookrequestresponse)




## Messages

### CreateWebhookRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| description | [ string](#string) |  |
| data | [ Webhook.WebhookData](#webhookwebhookdata) |  |
| filters | [ Webhook.WebhookFilters](#webhookwebhookfilters) |  |
| health_levels | [repeated string](#string) | Filter events by health level caused. |
| tags | [repeated int64](#int64) |  |
| certificate_id | [ int64](#int64) | Optionally, a client certificate can be used for the webhook call. See the CertificateService for certificate management options. |

### DeleteWebhookRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) |  |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |

### DeleteWebhookRequest.Response




### DisableWebhookRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) |  |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |

### EnableWebhookRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) |  |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |

### GetWebhookRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) |  |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |

### ListWebhooksRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ WebhookSelection](#webhookselection) |  |
| pagination | [ hiber.Pagination](#hiberpagination) |  |
| sort | [repeated ListWebhooksRequest.Sort](#listwebhooksrequestsort) |  |

### ListWebhooksRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| webhooks | [repeated Webhook](#webhook) |  |
| request | [ ListWebhooksRequest](#listwebhooksrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### UpdateWebhookFilterRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) |  |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| deprecated_event_filter | [ UpdateWebhookFilterRequest.UpdateEvents](#updatewebhookfilterrequestupdateevents) | <strong>Deprecated.</strong>  |
| deprecated_modem_filter | [ UpdateWebhookFilterRequest.UpdateModems](#updatewebhookfilterrequestupdatemodems) | <strong>Deprecated.</strong>  |
| deprecated_tag_filter | [ UpdateWebhookFilterRequest.UpdateTags](#updatewebhookfilterrequestupdatetags) | <strong>Deprecated.</strong>  |
| event_filter | [ hiber.Filter.Events.Update](#hiberfiltereventsupdate) |  |
| modem_filter | [ hiber.Filter.Modems.Update](#hiberfiltermodemsupdate) |  |
| tag_filter | [ hiber.Filter.Tags.Update](#hiberfiltertagsupdate) |  |
| add_health_levels_to_filter | [repeated string](#string) | Add health levels to the health levels filter. |
| remove_health_levels_from_filter | [repeated string](#string) | Remove health levels from the health levels filter. |

### UpdateWebhookFilterRequest.UpdateEvents

<strong>Deprecated.</strong> 

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.Filter.Events](#hiberfilterevents) |  |

### UpdateWebhookFilterRequest.UpdateModems

<strong>Deprecated.</strong> 

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.Filter.Modems](#hiberfiltermodems) |  |

### UpdateWebhookFilterRequest.UpdateTags

<strong>Deprecated.</strong> 

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.Filter.Tags](#hiberfiltertags) |  |

### UpdateWebhookRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) |  |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| update | [ UpdateWebhookRequest.UpdateWebhook](#updatewebhookrequestupdatewebhook) |  |

### UpdateWebhookRequest.UpdateWebhook



| Field | Type | Description |
| ----- | ---- | ----------- |
| url | [ string](#string) |  |
| secret | [ hiber.UpdateClearableString](#hiberupdateclearablestring) |  |
| content_type | [ Webhook.ContentType](#webhookcontenttype) |  |
| description | [ hiber.UpdateClearableString](#hiberupdateclearablestring) |  |
| deprecated_event_filter | [ UpdateWebhookRequest.UpdateWebhook.UpdateEvents](#updatewebhookrequestupdatewebhookupdateevents) | <strong>Deprecated.</strong>  |
| deprecated_modem_filter | [ UpdateWebhookRequest.UpdateWebhook.UpdateModems](#updatewebhookrequestupdatewebhookupdatemodems) | <strong>Deprecated.</strong>  |
| deprecated_tag_filter | [ UpdateWebhookRequest.UpdateWebhook.UpdateTags](#updatewebhookrequestupdatewebhookupdatetags) | <strong>Deprecated.</strong>  |
| event_filter | [ hiber.Filter.Events.Update](#hiberfiltereventsupdate) |  |
| modem_filter | [ hiber.Filter.Modems.Update](#hiberfiltermodemsupdate) |  |
| tag_filter | [ hiber.Filter.Tags.Update](#hiberfiltertagsupdate) |  |
| add_health_levels | [repeated string](#string) | Add health levels to the health levels filter. |
| remove_health_levels | [repeated string](#string) | Remove health levels from the health levels filter. |
| active | [ hiber.UpdateBoolean](#hiberupdateboolean) |  |
| certificate_id | [ hiber.UpdateOptionalId](#hiberupdateoptionalid) | A value of 0 removes the certificate |
| health_warning_period | [ hiber.Duration](#hiberduration) | Period to consider when determining health from warning events. Warning events cannot be resolved. Set this to 0 to disable warnings based on failure percentage. |
| health_warning_failure_percentage | [ hiber.UpdateZeroableInt](#hiberupdatezeroableint) | Allowed percentage of call failures. If the failure percentage is higher, within the warning period, the health is switched to WARNING. |
| update_hmac_header_name | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | Update the custom hmac header, or clear to reset to default. |
| add_custom_headers | [map UpdateWebhookRequest.UpdateWebhook.AddCustomHeadersEntry](#updatewebhookrequestupdatewebhookaddcustomheadersentry) | Custom headers to add to every call. |
| remove_custom_headers | [repeated string](#string) | Remove previously configured custom headers. |
| replace_custom_headers | [map UpdateWebhookRequest.UpdateWebhook.ReplaceCustomHeadersEntry](#updatewebhookrequestupdatewebhookreplacecustomheadersentry) | Replace the custom headers to add to every call. If set, remove_custom_headers is ignored. |

### UpdateWebhookRequest.UpdateWebhook.AddCustomHeadersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ string](#string) |  |

### UpdateWebhookRequest.UpdateWebhook.ReplaceCustomHeadersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ string](#string) |  |

### UpdateWebhookRequest.UpdateWebhook.UpdateEvents

<strong>Deprecated.</strong> 

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.Filter.Events](#hiberfilterevents) |  |

### UpdateWebhookRequest.UpdateWebhook.UpdateModems

<strong>Deprecated.</strong> 

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.Filter.Modems](#hiberfiltermodems) |  |

### UpdateWebhookRequest.UpdateWebhook.UpdateTags

<strong>Deprecated.</strong> 

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.Filter.Tags](#hiberfiltertags) |  |

### UpdateWebhookTagsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| webhook_ids | [repeated int64](#int64) |  |
| update | [ hiber.tag.UpdateTagsForItem](#hibertagupdatetagsforitem) |  |

### UpdateWebhookTagsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| webhooks | [repeated Webhook](#webhook) |  |

### UpdateWebhooksRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| webhook_updates | [repeated UpdateWebhooksRequest.Update](#updatewebhooksrequestupdate) |  |

### UpdateWebhooksRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| webhooks | [repeated Webhook](#webhook) |  |
| request | [ UpdateWebhooksRequest](#updatewebhooksrequest) |  |

### UpdateWebhooksRequest.Update



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) |  |
| update | [ UpdateWebhookRequest.UpdateWebhook](#updatewebhookrequestupdatewebhook) |  |

### Webhook

Webhook publisher that sends events to a webhook.

When the webhook call fails, it enters cooldown, so as not to overload a failing server
or spend unnecessary time on an incorrectly configured webhook.
When the first call after the cooldown time has passed fails again, the cooldown is increased as follows:
1m, 2m, 5m, 10m, 15m, 30m, 1h, 3h, 6h, 12h, 24h.

To disable the cooldown, use EnableWebhookRequest to re-enable it.

| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) |  |
| organization | [ string](#string) |  |
| created_by | [ string](#string) |  |
| description | [ string](#string) |  |
| data | [ Webhook.WebhookData](#webhookwebhookdata) |  |
| filters | [ Webhook.WebhookFilters](#webhookwebhookfilters) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| health | [ hiber.Health](#hiberhealth) |  |
| health_config | [ Webhook.HealthConfig](#webhookhealthconfig) |  |
| in_cooldown_until | [ hiber.Timestamp](#hibertimestamp) | The time the cooldown ends. |

### Webhook.HealthConfig

Health configuration for the webhook. Defines how the health is calculated.

| Field | Type | Description |
| ----- | ---- | ----------- |
| health_warning_period | [ hiber.Duration](#hiberduration) | Period to consider when determining health from warning events. Warning events cannot be resolved. |
| health_warning_failure_percentage | [ int32](#int32) | Allowed percentage of failures. If the failure percentage is higher, within the warning period, the health is switched to WARNING. |

### Webhook.WebhookData



| Field | Type | Description |
| ----- | ---- | ----------- |
| url | [ string](#string) |  |
| secret | [ string](#string) | Used to generate the HMAC-SHA256 header on every webhook call, which you can use to verify the message. The HMAC-SHA256 header is calculated with the message body and this secret. There are many examples of how to do this in different languages, for example: https://github.com/danharper/hmac-examples |
| hmac_header_name | [ string](#string) | The header that the hmac value is placed in. Defaults to X-Hub-Signature. |
| content_type | [ Webhook.ContentType](#webhookcontenttype) |  |
| disabled | [ bool](#bool) |  |
| certificate_id | [ int64](#int64) |  |
| certificate_name | [ string](#string) |  |
| ca_certificate_id | [ int64](#int64) |  |
| ca_certificate_name | [ string](#string) |  |
| custom_headers | [map Webhook.WebhookData.CustomHeadersEntry](#webhookwebhookdatacustomheadersentry) | Custom headers to add to every call. |

### Webhook.WebhookData.CustomHeadersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ string](#string) |  |

### Webhook.WebhookFilters



| Field | Type | Description |
| ----- | ---- | ----------- |
| event_types | [ hiber.Filter.Events](#hiberfilterevents) |  |
| modem_numbers | [ hiber.Filter.Modems](#hiberfiltermodems) |  |
| tags | [ hiber.Filter.Tags](#hiberfiltertags) |  |
| health_levels | [repeated string](#string) | Filter events by health level caused. |

### WebhookCall



| Field | Type | Description |
| ----- | ---- | ----------- |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| url | [ string](#string) |  |
| headers | [map WebhookCall.HeadersEntry](#webhookcallheadersentry) |  |
| body_proto | [ bytes](#bytes) |  |
| body_json | [ string](#string) |  |
| successful | [ bool](#bool) |  |
| error | [ string](#string) |  |

### WebhookCall.HeadersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ string](#string) |  |

### WebhookHistoryRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| webhook_id | [ int64](#int64) |  |
| selection | [ WebhookHistorySelection](#webhookhistoryselection) |  |
| pagination | [ hiber.Pagination](#hiberpagination) |  |

### WebhookHistoryRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| calls | [repeated WebhookCall](#webhookcall) |  |
| request | [ WebhookHistoryRequest](#webhookhistoryrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### WebhookHistorySelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| only_failures | [ bool](#bool) |  |
| time_range | [ hiber.TimeRange](#hibertimerange) |  |

### WebhookSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| description | [ string](#string) |  |
| url | [ string](#string) |  |
| webhooks | [ hiber.Filter.Webhooks](#hiberfilterwebhooks) |  |
| tags | [ hiber.tag.TagSelection](#hibertagtagselection) |  |
| health | [repeated hiber.Health](#hiberhealth) |  |
| certificate_ids | [repeated int64](#int64) |  |
| search | [ string](#string) | Search in the all available text, like description and url. |


## Enums
### ListWebhooksRequest.Sort


| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | Sort by id. | 0 |
| ID_DESC | Sort by id, high to low. | 1 |
| DESCRIPTION | Sort by description. | 2 |
| DESCRIPTION_DESC | Sort by description, z to a. | 3 |
| URL | Sort by url. | 4 |
| URL_DESC | Sort by url, z to a. | 5 |
| HEALTH | Sort unhealthy webhooks before health webhooks. | 6 |

### Webhook.ContentType


| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT |  | 0 |
| JSON |  | 1 |
| PROTO |  | 2 |



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

