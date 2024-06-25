# publisher.proto



#### This file was generated from [publisher.proto](https://github.com/HiberGlobal/api/blob/master/publisher.proto).

## Table of Contents



- Messages
  - [Publisher](#publisher)
  - [Publisher.Data](#publisherdata)
  - [Publisher.Data.HTTPConfig](#publisherdatahttpconfig)
  - [Publisher.Data.MQTTConfig](#publisherdatamqttconfig)
  - [Publisher.Data.ShellSsipConfig](#publisherdatashellssipconfig)
  - [Publisher.Filters](#publisherfilters)
  - [UpdatePublisherRequest](#updatepublisherrequest)
  - [UpdatePublisherRequest.UpdateModems](#updatepublisherrequestupdatemodems)

- Enums
  - [Publisher.ContentType](#publishercontenttype)
  - [Publisher.Data.MQTTConfig.QoS](#publisherdatamqttconfigqos)
  - [Publisher.Type](#publishertype)

- Referenced messages from [email_notifications.proto](#referenced-messages-from-email_notificationsproto)
  - [hiber.email.EmailHistorySelection](#hiberemailemailhistoryselection)
  - [hiber.email.EmailNotificationHistoryRequest](#hiberemailemailnotificationhistoryrequest)
  - [hiber.email.EmailNotificationHistoryRequest.Response](#hiberemailemailnotificationhistoryrequestresponse)
  - [hiber.email.EmailNotificationHistoryRequest.Response.Email](#hiberemailemailnotificationhistoryrequestresponseemail)
  - [hiber.email.EmailNotificationPreferences](#hiberemailemailnotificationpreferences)
  - [hiber.email.EmailNotificationPreferences.CustomRecipient](#hiberemailemailnotificationpreferencescustomrecipient)
  - [hiber.email.ListEmailNotificationPreferencesRequest](#hiberemaillistemailnotificationpreferencesrequest)
  - [hiber.email.ListEmailNotificationPreferencesRequest.Response](#hiberemaillistemailnotificationpreferencesrequestresponse)
  - [hiber.email.RemoveAllEmailNotificationPreferencesRequest](#hiberemailremoveallemailnotificationpreferencesrequest)
  - [hiber.email.RemoveAllEmailNotificationPreferencesRequest.Response](#hiberemailremoveallemailnotificationpreferencesrequestresponse)
  - [hiber.email.UpdateEmailNotificationPreferencesRequest](#hiberemailupdateemailnotificationpreferencesrequest)
  - [hiber.email.ViewEmailNotificationPreferencesRequest](#hiberemailviewemailnotificationpreferencesrequest)


- Referenced messages from [integration_mqtt.proto](#referenced-messages-from-integration_mqttproto)
  - [hiber.integration.mqtt.CreateMQTTPublisherRequest](#hiberintegrationmqttcreatemqttpublisherrequest)
  - [hiber.integration.mqtt.DeleteMQTTPublisherRequest](#hiberintegrationmqttdeletemqttpublisherrequest)
  - [hiber.integration.mqtt.DeleteMQTTPublisherRequest.Response](#hiberintegrationmqttdeletemqttpublisherrequestresponse)
  - [hiber.integration.mqtt.DisableMQTTPublisherRequest](#hiberintegrationmqttdisablemqttpublisherrequest)
  - [hiber.integration.mqtt.DisableMQTTPublisherRequest.Response](#hiberintegrationmqttdisablemqttpublisherrequestresponse)
  - [hiber.integration.mqtt.EnableMQTTPublisherRequest](#hiberintegrationmqttenablemqttpublisherrequest)
  - [hiber.integration.mqtt.EnableMQTTPublisherRequest.Response](#hiberintegrationmqttenablemqttpublisherrequestresponse)
  - [hiber.integration.mqtt.ListMQTTPublishersRequest](#hiberintegrationmqttlistmqttpublishersrequest)
  - [hiber.integration.mqtt.ListMQTTPublishersRequest.Response](#hiberintegrationmqttlistmqttpublishersrequestresponse)
  - [hiber.integration.mqtt.MQTTMessage](#hiberintegrationmqttmqttmessage)
  - [hiber.integration.mqtt.MQTTPublisher](#hiberintegrationmqttmqttpublisher)
  - [hiber.integration.mqtt.MQTTPublisher.Data](#hiberintegrationmqttmqttpublisherdata)
  - [hiber.integration.mqtt.MQTTPublisher.HealthConfig](#hiberintegrationmqttmqttpublisherhealthconfig)
  - [hiber.integration.mqtt.MQTTPublisherHistoryRequest](#hiberintegrationmqttmqttpublisherhistoryrequest)
  - [hiber.integration.mqtt.MQTTPublisherHistoryRequest.Response](#hiberintegrationmqttmqttpublisherhistoryrequestresponse)
  - [hiber.integration.mqtt.MQTTPublisherHistorySelection](#hiberintegrationmqttmqttpublisherhistoryselection)
  - [hiber.integration.mqtt.MQTTPublisherSelection](#hiberintegrationmqttmqttpublisherselection)
  - [hiber.integration.mqtt.UpdateMQTTPublisherRequest](#hiberintegrationmqttupdatemqttpublisherrequest)
  - [hiber.integration.mqtt.UpdateMQTTPublisherTagsRequest](#hiberintegrationmqttupdatemqttpublishertagsrequest)
  - [hiber.integration.mqtt.UpdateMQTTPublisherTagsRequest.Response](#hiberintegrationmqttupdatemqttpublishertagsrequestresponse)

    - [hiber.integration.mqtt.ListMQTTPublishersRequest.Sort](#hiberintegrationmqttlistmqttpublishersrequestsort)
    - [hiber.integration.mqtt.MQTTPublisher.ContentType](#hiberintegrationmqttmqttpublishercontenttype)
    - [hiber.integration.mqtt.MQTTPublisher.Data.QoS](#hiberintegrationmqttmqttpublisherdataqos)

- Referenced messages from [integration_slack.proto](#referenced-messages-from-integration_slackproto)
  - [hiber.integration.slack.CreateSlackPublisherRequest](#hiberintegrationslackcreateslackpublisherrequest)
  - [hiber.integration.slack.DeleteSlackPublisherRequest](#hiberintegrationslackdeleteslackpublisherrequest)
  - [hiber.integration.slack.DeleteSlackPublisherRequest.Response](#hiberintegrationslackdeleteslackpublisherrequestresponse)
  - [hiber.integration.slack.DisableSlackPublisherRequest](#hiberintegrationslackdisableslackpublisherrequest)
  - [hiber.integration.slack.DisableSlackPublisherRequest.Response](#hiberintegrationslackdisableslackpublisherrequestresponse)
  - [hiber.integration.slack.EnableSlackPublisherRequest](#hiberintegrationslackenableslackpublisherrequest)
  - [hiber.integration.slack.EnableSlackPublisherRequest.Response](#hiberintegrationslackenableslackpublisherrequestresponse)
  - [hiber.integration.slack.ListSlackPublishersRequest](#hiberintegrationslacklistslackpublishersrequest)
  - [hiber.integration.slack.ListSlackPublishersRequest.Response](#hiberintegrationslacklistslackpublishersrequestresponse)
  - [hiber.integration.slack.SlackMessage](#hiberintegrationslackslackmessage)
  - [hiber.integration.slack.SlackPublisher](#hiberintegrationslackslackpublisher)
  - [hiber.integration.slack.SlackPublisher.Data](#hiberintegrationslackslackpublisherdata)
  - [hiber.integration.slack.SlackPublisher.HealthConfig](#hiberintegrationslackslackpublisherhealthconfig)
  - [hiber.integration.slack.SlackPublisherHistoryRequest](#hiberintegrationslackslackpublisherhistoryrequest)
  - [hiber.integration.slack.SlackPublisherHistoryRequest.Response](#hiberintegrationslackslackpublisherhistoryrequestresponse)
  - [hiber.integration.slack.SlackPublisherHistorySelection](#hiberintegrationslackslackpublisherhistoryselection)
  - [hiber.integration.slack.SlackPublisherSelection](#hiberintegrationslackslackpublisherselection)
  - [hiber.integration.slack.UpdateSlackPublisherRequest](#hiberintegrationslackupdateslackpublisherrequest)
  - [hiber.integration.slack.UpdateSlackPublisherTagsRequest](#hiberintegrationslackupdateslackpublishertagsrequest)
  - [hiber.integration.slack.UpdateSlackPublisherTagsRequest.Response](#hiberintegrationslackupdateslackpublishertagsrequestresponse)

    - [hiber.integration.slack.ListSlackPublishersRequest.Sort](#hiberintegrationslacklistslackpublishersrequestsort)

- Referenced messages from [tag.proto](#referenced-messages-from-tagproto)
  - [hiber.tag.Tag](#hibertagtag)
  - [hiber.tag.Tag.Label](#hibertagtaglabel)
  - [hiber.tag.TagSelection](#hibertagtagselection)


- Referenced messages from [webhook.proto](#referenced-messages-from-webhookproto)
  - [hiber.webhook.CreateWebhookRequest](#hiberwebhookcreatewebhookrequest)
  - [hiber.webhook.DeleteWebhookRequest](#hiberwebhookdeletewebhookrequest)
  - [hiber.webhook.DeleteWebhookRequest.Response](#hiberwebhookdeletewebhookrequestresponse)
  - [hiber.webhook.DisableWebhookRequest](#hiberwebhookdisablewebhookrequest)
  - [hiber.webhook.EnableWebhookRequest](#hiberwebhookenablewebhookrequest)
  - [hiber.webhook.GetWebhookRequest](#hiberwebhookgetwebhookrequest)
  - [hiber.webhook.ListWebhooksRequest](#hiberwebhooklistwebhooksrequest)
  - [hiber.webhook.ListWebhooksRequest.Response](#hiberwebhooklistwebhooksrequestresponse)
  - [hiber.webhook.UpdateWebhookFilterRequest](#hiberwebhookupdatewebhookfilterrequest)
  - [hiber.webhook.UpdateWebhookRequest](#hiberwebhookupdatewebhookrequest)
  - [hiber.webhook.UpdateWebhookRequest.UpdateWebhook](#hiberwebhookupdatewebhookrequestupdatewebhook)
  - [hiber.webhook.UpdateWebhookRequest.UpdateWebhook.AddCustomHeadersEntry](#hiberwebhookupdatewebhookrequestupdatewebhookaddcustomheadersentry)
  - [hiber.webhook.UpdateWebhookRequest.UpdateWebhook.ReplaceCustomHeadersEntry](#hiberwebhookupdatewebhookrequestupdatewebhookreplacecustomheadersentry)
  - [hiber.webhook.UpdateWebhookRequest.UpdateWebhook.UpdateEvents](#hiberwebhookupdatewebhookrequestupdatewebhookupdateevents)
  - [hiber.webhook.UpdateWebhookRequest.UpdateWebhook.UpdateModems](#hiberwebhookupdatewebhookrequestupdatewebhookupdatemodems)
  - [hiber.webhook.UpdateWebhookRequest.UpdateWebhook.UpdateTags](#hiberwebhookupdatewebhookrequestupdatewebhookupdatetags)
  - [hiber.webhook.UpdateWebhookTagsRequest](#hiberwebhookupdatewebhooktagsrequest)
  - [hiber.webhook.UpdateWebhookTagsRequest.Response](#hiberwebhookupdatewebhooktagsrequestresponse)
  - [hiber.webhook.UpdateWebhooksRequest](#hiberwebhookupdatewebhooksrequest)
  - [hiber.webhook.UpdateWebhooksRequest.Response](#hiberwebhookupdatewebhooksrequestresponse)
  - [hiber.webhook.UpdateWebhooksRequest.Update](#hiberwebhookupdatewebhooksrequestupdate)
  - [hiber.webhook.Webhook](#hiberwebhookwebhook)
  - [hiber.webhook.Webhook.HealthConfig](#hiberwebhookwebhookhealthconfig)
  - [hiber.webhook.Webhook.WebhookData](#hiberwebhookwebhookwebhookdata)
  - [hiber.webhook.Webhook.WebhookData.CustomHeadersEntry](#hiberwebhookwebhookwebhookdatacustomheadersentry)
  - [hiber.webhook.Webhook.WebhookFilters](#hiberwebhookwebhookwebhookfilters)
  - [hiber.webhook.WebhookCall](#hiberwebhookwebhookcall)
  - [hiber.webhook.WebhookCall.HeadersEntry](#hiberwebhookwebhookcallheadersentry)
  - [hiber.webhook.WebhookHistoryRequest](#hiberwebhookwebhookhistoryrequest)
  - [hiber.webhook.WebhookHistoryRequest.Response](#hiberwebhookwebhookhistoryrequestresponse)
  - [hiber.webhook.WebhookHistorySelection](#hiberwebhookwebhookhistoryselection)
  - [hiber.webhook.WebhookSelection](#hiberwebhookwebhookselection)

    - [hiber.webhook.ListWebhooksRequest.Sort](#hiberwebhooklistwebhooksrequestsort)
    - [hiber.webhook.Webhook.ContentType](#hiberwebhookwebhookcontenttype)

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

## Messages

### Publisher

Generic publisher. A Publisher is a generic parent of the
- webhook publisher
- MQTT publisher
- email publisher

As such, it has common data and can have a configuration for one of those types.

Used to have it's own API encompassing everything, but this has been split up to its individual parts in
- WebhookService
- MQTTService
- EmailNotificationPreferencesService

Now, this types is only used in the relevant events.

| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) |  |
| description | [ string](#string) |  |
| deprecated_data | [ Publisher.Data](#publisherdata) | <strong>Deprecated.</strong> This field remains for backwards compatibility, but it should not be used. |
| filters | [ Publisher.Filters](#publisherfilters) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| health | [ hiber.Health](#hiberhealth) |  |
| type | [ Publisher.Type](#publishertype) |  |
| in_cooldown_until | [ hiber.Timestamp](#hibertimestamp) |  |
| disabled | [ bool](#bool) |  |
| created_by | [ string](#string) | Id of the user that created this publisher |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.http | [ hiber.webhook.Webhook.WebhookData](#hiberwebhookwebhookwebhookdata) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.mqtt | [ hiber.integration.mqtt.MQTTPublisher.Data](#hiberintegrationmqttmqttpublisherdata) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.email | [ hiber.email.EmailNotificationPreferences](#hiberemailemailnotificationpreferences) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.slack | [ hiber.integration.slack.SlackPublisher.Data](#hiberintegrationslackslackpublisherdata) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.shell_ssip | [ Publisher.Data.ShellSsipConfig](#publisherdatashellssipconfig) |  |

### Publisher.Data

<strong>Deprecated.</strong> This type remains for backwards compatibility, but it should not be used.

| Field | Type | Description |
| ----- | ---- | ----------- |
| url | [ string](#string) |  |
| content_type | [ Publisher.ContentType](#publishercontenttype) |  |
| disabled | [ bool](#bool) |  |
| certificate_id | [ int64](#int64) |  |
| certificate_name | [ string](#string) |  |
| ca_certificate_id | [ int64](#int64) |  |
| ca_certificate_name | [ string](#string) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **config**.http | [ Publisher.Data.HTTPConfig](#publisherdatahttpconfig) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **config**.mqtt | [ Publisher.Data.MQTTConfig](#publisherdatamqttconfig) |  |

### Publisher.Data.HTTPConfig

<strong>Deprecated.</strong> This field remains for backwards compatibility, but it should not be used.

| Field | Type | Description |
| ----- | ---- | ----------- |
| secret | [ string](#string) | Used to generate the HMAC-SHA256 header on every publisher call, which you can use to verify the message. The HMAC-SHA256 header is calculated with the message body and this secret. There are many examples of how to do this in different languages, for example: https://github.com/danharper/hmac-examples |

### Publisher.Data.MQTTConfig

<strong>Deprecated.</strong> This field remains for backwards compatibility, but it should not be used.

| Field | Type | Description |
| ----- | ---- | ----------- |
| topic | [ string](#string) |  |
| qos | [ Publisher.Data.MQTTConfig.QoS](#publisherdatamqttconfigqos) |  |
| username | [ string](#string) | Optional username to authenticate with. |
| password | [ string](#string) | Optional password to authenticate with. Requires username to be set. |
| identifier | [ string](#string) | Identifier used by the MQTT client. Defaults to "hiber". |

### Publisher.Data.ShellSsipConfig



| Field | Type | Description |
| ----- | ---- | ----------- |
| url | [ string](#string) |  |
| tenant_id | [ string](#string) |  |
| resource_id | [ string](#string) |  |

### Publisher.Filters



| Field | Type | Description |
| ----- | ---- | ----------- |
| event_types | [ hiber.Filter.Events](#hiberfilterevents) |  |
| modem_numbers | [ hiber.Filter.Modems](#hiberfiltermodems) |  |
| tags | [ hiber.Filter.Tags](#hiberfiltertags) |  |

### UpdatePublisherRequest

<strong>Deprecated.</strong> 


### UpdatePublisherRequest.UpdateModems

<strong>Deprecated.</strong> 

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.Filter.Modems](#hiberfiltermodems) |  |


## Enums
### Publisher.ContentType
<strong>Deprecated.</strong> This type remains for backwards compatibility, but it should not be used.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT |  | 0 |
| JSON |  | 1 |
| PROTO |  | 2 |

### Publisher.Data.MQTTConfig.QoS


| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT |  | 0 |
| AT_MOST_ONCE | Qos level 0 | 1 |
| AT_LEAST_ONCE | Qos level 1 | 2 |
| EXACTLY_ONCE | Qos level 2 | 3 |

### Publisher.Type


| Name | Description | Number |
| ---- | ----------- | ------ |
| HTTP |  | 0 |
| MQTT |  | 1 |
| EMAIL |  | 3 |
| SLACK |  | 4 |
| SHELL_SSIP |  | 5 |



## Referenced messages from email_notifications.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [email_notifications.proto](https://github.com/HiberGlobal/api/blob/master/email_notifications.proto).


### hiber.email.EmailHistorySelection



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** time_range | [optional hiber.TimeRange](#hibertimerange) |  |
|  **optional** only_failures | [optional bool](#bool) |  |

### hiber.email.EmailNotificationHistoryRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** custom | [optional hiber.email.EmailNotificationPreferences.CustomRecipient](#hiberemailemailnotificationpreferencescustomrecipient) | Custom email address preferences to get the history for. If not set, your email is used. |
|  **optional** selection | [optional hiber.email.EmailHistorySelection](#hiberemailemailhistoryselection) |  |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |

### hiber.email.EmailNotificationHistoryRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| emails | [repeated hiber.email.EmailNotificationHistoryRequest.Response.Email](#hiberemailemailnotificationhistoryrequestresponseemail) |  |
| request | [ hiber.email.EmailNotificationHistoryRequest](#hiberemailemailnotificationhistoryrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### hiber.email.EmailNotificationHistoryRequest.Response.Email



| Field | Type | Description |
| ----- | ---- | ----------- |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| title | [ string](#string) |  |
| successful | [ bool](#bool) |  |
| error | [ string](#string) |  |

### hiber.email.EmailNotificationPreferences



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | The organization that owns this publisher |
| enabled_notifications | [ hiber.Filter.Events](#hiberfilterevents) | Events to receive by email. |
| filter_modems | [ hiber.Filter.Modems](#hiberfiltermodems) | Filter events by modems. |
| filter_tags | [ hiber.Filter.Tags](#hiberfiltertags) | Filter events by tags. |
| filter_health_levels | [repeated string](#string) | Filter events by health level caused. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **recipient**.user_id | [ string](#string) | User who created this publisher. Only set if no custom email address is given. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **recipient**.custom | [ hiber.email.EmailNotificationPreferences.CustomRecipient](#hiberemailemailnotificationpreferencescustomrecipient) | Custom email address. For publishers that send to an email address other than this users' email address. |
| active | [ bool](#bool) | Whether email is active for this user/address. |

### hiber.email.EmailNotificationPreferences.CustomRecipient



| Field | Type | Description |
| ----- | ---- | ----------- |
| email | [ string](#string) |  |
| name | [ string](#string) |  |

### hiber.email.ListEmailNotificationPreferencesRequest

List the custom recipients and their preferences. Optionally, personal email preferences can be included.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** search_email | [optional string](#string) | Search for a (partial) custom email address. |
|  **optional** include_personal_email_preferences | [optional bool](#bool) | By default, this request only returns the email preferences for custom emails, but you can choose to view user-specific preferences as well. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |

### hiber.email.ListEmailNotificationPreferencesRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| email_preferences | [repeated hiber.email.EmailNotificationPreferences](#hiberemailemailnotificationpreferences) |  |
| request | [ hiber.email.ListEmailNotificationPreferencesRequest](#hiberemaillistemailnotificationpreferencesrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### hiber.email.RemoveAllEmailNotificationPreferencesRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** custom | [optional hiber.email.EmailNotificationPreferences.CustomRecipient](#hiberemailemailnotificationpreferencescustomrecipient) | Custom email address preferences to disable. |

### hiber.email.RemoveAllEmailNotificationPreferencesRequest.Response




### hiber.email.UpdateEmailNotificationPreferencesRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** custom | [optional hiber.email.EmailNotificationPreferences.CustomRecipient](#hiberemailemailnotificationpreferencescustomrecipient) | Custom email address. Only set this if you want to send notification to an email address not associated with your user. |
|  **optional** enabled_notifications | [optional hiber.Filter.Events](#hiberfilterevents) | Events to receive by email. An empty value enables email for all events. |
|  **optional** deprecated_enabled_notifications | [optional hiber.Filter.Events.Update](#hiberfiltereventsupdate) | <strong>Deprecated.</strong>  |
|  **optional** filter_modems | [optional hiber.Filter.Modems](#hiberfiltermodems) | Filter events by modems. An empty value enables email for every modem's events. |
|  **optional** deprecated_filter_modems | [optional hiber.Filter.Modems.Update](#hiberfiltermodemsupdate) | <strong>Deprecated.</strong>  |
|  **optional** filter_tags | [optional hiber.Filter.Tags](#hiberfiltertags) | Filter events by tags. An empty value enables email for all tags. |
|  **optional** deprecated_filter_tags | [optional hiber.Filter.Tags.Update](#hiberfiltertagsupdate) | <strong>Deprecated.</strong>  |
| add_health_levels_to_filter | [repeated string](#string) | Add health levels to the health levels filter. |
| remove_health_levels_from_filter | [repeated string](#string) | Remove health levels from the health levels filter. |

### hiber.email.ViewEmailNotificationPreferencesRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** email | [optional string](#string) | View the configuration for any email publisher with a custom email address. Optional, should only be used if you want to get the email preferences for a custom recipient. When not set, your personal email preferences are returned. |


### Enums


## Referenced messages from integration_mqtt.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [integration_mqtt.proto](https://github.com/HiberGlobal/api/blob/master/integration_mqtt.proto).


### hiber.integration.mqtt.CreateMQTTPublisherRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** description | [optional string](#string) |  |
|  **optional** filter_event_types | [optional hiber.Filter.Events](#hiberfilterevents) |  |
|  **optional** filter_modem_numbers | [optional hiber.Filter.Modems](#hiberfiltermodems) |  |
|  **optional** filter_tags | [optional hiber.Filter.Tags](#hiberfiltertags) |  |
| url | [ string](#string) | The url of an MQTT server to send the events to, i.e. mqtt[s]://example.com:8883 |
| content_type | [ hiber.integration.mqtt.MQTTPublisher.ContentType](#hiberintegrationmqttmqttpublishercontenttype) |  |
| topic | [ string](#string) | The MQTT topic to send to on the receiving server. |
| qos | [ hiber.integration.mqtt.MQTTPublisher.Data.QoS](#hiberintegrationmqttmqttpublisherdataqos) | MQTT QoS value. |
|  **optional** identifier | [optional string](#string) | Identifier used by the MQTT client. Defaults to "hiber". |
|  **optional** username | [optional string](#string) | Optional username to authenticate with. |
|  **optional** password | [optional string](#string) | Optional password to authenticate with. Requires username to be set. |
|  **optional** certificate_id | [optional int64](#int64) | Client certificate to use when connecting to the MQTT server. |
|  **optional** server_ca_certificate_id | [optional int64](#int64) | Server CA certificate to use when connecting to the MQTT server. |
|  **optional** disabled | [optional bool](#bool) | Disable the MQTT publisher after creation, so it needs to be enabled before it is active. |
| tags | [repeated int64](#int64) |  |

### hiber.integration.mqtt.DeleteMQTTPublisherRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| id | [ int64](#int64) |  |

### hiber.integration.mqtt.DeleteMQTTPublisherRequest.Response




### hiber.integration.mqtt.DisableMQTTPublisherRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.integration.mqtt.MQTTPublisherSelection](#hiberintegrationmqttmqttpublisherselection) |  |

### hiber.integration.mqtt.DisableMQTTPublisherRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| publishers | [repeated hiber.integration.mqtt.MQTTPublisher](#hiberintegrationmqttmqttpublisher) |  |
| request | [ hiber.integration.mqtt.DisableMQTTPublisherRequest](#hiberintegrationmqttdisablemqttpublisherrequest) |  |

### hiber.integration.mqtt.EnableMQTTPublisherRequest

Enable a disabled publisher or re-enable a publisher that's failed and is in cooldown.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.integration.mqtt.MQTTPublisherSelection](#hiberintegrationmqttmqttpublisherselection) |  |

### hiber.integration.mqtt.EnableMQTTPublisherRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| publishers | [repeated hiber.integration.mqtt.MQTTPublisher](#hiberintegrationmqttmqttpublisher) |  |
| request | [ hiber.integration.mqtt.EnableMQTTPublisherRequest](#hiberintegrationmqttenablemqttpublisherrequest) |  |

### hiber.integration.mqtt.ListMQTTPublishersRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional hiber.integration.mqtt.MQTTPublisherSelection](#hiberintegrationmqttmqttpublisherselection) |  |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |
| sort | [repeated hiber.integration.mqtt.ListMQTTPublishersRequest.Sort](#hiberintegrationmqttlistmqttpublishersrequestsort) |  |

### hiber.integration.mqtt.ListMQTTPublishersRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| publishers | [repeated hiber.integration.mqtt.MQTTPublisher](#hiberintegrationmqttmqttpublisher) |  |
| request | [ hiber.integration.mqtt.ListMQTTPublishersRequest](#hiberintegrationmqttlistmqttpublishersrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### hiber.integration.mqtt.MQTTMessage



| Field | Type | Description |
| ----- | ---- | ----------- |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| publisher_data | [ hiber.integration.mqtt.MQTTPublisher.Data](#hiberintegrationmqttmqttpublisherdata) |  |
| message | [ hiber.BytesOrHex](#hiberbytesorhex) |  |
| successful | [ bool](#bool) |  |
| error | [ string](#string) |  |

### hiber.integration.mqtt.MQTTPublisher



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) |  |
| description | [ string](#string) |  |
| created_by | [ string](#string) | The uid of the user that created this publisher |
| data | [ hiber.integration.mqtt.MQTTPublisher.Data](#hiberintegrationmqttmqttpublisherdata) |  |
| filter_event_types | [ hiber.Filter.Events](#hiberfilterevents) |  |
| filter_modem_numbers | [ hiber.Filter.Modems](#hiberfiltermodems) |  |
| filter_tags | [ hiber.Filter.Tags](#hiberfiltertags) |  |
| health | [ hiber.Health](#hiberhealth) |  |
| health_config | [ hiber.integration.mqtt.MQTTPublisher.HealthConfig](#hiberintegrationmqttmqttpublisherhealthconfig) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |

### hiber.integration.mqtt.MQTTPublisher.Data



| Field | Type | Description |
| ----- | ---- | ----------- |
| url | [ string](#string) | The url of an MQTT server to send the events to, i.e. mqtt[s]://example.com:8883 |
| content_type | [ hiber.integration.mqtt.MQTTPublisher.ContentType](#hiberintegrationmqttmqttpublishercontenttype) |  |
| topic | [ string](#string) | The MQTT topic to send to on the receiving server. |
| qos | [ hiber.integration.mqtt.MQTTPublisher.Data.QoS](#hiberintegrationmqttmqttpublisherdataqos) | MQTT QoS value. |
| identifier | [ string](#string) | Identifier used by the MQTT client. Defaults to "hiber". |
| username | [ string](#string) | Optional username to authenticate with. |
| password | [ string](#string) | Optional password to authenticate with. Requires username to be set. |
| certificate_id | [ int64](#int64) | Client certificate to use when connecting to the MQTT server. |
| certificate_name | [ string](#string) |  |
| ca_certificate_id | [ int64](#int64) | CA certificate for the client certificate to use when connecting to the MQTT server. |
| ca_certificate_name | [ string](#string) |  |
| server_ca_certificate_id | [ int64](#int64) | Server CA certificate to use when connecting to the MQTT server. |
| server_ca_certificate_name | [ string](#string) |  |
| disabled | [ bool](#bool) |  |

### hiber.integration.mqtt.MQTTPublisher.HealthConfig

Health configuration for the mqtt integration. Defines how the health is calculated.

| Field | Type | Description |
| ----- | ---- | ----------- |
| health_warning_period | [ hiber.Duration](#hiberduration) | Period to consider when determining health from warning events. Warning events cannot be resolved. |
| health_warning_failure_percentage | [ int32](#int32) | Allowed percentage of failures. If the failure percentage is higher, within the warning period, the health is switched to WARNING. |

### hiber.integration.mqtt.MQTTPublisherHistoryRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| id | [ int64](#int64) |  |
|  **optional** selection | [optional hiber.integration.mqtt.MQTTPublisherHistorySelection](#hiberintegrationmqttmqttpublisherhistoryselection) |  |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |

### hiber.integration.mqtt.MQTTPublisherHistoryRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| items | [repeated hiber.integration.mqtt.MQTTMessage](#hiberintegrationmqttmqttmessage) |  |
| request | [ hiber.integration.mqtt.MQTTPublisherHistoryRequest](#hiberintegrationmqttmqttpublisherhistoryrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### hiber.integration.mqtt.MQTTPublisherHistorySelection



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** time_range | [optional hiber.TimeRange](#hibertimerange) |  |
|  **optional** only_failures | [optional bool](#bool) |  |

### hiber.integration.mqtt.MQTTPublisherSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** publishers | [optional hiber.Filter.Publishers](#hiberfilterpublishers) | Filter by id. |
|  **optional** description | [optional string](#string) | Partial text match on the description. |
|  **optional** search_url | [optional string](#string) | Partial text match on the url. |
|  **optional** search_topic | [optional string](#string) | Partial text match on the topic. |
| content_types | [repeated hiber.integration.mqtt.MQTTPublisher.ContentType](#hiberintegrationmqttmqttpublishercontenttype) | Only return MQTT integrations that use the given content types. |
| certificate_ids | [repeated int64](#int64) | Filter by referenced certificate (id), either as client or server certificate. |
|  **optional** tags | [optional hiber.tag.TagSelection](#hibertagtagselection) |  |
| health | [repeated hiber.Health](#hiberhealth) |  |

### hiber.integration.mqtt.UpdateMQTTPublisherRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| id | [ int64](#int64) |  |
|  **optional** deprecated_filter_event_types | [optional hiber.Filter.Events.Update](#hiberfiltereventsupdate) | <strong>Deprecated.</strong>  |
|  **optional** filter_event_types | [optional hiber.Filter.Events](#hiberfilterevents) |  |
|  **optional** deprecated_filter_modem_numbers | [optional hiber.Filter.Modems.Update](#hiberfiltermodemsupdate) | <strong>Deprecated.</strong>  |
|  **optional** filter_modem_numbers | [optional hiber.Filter.Modems](#hiberfiltermodems) |  |
|  **optional** deprecated_filter_tags | [optional hiber.Filter.Tags.Update](#hiberfiltertagsupdate) | <strong>Deprecated.</strong>  |
|  **optional** filter_tags | [optional hiber.Filter.Tags](#hiberfiltertags) |  |
|  **optional** deprecated_description | [optional hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
|  **optional** description | [optional string](#string) |  |
|  **optional** url | [optional string](#string) | The url of an MQTT server to send the events to, i.e. mqtt[s]://example.com:8883 |
|  **optional** content_type | [optional hiber.integration.mqtt.MQTTPublisher.ContentType](#hiberintegrationmqttmqttpublishercontenttype) |  |
|  **optional** topic | [optional string](#string) | The MQTT topic to send to on the receiving server. |
|  **optional** qos | [optional hiber.integration.mqtt.MQTTPublisher.Data.QoS](#hiberintegrationmqttmqttpublisherdataqos) | MQTT QoS value. |
|  **optional** identifier | [optional string](#string) | Identifier used by the MQTT client. Defaults to "hiber". |
|  **optional** deprecated_identifier | [optional hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
|  **optional** username | [optional string](#string) | Optional username to authenticate with. |
|  **optional** deprecated_username | [optional hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
|  **optional** password | [optional string](#string) | Optional password to authenticate with. Requires username to be set. |
|  **optional** deprecated_password | [optional hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
|  **optional** certificate_id | [optional int64](#int64) | Update or remove the client certificate to use when connecting to the MQTT server. |
|  **optional** deprecated_certificate_id | [optional hiber.UpdateOptionalId](#hiberupdateoptionalid) | <strong>Deprecated.</strong>  |
|  **optional** server_ca_certificate_id | [optional int64](#int64) | Update or remove the server CA certificate to use when connecting to the MQTT server. |
|  **optional** deprecated_server_ca_certificate_id | [optional hiber.UpdateOptionalId](#hiberupdateoptionalid) | <strong>Deprecated.</strong>  |
|  **optional** active | [optional bool](#bool) | Disable the MQTT publisher, so it needs to be enabled again before it is active. |
|  **optional** deprecated_active | [optional hiber.UpdateBoolean](#hiberupdateboolean) | <strong>Deprecated.</strong>  |
|  **optional** health_warning_period | [optional hiber.Duration](#hiberduration) | Period to consider when determining health from warning events. Warning events cannot be resolved. Set this to 0 to disable warnings based on failure percentage. |
|  **optional** health_warning_failure_percentage | [optional uint32](#uint32) | Allowed percentage of call failures. If the failure percentage is higher, within the warning period, the health is switched to WARNING. |
|  **optional** deprecated_health_warning_failure_percentage | [optional hiber.UpdateZeroableInt](#hiberupdatezeroableint) | <strong>Deprecated.</strong>  |

### hiber.integration.mqtt.UpdateMQTTPublisherTagsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) |  |
| selection | [ hiber.integration.mqtt.MQTTPublisherSelection](#hiberintegrationmqttmqttpublisherselection) |  |
| update | [ hiber.tag.UpdateTagsForItem](#hibertagupdatetagsforitem) |  |

### hiber.integration.mqtt.UpdateMQTTPublisherTagsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| mqtt_publishers | [repeated hiber.integration.mqtt.MQTTPublisher](#hiberintegrationmqttmqttpublisher) |  |


### Enums
#### hiber.integration.mqtt.ListMQTTPublishersRequest.Sort


| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | Sort by id. | 0 |
| ID_DESC | Sort by id, high to low. | 1 |
| DESCRIPTION | Sort by description. | 2 |
| DESCRIPTION_DESC | Sort by description, z to a. | 3 |
| URL | Sort by url. | 4 |
| URL_DESC | Sort by url, z to a. | 5 |
| TOPIC | Sort by topic. | 6 |
| TOPIC_DESC | Sort by topic, z to a. | 7 |
| HEALTH | Sort unhealthy webhooks before health webhooks. | 8 |

#### hiber.integration.mqtt.MQTTPublisher.ContentType


| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT |  | 0 |
| JSON |  | 1 |
| PROTO |  | 2 |

#### hiber.integration.mqtt.MQTTPublisher.Data.QoS


| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT |  | 0 |
| AT_MOST_ONCE | Qos level 0 | 1 |
| AT_LEAST_ONCE | Qos level 1 | 2 |
| EXACTLY_ONCE | Qos level 2 | 3 |



## Referenced messages from integration_slack.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [integration_slack.proto](https://github.com/HiberGlobal/api/blob/master/integration_slack.proto).


### hiber.integration.slack.CreateSlackPublisherRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| description | [ string](#string) |  |
|  **optional** filter_event_types | [optional hiber.Filter.Events](#hiberfilterevents) |  |
|  **optional** filter_modem_numbers | [optional hiber.Filter.Modems](#hiberfiltermodems) |  |
|  **optional** filter_tags | [optional hiber.Filter.Tags](#hiberfiltertags) |  |
| filter_health_levels | [repeated string](#string) | Filter events by health level caused. |
| url | [ string](#string) |  |
|  **optional** channel | [optional string](#string) |  |
|  **optional** disabled | [optional bool](#bool) |  |
| tags | [repeated int64](#int64) |  |

### hiber.integration.slack.DeleteSlackPublisherRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| id | [ int64](#int64) |  |

### hiber.integration.slack.DeleteSlackPublisherRequest.Response




### hiber.integration.slack.DisableSlackPublisherRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.integration.slack.SlackPublisherSelection](#hiberintegrationslackslackpublisherselection) |  |

### hiber.integration.slack.DisableSlackPublisherRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| publishers | [repeated hiber.integration.slack.SlackPublisher](#hiberintegrationslackslackpublisher) |  |
| request | [ hiber.integration.slack.DisableSlackPublisherRequest](#hiberintegrationslackdisableslackpublisherrequest) |  |

### hiber.integration.slack.EnableSlackPublisherRequest

Enable a disabled publisher or re-enable a publisher that's failed and is in cooldown.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.integration.slack.SlackPublisherSelection](#hiberintegrationslackslackpublisherselection) |  |

### hiber.integration.slack.EnableSlackPublisherRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| publishers | [repeated hiber.integration.slack.SlackPublisher](#hiberintegrationslackslackpublisher) |  |
| request | [ hiber.integration.slack.EnableSlackPublisherRequest](#hiberintegrationslackenableslackpublisherrequest) |  |

### hiber.integration.slack.ListSlackPublishersRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional hiber.integration.slack.SlackPublisherSelection](#hiberintegrationslackslackpublisherselection) |  |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |
| sort | [repeated hiber.integration.slack.ListSlackPublishersRequest.Sort](#hiberintegrationslacklistslackpublishersrequestsort) |  |

### hiber.integration.slack.ListSlackPublishersRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| publishers | [repeated hiber.integration.slack.SlackPublisher](#hiberintegrationslackslackpublisher) |  |
| request | [ hiber.integration.slack.ListSlackPublishersRequest](#hiberintegrationslacklistslackpublishersrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### hiber.integration.slack.SlackMessage



| Field | Type | Description |
| ----- | ---- | ----------- |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| publisher_data | [ hiber.integration.slack.SlackPublisher.Data](#hiberintegrationslackslackpublisherdata) |  |
| message | [ hiber.BytesOrHex](#hiberbytesorhex) |  |
| successful | [ bool](#bool) |  |
| error | [ string](#string) |  |

### hiber.integration.slack.SlackPublisher



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) |  |
| description | [ string](#string) |  |
| created_by | [ string](#string) | The uid of the user that created this publisher |
| data | [ hiber.integration.slack.SlackPublisher.Data](#hiberintegrationslackslackpublisherdata) |  |
| filter_event_types | [ hiber.Filter.Events](#hiberfilterevents) |  |
| filter_modem_numbers | [ hiber.Filter.Modems](#hiberfiltermodems) |  |
| filter_tags | [ hiber.Filter.Tags](#hiberfiltertags) |  |
| filter_health_levels | [repeated string](#string) | Filter events by health level caused. |
| health | [ hiber.Health](#hiberhealth) |  |
| health_config | [ hiber.integration.slack.SlackPublisher.HealthConfig](#hiberintegrationslackslackpublisherhealthconfig) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |

### hiber.integration.slack.SlackPublisher.Data



| Field | Type | Description |
| ----- | ---- | ----------- |
| url | [ string](#string) | The slack webhook URL. See https://api.slack.com/messaging/webhooks for information on Slack webhooks. |
| channel | [ string](#string) | The channel the webhook is configured to send to. This is used purely for display purposes, since Slack webhooks are bound to a single channel. |
| disabled | [ bool](#bool) |  |

### hiber.integration.slack.SlackPublisher.HealthConfig

Health configuration for the slack integration. Defines how the health is calculated.

| Field | Type | Description |
| ----- | ---- | ----------- |
| health_warning_period | [ hiber.Duration](#hiberduration) | Period to consider when determining health from warning events. Warning events cannot be resolved. |
| health_warning_failure_percentage | [ int32](#int32) | Allowed percentage of failures. If the failure percentage is higher, within the warning period, the health is switched to WARNING. |

### hiber.integration.slack.SlackPublisherHistoryRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| id | [ int64](#int64) |  |
|  **optional** selection | [optional hiber.integration.slack.SlackPublisherHistorySelection](#hiberintegrationslackslackpublisherhistoryselection) |  |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |

### hiber.integration.slack.SlackPublisherHistoryRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| items | [repeated hiber.integration.slack.SlackMessage](#hiberintegrationslackslackmessage) |  |
| request | [ hiber.integration.slack.SlackPublisherHistoryRequest](#hiberintegrationslackslackpublisherhistoryrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### hiber.integration.slack.SlackPublisherHistorySelection



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** time_range | [optional hiber.TimeRange](#hibertimerange) |  |
|  **optional** only_failures | [optional bool](#bool) |  |

### hiber.integration.slack.SlackPublisherSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** publishers | [optional hiber.Filter.Publishers](#hiberfilterpublishers) | Filter by id. |
|  **optional** description | [optional string](#string) | Partial text match on the description. |
|  **optional** search_url | [optional string](#string) | Partial text match on the url. |
|  **optional** search_channel | [optional string](#string) | Partial text match on the channel. |
|  **optional** tags | [optional hiber.tag.TagSelection](#hibertagtagselection) |  |
| health | [repeated hiber.Health](#hiberhealth) |  |
|  **optional** search | [optional string](#string) | Search in the all available text, like description and url. |

### hiber.integration.slack.UpdateSlackPublisherRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| id | [ int64](#int64) |  |
|  **optional** deprecated_filter_event_types | [optional hiber.Filter.Events.Update](#hiberfiltereventsupdate) | <strong>Deprecated.</strong>  |
|  **optional** filter_event_types | [optional hiber.Filter.Events](#hiberfilterevents) |  |
|  **optional** deprecated_filter_modem_numbers | [optional hiber.Filter.Modems.Update](#hiberfiltermodemsupdate) | <strong>Deprecated.</strong>  |
|  **optional** filter_modem_numbers | [optional hiber.Filter.Modems](#hiberfiltermodems) |  |
|  **optional** deprecated_filter_tags | [optional hiber.Filter.Tags.Update](#hiberfiltertagsupdate) | <strong>Deprecated.</strong>  |
|  **optional** filter_tags | [optional hiber.Filter.Tags](#hiberfiltertags) |  |
| add_health_levels_to_filter | [repeated string](#string) | Add health levels to the health levels filter. |
| remove_health_levels_from_filter | [repeated string](#string) | Remove health levels from the health levels filter. |
|  **optional** description | [optional string](#string) |  |
|  **optional** deprecated_description | [optional hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
|  **optional** url | [optional string](#string) |  |
|  **optional** channel | [optional string](#string) |  |
|  **optional** deprecated_channel | [optional hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
|  **optional** active | [optional bool](#bool) |  |
|  **optional** deprecated_active | [optional hiber.UpdateBoolean](#hiberupdateboolean) | <strong>Deprecated.</strong>  |
|  **optional** health_warning_period | [optional hiber.Duration](#hiberduration) | Period to consider when determining health from warning events. Warning events cannot be resolved. Set this to 0 to disable warnings based on failure percentage. |
|  **optional** health_warning_failure_percentage | [optional uint32](#uint32) | Allowed percentage of call failures. If the failure percentage is higher, within the warning period, the health is switched to WARNING. |
|  **optional** deprecated_health_warning_failure_percentage | [optional hiber.UpdateZeroableInt](#hiberupdatezeroableint) | <strong>Deprecated.</strong>  |

### hiber.integration.slack.UpdateSlackPublisherTagsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) |  |
| selection | [ hiber.integration.slack.SlackPublisherSelection](#hiberintegrationslackslackpublisherselection) |  |
| update | [ hiber.tag.UpdateTagsForItem](#hibertagupdatetagsforitem) |  |

### hiber.integration.slack.UpdateSlackPublisherTagsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| slack_publishers | [repeated hiber.integration.slack.SlackPublisher](#hiberintegrationslackslackpublisher) |  |


### Enums
#### hiber.integration.slack.ListSlackPublishersRequest.Sort


| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | Sort by id. | 0 |
| ID_DESC | Sort by id, high to low. | 1 |
| DESCRIPTION | Sort by description. | 2 |
| DESCRIPTION_DESC | Sort by description, z to a. | 3 |
| URL | Sort by url. | 4 |
| URL_DESC | Sort by url, z to a. | 5 |
| CHANNEL | Sort by channel. | 6 |
| CHANNEL_DESC | Sort by channel, z to a. | 7 |
| HEALTH | Sort unhealthy webhooks before health webhooks. | 8 |



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
|  **optional** filter | [optional hiber.Filter.Tags](#hiberfiltertags) |  |
| types | [repeated string](#string) |  |


### Enums


## Referenced messages from webhook.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [webhook.proto](https://github.com/HiberGlobal/api/blob/master/webhook.proto).


### hiber.webhook.CreateWebhookRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| description | [ string](#string) |  |
| data | [ hiber.webhook.Webhook.WebhookData](#hiberwebhookwebhookwebhookdata) |  |
|  **optional** filters | [optional hiber.webhook.Webhook.WebhookFilters](#hiberwebhookwebhookwebhookfilters) |  |
| health_levels | [repeated string](#string) | Filter events by health level caused. |
| tags | [repeated int64](#int64) |  |
|  **optional** certificate_id | [optional int64](#int64) | Optionally, a client certificate can be used for the webhook call. See the CertificateService for certificate management options. |

### hiber.webhook.DeleteWebhookRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) |  |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |

### hiber.webhook.DeleteWebhookRequest.Response




### hiber.webhook.DisableWebhookRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) |  |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |

### hiber.webhook.EnableWebhookRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) |  |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |

### hiber.webhook.GetWebhookRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) |  |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |

### hiber.webhook.ListWebhooksRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional hiber.webhook.WebhookSelection](#hiberwebhookwebhookselection) | Select the webhooks to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |
| sort | [repeated hiber.webhook.ListWebhooksRequest.Sort](#hiberwebhooklistwebhooksrequestsort) |  |

### hiber.webhook.ListWebhooksRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| webhooks | [repeated hiber.webhook.Webhook](#hiberwebhookwebhook) |  |
| request | [ hiber.webhook.ListWebhooksRequest](#hiberwebhooklistwebhooksrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### hiber.webhook.UpdateWebhookFilterRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) |  |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** deprecated_event_filter | [optional hiber.Filter.Events.Update](#hiberfiltereventsupdate) | <strong>Deprecated.</strong>  |
|  **optional** event_filter | [optional hiber.Filter.Events](#hiberfilterevents) |  |
|  **optional** deprecated_modem_filter | [optional hiber.Filter.Modems.Update](#hiberfiltermodemsupdate) | <strong>Deprecated.</strong>  |
|  **optional** modem_filter | [optional hiber.Filter.Modems](#hiberfiltermodems) |  |
|  **optional** deprecated_tag_filter | [optional hiber.Filter.Tags.Update](#hiberfiltertagsupdate) | <strong>Deprecated.</strong>  |
|  **optional** tag_filter | [optional hiber.Filter.Tags](#hiberfiltertags) |  |
| add_health_levels_to_filter | [repeated string](#string) | Add health levels to the health levels filter. |
| remove_health_levels_from_filter | [repeated string](#string) | Remove health levels from the health levels filter. |

### hiber.webhook.UpdateWebhookRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) |  |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| update | [ hiber.webhook.UpdateWebhookRequest.UpdateWebhook](#hiberwebhookupdatewebhookrequestupdatewebhook) |  |

### hiber.webhook.UpdateWebhookRequest.UpdateWebhook



| Field | Type | Description |
| ----- | ---- | ----------- |
| url | [ string](#string) |  |
|  **optional** deprecated_secret | [optional hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
|  **optional** secret | [optional string](#string) |  |
|  **optional** content_type | [optional hiber.webhook.Webhook.ContentType](#hiberwebhookwebhookcontenttype) |  |
|  **optional** deprecated_description | [optional hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
|  **optional** description | [optional string](#string) |  |
|  **optional** deprecated_event_filter | [optional hiber.Filter.Events.Update](#hiberfiltereventsupdate) | <strong>Deprecated.</strong>  |
|  **optional** event_filter | [optional hiber.Filter.Events](#hiberfilterevents) |  |
|  **optional** deprecated_modem_filter | [optional hiber.Filter.Modems.Update](#hiberfiltermodemsupdate) | <strong>Deprecated.</strong>  |
|  **optional** modem_filter | [optional hiber.Filter.Modems](#hiberfiltermodems) |  |
|  **optional** deprecated_tag_filter | [optional hiber.Filter.Tags.Update](#hiberfiltertagsupdate) | <strong>Deprecated.</strong>  |
|  **optional** tag_filter | [optional hiber.Filter.Tags](#hiberfiltertags) |  |
| add_health_levels | [repeated string](#string) | Add health levels to the health levels filter. |
| remove_health_levels | [repeated string](#string) | Remove health levels from the health levels filter. |
|  **optional** deprecated_active | [optional hiber.UpdateBoolean](#hiberupdateboolean) | <strong>Deprecated.</strong>  |
|  **optional** active | [optional bool](#bool) |  |
|  **optional** deprecated_certificate_id | [optional hiber.UpdateOptionalId](#hiberupdateoptionalid) | <strong>Deprecated.</strong> A value of 0 removes the certificate |
|  **optional** certificate_id | [optional int64](#int64) |  |
|  **optional** health_warning_period | [optional hiber.Duration](#hiberduration) | Period to consider when determining health from warning events. Warning events cannot be resolved. Set this to 0 to disable warnings based on failure percentage. |
|  **optional** health_warning_failure_percentage | [optional uint32](#uint32) | Allowed percentage of call failures. If the failure percentage is higher, within the warning period, the health is switched to WARNING. |
|  **optional** deprecated_health_warning_failure_percentage | [optional hiber.UpdateZeroableInt](#hiberupdatezeroableint) | <strong>Deprecated.</strong>  |
|  **optional** update_hmac_header_name | [optional string](#string) | Update the custom hmac header, or clear to reset to default. |
|  **optional** deprecated_update_hmac_header_name | [optional hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
| add_custom_headers | [map hiber.webhook.UpdateWebhookRequest.UpdateWebhook.AddCustomHeadersEntry](#hiberwebhookupdatewebhookrequestupdatewebhookaddcustomheadersentry) | Custom headers to add to every call. |
| remove_custom_headers | [repeated string](#string) | Remove previously configured custom headers. |
| replace_custom_headers | [map hiber.webhook.UpdateWebhookRequest.UpdateWebhook.ReplaceCustomHeadersEntry](#hiberwebhookupdatewebhookrequestupdatewebhookreplacecustomheadersentry) | Replace the custom headers to add to every call. If set, remove_custom_headers is ignored. |

### hiber.webhook.UpdateWebhookRequest.UpdateWebhook.AddCustomHeadersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ string](#string) |  |

### hiber.webhook.UpdateWebhookRequest.UpdateWebhook.ReplaceCustomHeadersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ string](#string) |  |

### hiber.webhook.UpdateWebhookRequest.UpdateWebhook.UpdateEvents

<strong>Deprecated.</strong> 

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.Filter.Events](#hiberfilterevents) |  |

### hiber.webhook.UpdateWebhookRequest.UpdateWebhook.UpdateModems

<strong>Deprecated.</strong> 

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.Filter.Modems](#hiberfiltermodems) |  |

### hiber.webhook.UpdateWebhookRequest.UpdateWebhook.UpdateTags

<strong>Deprecated.</strong> 

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.Filter.Tags](#hiberfiltertags) |  |

### hiber.webhook.UpdateWebhookTagsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) |  |
| webhook_ids | [repeated int64](#int64) |  |
| update | [ hiber.tag.UpdateTagsForItem](#hibertagupdatetagsforitem) |  |

### hiber.webhook.UpdateWebhookTagsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| webhooks | [repeated hiber.webhook.Webhook](#hiberwebhookwebhook) |  |

### hiber.webhook.UpdateWebhooksRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| webhook_updates | [repeated hiber.webhook.UpdateWebhooksRequest.Update](#hiberwebhookupdatewebhooksrequestupdate) |  |

### hiber.webhook.UpdateWebhooksRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| webhooks | [repeated hiber.webhook.Webhook](#hiberwebhookwebhook) |  |
| request | [ hiber.webhook.UpdateWebhooksRequest](#hiberwebhookupdatewebhooksrequest) |  |

### hiber.webhook.UpdateWebhooksRequest.Update



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) |  |
| update | [ hiber.webhook.UpdateWebhookRequest.UpdateWebhook](#hiberwebhookupdatewebhookrequestupdatewebhook) |  |

### hiber.webhook.Webhook

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
| data | [ hiber.webhook.Webhook.WebhookData](#hiberwebhookwebhookwebhookdata) |  |
| filters | [ hiber.webhook.Webhook.WebhookFilters](#hiberwebhookwebhookwebhookfilters) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| health | [ hiber.Health](#hiberhealth) |  |
| health_config | [ hiber.webhook.Webhook.HealthConfig](#hiberwebhookwebhookhealthconfig) |  |
| in_cooldown_until | [ hiber.Timestamp](#hibertimestamp) | The time the cooldown ends. |

### hiber.webhook.Webhook.HealthConfig

Health configuration for the webhook. Defines how the health is calculated.

| Field | Type | Description |
| ----- | ---- | ----------- |
| health_warning_period | [ hiber.Duration](#hiberduration) | Period to consider when determining health from warning events. Warning events cannot be resolved. |
| health_warning_failure_percentage | [ int32](#int32) | Allowed percentage of failures. If the failure percentage is higher, within the warning period, the health is switched to WARNING. |

### hiber.webhook.Webhook.WebhookData



| Field | Type | Description |
| ----- | ---- | ----------- |
| url | [ string](#string) |  |
|  **optional** secret | [optional string](#string) | Used to generate the HMAC-SHA256 header on every webhook call, which you can use to verify the message. The HMAC-SHA256 header is calculated with the message body and this secret. There are many examples of how to do this in different languages, for example: https://github.com/danharper/hmac-examples |
| hmac_header_name | [ string](#string) | The header that the hmac value is placed in. Defaults to X-Hub-Signature. |
| content_type | [ hiber.webhook.Webhook.ContentType](#hiberwebhookwebhookcontenttype) |  |
| disabled | [ bool](#bool) |  |
|  **optional** certificate_id | [optional int64](#int64) |  |
|  **optional** certificate_name | [optional string](#string) |  |
|  **optional** ca_certificate_id | [optional int64](#int64) |  |
|  **optional** ca_certificate_name | [optional string](#string) |  |
| custom_headers | [map hiber.webhook.Webhook.WebhookData.CustomHeadersEntry](#hiberwebhookwebhookwebhookdatacustomheadersentry) | Custom headers to add to every call. |

### hiber.webhook.Webhook.WebhookData.CustomHeadersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ string](#string) |  |

### hiber.webhook.Webhook.WebhookFilters



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** event_types | [optional hiber.Filter.Events](#hiberfilterevents) |  |
|  **optional** modem_numbers | [optional hiber.Filter.Modems](#hiberfiltermodems) |  |
|  **optional** tags | [optional hiber.Filter.Tags](#hiberfiltertags) |  |
| health_levels | [repeated string](#string) | Filter events by health level caused. |

### hiber.webhook.WebhookCall



| Field | Type | Description |
| ----- | ---- | ----------- |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| url | [ string](#string) |  |
| headers | [map hiber.webhook.WebhookCall.HeadersEntry](#hiberwebhookwebhookcallheadersentry) |  |
| body_proto | [ bytes](#bytes) |  |
| body_json | [ string](#string) |  |
| successful | [ bool](#bool) |  |
| error | [ string](#string) |  |

### hiber.webhook.WebhookCall.HeadersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ string](#string) |  |

### hiber.webhook.WebhookHistoryRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| webhook_id | [ int64](#int64) |  |
|  **optional** selection | [optional hiber.webhook.WebhookHistorySelection](#hiberwebhookwebhookhistoryselection) |  |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |

### hiber.webhook.WebhookHistoryRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| calls | [repeated hiber.webhook.WebhookCall](#hiberwebhookwebhookcall) |  |
| request | [ hiber.webhook.WebhookHistoryRequest](#hiberwebhookwebhookhistoryrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### hiber.webhook.WebhookHistorySelection



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** only_failures | [optional bool](#bool) |  |
|  **optional** time_range | [optional hiber.TimeRange](#hibertimerange) |  |

### hiber.webhook.WebhookSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** description | [optional string](#string) |  |
|  **optional** url | [optional string](#string) |  |
|  **optional** webhooks | [optional hiber.Filter.Webhooks](#hiberfilterwebhooks) |  |
|  **optional** tags | [optional hiber.tag.TagSelection](#hibertagtagselection) |  |
| health | [repeated hiber.Health](#hiberhealth) |  |
| certificate_ids | [repeated int64](#int64) |  |
|  **optional** search | [optional string](#string) | Search in the all available text, like description and url. |


### Enums
#### hiber.webhook.ListWebhooksRequest.Sort


| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | Sort by id. | 0 |
| ID_DESC | Sort by id, high to low. | 1 |
| DESCRIPTION | Sort by description. | 2 |
| DESCRIPTION_DESC | Sort by description, z to a. | 3 |
| URL | Sort by url. | 4 |
| URL_DESC | Sort by url, z to a. | 5 |
| HEALTH | Sort unhealthy webhooks before health webhooks. | 6 |

#### hiber.webhook.Webhook.ContentType


| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT |  | 0 |
| JSON |  | 1 |
| PROTO |  | 2 |



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
The textual field has the commonly used ISO 8601 local date format (i.e. "2018-01-01").
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
| ASSET_UPDATED | An asset in your organization was updated (i.e. renamed, tagged). | 71 |
| ASSET_DELETED | An asset in your organization was deleted. | 72 |
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

