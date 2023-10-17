# dashboard.proto



#### This file was generated from [dashboard.proto](https://github.com/HiberGlobal/api/blob/master/dashboard.proto).

## Table of Contents

- Services
  - [DashboardService](#dashboardservice)

- Messages
  - [DashboardRequest](#dashboardrequest)
  - [DashboardRequest.Response](#dashboardrequestresponse)

- Enums

- Referenced messages from [event.proto](#referenced-messages-from-eventproto)
  - [hiber.event.BundledEvent](#hibereventbundledevent)
  - [hiber.event.BundledEvent.ApproximatedAmount](#hibereventbundledeventapproximatedamount)
  - [hiber.event.BundledEvent.ExactAmount](#hibereventbundledeventexactamount)
  - [hiber.event.Event](#hibereventevent)
  - [hiber.event.Event.AssignmentEvent](#hibereventeventassignmentevent)
  - [hiber.event.Event.AssignmentEvent.AssignedEvent](#hibereventeventassignmenteventassignedevent)
  - [hiber.event.Event.AssignmentEvent.UnassignedEvent](#hibereventeventassignmenteventunassignedevent)
  - [hiber.event.Event.ExportEvent](#hibereventeventexportevent)
  - [hiber.event.Event.ExportEvent.ExportCreatedEvent](#hibereventeventexporteventexportcreatedevent)
  - [hiber.event.Event.ExportEvent.ExportFailedEvent](#hibereventeventexporteventexportfailedevent)
  - [hiber.event.Event.ExportEvent.ExportReadyEvent](#hibereventeventexporteventexportreadyevent)
  - [hiber.event.Event.Modem](#hibereventeventmodem)
  - [hiber.event.Event.ModemEvent](#hibereventeventmodemevent)
  - [hiber.event.Event.ModemEvent.AlarmEvent](#hibereventeventmodemeventalarmevent)
  - [hiber.event.Event.ModemEvent.AlarmEvent.CreatedEvent](#hibereventeventmodemeventalarmeventcreatedevent)
  - [hiber.event.Event.ModemEvent.AlarmEvent.DeletedEvent](#hibereventeventmodemeventalarmeventdeletedevent)
  - [hiber.event.Event.ModemEvent.AlarmEvent.ModemAlarmEvent](#hibereventeventmodemeventalarmeventmodemalarmevent)
  - [hiber.event.Event.ModemEvent.AlarmEvent.ModemAlarmEvent.ErrorMessagesEntry](#hibereventeventmodemeventalarmeventmodemalarmeventerrormessagesentry)
  - [hiber.event.Event.ModemEvent.AlarmEvent.UpdatedEvent](#hibereventeventmodemeventalarmeventupdatedevent)
  - [hiber.event.Event.ModemEvent.AlarmEvent.UpdatedEvent.Update](#hibereventeventmodemeventalarmeventupdatedeventupdate)
  - [hiber.event.Event.ModemEvent.MessageBodyParserEvent](#hibereventeventmodemeventmessagebodyparserevent)
  - [hiber.event.Event.ModemEvent.MessageBodyParserEvent.CreatedEvent](#hibereventeventmodemeventmessagebodyparsereventcreatedevent)
  - [hiber.event.Event.ModemEvent.MessageBodyParserEvent.DeletedEvent](#hibereventeventmodemeventmessagebodyparsereventdeletedevent)
  - [hiber.event.Event.ModemEvent.MessageBodyParserEvent.UpdatedEvent](#hibereventeventmodemeventmessagebodyparsereventupdatedevent)
  - [hiber.event.Event.ModemEvent.MessageEvent](#hibereventeventmodemeventmessageevent)
  - [hiber.event.Event.ModemEvent.MessageEvent.ModemMessageBodyParsedEvent](#hibereventeventmodemeventmessageeventmodemmessagebodyparsedevent)
  - [hiber.event.Event.ModemEvent.MessageEvent.ModemMessageBodyReceivedEvent](#hibereventeventmodemeventmessageeventmodemmessagebodyreceivedevent)
  - [hiber.event.Event.ModemEvent.MessageEvent.ModemMessageCannotBeParsedEvent](#hibereventeventmodemeventmessageeventmodemmessagecannotbeparsedevent)
  - [hiber.event.Event.ModemEvent.MessageEvent.ModemMessageReceivedEvent](#hibereventeventmodemeventmessageeventmodemmessagereceivedevent)
  - [hiber.event.Event.ModemEvent.ModemCreatedEvent](#hibereventeventmodemeventmodemcreatedevent)
  - [hiber.event.Event.ModemEvent.ModemInstalledEvent](#hibereventeventmodemeventmodeminstalledevent)
  - [hiber.event.Event.ModemEvent.ModemLocationUpdatedEvent](#hibereventeventmodemeventmodemlocationupdatedevent)
  - [hiber.event.Event.ModemEvent.ModemUpdatedEvent](#hibereventeventmodemeventmodemupdatedevent)
  - [hiber.event.Event.ModemEvent.ModemUpdatedEvent.PeripheralsEntry](#hibereventeventmodemeventmodemupdatedeventperipheralsentry)
  - [hiber.event.Event.OrganizationEvent](#hibereventeventorganizationevent)
  - [hiber.event.Event.OrganizationEvent.EventConfigurationUpdated](#hibereventeventorganizationeventeventconfigurationupdated)
  - [hiber.event.Event.OrganizationEvent.EventConfigurationUpdated.ModemMessageSummaryUpdate](#hibereventeventorganizationeventeventconfigurationupdatedmodemmessagesummaryupdate)
  - [hiber.event.Event.OrganizationEvent.ModemMessageSummaryEvent](#hibereventeventorganizationeventmodemmessagesummaryevent)
  - [hiber.event.Event.OrganizationEvent.ModemMessageSummaryEvent.MessageCount](#hibereventeventorganizationeventmodemmessagesummaryeventmessagecount)
  - [hiber.event.Event.OrganizationEvent.OrganizationCreatedEvent](#hibereventeventorganizationeventorganizationcreatedevent)
  - [hiber.event.Event.OrganizationEvent.OrganizationDeletedEvent](#hibereventeventorganizationeventorganizationdeletedevent)
  - [hiber.event.Event.OrganizationEvent.OrganizationUpdatedEvent](#hibereventeventorganizationeventorganizationupdatedevent)
  - [hiber.event.Event.PublisherEvent](#hibereventeventpublisherevent)
  - [hiber.event.Event.PublisherEvent.AutoDisabledEvent](#hibereventeventpublishereventautodisabledevent)
  - [hiber.event.Event.PublisherEvent.CreatedEvent](#hibereventeventpublishereventcreatedevent)
  - [hiber.event.Event.PublisherEvent.DeletedEvent](#hibereventeventpublishereventdeletedevent)
  - [hiber.event.Event.PublisherEvent.FailedEvent](#hibereventeventpublishereventfailedevent)
  - [hiber.event.Event.PublisherEvent.UpdatedEvent](#hibereventeventpublishereventupdatedevent)
  - [hiber.event.Event.PublisherEvent.UpdatedEvent.EmailUpdate](#hibereventeventpublishereventupdatedeventemailupdate)
  - [hiber.event.Event.PublisherEvent.UpdatedEvent.MQTTUpdate](#hibereventeventpublishereventupdatedeventmqttupdate)
  - [hiber.event.Event.PublisherEvent.UpdatedEvent.ShellSsipUpdate](#hibereventeventpublishereventupdatedeventshellssipupdate)
  - [hiber.event.Event.PublisherEvent.UpdatedEvent.SlackUpdate](#hibereventeventpublishereventupdatedeventslackupdate)
  - [hiber.event.Event.PublisherEvent.UpdatedEvent.WebhookUpdate](#hibereventeventpublishereventupdatedeventwebhookupdate)
  - [hiber.event.Event.TokenEvent](#hibereventeventtokenevent)
  - [hiber.event.Event.TokenEvent.TokenCreatedEvent](#hibereventeventtokeneventtokencreatedevent)
  - [hiber.event.Event.TokenEvent.TokenDeletedEvent](#hibereventeventtokeneventtokendeletedevent)
  - [hiber.event.Event.TokenEvent.TokenExpiredEvent](#hibereventeventtokeneventtokenexpiredevent)
  - [hiber.event.Event.TokenEvent.TokenExpiryWarningEvent](#hibereventeventtokeneventtokenexpirywarningevent)
  - [hiber.event.Event.TransferEvent](#hibereventeventtransferevent)
  - [hiber.event.Event.UserEvent](#hibereventeventuserevent)
  - [hiber.event.Event.UserEvent.UserAccessRequestEvent](#hibereventeventusereventuseraccessrequestevent)
  - [hiber.event.Event.UserEvent.UserAddedEvent](#hibereventeventusereventuseraddedevent)
  - [hiber.event.Event.UserEvent.UserInvitedEvent](#hibereventeventusereventuserinvitedevent)
  - [hiber.event.Event.UserEvent.UserRemovedEvent](#hibereventeventusereventuserremovedevent)
  - [hiber.event.Event.UserEvent.UserValidationUpdatedEvent](#hibereventeventusereventuservalidationupdatedevent)
  - [hiber.event.EventConfiguration](#hibereventeventconfiguration)
  - [hiber.event.EventConfiguration.EventHealthLevelConfiguration](#hibereventeventconfigurationeventhealthlevelconfiguration)
  - [hiber.event.EventConfiguration.ModemMessageSummaryConfiguration](#hibereventeventconfigurationmodemmessagesummaryconfiguration)
  - [hiber.event.EventConfiguration.Request](#hibereventeventconfigurationrequest)
  - [hiber.event.EventHistory](#hibereventeventhistory)
  - [hiber.event.EventHistory.Request](#hibereventeventhistoryrequest)
  - [hiber.event.EventHistory.Response](#hibereventeventhistoryresponse)
  - [hiber.event.EventSelection](#hibereventeventselection)
  - [hiber.event.EventStreamRequest](#hibereventeventstreamrequest)
  - [hiber.event.ListEventsRequest](#hibereventlisteventsrequest)
  - [hiber.event.ListEventsRequest.Response](#hibereventlisteventsrequestresponse)
  - [hiber.event.ListEventsRequest.Response.EventTypeResponse](#hibereventlisteventsrequestresponseeventtyperesponse)
  - [hiber.event.MarkEventsResolved](#hibereventmarkeventsresolved)
  - [hiber.event.MarkEventsResolved.Request](#hibereventmarkeventsresolvedrequest)
  - [hiber.event.MarkEventsResolved.Response](#hibereventmarkeventsresolvedresponse)
  - [hiber.event.ModemHealthEvents](#hibereventmodemhealthevents)
  - [hiber.event.ModemHealthEvents.Request](#hibereventmodemhealtheventsrequest)
  - [hiber.event.ModemHealthEvents.Response](#hibereventmodemhealtheventsresponse)
  - [hiber.event.ResolveEvent](#hibereventresolveevent)
  - [hiber.event.ResolveEvent.Request](#hibereventresolveeventrequest)
  - [hiber.event.ResolveEvent.Response](#hibereventresolveeventresponse)
  - [hiber.event.UpdateEventHealthConfiguration](#hibereventupdateeventhealthconfiguration)
  - [hiber.event.UpdateEventHealthConfiguration.Request](#hibereventupdateeventhealthconfigurationrequest)
  - [hiber.event.UpdateEventHealthConfiguration.Response](#hibereventupdateeventhealthconfigurationresponse)
  - [hiber.event.UpdateEventHealthConfiguration.UpdateEventHealth](#hibereventupdateeventhealthconfigurationupdateeventhealth)

    - [hiber.event.ListEventsRequest.Sort](#hibereventlisteventsrequestsort)

- Referenced messages from [modem.proto](#referenced-messages-from-modemproto)
  - [hiber.modem.Modem](#hibermodemmodem)
  - [hiber.modem.ModemSelection](#hibermodemmodemselection)

    - [hiber.modem.ListModemsRequest.Sort](#hibermodemlistmodemsrequestsort)
    - [hiber.modem.Modem.Lifecycle](#hibermodemmodemlifecycle)
    - [hiber.modem.Modem.Type](#hibermodemmodemtype)
    - [hiber.modem.ModemMessage.Source](#hibermodemmodemmessagesource)

- [Scalar Value Types](#scalar-value-types)


## DashboardService
Dashboard calls related to the Hiber Mission Control Dashboard

### Dashboard
> **rpc** Dashboard([DashboardRequest](#dashboardrequest))
    [DashboardRequest.Response](#dashboardrequestresponse)




## Messages

### DashboardRequest

Get the data for the dashboard. This includes map data, message count and relevant status events.
MapSelection is used for the map data, as used in the MapService.
ModemMessageSelection is used to filter the messages used for the count by day.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| message_count_selection | [ hiber.modem.ModemMessageSelection](#hibermodemmodemmessageselection) | Selection for modem messages. |
| event_selection | [ hiber.event.EventSelection](#hibereventeventselection) | Selection for bundled events, only used when any value is set. |
| time_zone_offset | [ int32](#int32) | Numeric timezone offset for message count, day grouping. Optional. |
| time_zone | [ string](#string) | Timezone string for message count, day grouping. Optional. |

### DashboardRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| message_count_per_day | [repeated hiber.modem.MessageCountRequest.Response.MessageCount](#hibermodemmessagecountrequestresponsemessagecount) | none |
| modem_warning_count | [ int32](#int32) | Counts of the number of modems with warnings. |
| modem_error_count | [ int32](#int32) | Counts of the number of modems with errors. |
| request | [ DashboardRequest](#dashboardrequest) | none |
| events | [repeated hiber.event.BundledEvent](#hibereventbundledevent) | Returns event bundles matching the given selection, or an empty list if the event selection wasn't set. |


## Enums


## Referenced messages from event.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [event.proto](https://github.com/HiberGlobal/api/blob/master/event.proto).


### hiber.event.BundledEvent

A bundle/set of events, all of the same event-type.

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.EventType](#hibereventtype) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **amount**.exact_amount | [ hiber.event.BundledEvent.ExactAmount](#hibereventbundledeventexactamount) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **amount**.approximated_amount | [ hiber.event.BundledEvent.ApproximatedAmount](#hibereventbundledeventapproximatedamount) | none |
| deprecated_amount | [ int32](#int32) | Deprecated in favour of using the amount field that is either an ExactAmount or ApproximatedAmount |
| deprecated_last_event | [ hiber.Timestamp](#hibertimestamp) | Deprecated in favour of using the amount field that is either an ExactAmount or ApproximatedAmount. since `last_event` is not available when using approximation (we don't know the actual last event), this field is only present when getting an ExactAmount. |
| deprecated_approximated_amount | [ bool](#bool) | Indicates that the amount is an approximation, and not an exact value. Some events will be approximated to avoid a large number of events affecting the request time. Deprecated in favour of using the oneof_amount field that is either an ExactAmount or ApproximatedAmount |

### hiber.event.BundledEvent.ApproximatedAmount

Indicates that the amount is an approximation, and not an exact value.
Some events will be approximated to avoid a large number of events affecting the request time.
Because of the nature of approximation, we don't have a "last" event, so no timestamp is available.

| Field | Type | Description |
| ----- | ---- | ----------- |
| amount | [ int32](#int32) | none |

### hiber.event.BundledEvent.ExactAmount

Indicates that the amount is an exact count, and not an approximated value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| amount | [ int32](#int32) | none |
| last_event | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event

Generic Event object, used in streams where events are mixed. Protobuf provides helper methods to extract
the contained object.

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.EventType](#hibereventtype) | Time of the event. |
| time | [ hiber.Timestamp](#hibertimestamp) | Time of the event. |
| is_error | [ bool](#bool) | Whether this event causes the 'Error' health level. If your organization does not use the default health levels, this field will be omitted. Use health_level instead. |
| is_warning | [ bool](#bool) | Whether this event causes the 'Warning' health level. If your organization does not use the default health levels, this field will be omitted. Use health_level instead. |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The health level caused by this event. This health generally applies to either a modem, a token or a publisher, and is also applied to the organization health. Not every event affects health, so this field might be empty. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **resolved_status**.resolved | [ bool](#bool) | Whether this event was resolved. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **resolved_status**.resolve_identifier | [ string](#string) | The identifier to use when resolving this event. Only present when not resolved, and only available for some event types. |
| title | [ string](#string) | Short text describing the event. |
| description | [ string](#string) | Longer text describing the event in more detail. |
| modem | [ hiber.event.Event.Modem](#hibereventeventmodem) | The modem number for this event, if it is related to a single modem. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | The tags for this event, if any. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_created | [ hiber.event.Event.ModemEvent.ModemCreatedEvent](#hibereventeventmodemeventmodemcreatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_updated | [ hiber.event.Event.ModemEvent.ModemUpdatedEvent](#hibereventeventmodemeventmodemupdatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_location_updated | [ hiber.event.Event.ModemEvent.ModemLocationUpdatedEvent](#hibereventeventmodemeventmodemlocationupdatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_installed | [ hiber.event.Event.ModemEvent.ModemInstalledEvent](#hibereventeventmodemeventmodeminstalledevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_message_received | [ hiber.event.Event.ModemEvent.MessageEvent.ModemMessageReceivedEvent](#hibereventeventmodemeventmessageeventmodemmessagereceivedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_message_body_received | [ hiber.event.Event.ModemEvent.MessageEvent.ModemMessageBodyReceivedEvent](#hibereventeventmodemeventmessageeventmodemmessagebodyreceivedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_message_body_parsed | [ hiber.event.Event.ModemEvent.MessageEvent.ModemMessageBodyParsedEvent](#hibereventeventmodemeventmessageeventmodemmessagebodyparsedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_message_cannot_be_parsed | [ hiber.event.Event.ModemEvent.MessageEvent.ModemMessageCannotBeParsedEvent](#hibereventeventmodemeventmessageeventmodemmessagecannotbeparsedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_message_body_parser_created | [ hiber.event.Event.ModemEvent.MessageBodyParserEvent.CreatedEvent](#hibereventeventmodemeventmessagebodyparsereventcreatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_message_body_parser_updated | [ hiber.event.Event.ModemEvent.MessageBodyParserEvent.UpdatedEvent](#hibereventeventmodemeventmessagebodyparsereventupdatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_message_body_parser_deleted | [ hiber.event.Event.ModemEvent.MessageBodyParserEvent.DeletedEvent](#hibereventeventmodemeventmessagebodyparsereventdeletedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_alarm | [ hiber.event.Event.ModemEvent.AlarmEvent.ModemAlarmEvent](#hibereventeventmodemeventalarmeventmodemalarmevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_alarm_created | [ hiber.event.Event.ModemEvent.AlarmEvent.CreatedEvent](#hibereventeventmodemeventalarmeventcreatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_alarm_updated | [ hiber.event.Event.ModemEvent.AlarmEvent.UpdatedEvent](#hibereventeventmodemeventalarmeventupdatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_alarm_deleted | [ hiber.event.Event.ModemEvent.AlarmEvent.DeletedEvent](#hibereventeventmodemeventalarmeventdeletedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.assigned | [ hiber.event.Event.AssignmentEvent.AssignedEvent](#hibereventeventassignmenteventassignedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.unassigned | [ hiber.event.Event.AssignmentEvent.UnassignedEvent](#hibereventeventassignmenteventunassignedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.user_added | [ hiber.event.Event.UserEvent.UserAddedEvent](#hibereventeventusereventuseraddedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.user_removed | [ hiber.event.Event.UserEvent.UserRemovedEvent](#hibereventeventusereventuserremovedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.user_invited | [ hiber.event.Event.UserEvent.UserInvitedEvent](#hibereventeventusereventuserinvitedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.user_access_request | [ hiber.event.Event.UserEvent.UserAccessRequestEvent](#hibereventeventusereventuseraccessrequestevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.user_validation_updated | [ hiber.event.Event.UserEvent.UserValidationUpdatedEvent](#hibereventeventusereventuservalidationupdatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.transfer | [ hiber.event.Event.TransferEvent](#hibereventeventtransferevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.token_expiry_warning | [ hiber.event.Event.TokenEvent.TokenExpiryWarningEvent](#hibereventeventtokeneventtokenexpirywarningevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.token_expired | [ hiber.event.Event.TokenEvent.TokenExpiredEvent](#hibereventeventtokeneventtokenexpiredevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.token_created | [ hiber.event.Event.TokenEvent.TokenCreatedEvent](#hibereventeventtokeneventtokencreatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.token_deleted | [ hiber.event.Event.TokenEvent.TokenDeletedEvent](#hibereventeventtokeneventtokendeletedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.organization_created | [ hiber.event.Event.OrganizationEvent.OrganizationCreatedEvent](#hibereventeventorganizationeventorganizationcreatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.organization_updated | [ hiber.event.Event.OrganizationEvent.OrganizationUpdatedEvent](#hibereventeventorganizationeventorganizationupdatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.organization_deleted | [ hiber.event.Event.OrganizationEvent.OrganizationDeletedEvent](#hibereventeventorganizationeventorganizationdeletedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_message_summary | [ hiber.event.Event.OrganizationEvent.ModemMessageSummaryEvent](#hibereventeventorganizationeventmodemmessagesummaryevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.organization_event_configuration_updated | [ hiber.event.Event.OrganizationEvent.EventConfigurationUpdated](#hibereventeventorganizationeventeventconfigurationupdated) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.publisher_created | [ hiber.event.Event.PublisherEvent.CreatedEvent](#hibereventeventpublishereventcreatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.publisher_updated | [ hiber.event.Event.PublisherEvent.UpdatedEvent](#hibereventeventpublishereventupdatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.publisher_deleted | [ hiber.event.Event.PublisherEvent.DeletedEvent](#hibereventeventpublishereventdeletedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.publisher_auto_disabled | [ hiber.event.Event.PublisherEvent.AutoDisabledEvent](#hibereventeventpublishereventautodisabledevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.publisher_failed | [ hiber.event.Event.PublisherEvent.FailedEvent](#hibereventeventpublishereventfailedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.export_created | [ hiber.event.Event.ExportEvent.ExportCreatedEvent](#hibereventeventexporteventexportcreatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.export_ready | [ hiber.event.Event.ExportEvent.ExportReadyEvent](#hibereventeventexporteventexportreadyevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.export_failed | [ hiber.event.Event.ExportEvent.ExportFailedEvent](#hibereventeventexporteventexportfailedevent) | none |

### hiber.event.Event.AssignmentEvent




### hiber.event.Event.AssignmentEvent.AssignedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| created | [ hiber.assign.Assignment](#hiberassignassignment) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.AssignmentEvent.UnassignedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| removed | [ hiber.assign.Assignment](#hiberassignassignment) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.ExportEvent




### hiber.event.Event.ExportEvent.ExportCreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| export | [ hiber.export.Export](#hiberexportexport) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.ExportEvent.ExportFailedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| export | [ hiber.export.Export](#hiberexportexport) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.ExportEvent.ExportReadyEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| export | [ hiber.export.Export](#hiberexportexport) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.Modem

The modem data for this event, if it is related to a single modem.

| Field | Type | Description |
| ----- | ---- | ----------- |
| number | [ string](#string) | none |
| name | [ string](#string) | none |
| identifier | [ string](#string) | none |

### hiber.event.Event.ModemEvent




### hiber.event.Event.ModemEvent.AlarmEvent




### hiber.event.Event.ModemEvent.AlarmEvent.CreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| created | [ hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.ModemEvent.AlarmEvent.DeletedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| deleted | [ string](#string) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.ModemEvent.AlarmEvent.ModemAlarmEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| modem_number | [ string](#string) | none |
| modem_external_device_id | [ string](#string) | none |
| modem_message_id | [ uint64](#uint64) | The id of the modem that triggered the alarm, if any. |
| alarm_identifier | [ string](#string) | The identifier of the alarm. |
| alarm_description | [ string](#string) | The description of the alarm. |
| error_messages | [map hiber.event.Event.ModemEvent.AlarmEvent.ModemAlarmEvent.ErrorMessagesEntry](#hibereventeventmodemeventalarmeventmodemalarmeventerrormessagesentry) | The filled in error message(s) for the failing checks in the alarm. |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The highest health level caused by the failing checks in this alarm, for the modem (and organization). |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| resolved_at | [ hiber.Timestamp](#hibertimestamp) | When this alarm event was resolved. |
| health_level_after_resolved | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | Optional health that this alarm event causes after it has been resolved. |
| health_level_after_resolved_until | [ hiber.Timestamp](#hibertimestamp) | How long the optional health that this alarm event causes after it has been resolved lasts. |

### hiber.event.Event.ModemEvent.AlarmEvent.ModemAlarmEvent.ErrorMessagesEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ string](#string) | none |

### hiber.event.Event.ModemEvent.AlarmEvent.UpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| updated | [ hiber.event.Event.ModemEvent.AlarmEvent.UpdatedEvent.Update](#hibereventeventmodemeventalarmeventupdatedeventupdate) | none |
| alarm_identifier | [ string](#string) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.ModemEvent.AlarmEvent.UpdatedEvent.Update



| Field | Type | Description |
| ----- | ---- | ----------- |
| description | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| trigger_condition | [ string](#string) | none |
| checks | [ google.protobuf.Struct](#googleprotobufstruct) | none |
| update_default_health_level | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| update_health_level_after_resolved | [ hiber.modem.alarm.ModemAlarm.HealthLevelAfterResolved](#hibermodemalarmmodemalarmhealthlevelafterresolved) | none |

### hiber.event.Event.ModemEvent.MessageBodyParserEvent

Events related to ModemMessageBodyParsers.


### hiber.event.Event.ModemEvent.MessageBodyParserEvent.CreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| created | [ hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.ModemEvent.MessageBodyParserEvent.DeletedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| deleted | [ string](#string) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.ModemEvent.MessageBodyParserEvent.UpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| updated_name | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| updated_content_ksy | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| updated_simple_parser | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser](#hibermodemmessagebodyparsersimplemodemmessagebodyparser) | none |
| updated_available_to_child_organizations | [ hiber.Filter.ChildOrganizations.Update](#hiberfilterchildorganizationsupdate) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.ModemEvent.MessageEvent




### hiber.event.Event.ModemEvent.MessageEvent.ModemMessageBodyParsedEvent

This event is generated whenever a message is parsed successfully by an assigned body parser.
If multiple body parsers are assigned to a modem, multiple ModemMessageParsedEvent events will
be produced by an incoming message.
For the total result of all assigned parsers, see the ModemMessageReceivedEvent, which is produced
after all body parsers have been applied.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| modem_number | [ string](#string) | none |
| modem_external_device_id | [ string](#string) | External device id for this modem (e.g. a MAC address). |
| message_id | [ uint64](#uint64) | Id of the message that was parsed. |
| sent_at | [ hiber.Timestamp](#hibertimestamp) | Time the message was sent from the modem. |
| parser_identifier | [ string](#string) | The identifier of the parser that parsed the body. |
| parser_name | [ string](#string) | The name of the parser that parsed the body. |
| parsed_message | [ google.protobuf.Struct](#googleprotobufstruct) | The resulting json from parsing the message body. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | The modem's tags. |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.ModemEvent.MessageEvent.ModemMessageBodyReceivedEvent

This lightweight event is generated whenever a message comes in, after is has been decrypted.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| modem_number | [ string](#string) | none |
| modem_external_device_id | [ string](#string) | External device id for this modem (e.g. a MAC address). |
| message_id | [ uint64](#uint64) | Id of the message that was parsed. |
| sent_at | [ hiber.Timestamp](#hibertimestamp) | Time the message was sent from the modem. |
| body | [ hiber.BytesOrHex](#hiberbytesorhex) | Message body convenience object. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | The modem's tags. |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.ModemEvent.MessageEvent.ModemMessageCannotBeParsedEvent

Triggered when a message cannot be parsed. This can have multiple reasons, for example, an invalid
message version.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| modem_number | [ string](#string) | none |
| modem_external_device_id | [ string](#string) | External device id for this modem (e.g. a MAC address). |
| modem_message_id | [ uint64](#uint64) | The message that cannot be parsed. This message may or may not be available in the system, depending one the reason it could not be parsed. |
| time | [ hiber.Timestamp](#hibertimestamp) | The moment this event was triggered. |
| reason | [ string](#string) | The reason this message could not be parsed. This could be, for example: - invalid message envelope, but with enough information to determine the modem - all body parsers failed to parse the body of the message |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The health level caused for the modem (and organization) by this event. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **resolved_status**.resolved | [ bool](#bool) | Whether this event was resolved. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **resolved_status**.resolve_identifier | [ string](#string) | The identifier to use when resolving this event. Only present when not resolved |

### hiber.event.Event.ModemEvent.MessageEvent.ModemMessageReceivedEvent

This event is generated whenever a message comes in, after is has been decrypted
and parsed (if any body parsers are configured for the modem).

It contains the relevant data in the message object, including location and the
user-defined body.

If any body parser(s) are configured for the modem, the modem message object also contains
a ParsedBody for each of them.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| modem_number | [ string](#string) | none |
| modem_external_device_id | [ string](#string) | External device id for this modem (e.g. a MAC address). |
| message | [ hiber.modem.ModemMessage](#hibermodemmodemmessage) | The received message, including parsed body. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | The modem's tags. |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.ModemEvent.ModemCreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| modem_number | [ string](#string) | none |
| modem_external_device_id | [ string](#string) | External device id for this modem (e.g. a MAC address). |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |

### hiber.event.Event.ModemEvent.ModemInstalledEvent

When the modem is marked as installed.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| modem_number | [ string](#string) | none |
| modem_external_device_id | [ string](#string) | External device id for this modem (e.g. a MAC address). |
| time | [ hiber.Timestamp](#hibertimestamp) | The time this modem was installed. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |

### hiber.event.Event.ModemEvent.ModemLocationUpdatedEvent

When a message comes in, the modem's location is updated automatically. This event is generated whenever the
modem's location is updated

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| modem_number | [ string](#string) | none |
| modem_external_device_id | [ string](#string) | External device id for this modem (e.g. a MAC address). |
| location | [ hiber.Location](#hiberlocation) | The updated location for this modem. |
| updated_at | [ hiber.Timestamp](#hibertimestamp) | The device time of the first message with the new location. |
| time | [ hiber.Timestamp](#hibertimestamp) | The time this event was generated on the server, after the message was received. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |

### hiber.event.Event.ModemEvent.ModemUpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| modem_number | [ string](#string) | none |
| modem_external_device_id | [ string](#string) | External device id for this modem (e.g. a MAC address). |
| display_name | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| custom_antenna | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| gps | [ hiber.UpdateBoolean](#hiberupdateboolean) | none |
| location | [ hiber.Location](#hiberlocation) | none |
| peripherals | [map hiber.event.Event.ModemEvent.ModemUpdatedEvent.PeripheralsEntry](#hibereventeventmodemeventmodemupdatedeventperipheralsentry) | none |
| notes | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| secure_notes_updated | [ bool](#bool) | none |
| health_warning_period | [ hiber.Duration](#hiberduration) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |

### hiber.event.Event.ModemEvent.ModemUpdatedEvent.PeripheralsEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ string](#string) | none |

### hiber.event.Event.OrganizationEvent




### hiber.event.Event.OrganizationEvent.EventConfigurationUpdated



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| modem_message_summary_update | [ hiber.event.Event.OrganizationEvent.EventConfigurationUpdated.ModemMessageSummaryUpdate](#hibereventeventorganizationeventeventconfigurationupdatedmodemmessagesummaryupdate) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.OrganizationEvent.EventConfigurationUpdated.ModemMessageSummaryUpdate



| Field | Type | Description |
| ----- | ---- | ----------- |
| enabled | [ hiber.UpdateBoolean](#hiberupdateboolean) | none |
| period | [ hiber.Duration](#hiberduration) | none |
| align_to_time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.OrganizationEvent.ModemMessageSummaryEvent

Message summary event that is sent when it has been configured for the organization.
The period is configurable, using the EventConfiguration.
This event is disabled by default.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| message_count | [repeated hiber.event.Event.OrganizationEvent.ModemMessageSummaryEvent.MessageCount](#hibereventeventorganizationeventmodemmessagesummaryeventmessagecount) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| time_range | [ hiber.TimeRange](#hibertimerange) | none |

### hiber.event.Event.OrganizationEvent.ModemMessageSummaryEvent.MessageCount



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem | [ string](#string) | none |
| source | [ hiber.modem.ModemMessage.Source](#hibermodemmodemmessagesource) | none |
| amount | [ int32](#int32) | none |

### hiber.event.Event.OrganizationEvent.OrganizationCreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| parent_organization | [ string](#string) | none |
| created | [ hiber.organization.Organization](#hiberorganizationorganization) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| avatar | [ hiber.Avatar](#hiberavatar) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.OrganizationEvent.OrganizationDeletedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| parent_organization | [ string](#string) | none |
| deleted_organization | [ string](#string) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.OrganizationEvent.OrganizationUpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| display_name_updated | [ string](#string) | none |
| vat_number_updated | [ string](#string) | none |
| address_updated | [ hiber.organization.Organization.Address](#hiberorganizationorganizationaddress) | none |
| is_business_updated | [ hiber.UpdateBoolean](#hiberupdateboolean) | none |
| billing_name_updated | [ string](#string) | none |
| billing_address_updated | [ hiber.organization.Organization.Address](#hiberorganizationorganizationaddress) | none |
| contact_updated | [ hiber.organization.Organization.Contact](#hiberorganizationorganizationcontact) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| features_added | [repeated hiber.organization.Organization.Feature](#hiberorganizationorganizationfeature) | none |
| features_removed | [repeated hiber.organization.Organization.Feature](#hiberorganizationorganizationfeature) | none |

### hiber.event.Event.PublisherEvent




### hiber.event.Event.PublisherEvent.AutoDisabledEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| id | [ int64](#int64) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The health level caused for the publisher (and organization) by this event. |

### hiber.event.Event.PublisherEvent.CreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| created | [ hiber.publisher.Publisher](#hiberpublisherpublisher) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.PublisherEvent.DeletedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| deleted | [ hiber.publisher.Publisher](#hiberpublisherpublisher) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.PublisherEvent.FailedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| reason | [ string](#string) | none |
| failed | [ hiber.publisher.Publisher](#hiberpublisherpublisher) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The health level caused for the publisher (and organization) by this event. |

### hiber.event.Event.PublisherEvent.UpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| updated_description | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| partial_update_data | [ hiber.publisher.Publisher.Data](#hiberpublisherpublisherdata) | Deprecated in favor of the new updated_data field |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **updated_data**.webhook | [ hiber.event.Event.PublisherEvent.UpdatedEvent.WebhookUpdate](#hibereventeventpublishereventupdatedeventwebhookupdate) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **updated_data**.mqtt | [ hiber.event.Event.PublisherEvent.UpdatedEvent.MQTTUpdate](#hibereventeventpublishereventupdatedeventmqttupdate) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **updated_data**.email | [ hiber.event.Event.PublisherEvent.UpdatedEvent.EmailUpdate](#hibereventeventpublishereventupdatedeventemailupdate) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **updated_data**.slack | [ hiber.event.Event.PublisherEvent.UpdatedEvent.SlackUpdate](#hibereventeventpublishereventupdatedeventslackupdate) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **updated_data**.shell_ssip | [ hiber.event.Event.PublisherEvent.UpdatedEvent.ShellSsipUpdate](#hibereventeventpublishereventupdatedeventshellssipupdate) | none |
| updated_event_filter | [ hiber.Filter.Events.Update](#hiberfiltereventsupdate) | none |
| updated_modem_filter | [ hiber.Filter.Modems.Update](#hiberfiltermodemsupdate) | none |
| updated_tag_filter | [ hiber.Filter.Tags.Update](#hiberfiltertagsupdate) | none |
| updated_active_state | [ hiber.UpdateBoolean](#hiberupdateboolean) | none |
| health_warning_period | [ hiber.Duration](#hiberduration) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.PublisherEvent.UpdatedEvent.EmailUpdate




### hiber.event.Event.PublisherEvent.UpdatedEvent.MQTTUpdate



| Field | Type | Description |
| ----- | ---- | ----------- |
| url | [ string](#string) | none |
| content_type | [ hiber.integration.mqtt.MQTTPublisher.ContentType](#hiberintegrationmqttmqttpublishercontenttype) | none |
| topic | [ string](#string) | none |
| qos | [ hiber.integration.mqtt.MQTTPublisher.Data.QoS](#hiberintegrationmqttmqttpublisherdataqos) | none |
| identifier | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| username | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| password | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| certificate_id | [ hiber.UpdateOptionalId](#hiberupdateoptionalid) | none |

### hiber.event.Event.PublisherEvent.UpdatedEvent.ShellSsipUpdate




### hiber.event.Event.PublisherEvent.UpdatedEvent.SlackUpdate




### hiber.event.Event.PublisherEvent.UpdatedEvent.WebhookUpdate



| Field | Type | Description |
| ----- | ---- | ----------- |
| url | [ string](#string) | none |
| secret | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| content_type | [ hiber.webhook.Webhook.ContentType](#hiberwebhookwebhookcontenttype) | none |
| certificate_id | [ hiber.UpdateOptionalId](#hiberupdateoptionalid) | none |

### hiber.event.Event.TokenEvent




### hiber.event.Event.TokenEvent.TokenCreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| token | [ hiber.token.Token](#hibertokentoken) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.TokenEvent.TokenDeletedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| token | [ hiber.token.Token](#hibertokentoken) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.TokenEvent.TokenExpiredEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| token | [ hiber.token.Token](#hibertokentoken) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.TokenEvent.TokenExpiryWarningEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| token | [ hiber.token.Token](#hibertokentoken) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The health level caused for the organization by this event. |

### hiber.event.Event.TransferEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| transfer | [ hiber.transfer.Transfer](#hibertransfertransfer) | none |

### hiber.event.Event.UserEvent




### hiber.event.Event.UserEvent.UserAccessRequestEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| user | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |

### hiber.event.Event.UserEvent.UserAddedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| user | [ string](#string) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.UserEvent.UserInvitedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| email | [ string](#string) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.UserEvent.UserRemovedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| user | [ string](#string) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.Event.UserEvent.UserValidationUpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| email_validation_regex | [ string](#string) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.event.EventConfiguration

Configuration for configurable events.
Some events are disable by default, or can be configured in different ways. Their configuration is available here.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| modem_message_summary_configuration | [ hiber.event.EventConfiguration.ModemMessageSummaryConfiguration](#hibereventeventconfigurationmodemmessagesummaryconfiguration) | none |
| event_health_level_configuration | [repeated hiber.event.EventConfiguration.EventHealthLevelConfiguration](#hibereventeventconfigurationeventhealthlevelconfiguration) | List of event-types that have a health-level associated with them. Ignored when updating. |

### hiber.event.EventConfiguration.EventHealthLevelConfiguration

Details the health level configuration for an event-type.
Health of the system can be influenced by multiple things, among which certain events.
When an event that has health associated with it,
said health level will be applied to the part of the system it refers to.
For instance, an event about not being able to parse modem messages, will influence modem health.
An event about a failing parser, will affect parser health.

In general, when multiple events affect the health level of a subsystem,
the most severe health will be applied.

When an expiry duration is set, events will no longer affect health of the subsystem after the configured period.
Health levels reset to the least severe applicable level, typically "Ok".

For instance, an event might not be relevant anymore after 5 days.
By setting expiry to "5d", the event will resolve automatically 5 days after the last event happened.
Depending on other factors that influence modem health,
the health level will be reset to the least severe health level available.

If there is no expiry duration, events need to be resolved manually.

To update, use EventService/UpdateEventHealthConfiguration(UpdateEventHealthConfiguration.Request)

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.EventType](#hibereventtype) | The event type for which this configuration is applicable. |
| level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The health level to produce when this event happens. |
| expiry | [ hiber.Duration](#hiberduration) | If set, the duration for which the health level is applied. Afterward this event has no effect on health. |
| created_at | [ hiber.Timestamp](#hibertimestamp) | When this configuration item was created. |
| updated_at | [ hiber.Timestamp](#hibertimestamp) | The most recent time this configuration item was updated. |

### hiber.event.EventConfiguration.ModemMessageSummaryConfiguration

When enabled, this sends a ModemMessageSummaryEvent periodically.
For example, you can configure the message summary to be a daily message, aligned to midnight in your time zone.

| Field | Type | Description |
| ----- | ---- | ----------- |
| enabled | [ bool](#bool) | The message summary event is disabled by default. |
| period | [ hiber.Duration](#hiberduration) | The period to send the message summary event for. The event can be sent every hour, day, etc. |
| align_to_time | [ hiber.Timestamp](#hibertimestamp) | Align the period to given time. For example, an hourly period sends can be aligned to 0:00 to send every whole hour. A weekly period can be aligned to send at a specific time on Monday by aligning to a timestamp on a Monday. If a textual time zone is configured in this timestamp, it is used as well and should shift with changes like daylight saving time automatically. |
| include_empty_summaries | [ bool](#bool) | Send an event, even if the summary does not contain any information |

### hiber.event.EventConfiguration.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |

### hiber.event.EventHistory

Get the history of events that match the given filter, chronologically (by default, from now backwards in time).

Only returns the Event with first-level fields set, event details are not included in the response
(the oneof is not set).


### hiber.event.EventHistory.Request

Selection for which events to include the response.
Using the EventSelection you'll be able to filter on specific types, or other properties of events.
The Pagination object will let you limit the number of events returned.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.event.EventSelection](#hibereventeventselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |

### hiber.event.EventHistory.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ hiber.event.EventHistory.Request](#hibereventeventhistoryrequest) | none |
| events | [repeated hiber.event.Event](#hibereventevent) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### hiber.event.EventSelection

Selection object for Event list and stream. Filter events on modem, webhook, time and error state, and
paginate the list.
Events are returned bundled by default. this means that, instead of the details, you get a list of bundles,
one per event type, with the count.

| Field | Type | Description |
| ----- | ---- | ----------- |
| events | [ hiber.Filter.Events](#hiberfilterevents) | none |
| modems | [ hiber.Filter.Modems](#hiberfiltermodems) | none |
| publishers | [ hiber.Filter.Publishers](#hiberfilterpublishers) | none |
| tags | [ hiber.Filter.Tags](#hiberfiltertags) | none |
| time_range | [ hiber.TimeRange](#hibertimerange) | none |
| health_levels | [repeated string](#string) | Filter events by actual configured health level. |
| include_resolved_events | [ bool](#bool) | By default, events that have been resolved are not listed. |
| unbundled_events | [ bool](#bool) | When not set, no unbundled events are returned. When set, returns unbundled events per type, paginated per type. Deprecated: use unbundled_events on ListEventsRequest |
| errors_only | [ bool](#bool) | Return only events that cause the default Error health. Deprecated: use health_levels with custom health levels instead. |
| warnings_only | [ bool](#bool) | Return only events that cause the default Warning health. Deprecated: use health_levels with custom health levels instead. |

### hiber.event.EventStreamRequest

Creates a stream for new events, matching the provided selection.

Note: streams are limited to one per user due to GRPC limitations.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.event.EventSelection](#hibereventeventselection) | The selection for the events. |
| child_organizations | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | Include events from child organizations, if requested. This is only available for streaming, listing events can only be listed per organization. Keep in mind that filtering events using the selection is limited. Filtering on tags or publishers, for example, can only apply to the parent organization. |

### hiber.event.ListEventsRequest

Lists all events matching the given criteria.
The frequency of event can vary greatly per type, resulting in unclear pagination and some event types overshadowing
others. For this reason, event are bundled by default, reducing them to a count per event type.
If unbundled events for certain types are required, this can be toggled in the selection object.
Pagination is only applied to unbundled events, and is applied per event type. This may result in a non-linear
timeline from page to page when selecting two types with a large difference in frequency, but makes sure you
see the most recent events of each type on the first page.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.event.EventSelection](#hibereventeventselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | Pagination is applied per event type on unbundled events. It is not necessary for bundled events. |
| sort | [ hiber.event.ListEventsRequest.Sort](#hibereventlisteventsrequestsort) | none |
| unbundled_events | [ bool](#bool) | When not set, bundled/grouped events are returned. When set, returns unbundled events per type, paginated per type. Overrides unbundled_events in EventSelection message. |

### hiber.event.ListEventsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ hiber.event.ListEventsRequest](#hibereventlisteventsrequest) | none |
| events | [repeated hiber.event.BundledEvent](#hibereventbundledevent) | none |
| unbundled_events | [repeated hiber.event.ListEventsRequest.Response.EventTypeResponse](#hibereventlisteventsrequestresponseeventtyperesponse) | none |

### hiber.event.ListEventsRequest.Response.EventTypeResponse



| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.EventType](#hibereventtype) | none |
| unbundled_events | [repeated hiber.event.Event](#hibereventevent) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### hiber.event.MarkEventsResolved

Mark a selection of events as resolved.


### hiber.event.MarkEventsResolved.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.event.EventSelection](#hibereventeventselection) | Selection of events to resolve. |

### hiber.event.MarkEventsResolved.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| resolved | [ uint32](#uint32) | The amount of events that were resolved. |
| request | [ hiber.event.MarkEventsResolved.Request](#hibereventmarkeventsresolvedrequest) | The original request, echoed back with any applied corrections. |

### hiber.event.ModemHealthEvents

Get the list of events that affect modem health, chronologically (by default, from now backwards in time).

Only returns the Event with first-level fields set, event details are not included in the response
(the oneof is not set).


### hiber.event.ModemHealthEvents.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.event.EventSelection](#hibereventeventselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |

### hiber.event.ModemHealthEvents.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ hiber.event.ModemHealthEvents.Request](#hibereventmodemhealtheventsrequest) | none |
| events | [repeated hiber.event.Event](#hibereventevent) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### hiber.event.ResolveEvent

Resolve a resolvable event using its resolve_identifier.


### hiber.event.ResolveEvent.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| resolve_identifier | [ string](#string) | The resolve identifier of the event you wish to resolve. |

### hiber.event.ResolveEvent.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| event | [ hiber.event.Event](#hibereventevent) | none |

### hiber.event.UpdateEventHealthConfiguration




### hiber.event.UpdateEventHealthConfiguration.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| updates | [repeated hiber.event.UpdateEventHealthConfiguration.UpdateEventHealth](#hibereventupdateeventhealthconfigurationupdateeventhealth) | List of event-types to update health for. When listing same event twice, behaviour is undefined. |

### hiber.event.UpdateEventHealthConfiguration.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ hiber.event.UpdateEventHealthConfiguration.Request](#hibereventupdateeventhealthconfigurationrequest) | The original request, echoed back. |
| event_configuration | [ hiber.event.EventConfiguration](#hibereventeventconfiguration) | The updated event configuration. |

### hiber.event.UpdateEventHealthConfiguration.UpdateEventHealth

Updates health-level configuration for a specific event-type.
To find available health-level names, use HealthService/List(ListHealthLevels.Request).
To clear an existing expiry, set `updated` true and leave `duration` to be the default value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.EventType](#hibereventtype) | When set, events of this type will affect the system with the configured health level. |
| level | [ string](#string) | The health level to produce when the event happens, by name. |
| expiry | [ hiber.UpdateOptionalDuration](#hiberupdateoptionalduration) | After the expiry duration, the event will not affect health anymore. Clear for manual resolving of events. |


### Enums
#### hiber.event.ListEventsRequest.Sort


| Name | Description | Number |
| ---- | ----------- | ------ |
| TIME_DESCENDING | none | 0 |
| TIME_ASCENDING | none | 1 |
| MODEM_NUMBER_ASC | none | 2 |
| MODEM_NUMBER_DESC | none | 3 |
| MODEM_NUMBER_SPECIFIED | none | 4 |



## Referenced messages from modem.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [modem.proto](https://github.com/HiberGlobal/api/blob/master/modem.proto).


### hiber.modem.Modem

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
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | Health level based on the modem alarm and some always-present alarms. |
| lifecycle | [ hiber.modem.Modem.Lifecycle](#hibermodemmodemlifecycle) | none |
| technical | [ hiber.modem.Modem.TechnicalData](#hibermodemmodemtechnicaldata) | additional information |
| peripherals | [ hiber.modem.Modem.Peripherals](#hibermodemmodemperipherals) | none |
| notes | [ string](#string) | Notes field that can be used to add additional information to a modem. |
| secure_notes | [ string](#string) | Secure notes field that can be used to add additional information to a modem, with limited accessibility. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| is_gateway | [ bool](#bool) | [DEPRECATED] Whether the modem is a gateway, it has been configured as a gateway and has connected devices. Use `type` instead. |
| is_device_connected_to_gateway | [ bool](#bool) | [DEPRECATED] Whether the modem is connected to a modem configured as a gateway. Use `type` instead. |
| connected_to_gateway | [ string](#string) | [DEPRECATED] The modem number that this modem is connected to, if any. Use `connected_device_info.connected_to_gateway` instead. |
| external_device_ids | [repeated string](#string) | [DEPRECATED] External device ids, if any. Use `connected_device_info.external_device_ids` instead. |
| type | [ hiber.modem.Modem.Type](#hibermodemmodemtype) | The type of modem. Used mainly to differentiate in the UI or to sort on. |
| gateway_info | [ hiber.modem.Modem.GatewayInfo](#hibermodemmodemgatewayinfo) | Additional information when this modem is a gateway. |
| connected_device_info | [ hiber.modem.Modem.ConnectedDeviceInfo](#hibermodemmodemconnecteddeviceinfo) | Additional information when this modem is a connected device. |
| metadata | [ google.protobuf.Struct](#googleprotobufstruct) | Modem metadata, typically extracted from messages. |
| time_zone | [ string](#string) | The timezone configured for the modem. |
| transmission_interval | [ hiber.Duration](#hiberduration) | The transmission interval for this modem, if configured. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **_expected_transmission_rate**.expected_transmission_rate | [optional hiber.value.Value.Numeric.Rate](#hibervaluevaluenumericrate) | The expected transmission rate for this modem. |

### hiber.modem.ModemSelection

Selection object for modems.
Filter modems by modem id, (child)organization, tags, activation status and time, service type and last message time.

| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [ hiber.Filter.Modems](#hiberfiltermodems) | none |
| free_text_search | [ string](#string) | none |
| only_active | [ bool](#bool) | Use lifecycle filter instead. |
| activated_in | [ hiber.TimeRange](#hibertimerange) | none |
| with_last_message_in | [ hiber.TimeRange](#hibertimerange) | none |
| health_levels | [repeated string](#string) | Filter modems by health level. |
| lifecycles | [repeated hiber.modem.Modem.Lifecycle](#hibermodemmodemlifecycle) | Filter modems by lifecycle(s). Defaults to nominal lifecycles, excluding disabled or decommissioned modems. |
| transfers | [ hiber.modem.ModemSelection.Transfers](#hibermodemmodemselectiontransfers) | none |
| include_types | [repeated hiber.modem.Modem.Type](#hibermodemmodemtype) | Only include modems that have a type listed in types. In other words, when providing multiple types, this is an "OR" relationship. |
| exclude_types | [repeated hiber.modem.Modem.Type](#hibermodemmodemtype) | Exclude modems that have a type listed in types. |
| device_types | [ hiber.Filter.DeviceTypes](#hiberfilterdevicetypes) | none |
| sensorBrands | [ hiber.Filter.SensorBrands](#hiberfiltersensorbrands) | none |
| identifiers | [ hiber.Filter.ModemIdentifiers](#hiberfiltermodemidentifiers) | none |
| only_gateways | [ bool](#bool) | [DEPRECATED] Only list devices that are a gateway. Replaced by `types`. If you only want to have gateways in the result, create a selection with only `Modem.Type.GATEWAY` for `types`. |
| only_has_external_device_ids | [ bool](#bool) | [DEPRECATED] Only list devices that are a connected devices. Typically these are LoRaWAN sensors. Replaced by `types`. If you only want to have connected devices in the result, create a selection with only `Modem.Type.CONNECTED_DEVICE` for `types`. |
| connected_to_gateways | [ hiber.Filter.Modems](#hiberfiltermodems) | none |
| external_device_ids | [repeated string](#string) | none |
| filter_by_tags | [ hiber.tag.TagSelection](#hibertagtagselection) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **peripheral_selection**.peripherals | [ hiber.modem.ModemSelection.Peripherals](#hibermodemmodemselectionperipherals) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **peripheral_selection**.only_without_peripheral | [ bool](#bool) | When set to true, only modems that do not have any peripheral will be included in the result. |
| only_connected_to_gateway | [ bool](#bool) | Only select modems that are connected to a gateway (connected devices). |
| not_connected_to_gateway | [ bool](#bool) | Only select modems that are not connected to a gateway (i.e. gateways). |


### Enums
#### hiber.modem.ListModemsRequest.Sort
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

#### hiber.modem.Modem.Lifecycle


| Name | Description | Number |
| ---- | ----------- | ------ |
| ACCEPTANCE_TESTING | Device is deployed, but not active yet. Invisible for customer. | 0 |
| INSTALLED | Device is active and sending messages. See health for more details on its health, based on the past messages. | 1 |
| PAUSED | Device is paused and not sending messages. This should be of a temporary nature. (e.g. a change to the installation is being made) | 6 |
| DISABLED | Device is disabled and not sending messages. Invisible for customer. This could be either temporary or become permanent. Used for cases where devices is being serviced and customer should not be burdened with the health of this device. | 5 |
| DECOMMISSIONED | Device is (going to be) removed from installation and will not return to installed status again. | 4 |
| DEFECTIVE | Device is defective and should not be used anymore. | 7 |

#### hiber.modem.Modem.Type
The effective type of this modem.
Type can depend on the hardware itself as well as network topology.

| Name | Description | Number |
| ---- | ----------- | ------ |
| OTHER | A device of which the specific type is not known | 0 |
| DISCONNECTED_SENSOR | A device that is not currently connected to a gateway. | 1 |
| GATEWAY | A device that can receive messages from sensors in the field and relay them (directly) to the satellite. Typically a LoRaWAN hub. Note that gateways also send messages themselves (e.g. a daily heartbeat). | 2 |
| SENSOR | A sensor that can (only) send data to a gateway. Typically using a LoRaWAN connection. | 3 |

#### hiber.modem.ModemMessage.Source


| Name | Description | Number |
| ---- | ----------- | ------ |
| HIBERBAND | A real message from a modem or gateway, sent over Hiberband to the server. | 0 |
| DIRECT_TO_API | A real message from a modem or gateway, sent directly to the API using a persistent connection. | 1 |
| TEST | A test message sent to the testing API. | 2 |
| SIMULATION | A simulated message, generated by the server. | 3 |

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

