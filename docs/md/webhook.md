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
| description | [ string](#string) | none |
| data | [ Webhook.WebhookData](#webhookwebhookdata) | none |
| filters | [ Webhook.WebhookFilters](#webhookwebhookfilters) | none |
| health_levels | [repeated string](#string) | Filter events by health level caused. |
| tags | [repeated int64](#int64) | none |
| certificate_id | [ int64](#int64) | Optionally, a client certificate can be used for the webhook call. See the CertificateService for certificate management options. |

### DeleteWebhookRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) | none |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |

### DeleteWebhookRequest.Response




### DisableWebhookRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) | none |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |

### EnableWebhookRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) | none |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |

### GetWebhookRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) | none |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |

### ListWebhooksRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ WebhookSelection](#webhookselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |
| sort | [repeated ListWebhooksRequest.Sort](#listwebhooksrequestsort) | none |

### ListWebhooksRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| webhooks | [repeated Webhook](#webhook) | none |
| request | [ ListWebhooksRequest](#listwebhooksrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### UpdateWebhookFilterRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) | none |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| deprecated_event_filter | [ UpdateWebhookFilterRequest.UpdateEvents](#updatewebhookfilterrequestupdateevents) | none |
| deprecated_modem_filter | [ UpdateWebhookFilterRequest.UpdateModems](#updatewebhookfilterrequestupdatemodems) | none |
| deprecated_tag_filter | [ UpdateWebhookFilterRequest.UpdateTags](#updatewebhookfilterrequestupdatetags) | none |
| event_filter | [ hiber.Filter.Events.Update](#hiberfiltereventsupdate) | none |
| modem_filter | [ hiber.Filter.Modems.Update](#hiberfiltermodemsupdate) | none |
| tag_filter | [ hiber.Filter.Tags.Update](#hiberfiltertagsupdate) | none |
| add_health_levels_to_filter | [repeated string](#string) | Add health levels to the health levels filter. |
| remove_health_levels_from_filter | [repeated string](#string) | Remove health levels from the health levels filter. |

### UpdateWebhookFilterRequest.UpdateEvents



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ hiber.Filter.Events](#hiberfilterevents) | none |

### UpdateWebhookFilterRequest.UpdateModems



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ hiber.Filter.Modems](#hiberfiltermodems) | none |

### UpdateWebhookFilterRequest.UpdateTags



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ hiber.Filter.Tags](#hiberfiltertags) | none |

### UpdateWebhookRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) | none |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| update | [ UpdateWebhookRequest.UpdateWebhook](#updatewebhookrequestupdatewebhook) | none |

### UpdateWebhookRequest.UpdateWebhook



| Field | Type | Description |
| ----- | ---- | ----------- |
| url | [ string](#string) | none |
| secret | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| content_type | [ Webhook.ContentType](#webhookcontenttype) | none |
| description | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| deprecated_event_filter | [ UpdateWebhookRequest.UpdateWebhook.UpdateEvents](#updatewebhookrequestupdatewebhookupdateevents) | none |
| deprecated_modem_filter | [ UpdateWebhookRequest.UpdateWebhook.UpdateModems](#updatewebhookrequestupdatewebhookupdatemodems) | none |
| deprecated_tag_filter | [ UpdateWebhookRequest.UpdateWebhook.UpdateTags](#updatewebhookrequestupdatewebhookupdatetags) | none |
| event_filter | [ hiber.Filter.Events.Update](#hiberfiltereventsupdate) | none |
| modem_filter | [ hiber.Filter.Modems.Update](#hiberfiltermodemsupdate) | none |
| tag_filter | [ hiber.Filter.Tags.Update](#hiberfiltertagsupdate) | none |
| add_health_levels | [repeated string](#string) | Add health levels to the health levels filter. |
| remove_health_levels | [repeated string](#string) | Remove health levels from the health levels filter. |
| active | [ hiber.UpdateBoolean](#hiberupdateboolean) | none |
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
| key | [ string](#string) | none |
| value | [ string](#string) | none |

### UpdateWebhookRequest.UpdateWebhook.ReplaceCustomHeadersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ string](#string) | none |

### UpdateWebhookRequest.UpdateWebhook.UpdateEvents



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ hiber.Filter.Events](#hiberfilterevents) | none |

### UpdateWebhookRequest.UpdateWebhook.UpdateModems



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ hiber.Filter.Modems](#hiberfiltermodems) | none |

### UpdateWebhookRequest.UpdateWebhook.UpdateTags



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ hiber.Filter.Tags](#hiberfiltertags) | none |

### UpdateWebhookTagsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| webhook_ids | [repeated int64](#int64) | none |
| update | [ hiber.tag.UpdateTagsForItem](#hibertagupdatetagsforitem) | none |

### UpdateWebhookTagsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| webhooks | [repeated Webhook](#webhook) | none |

### UpdateWebhooksRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| webhook_updates | [repeated UpdateWebhooksRequest.Update](#updatewebhooksrequestupdate) | none |

### UpdateWebhooksRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| webhooks | [repeated Webhook](#webhook) | none |
| request | [ UpdateWebhooksRequest](#updatewebhooksrequest) | none |

### UpdateWebhooksRequest.Update



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) | none |
| update | [ UpdateWebhookRequest.UpdateWebhook](#updatewebhookrequestupdatewebhook) | none |

### Webhook

Webhook publisher that sends events to a webhook.

When the webhook call fails, it enters cooldown, so as not to overload a failing server
or spend unnecessary time on an incorrectly configured webhook.
When the first call after the cooldown time has passed fails again, the cooldown is increased as follows:
1m, 2m, 5m, 10m, 15m, 30m, 1h, 3h, 6h, 12h, 24h.

To disable the cooldown, use EnableWebhookRequest to re-enable it.

| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) | none |
| organization | [ string](#string) | none |
| created_by | [ string](#string) | none |
| description | [ string](#string) | none |
| data | [ Webhook.WebhookData](#webhookwebhookdata) | none |
| filters | [ Webhook.WebhookFilters](#webhookwebhookfilters) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| health | [ hiber.Health](#hiberhealth) | none |
| health_config | [ Webhook.HealthConfig](#webhookhealthconfig) | none |
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
| url | [ string](#string) | none |
| secret | [ string](#string) | Used to generate the HMAC-SHA256 header on every webhook call, which you can use to verify the message. The HMAC-SHA256 header is calculated with the message body and this secret. There are many examples of how to do this in different languages, for example: https://github.com/danharper/hmac-examples |
| hmac_header_name | [ string](#string) | The header that the hmac value is placed in. Defaults to X-Hub-Signature. |
| content_type | [ Webhook.ContentType](#webhookcontenttype) | none |
| disabled | [ bool](#bool) | none |
| certificate_id | [ int64](#int64) | none |
| certificate_name | [ string](#string) | none |
| ca_certificate_id | [ int64](#int64) | none |
| ca_certificate_name | [ string](#string) | none |
| custom_headers | [map Webhook.WebhookData.CustomHeadersEntry](#webhookwebhookdatacustomheadersentry) | Custom headers to add to every call. |

### Webhook.WebhookData.CustomHeadersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ string](#string) | none |

### Webhook.WebhookFilters



| Field | Type | Description |
| ----- | ---- | ----------- |
| event_types | [ hiber.Filter.Events](#hiberfilterevents) | none |
| modem_numbers | [ hiber.Filter.Modems](#hiberfiltermodems) | none |
| tags | [ hiber.Filter.Tags](#hiberfiltertags) | none |
| health_levels | [repeated string](#string) | Filter events by health level caused. |

### WebhookCall



| Field | Type | Description |
| ----- | ---- | ----------- |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| url | [ string](#string) | none |
| headers | [map WebhookCall.HeadersEntry](#webhookcallheadersentry) | none |
| body_proto | [ bytes](#bytes) | none |
| body_json | [ string](#string) | none |
| successful | [ bool](#bool) | none |
| error | [ string](#string) | none |

### WebhookCall.HeadersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ string](#string) | none |

### WebhookHistoryRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| webhook_id | [ int64](#int64) | none |
| selection | [ WebhookHistorySelection](#webhookhistoryselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |

### WebhookHistoryRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| calls | [repeated WebhookCall](#webhookcall) | none |
| request | [ WebhookHistoryRequest](#webhookhistoryrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### WebhookHistorySelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| only_failures | [ bool](#bool) | none |
| time_range | [ hiber.TimeRange](#hibertimerange) | none |

### WebhookSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| description | [ string](#string) | none |
| url | [ string](#string) | none |
| webhooks | [ hiber.Filter.Webhooks](#hiberfilterwebhooks) | none |
| tags | [ hiber.tag.TagSelection](#hibertagtagselection) | none |
| health | [repeated hiber.Health](#hiberhealth) | none |
| certificate_ids | [repeated int64](#int64) | none |
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
| DEFAULT | none | 0 |
| JSON | none | 1 |
| PROTO | none | 2 |



## Referenced messages from tag.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [tag.proto](https://github.com/HiberGlobal/api/blob/master/tag.proto).


### hiber.tag.Tag



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) | none |
| label | [ hiber.tag.Tag.Label](#hibertagtaglabel) | none |

### hiber.tag.Tag.Label



| Field | Type | Description |
| ----- | ---- | ----------- |
| name | [ string](#string) | none |
| type | [ string](#string) | none |

### hiber.tag.TagSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| search | [repeated string](#string) | none |
| names | [repeated string](#string) | none |
| filter | [ hiber.Filter.Tags](#hiberfiltertags) | none |
| types | [repeated string](#string) | none |


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

