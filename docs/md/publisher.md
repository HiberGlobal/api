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
  - [hiber.webhook.UpdateWebhookFilterRequest.UpdateEvents](#hiberwebhookupdatewebhookfilterrequestupdateevents)
  - [hiber.webhook.UpdateWebhookFilterRequest.UpdateModems](#hiberwebhookupdatewebhookfilterrequestupdatemodems)
  - [hiber.webhook.UpdateWebhookFilterRequest.UpdateTags](#hiberwebhookupdatewebhookfilterrequestupdatetags)
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
| id | [ int64](#int64) | none |
| description | [ string](#string) | none |
| deprecated_data | [ Publisher.Data](#publisherdata) | This field remains for backwards compatibility, but it should not be used. |
| filters | [ Publisher.Filters](#publisherfilters) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| health | [ hiber.Health](#hiberhealth) | none |
| type | [ Publisher.Type](#publishertype) | none |
| in_cooldown_until | [ hiber.Timestamp](#hibertimestamp) | none |
| disabled | [ bool](#bool) | none |
| created_by | [ string](#string) | Firebase uid of the user that created this publisher |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.http | [ hiber.webhook.Webhook.WebhookData](#hiberwebhookwebhookwebhookdata) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.mqtt | [ hiber.integration.mqtt.MQTTPublisher.Data](#hiberintegrationmqttmqttpublisherdata) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.email | [ hiber.email.EmailNotificationPreferences](#hiberemailemailnotificationpreferences) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.slack | [ hiber.integration.slack.SlackPublisher.Data](#hiberintegrationslackslackpublisherdata) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.shell_ssip | [ Publisher.Data.ShellSsipConfig](#publisherdatashellssipconfig) | none |

### Publisher.Data

This type remains for backwards compatibility, but it should not be used.

| Field | Type | Description |
| ----- | ---- | ----------- |
| url | [ string](#string) | none |
| content_type | [ Publisher.ContentType](#publishercontenttype) | none |
| disabled | [ bool](#bool) | none |
| certificate_id | [ int64](#int64) | none |
| certificate_name | [ string](#string) | none |
| ca_certificate_id | [ int64](#int64) | none |
| ca_certificate_name | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **config**.http | [ Publisher.Data.HTTPConfig](#publisherdatahttpconfig) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **config**.mqtt | [ Publisher.Data.MQTTConfig](#publisherdatamqttconfig) | none |

### Publisher.Data.HTTPConfig

This field remains for backwards compatibility, but it should not be used.

| Field | Type | Description |
| ----- | ---- | ----------- |
| secret | [ string](#string) | Used to generate the HMAC-SHA256 header on every publisher call, which you can use to verify the message. The HMAC-SHA256 header is calculated with the message body and this secret. There are many examples of how to do this in different languages, for example: https://github.com/danharper/hmac-examples |

### Publisher.Data.MQTTConfig

This field remains for backwards compatibility, but it should not be used.

| Field | Type | Description |
| ----- | ---- | ----------- |
| topic | [ string](#string) | none |
| qos | [ Publisher.Data.MQTTConfig.QoS](#publisherdatamqttconfigqos) | none |
| username | [ string](#string) | Optional username to authenticate with. |
| password | [ string](#string) | Optional password to authenticate with. Requires username to be set. |
| identifier | [ string](#string) | Identifier used by the MQTT client. Defaults to "hiber". |

### Publisher.Data.ShellSsipConfig



| Field | Type | Description |
| ----- | ---- | ----------- |
| url | [ string](#string) | none |
| tenant_id | [ string](#string) | none |
| resource_id | [ string](#string) | none |

### Publisher.Filters



| Field | Type | Description |
| ----- | ---- | ----------- |
| event_types | [ hiber.Filter.Events](#hiberfilterevents) | none |
| modem_numbers | [ hiber.Filter.Modems](#hiberfiltermodems) | none |
| tags | [ hiber.Filter.Tags](#hiberfiltertags) | none |

### UpdatePublisherRequest




### UpdatePublisherRequest.UpdateModems



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ hiber.Filter.Modems](#hiberfiltermodems) | none |


## Enums
### Publisher.ContentType
This type remains for backwards compatibility, but it should not be used.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | none | 0 |
| JSON | none | 1 |
| PROTO | none | 2 |

### Publisher.Data.MQTTConfig.QoS


| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | none | 0 |
| AT_MOST_ONCE | Qos level 0 | 1 |
| AT_LEAST_ONCE | Qos level 1 | 2 |
| EXACTLY_ONCE | Qos level 2 | 3 |

### Publisher.Type


| Name | Description | Number |
| ---- | ----------- | ------ |
| HTTP | none | 0 |
| MQTT | none | 1 |
| EMAIL | none | 3 |
| SLACK | none | 4 |
| SHELL_SSIP | none | 5 |



## Referenced messages from email_notifications.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [email_notifications.proto](https://github.com/HiberGlobal/api/blob/master/email_notifications.proto).


### hiber.email.EmailHistorySelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| time_range | [ hiber.TimeRange](#hibertimerange) | none |
| only_failures | [ bool](#bool) | none |

### hiber.email.EmailNotificationHistoryRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| custom | [ hiber.email.EmailNotificationPreferences.CustomRecipient](#hiberemailemailnotificationpreferencescustomrecipient) | Custom email address preferences to get the history for. If not set, your email is used. |
| selection | [ hiber.email.EmailHistorySelection](#hiberemailemailhistoryselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |

### hiber.email.EmailNotificationHistoryRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| emails | [repeated hiber.email.EmailNotificationHistoryRequest.Response.Email](#hiberemailemailnotificationhistoryrequestresponseemail) | none |
| request | [ hiber.email.EmailNotificationHistoryRequest](#hiberemailemailnotificationhistoryrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### hiber.email.EmailNotificationHistoryRequest.Response.Email



| Field | Type | Description |
| ----- | ---- | ----------- |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| title | [ string](#string) | none |
| successful | [ bool](#bool) | none |
| error | [ string](#string) | none |

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
| email | [ string](#string) | none |
| name | [ string](#string) | none |

### hiber.email.ListEmailNotificationPreferencesRequest

List the custom recipients and their preferences. Optionally, personal email preferences can be included.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| search_email | [ string](#string) | Search for a (partial) custom email address. |
| include_personal_email_preferences | [ bool](#bool) | By default, this request only returns the email preferences for custom emails, but you can choose to view user-specific preferences as well. |
| pagination | [ hiber.Pagination](#hiberpagination) | none |

### hiber.email.ListEmailNotificationPreferencesRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| email_preferences | [repeated hiber.email.EmailNotificationPreferences](#hiberemailemailnotificationpreferences) | none |
| request | [ hiber.email.ListEmailNotificationPreferencesRequest](#hiberemaillistemailnotificationpreferencesrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### hiber.email.RemoveAllEmailNotificationPreferencesRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| custom | [ hiber.email.EmailNotificationPreferences.CustomRecipient](#hiberemailemailnotificationpreferencescustomrecipient) | Custom email address preferences to disable. |

### hiber.email.RemoveAllEmailNotificationPreferencesRequest.Response




### hiber.email.UpdateEmailNotificationPreferencesRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| custom | [ hiber.email.EmailNotificationPreferences.CustomRecipient](#hiberemailemailnotificationpreferencescustomrecipient) | Custom email address. Only set this if you want to send notification to an email address not associated with your user. |
| enabled_notifications | [ hiber.Filter.Events.Update](#hiberfiltereventsupdate) | Events to receive by email. An empty value enables email for all events. |
| filter_modems | [ hiber.Filter.Modems.Update](#hiberfiltermodemsupdate) | Filter events by modems. An empty value enables email for every modem's events. |
| filter_tags | [ hiber.Filter.Tags.Update](#hiberfiltertagsupdate) | Filter events by tags. An empty value enables email for all tags. |
| add_health_levels_to_filter | [repeated string](#string) | Add health levels to the health levels filter. |
| remove_health_levels_from_filter | [repeated string](#string) | Remove health levels from the health levels filter. |

### hiber.email.ViewEmailNotificationPreferencesRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| email | [ string](#string) | View the configuration for any email publisher with a custom email address. Optional, should only be used if you want to get the email preferences for a custom recipient. When not set, your personal email preferences are returned. |


### Enums


## Referenced messages from integration_mqtt.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [integration_mqtt.proto](https://github.com/HiberGlobal/api/blob/master/integration_mqtt.proto).


### hiber.integration.mqtt.CreateMQTTPublisherRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| description | [ string](#string) | none |
| filter_event_types | [ hiber.Filter.Events](#hiberfilterevents) | none |
| filter_modem_numbers | [ hiber.Filter.Modems](#hiberfiltermodems) | none |
| filter_tags | [ hiber.Filter.Tags](#hiberfiltertags) | none |
| url | [ string](#string) | The url of an MQTT server to send the events to, i.e. mqtt[s]://example.com:8883 |
| content_type | [ hiber.integration.mqtt.MQTTPublisher.ContentType](#hiberintegrationmqttmqttpublishercontenttype) | none |
| topic | [ string](#string) | The MQTT topic to send to on the receiving server. |
| qos | [ hiber.integration.mqtt.MQTTPublisher.Data.QoS](#hiberintegrationmqttmqttpublisherdataqos) | MQTT QoS value. |
| identifier | [ string](#string) | Identifier used by the MQTT client. Defaults to "hiber". |
| username | [ string](#string) | Optional username to authenticate with. |
| password | [ string](#string) | Optional password to authenticate with. Requires username to be set. |
| certificate_id | [ int64](#int64) | Client certificate to use when connecting to the MQTT server. |
| server_ca_certificate_id | [ int64](#int64) | Server CA certificate to use when connecting to the MQTT server. |
| disabled | [ bool](#bool) | Disable the MQTT publisher after creation, so it needs to be enabled before it is active. |
| tags | [repeated int64](#int64) | none |

### hiber.integration.mqtt.DeleteMQTTPublisherRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| id | [ int64](#int64) | none |

### hiber.integration.mqtt.DeleteMQTTPublisherRequest.Response




### hiber.integration.mqtt.DisableMQTTPublisherRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.integration.mqtt.MQTTPublisherSelection](#hiberintegrationmqttmqttpublisherselection) | none |

### hiber.integration.mqtt.DisableMQTTPublisherRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| publishers | [repeated hiber.integration.mqtt.MQTTPublisher](#hiberintegrationmqttmqttpublisher) | none |
| request | [ hiber.integration.mqtt.DisableMQTTPublisherRequest](#hiberintegrationmqttdisablemqttpublisherrequest) | none |

### hiber.integration.mqtt.EnableMQTTPublisherRequest

Enable a disabled publisher or re-enable a publisher that's failed and is in cooldown.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.integration.mqtt.MQTTPublisherSelection](#hiberintegrationmqttmqttpublisherselection) | none |

### hiber.integration.mqtt.EnableMQTTPublisherRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| publishers | [repeated hiber.integration.mqtt.MQTTPublisher](#hiberintegrationmqttmqttpublisher) | none |
| request | [ hiber.integration.mqtt.EnableMQTTPublisherRequest](#hiberintegrationmqttenablemqttpublisherrequest) | none |

### hiber.integration.mqtt.ListMQTTPublishersRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.integration.mqtt.MQTTPublisherSelection](#hiberintegrationmqttmqttpublisherselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |
| sort | [repeated hiber.integration.mqtt.ListMQTTPublishersRequest.Sort](#hiberintegrationmqttlistmqttpublishersrequestsort) | none |

### hiber.integration.mqtt.ListMQTTPublishersRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| publishers | [repeated hiber.integration.mqtt.MQTTPublisher](#hiberintegrationmqttmqttpublisher) | none |
| request | [ hiber.integration.mqtt.ListMQTTPublishersRequest](#hiberintegrationmqttlistmqttpublishersrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### hiber.integration.mqtt.MQTTMessage



| Field | Type | Description |
| ----- | ---- | ----------- |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| publisher_data | [ hiber.integration.mqtt.MQTTPublisher.Data](#hiberintegrationmqttmqttpublisherdata) | none |
| message | [ hiber.BytesOrHex](#hiberbytesorhex) | none |
| successful | [ bool](#bool) | none |
| error | [ string](#string) | none |

### hiber.integration.mqtt.MQTTPublisher



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) | none |
| description | [ string](#string) | none |
| created_by | [ string](#string) | The uid of the user that created this publisher |
| data | [ hiber.integration.mqtt.MQTTPublisher.Data](#hiberintegrationmqttmqttpublisherdata) | none |
| filter_event_types | [ hiber.Filter.Events](#hiberfilterevents) | none |
| filter_modem_numbers | [ hiber.Filter.Modems](#hiberfiltermodems) | none |
| filter_tags | [ hiber.Filter.Tags](#hiberfiltertags) | none |
| health | [ hiber.Health](#hiberhealth) | none |
| health_config | [ hiber.integration.mqtt.MQTTPublisher.HealthConfig](#hiberintegrationmqttmqttpublisherhealthconfig) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |

### hiber.integration.mqtt.MQTTPublisher.Data



| Field | Type | Description |
| ----- | ---- | ----------- |
| url | [ string](#string) | The url of an MQTT server to send the events to, i.e. mqtt[s]://example.com:8883 |
| content_type | [ hiber.integration.mqtt.MQTTPublisher.ContentType](#hiberintegrationmqttmqttpublishercontenttype) | none |
| topic | [ string](#string) | The MQTT topic to send to on the receiving server. |
| qos | [ hiber.integration.mqtt.MQTTPublisher.Data.QoS](#hiberintegrationmqttmqttpublisherdataqos) | MQTT QoS value. |
| identifier | [ string](#string) | Identifier used by the MQTT client. Defaults to "hiber". |
| username | [ string](#string) | Optional username to authenticate with. |
| password | [ string](#string) | Optional password to authenticate with. Requires username to be set. |
| certificate_id | [ int64](#int64) | Client certificate to use when connecting to the MQTT server. |
| certificate_name | [ string](#string) | none |
| ca_certificate_id | [ int64](#int64) | CA certificate for the client certificate to use when connecting to the MQTT server. |
| ca_certificate_name | [ string](#string) | none |
| server_ca_certificate_id | [ int64](#int64) | Server CA certificate to use when connecting to the MQTT server. |
| server_ca_certificate_name | [ string](#string) | none |
| disabled | [ bool](#bool) | none |

### hiber.integration.mqtt.MQTTPublisher.HealthConfig

Health configuration for the mqtt integration. Defines how the health is calculated.

| Field | Type | Description |
| ----- | ---- | ----------- |
| health_warning_period | [ hiber.Duration](#hiberduration) | Period to consider when determining health from warning events. Warning events cannot be resolved. |
| health_warning_failure_percentage | [ int32](#int32) | Allowed percentage of failures. If the failure percentage is higher, within the warning period, the health is switched to WARNING. |

### hiber.integration.mqtt.MQTTPublisherHistoryRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| id | [ int64](#int64) | none |
| selection | [ hiber.integration.mqtt.MQTTPublisherHistorySelection](#hiberintegrationmqttmqttpublisherhistoryselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |

### hiber.integration.mqtt.MQTTPublisherHistoryRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| items | [repeated hiber.integration.mqtt.MQTTMessage](#hiberintegrationmqttmqttmessage) | none |
| request | [ hiber.integration.mqtt.MQTTPublisherHistoryRequest](#hiberintegrationmqttmqttpublisherhistoryrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### hiber.integration.mqtt.MQTTPublisherHistorySelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| time_range | [ hiber.TimeRange](#hibertimerange) | none |
| only_failures | [ bool](#bool) | none |

### hiber.integration.mqtt.MQTTPublisherSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| publishers | [ hiber.Filter.Publishers](#hiberfilterpublishers) | Filter by id. |
| description | [ string](#string) | Partial text match on the description. |
| search_url | [ string](#string) | Partial text match on the url. |
| search_topic | [ string](#string) | Partial text match on the topic. |
| content_types | [repeated hiber.integration.mqtt.MQTTPublisher.ContentType](#hiberintegrationmqttmqttpublishercontenttype) | Only return MQTT integrations that use the given content types. |
| certificate_ids | [repeated int64](#int64) | Filter by referenced certificate (id), either as client or server certificate. |
| tags | [ hiber.tag.TagSelection](#hibertagtagselection) | none |
| health | [repeated hiber.Health](#hiberhealth) | none |

### hiber.integration.mqtt.UpdateMQTTPublisherRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| id | [ int64](#int64) | none |
| filter_event_types | [ hiber.Filter.Events.Update](#hiberfiltereventsupdate) | none |
| filter_modem_numbers | [ hiber.Filter.Modems.Update](#hiberfiltermodemsupdate) | none |
| filter_tags | [ hiber.Filter.Tags.Update](#hiberfiltertagsupdate) | none |
| description | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| url | [ string](#string) | The url of an MQTT server to send the events to, i.e. mqtt[s]://example.com:8883 |
| content_type | [ hiber.integration.mqtt.MQTTPublisher.ContentType](#hiberintegrationmqttmqttpublishercontenttype) | none |
| topic | [ string](#string) | The MQTT topic to send to on the receiving server. |
| qos | [ hiber.integration.mqtt.MQTTPublisher.Data.QoS](#hiberintegrationmqttmqttpublisherdataqos) | MQTT QoS value. |
| identifier | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | Identifier used by the MQTT client. Defaults to "hiber". |
| username | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | Optional username to authenticate with. |
| password | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | Optional password to authenticate with. Requires username to be set. |
| certificate_id | [ hiber.UpdateOptionalId](#hiberupdateoptionalid) | Update or remove the client certificate to use when connecting to the MQTT server. |
| server_ca_certificate_id | [ hiber.UpdateOptionalId](#hiberupdateoptionalid) | Update or remove the server CA certificate to use when connecting to the MQTT server. |
| active | [ hiber.UpdateBoolean](#hiberupdateboolean) | Disable the MQTT publisher, so it needs to be enabled again before it is active. |
| health_warning_period | [ hiber.Duration](#hiberduration) | Period to consider when determining health from warning events. Warning events cannot be resolved. Set this to 0 to disable warnings based on failure percentage. |
| health_warning_failure_percentage | [ hiber.UpdateZeroableInt](#hiberupdatezeroableint) | Allowed percentage of call failures. If the failure percentage is higher, within the warning period, the health is switched to WARNING. |

### hiber.integration.mqtt.UpdateMQTTPublisherTagsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| selection | [ hiber.integration.mqtt.MQTTPublisherSelection](#hiberintegrationmqttmqttpublisherselection) | none |
| update | [ hiber.tag.UpdateTagsForItem](#hibertagupdatetagsforitem) | none |

### hiber.integration.mqtt.UpdateMQTTPublisherTagsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| mqtt_publishers | [repeated hiber.integration.mqtt.MQTTPublisher](#hiberintegrationmqttmqttpublisher) | none |


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
| DEFAULT | none | 0 |
| JSON | none | 1 |
| PROTO | none | 2 |

#### hiber.integration.mqtt.MQTTPublisher.Data.QoS


| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | none | 0 |
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
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| description | [ string](#string) | none |
| filter_event_types | [ hiber.Filter.Events](#hiberfilterevents) | none |
| filter_modem_numbers | [ hiber.Filter.Modems](#hiberfiltermodems) | none |
| filter_tags | [ hiber.Filter.Tags](#hiberfiltertags) | none |
| filter_health_levels | [repeated string](#string) | Filter events by health level caused. |
| url | [ string](#string) | none |
| channel | [ string](#string) | none |
| disabled | [ bool](#bool) | none |
| tags | [repeated int64](#int64) | none |

### hiber.integration.slack.DeleteSlackPublisherRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| id | [ int64](#int64) | none |

### hiber.integration.slack.DeleteSlackPublisherRequest.Response




### hiber.integration.slack.DisableSlackPublisherRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.integration.slack.SlackPublisherSelection](#hiberintegrationslackslackpublisherselection) | none |

### hiber.integration.slack.DisableSlackPublisherRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| publishers | [repeated hiber.integration.slack.SlackPublisher](#hiberintegrationslackslackpublisher) | none |
| request | [ hiber.integration.slack.DisableSlackPublisherRequest](#hiberintegrationslackdisableslackpublisherrequest) | none |

### hiber.integration.slack.EnableSlackPublisherRequest

Enable a disabled publisher or re-enable a publisher that's failed and is in cooldown.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.integration.slack.SlackPublisherSelection](#hiberintegrationslackslackpublisherselection) | none |

### hiber.integration.slack.EnableSlackPublisherRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| publishers | [repeated hiber.integration.slack.SlackPublisher](#hiberintegrationslackslackpublisher) | none |
| request | [ hiber.integration.slack.EnableSlackPublisherRequest](#hiberintegrationslackenableslackpublisherrequest) | none |

### hiber.integration.slack.ListSlackPublishersRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.integration.slack.SlackPublisherSelection](#hiberintegrationslackslackpublisherselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |
| sort | [repeated hiber.integration.slack.ListSlackPublishersRequest.Sort](#hiberintegrationslacklistslackpublishersrequestsort) | none |

### hiber.integration.slack.ListSlackPublishersRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| publishers | [repeated hiber.integration.slack.SlackPublisher](#hiberintegrationslackslackpublisher) | none |
| request | [ hiber.integration.slack.ListSlackPublishersRequest](#hiberintegrationslacklistslackpublishersrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### hiber.integration.slack.SlackMessage



| Field | Type | Description |
| ----- | ---- | ----------- |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| publisher_data | [ hiber.integration.slack.SlackPublisher.Data](#hiberintegrationslackslackpublisherdata) | none |
| message | [ hiber.BytesOrHex](#hiberbytesorhex) | none |
| successful | [ bool](#bool) | none |
| error | [ string](#string) | none |

### hiber.integration.slack.SlackPublisher



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) | none |
| description | [ string](#string) | none |
| created_by | [ string](#string) | The uid of the user that created this publisher |
| data | [ hiber.integration.slack.SlackPublisher.Data](#hiberintegrationslackslackpublisherdata) | none |
| filter_event_types | [ hiber.Filter.Events](#hiberfilterevents) | none |
| filter_modem_numbers | [ hiber.Filter.Modems](#hiberfiltermodems) | none |
| filter_tags | [ hiber.Filter.Tags](#hiberfiltertags) | none |
| filter_health_levels | [repeated string](#string) | Filter events by health level caused. |
| health | [ hiber.Health](#hiberhealth) | none |
| health_config | [ hiber.integration.slack.SlackPublisher.HealthConfig](#hiberintegrationslackslackpublisherhealthconfig) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |

### hiber.integration.slack.SlackPublisher.Data



| Field | Type | Description |
| ----- | ---- | ----------- |
| url | [ string](#string) | The slack webhook URL. See https://api.slack.com/messaging/webhooks for information on Slack webhooks. |
| channel | [ string](#string) | The channel the webhook is configured to send to. This is used purely for display purposes, since Slack webhooks are bound to a single channel. |
| disabled | [ bool](#bool) | none |

### hiber.integration.slack.SlackPublisher.HealthConfig

Health configuration for the slack integration. Defines how the health is calculated.

| Field | Type | Description |
| ----- | ---- | ----------- |
| health_warning_period | [ hiber.Duration](#hiberduration) | Period to consider when determining health from warning events. Warning events cannot be resolved. |
| health_warning_failure_percentage | [ int32](#int32) | Allowed percentage of failures. If the failure percentage is higher, within the warning period, the health is switched to WARNING. |

### hiber.integration.slack.SlackPublisherHistoryRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| id | [ int64](#int64) | none |
| selection | [ hiber.integration.slack.SlackPublisherHistorySelection](#hiberintegrationslackslackpublisherhistoryselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |

### hiber.integration.slack.SlackPublisherHistoryRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| items | [repeated hiber.integration.slack.SlackMessage](#hiberintegrationslackslackmessage) | none |
| request | [ hiber.integration.slack.SlackPublisherHistoryRequest](#hiberintegrationslackslackpublisherhistoryrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### hiber.integration.slack.SlackPublisherHistorySelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| time_range | [ hiber.TimeRange](#hibertimerange) | none |
| only_failures | [ bool](#bool) | none |

### hiber.integration.slack.SlackPublisherSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| publishers | [ hiber.Filter.Publishers](#hiberfilterpublishers) | Filter by id. |
| description | [ string](#string) | Partial text match on the description. |
| search_url | [ string](#string) | Partial text match on the url. |
| search_channel | [ string](#string) | Partial text match on the channel. |
| tags | [ hiber.tag.TagSelection](#hibertagtagselection) | none |
| health | [repeated hiber.Health](#hiberhealth) | none |
| search | [ string](#string) | Search in the all available text, like description and url. |

### hiber.integration.slack.UpdateSlackPublisherRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| id | [ int64](#int64) | none |
| filter_event_types | [ hiber.Filter.Events.Update](#hiberfiltereventsupdate) | none |
| filter_modem_numbers | [ hiber.Filter.Modems.Update](#hiberfiltermodemsupdate) | none |
| filter_tags | [ hiber.Filter.Tags.Update](#hiberfiltertagsupdate) | none |
| add_health_levels_to_filter | [repeated string](#string) | Add health levels to the health levels filter. |
| remove_health_levels_from_filter | [repeated string](#string) | Remove health levels from the health levels filter. |
| description | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| url | [ string](#string) | none |
| channel | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| active | [ hiber.UpdateBoolean](#hiberupdateboolean) | none |
| health_warning_period | [ hiber.Duration](#hiberduration) | Period to consider when determining health from warning events. Warning events cannot be resolved. Set this to 0 to disable warnings based on failure percentage. |
| health_warning_failure_percentage | [ hiber.UpdateZeroableInt](#hiberupdatezeroableint) | Allowed percentage of call failures. If the failure percentage is higher, within the warning period, the health is switched to WARNING. |

### hiber.integration.slack.UpdateSlackPublisherTagsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| selection | [ hiber.integration.slack.SlackPublisherSelection](#hiberintegrationslackslackpublisherselection) | none |
| update | [ hiber.tag.UpdateTagsForItem](#hibertagupdatetagsforitem) | none |

### hiber.integration.slack.UpdateSlackPublisherTagsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| slack_publishers | [repeated hiber.integration.slack.SlackPublisher](#hiberintegrationslackslackpublisher) | none |


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


## Referenced messages from webhook.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [webhook.proto](https://github.com/HiberGlobal/api/blob/master/webhook.proto).


### hiber.webhook.CreateWebhookRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| description | [ string](#string) | none |
| data | [ hiber.webhook.Webhook.WebhookData](#hiberwebhookwebhookwebhookdata) | none |
| filters | [ hiber.webhook.Webhook.WebhookFilters](#hiberwebhookwebhookwebhookfilters) | none |
| health_levels | [repeated string](#string) | Filter events by health level caused. |
| tags | [repeated int64](#int64) | none |
| certificate_id | [ int64](#int64) | Optionally, a client certificate can be used for the webhook call. See the CertificateService for certificate management options. |

### hiber.webhook.DeleteWebhookRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) | none |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |

### hiber.webhook.DeleteWebhookRequest.Response




### hiber.webhook.DisableWebhookRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) | none |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |

### hiber.webhook.EnableWebhookRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) | none |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |

### hiber.webhook.GetWebhookRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) | none |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |

### hiber.webhook.ListWebhooksRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.webhook.WebhookSelection](#hiberwebhookwebhookselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |
| sort | [repeated hiber.webhook.ListWebhooksRequest.Sort](#hiberwebhooklistwebhooksrequestsort) | none |

### hiber.webhook.ListWebhooksRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| webhooks | [repeated hiber.webhook.Webhook](#hiberwebhookwebhook) | none |
| request | [ hiber.webhook.ListWebhooksRequest](#hiberwebhooklistwebhooksrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### hiber.webhook.UpdateWebhookFilterRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) | none |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| deprecated_event_filter | [ hiber.webhook.UpdateWebhookFilterRequest.UpdateEvents](#hiberwebhookupdatewebhookfilterrequestupdateevents) | none |
| deprecated_modem_filter | [ hiber.webhook.UpdateWebhookFilterRequest.UpdateModems](#hiberwebhookupdatewebhookfilterrequestupdatemodems) | none |
| deprecated_tag_filter | [ hiber.webhook.UpdateWebhookFilterRequest.UpdateTags](#hiberwebhookupdatewebhookfilterrequestupdatetags) | none |
| event_filter | [ hiber.Filter.Events.Update](#hiberfiltereventsupdate) | none |
| modem_filter | [ hiber.Filter.Modems.Update](#hiberfiltermodemsupdate) | none |
| tag_filter | [ hiber.Filter.Tags.Update](#hiberfiltertagsupdate) | none |
| add_health_levels_to_filter | [repeated string](#string) | Add health levels to the health levels filter. |
| remove_health_levels_from_filter | [repeated string](#string) | Remove health levels from the health levels filter. |

### hiber.webhook.UpdateWebhookFilterRequest.UpdateEvents



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ hiber.Filter.Events](#hiberfilterevents) | none |

### hiber.webhook.UpdateWebhookFilterRequest.UpdateModems



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ hiber.Filter.Modems](#hiberfiltermodems) | none |

### hiber.webhook.UpdateWebhookFilterRequest.UpdateTags



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ hiber.Filter.Tags](#hiberfiltertags) | none |

### hiber.webhook.UpdateWebhookRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) | none |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| update | [ hiber.webhook.UpdateWebhookRequest.UpdateWebhook](#hiberwebhookupdatewebhookrequestupdatewebhook) | none |

### hiber.webhook.UpdateWebhookRequest.UpdateWebhook



| Field | Type | Description |
| ----- | ---- | ----------- |
| url | [ string](#string) | none |
| secret | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| content_type | [ hiber.webhook.Webhook.ContentType](#hiberwebhookwebhookcontenttype) | none |
| description | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| deprecated_event_filter | [ hiber.webhook.UpdateWebhookRequest.UpdateWebhook.UpdateEvents](#hiberwebhookupdatewebhookrequestupdatewebhookupdateevents) | none |
| deprecated_modem_filter | [ hiber.webhook.UpdateWebhookRequest.UpdateWebhook.UpdateModems](#hiberwebhookupdatewebhookrequestupdatewebhookupdatemodems) | none |
| deprecated_tag_filter | [ hiber.webhook.UpdateWebhookRequest.UpdateWebhook.UpdateTags](#hiberwebhookupdatewebhookrequestupdatewebhookupdatetags) | none |
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
| add_custom_headers | [map hiber.webhook.UpdateWebhookRequest.UpdateWebhook.AddCustomHeadersEntry](#hiberwebhookupdatewebhookrequestupdatewebhookaddcustomheadersentry) | Custom headers to add to every call. |
| remove_custom_headers | [repeated string](#string) | Remove previously configured custom headers. |
| replace_custom_headers | [map hiber.webhook.UpdateWebhookRequest.UpdateWebhook.ReplaceCustomHeadersEntry](#hiberwebhookupdatewebhookrequestupdatewebhookreplacecustomheadersentry) | Replace the custom headers to add to every call. If set, remove_custom_headers is ignored. |

### hiber.webhook.UpdateWebhookRequest.UpdateWebhook.AddCustomHeadersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ string](#string) | none |

### hiber.webhook.UpdateWebhookRequest.UpdateWebhook.ReplaceCustomHeadersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ string](#string) | none |

### hiber.webhook.UpdateWebhookRequest.UpdateWebhook.UpdateEvents



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ hiber.Filter.Events](#hiberfilterevents) | none |

### hiber.webhook.UpdateWebhookRequest.UpdateWebhook.UpdateModems



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ hiber.Filter.Modems](#hiberfiltermodems) | none |

### hiber.webhook.UpdateWebhookRequest.UpdateWebhook.UpdateTags



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ hiber.Filter.Tags](#hiberfiltertags) | none |

### hiber.webhook.UpdateWebhookTagsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| webhook_ids | [repeated int64](#int64) | none |
| update | [ hiber.tag.UpdateTagsForItem](#hibertagupdatetagsforitem) | none |

### hiber.webhook.UpdateWebhookTagsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| webhooks | [repeated hiber.webhook.Webhook](#hiberwebhookwebhook) | none |

### hiber.webhook.UpdateWebhooksRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| webhook_updates | [repeated hiber.webhook.UpdateWebhooksRequest.Update](#hiberwebhookupdatewebhooksrequestupdate) | none |

### hiber.webhook.UpdateWebhooksRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| webhooks | [repeated hiber.webhook.Webhook](#hiberwebhookwebhook) | none |
| request | [ hiber.webhook.UpdateWebhooksRequest](#hiberwebhookupdatewebhooksrequest) | none |

### hiber.webhook.UpdateWebhooksRequest.Update



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) | none |
| update | [ hiber.webhook.UpdateWebhookRequest.UpdateWebhook](#hiberwebhookupdatewebhookrequestupdatewebhook) | none |

### hiber.webhook.Webhook

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
| data | [ hiber.webhook.Webhook.WebhookData](#hiberwebhookwebhookwebhookdata) | none |
| filters | [ hiber.webhook.Webhook.WebhookFilters](#hiberwebhookwebhookwebhookfilters) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| health | [ hiber.Health](#hiberhealth) | none |
| health_config | [ hiber.webhook.Webhook.HealthConfig](#hiberwebhookwebhookhealthconfig) | none |
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
| url | [ string](#string) | none |
| secret | [ string](#string) | Used to generate the HMAC-SHA256 header on every webhook call, which you can use to verify the message. The HMAC-SHA256 header is calculated with the message body and this secret. There are many examples of how to do this in different languages, for example: https://github.com/danharper/hmac-examples |
| hmac_header_name | [ string](#string) | The header that the hmac value is placed in. Defaults to X-Hub-Signature. |
| content_type | [ hiber.webhook.Webhook.ContentType](#hiberwebhookwebhookcontenttype) | none |
| disabled | [ bool](#bool) | none |
| certificate_id | [ int64](#int64) | none |
| certificate_name | [ string](#string) | none |
| ca_certificate_id | [ int64](#int64) | none |
| ca_certificate_name | [ string](#string) | none |
| custom_headers | [map hiber.webhook.Webhook.WebhookData.CustomHeadersEntry](#hiberwebhookwebhookwebhookdatacustomheadersentry) | Custom headers to add to every call. |

### hiber.webhook.Webhook.WebhookData.CustomHeadersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ string](#string) | none |

### hiber.webhook.Webhook.WebhookFilters



| Field | Type | Description |
| ----- | ---- | ----------- |
| event_types | [ hiber.Filter.Events](#hiberfilterevents) | none |
| modem_numbers | [ hiber.Filter.Modems](#hiberfiltermodems) | none |
| tags | [ hiber.Filter.Tags](#hiberfiltertags) | none |
| health_levels | [repeated string](#string) | Filter events by health level caused. |

### hiber.webhook.WebhookCall



| Field | Type | Description |
| ----- | ---- | ----------- |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| url | [ string](#string) | none |
| headers | [map hiber.webhook.WebhookCall.HeadersEntry](#hiberwebhookwebhookcallheadersentry) | none |
| body_proto | [ bytes](#bytes) | none |
| body_json | [ string](#string) | none |
| successful | [ bool](#bool) | none |
| error | [ string](#string) | none |

### hiber.webhook.WebhookCall.HeadersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ string](#string) | none |

### hiber.webhook.WebhookHistoryRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| webhook_id | [ int64](#int64) | none |
| selection | [ hiber.webhook.WebhookHistorySelection](#hiberwebhookwebhookhistoryselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |

### hiber.webhook.WebhookHistoryRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| calls | [repeated hiber.webhook.WebhookCall](#hiberwebhookwebhookcall) | none |
| request | [ hiber.webhook.WebhookHistoryRequest](#hiberwebhookwebhookhistoryrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### hiber.webhook.WebhookHistorySelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| only_failures | [ bool](#bool) | none |
| time_range | [ hiber.TimeRange](#hibertimerange) | none |

### hiber.webhook.WebhookSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| description | [ string](#string) | none |
| url | [ string](#string) | none |
| webhooks | [ hiber.Filter.Webhooks](#hiberfilterwebhooks) | none |
| tags | [ hiber.tag.TagSelection](#hibertagtagselection) | none |
| health | [repeated hiber.Health](#hiberhealth) | none |
| certificate_ids | [repeated int64](#int64) | none |
| search | [ string](#string) | Search in the all available text, like description and url. |


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
| DEFAULT | none | 0 |
| JSON | none | 1 |
| PROTO | none | 2 |



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

