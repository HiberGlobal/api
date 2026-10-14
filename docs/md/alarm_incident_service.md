# alarm_incident_service.proto

Service to list incidents for an alarm assigned to a device.

An incident is a series of messages that trigger the alarm, e.g. a period of time that pressure is above a threshold.

#### This file was generated from [alarm_incident_service.proto](https://github.com/HiberGlobal/api/blob/master/alarm_incident_service.proto).

## Table of Contents

- Services
  - [AlarmIncidentService](#alarmincidentservice)

- Messages
  - [ListAlarmIncidents](#listalarmincidents)
  - [ListAlarmIncidents.Request](#listalarmincidentsrequest)
  - [ListAlarmIncidents.Response](#listalarmincidentsresponse)

- Enums
  - [ListAlarmIncidents.Request.Sort](#listalarmincidentsrequestsort)

- Referenced messages from [alarm_incident.proto](#referenced-messages-from-alarm_incidentproto)
  - [hiber.alarm.AlarmIncident](#hiberalarmalarmincident)
  - [hiber.alarm.AlarmIncident.Alarm](#hiberalarmalarmincidentalarm)
  - [hiber.alarm.AlarmIncident.Device](#hiberalarmalarmincidentdevice)
  - [hiber.alarm.AlarmIncident.ErrorMessagesEntry](#hiberalarmalarmincidenterrormessagesentry)
  - [hiber.alarm.AlarmIncident.Update](#hiberalarmalarmincidentupdate)
  - [hiber.alarm.AlarmIncident.Update.ErrorMessagesEntry](#hiberalarmalarmincidentupdateerrormessagesentry)
  - [hiber.alarm.AlarmIncident.Update.PreviousErrorMessagesEntry](#hiberalarmalarmincidentupdatepreviouserrormessagesentry)
  - [hiber.alarm.AlarmIncidentSelection](#hiberalarmalarmincidentselection)

    - [hiber.alarm.AlarmIncident.Status](#hiberalarmalarmincidentstatus)

- Referenced messages from [event.proto](#referenced-messages-from-eventproto)
  - [hiber.event.BundledEvent](#hibereventbundledevent)
  - [hiber.event.BundledEvent.ApproximatedAmount](#hibereventbundledeventapproximatedamount)
  - [hiber.event.BundledEvent.ExactAmount](#hibereventbundledeventexactamount)
  - [hiber.event.Event](#hibereventevent)
  - [hiber.event.Event.AlarmEvent](#hibereventeventalarmevent)
  - [hiber.event.Event.AlarmEvent.AlarmIncidentEvent](#hibereventeventalarmeventalarmincidentevent)
  - [hiber.event.Event.AlarmEvent.AlarmTriggeredEvent](#hibereventeventalarmeventalarmtriggeredevent)
  - [hiber.event.Event.AlarmEvent.AlarmTriggeredEvent.ErrorMessagesEntry](#hibereventeventalarmeventalarmtriggeredeventerrormessagesentry)
  - [hiber.event.Event.AlarmEvent.CreatedEvent](#hibereventeventalarmeventcreatedevent)
  - [hiber.event.Event.AlarmEvent.DeletedEvent](#hibereventeventalarmeventdeletedevent)
  - [hiber.event.Event.AlarmEvent.UpdatedEvent](#hibereventeventalarmeventupdatedevent)
  - [hiber.event.Event.AlarmEvent.UpdatedEvent.Update](#hibereventeventalarmeventupdatedeventupdate)
  - [hiber.event.Event.AssignmentEvent](#hibereventeventassignmentevent)
  - [hiber.event.Event.AssignmentEvent.AssignedEvent](#hibereventeventassignmenteventassignedevent)
  - [hiber.event.Event.AssignmentEvent.UnassignedEvent](#hibereventeventassignmenteventunassignedevent)
  - [hiber.event.Event.Device](#hibereventeventdevice)
  - [hiber.event.Event.DeviceEvent](#hibereventeventdeviceevent)
  - [hiber.event.Event.DeviceEvent.DeviceCreatedEvent](#hibereventeventdeviceeventdevicecreatedevent)
  - [hiber.event.Event.DeviceEvent.DeviceInstalledEvent](#hibereventeventdeviceeventdeviceinstalledevent)
  - [hiber.event.Event.DeviceEvent.DeviceLocationUpdatedEvent](#hibereventeventdeviceeventdevicelocationupdatedevent)
  - [hiber.event.Event.DeviceEvent.DeviceUpdatedEvent](#hibereventeventdeviceeventdeviceupdatedevent)
  - [hiber.event.Event.DeviceEvent.DeviceUpdatedEvent.PeripheralsEntry](#hibereventeventdeviceeventdeviceupdatedeventperipheralsentry)
  - [hiber.event.Event.ExportEvent](#hibereventeventexportevent)
  - [hiber.event.Event.ExportEvent.ExportCreatedEvent](#hibereventeventexporteventexportcreatedevent)
  - [hiber.event.Event.ExportEvent.ExportFailedEvent](#hibereventeventexporteventexportfailedevent)
  - [hiber.event.Event.ExportEvent.ExportReadyEvent](#hibereventeventexporteventexportreadyevent)
  - [hiber.event.Event.MessageBodyParserEvent](#hibereventeventmessagebodyparserevent)
  - [hiber.event.Event.MessageBodyParserEvent.CreatedEvent](#hibereventeventmessagebodyparsereventcreatedevent)
  - [hiber.event.Event.MessageBodyParserEvent.DeletedEvent](#hibereventeventmessagebodyparsereventdeletedevent)
  - [hiber.event.Event.MessageBodyParserEvent.UpdatedEvent](#hibereventeventmessagebodyparsereventupdatedevent)
  - [hiber.event.Event.MessageEvent](#hibereventeventmessageevent)
  - [hiber.event.Event.MessageEvent.MessageBodyParsedEvent](#hibereventeventmessageeventmessagebodyparsedevent)
  - [hiber.event.Event.MessageEvent.MessageBodyReceivedEvent](#hibereventeventmessageeventmessagebodyreceivedevent)
  - [hiber.event.Event.MessageEvent.MessageCannotBeParsedEvent](#hibereventeventmessageeventmessagecannotbeparsedevent)
  - [hiber.event.Event.MessageEvent.MessageReceivedEvent](#hibereventeventmessageeventmessagereceivedevent)
  - [hiber.event.Event.OrganizationEvent](#hibereventeventorganizationevent)
  - [hiber.event.Event.OrganizationEvent.EventConfigurationUpdated](#hibereventeventorganizationeventeventconfigurationupdated)
  - [hiber.event.Event.OrganizationEvent.EventConfigurationUpdated.MessageSummaryUpdate](#hibereventeventorganizationeventeventconfigurationupdatedmessagesummaryupdate)
  - [hiber.event.Event.OrganizationEvent.MessageSummaryEvent](#hibereventeventorganizationeventmessagesummaryevent)
  - [hiber.event.Event.OrganizationEvent.MessageSummaryEvent.MessageCount](#hibereventeventorganizationeventmessagesummaryeventmessagecount)
  - [hiber.event.Event.OrganizationEvent.OrganizationCreatedEvent](#hibereventeventorganizationeventorganizationcreatedevent)
  - [hiber.event.Event.OrganizationEvent.OrganizationDeletedEvent](#hibereventeventorganizationeventorganizationdeletedevent)
  - [hiber.event.Event.OrganizationEvent.OrganizationUpdatedEvent](#hibereventeventorganizationeventorganizationupdatedevent)
  - [hiber.event.Event.ProcessPointEvent](#hibereventeventprocesspointevent)
  - [hiber.event.Event.ProcessPointEvent.ProcessPointCreatedEvent](#hibereventeventprocesspointeventprocesspointcreatedevent)
  - [hiber.event.Event.ProcessPointEvent.ProcessPointDeletedEvent](#hibereventeventprocesspointeventprocesspointdeletedevent)
  - [hiber.event.Event.ProcessPointEvent.ProcessPointUpdatedEvent](#hibereventeventprocesspointeventprocesspointupdatedevent)
  - [hiber.event.Event.ProcessPointEvent.ProcessPointUpdatedEvent.Update](#hibereventeventprocesspointeventprocesspointupdatedeventupdate)
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
  - [hiber.event.Event.UserEvent.UserPermissionsUpdatedEvent](#hibereventeventusereventuserpermissionsupdatedevent)
  - [hiber.event.Event.UserEvent.UserRemovedEvent](#hibereventeventusereventuserremovedevent)
  - [hiber.event.Event.UserEvent.UserUpdatedEvent](#hibereventeventusereventuserupdatedevent)
  - [hiber.event.Event.UserEvent.UserValidationUpdatedEvent](#hibereventeventusereventuservalidationupdatedevent)
  - [hiber.event.Event.ValueEvent](#hibereventeventvalueevent)
  - [hiber.event.EventConfiguration](#hibereventeventconfiguration)
  - [hiber.event.EventConfiguration.EventHealthLevelConfiguration](#hibereventeventconfigurationeventhealthlevelconfiguration)
  - [hiber.event.EventConfiguration.MessageSummaryConfiguration](#hibereventeventconfigurationmessagesummaryconfiguration)
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
  - [hiber.IntRange](#hiberintrange)
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
  - [hiber.TimeWindow](#hibertimewindow)
  - [hiber.TimeWindow.CalendarWindow](#hibertimewindowcalendarwindow)
  - [hiber.TimeWindow.IntervalWindow](#hibertimewindowintervalwindow)
  - [hiber.Timestamp](#hibertimestamp)
  - [hiber.UpdateBoolean](#hiberupdateboolean)
  - [hiber.UpdateClearableString](#hiberupdateclearablestring)
  - [hiber.UpdateOptionalDuration](#hiberupdateoptionalduration)
  - [hiber.UpdateOptionalId](#hiberupdateoptionalid)
  - [hiber.UpdateZeroableInt](#hiberupdatezeroableint)
  - Enums
    - [hiber.CalendarPeriod](#hibercalendarperiod)
    - [hiber.EventType](#hibereventtype)
    - [hiber.Health](#hiberhealth)
    - [hiber.UnitOfMeasurement](#hiberunitofmeasurement)

- [Scalar Value Types](#scalar-value-types)


## AlarmIncidentService


### List
> **rpc** List([ListAlarmIncidents.Request](#listalarmincidentsrequest))
    [ListAlarmIncidents.Response](#listalarmincidentsresponse)

List alarm incidents.


## Messages

### ListAlarmIncidents

List alarm incidents in an organization.
Does not include resolved incidents by default.


### ListAlarmIncidents.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional AlarmIncidentSelection](#alarmincidentselection) | Selection of alarm incidents. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) | Pagination for the returned alarm incidents. |
|  **optional** sort_incidents | [optional ListAlarmIncidents.Request.Sort](#listalarmincidentsrequestsort) | How to sort the returned alarm incidents. |
|  **optional** sort_history | [optional hiber.event.ListEventsRequest.Sort](#hibereventlisteventsrequestsort) | How to sort the history for the returned alarm incidents. |

### ListAlarmIncidents.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| incidents | [repeated AlarmIncident](#alarmincident) | A list of alarm incidents. |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | A pagination object, which can be used to go through the incidents. |
| request | [ ListAlarmIncidents.Request](#listalarmincidentsrequest) | The request made to list the given incidents. |


## Enums
### ListAlarmIncidents.Request.Sort


| Name | Description | Number |
| ---- | ----------- | ------ |
| CREATED_DESC | Most recent incidents first. | 0 |
| CREATED_ASC | Oldest incidents first. | 1 |
| RESOLVED_DESC | Most recently resolved incidents first. | 2 |
| RESOLVED_ASC | Most recently resolved incidents last. | 3 |
| DURATION | Longest duration incidents first. | 4 |



## Referenced messages from alarm_incident.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [alarm_incident.proto](https://github.com/HiberGlobal/api/blob/master/alarm_incident.proto).


### hiber.alarm.AlarmIncident

Incident for an alarm assigned to a device.

An incident is a series of messages that trigger the alarm, e.g. a period of time that pressure is above a threshold.

The incident goes through a set of statuses, from started to resolved,
and tracks the health and error messages during that period.

When the status changes, an alarm incident event is produced.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) | Unique identifier for this incident. |
| alarm | [ hiber.alarm.AlarmIncident.Alarm](#hiberalarmalarmincidentalarm) | The alarm that produced the incident. |
| device | [ hiber.alarm.AlarmIncident.Device](#hiberalarmalarmincidentdevice) | The device that caused the incident. |
| status | [ hiber.alarm.AlarmIncident.Status](#hiberalarmalarmincidentstatus) | The status of the incident. |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The health caused by this incident. If this is RESOLVED, the last health caused by this incident before it was resolved. |
| error_messages | [map hiber.alarm.AlarmIncident.ErrorMessagesEntry](#hiberalarmalarmincidenterrormessagesentry) | The error messages for this incident. If this is RESOLVED, the error messages for this incident before it was resolved. |
| timeline | [repeated hiber.alarm.AlarmIncident.Update](#hiberalarmalarmincidentupdate) | History of events for this incident, tracking, for example, when it started and when it was resolved. |

### hiber.alarm.AlarmIncident.Alarm

The alarm that produced the incident.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) |  |
| name | [ string](#string) |  |
| description | [ string](#string) |  |

### hiber.alarm.AlarmIncident.Device

The device that caused the incident.

| Field | Type | Description |
| ----- | ---- | ----------- |
| number | [ string](#string) |  |
| identifier | [ string](#string) |  |
| name | [ string](#string) |  |
| device_type | [ string](#string) |  |
| lifecycle | [ hiber.modem.Modem.Lifecycle](#hibermodemmodemlifecycle) |  |

### hiber.alarm.AlarmIncident.ErrorMessagesEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ string](#string) |  |

### hiber.alarm.AlarmIncident.Update

The history for this incident.

| Field | Type | Description |
| ----- | ---- | ----------- |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
|  **optional** previous_status | [optional hiber.alarm.AlarmIncident.Status](#hiberalarmalarmincidentstatus) |  |
| status | [ hiber.alarm.AlarmIncident.Status](#hiberalarmalarmincidentstatus) |  |
|  **optional** previous_health_level | [optional hiber.health.HealthLevel](#hiberhealthhealthlevel) |  |
|  **optional** health_level | [optional hiber.health.HealthLevel](#hiberhealthhealthlevel) |  |
| previous_error_messages | [map hiber.alarm.AlarmIncident.Update.PreviousErrorMessagesEntry](#hiberalarmalarmincidentupdatepreviouserrormessagesentry) |  |
| error_messages | [map hiber.alarm.AlarmIncident.Update.ErrorMessagesEntry](#hiberalarmalarmincidentupdateerrormessagesentry) |  |

### hiber.alarm.AlarmIncident.Update.ErrorMessagesEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ string](#string) |  |

### hiber.alarm.AlarmIncident.Update.PreviousErrorMessagesEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ string](#string) |  |

### hiber.alarm.AlarmIncidentSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** search | [optional string](#string) | Search incident text, including identifier, alarm, device, error messages and status. |
| incident_identifier | [repeated string](#string) | Select incidents by identifier. |
|  **optional** alarms | [optional hiber.modem.alarm.ModemAlarmSelection](#hibermodemalarmmodemalarmselection) | Select incidents by alarm. |
|  **optional** devices | [optional hiber.modem.ModemSelection](#hibermodemmodemselection) | Select incidents by device. |
| current_status | [repeated hiber.alarm.AlarmIncident.Status](#hiberalarmalarmincidentstatus) | Select incidents that currently have one of the given statuses. |
| health_levels | [repeated string](#string) | Select incidents with a given health level. |
|  **optional** include_resolved | [optional bool](#bool) | By default, incidents that have been resolved are not listed. Set this to include them. |


### Enums
#### hiber.alarm.AlarmIncident.Status
The status of the incident.

| Name | Description | Number |
| ---- | ----------- | ------ |
| STARTED | The incident has started, no changes since that moment. | 0 |
| UPDATED | Since the incident started, some of the error messages changed significantly. | 1 |
| ESCALATED | Since the incident started, the health changed. | 2 |
| RESOLVED | The incident has resolved. | 3 |



## Referenced messages from event.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [event.proto](https://github.com/HiberGlobal/api/blob/master/event.proto).


### hiber.event.BundledEvent

A bundle/set of events, all of the same event-type.

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.EventType](#hibereventtype) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **amount**.exact_amount | [ hiber.event.BundledEvent.ExactAmount](#hibereventbundledeventexactamount) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **amount**.approximated_amount | [ hiber.event.BundledEvent.ApproximatedAmount](#hibereventbundledeventapproximatedamount) |  |
| deprecated_amount | [ int32](#int32) | <span class="deprecated deprecated-field">Deprecated</span> Deprecated in favour of using the amount field that is either an ExactAmount or ApproximatedAmount |
| deprecated_last_event | [ hiber.Timestamp](#hibertimestamp) | <span class="deprecated deprecated-field">Deprecated</span> Deprecated in favour of using the amount field that is either an ExactAmount or ApproximatedAmount. since `last_event` is not available when using approximation (we don't know the actual last event), this field is only present when getting an ExactAmount. |
| deprecated_approximated_amount | [ bool](#bool) | <span class="deprecated deprecated-field">Deprecated</span> Indicates that the amount is an approximation, and not an exact value. Some events will be approximated to avoid a large number of events affecting the request time. Deprecated in favour of using the oneof_amount field that is either an ExactAmount or ApproximatedAmount |

### hiber.event.BundledEvent.ApproximatedAmount

Indicates that the amount is an approximation, and not an exact value.
Some events will be approximated to avoid a large number of events affecting the request time.
Because of the nature of approximation, we don't have a "last" event, so no timestamp is available.

| Field | Type | Description |
| ----- | ---- | ----------- |
| amount | [ int32](#int32) |  |

### hiber.event.BundledEvent.ExactAmount

Indicates that the amount is an exact count, and not an approximated value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| amount | [ int32](#int32) |  |
| last_event | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event

Generic Event object, used in streams where events are mixed. Protobuf provides helper methods to extract
the contained object.

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.EventType](#hibereventtype) | Time of the event. |
| time | [ hiber.Timestamp](#hibertimestamp) | Time of the event. |
| is_error | [ bool](#bool) | <span class="deprecated deprecated-field">Deprecated</span> Whether this event causes the 'Error' health level. If your organization does not use the default health levels, this field will be omitted. Use health_level instead. |
| is_warning | [ bool](#bool) | <span class="deprecated deprecated-field">Deprecated</span> Whether this event causes the 'Warning' health level. If your organization does not use the default health levels, this field will be omitted. Use health_level instead. |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The health level caused by this event. This health generally applies to either a device, a token or a publisher, and is also applied to the organization health. Not every event affects health, so this field might be empty. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **resolved_status**.resolved | [ bool](#bool) | Whether this event was resolved. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **resolved_status**.resolve_identifier | [ string](#string) | The identifier to use when resolving this event. Only present when not resolved, and only available for some event types. |
| title | [ string](#string) | Short text describing the event. |
| description | [ string](#string) | Longer text describing the event in more detail. |
| device | [ hiber.event.Event.Device](#hibereventeventdevice) | The device data for this event, if it is related to a single device. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | The tags for this event, if any. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.process_point_created | [ hiber.event.Event.ProcessPointEvent.ProcessPointCreatedEvent](#hibereventeventprocesspointeventprocesspointcreatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.process_point_updated | [ hiber.event.Event.ProcessPointEvent.ProcessPointUpdatedEvent](#hibereventeventprocesspointeventprocesspointupdatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.process_point_deleted | [ hiber.event.Event.ProcessPointEvent.ProcessPointDeletedEvent](#hibereventeventprocesspointeventprocesspointdeletedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.device_created | [ hiber.event.Event.DeviceEvent.DeviceCreatedEvent](#hibereventeventdeviceeventdevicecreatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.device_updated | [ hiber.event.Event.DeviceEvent.DeviceUpdatedEvent](#hibereventeventdeviceeventdeviceupdatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.device_location_updated | [ hiber.event.Event.DeviceEvent.DeviceLocationUpdatedEvent](#hibereventeventdeviceeventdevicelocationupdatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.device_installed | [ hiber.event.Event.DeviceEvent.DeviceInstalledEvent](#hibereventeventdeviceeventdeviceinstalledevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.message_received | [ hiber.event.Event.MessageEvent.MessageReceivedEvent](#hibereventeventmessageeventmessagereceivedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.message_body_received | [ hiber.event.Event.MessageEvent.MessageBodyReceivedEvent](#hibereventeventmessageeventmessagebodyreceivedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.message_body_parsed | [ hiber.event.Event.MessageEvent.MessageBodyParsedEvent](#hibereventeventmessageeventmessagebodyparsedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.message_cannot_be_parsed | [ hiber.event.Event.MessageEvent.MessageCannotBeParsedEvent](#hibereventeventmessageeventmessagecannotbeparsedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.message_body_parser_created | [ hiber.event.Event.MessageBodyParserEvent.CreatedEvent](#hibereventeventmessagebodyparsereventcreatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.message_body_parser_updated | [ hiber.event.Event.MessageBodyParserEvent.UpdatedEvent](#hibereventeventmessagebodyparsereventupdatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.message_body_parser_deleted | [ hiber.event.Event.MessageBodyParserEvent.DeletedEvent](#hibereventeventmessagebodyparsereventdeletedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.alarm_triggered | [ hiber.event.Event.AlarmEvent.AlarmTriggeredEvent](#hibereventeventalarmeventalarmtriggeredevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.alarm_incident | [ hiber.event.Event.AlarmEvent.AlarmIncidentEvent](#hibereventeventalarmeventalarmincidentevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.alarm_created | [ hiber.event.Event.AlarmEvent.CreatedEvent](#hibereventeventalarmeventcreatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.alarm_updated | [ hiber.event.Event.AlarmEvent.UpdatedEvent](#hibereventeventalarmeventupdatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.alarm_deleted | [ hiber.event.Event.AlarmEvent.DeletedEvent](#hibereventeventalarmeventdeletedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.assigned | [ hiber.event.Event.AssignmentEvent.AssignedEvent](#hibereventeventassignmenteventassignedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.unassigned | [ hiber.event.Event.AssignmentEvent.UnassignedEvent](#hibereventeventassignmenteventunassignedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.user_added | [ hiber.event.Event.UserEvent.UserAddedEvent](#hibereventeventusereventuseraddedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.user_removed | [ hiber.event.Event.UserEvent.UserRemovedEvent](#hibereventeventusereventuserremovedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.user_updated | [ hiber.event.Event.UserEvent.UserUpdatedEvent](#hibereventeventusereventuserupdatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.user_invited | [ hiber.event.Event.UserEvent.UserInvitedEvent](#hibereventeventusereventuserinvitedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.user_access_request | [ hiber.event.Event.UserEvent.UserAccessRequestEvent](#hibereventeventusereventuseraccessrequestevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.user_validation_updated | [ hiber.event.Event.UserEvent.UserValidationUpdatedEvent](#hibereventeventusereventuservalidationupdatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.user_permissions_updated | [ hiber.event.Event.UserEvent.UserPermissionsUpdatedEvent](#hibereventeventusereventuserpermissionsupdatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.transfer | [ hiber.event.Event.TransferEvent](#hibereventeventtransferevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.token_expiry_warning | [ hiber.event.Event.TokenEvent.TokenExpiryWarningEvent](#hibereventeventtokeneventtokenexpirywarningevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.token_expired | [ hiber.event.Event.TokenEvent.TokenExpiredEvent](#hibereventeventtokeneventtokenexpiredevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.token_created | [ hiber.event.Event.TokenEvent.TokenCreatedEvent](#hibereventeventtokeneventtokencreatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.token_deleted | [ hiber.event.Event.TokenEvent.TokenDeletedEvent](#hibereventeventtokeneventtokendeletedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.organization_created | [ hiber.event.Event.OrganizationEvent.OrganizationCreatedEvent](#hibereventeventorganizationeventorganizationcreatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.organization_updated | [ hiber.event.Event.OrganizationEvent.OrganizationUpdatedEvent](#hibereventeventorganizationeventorganizationupdatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.organization_deleted | [ hiber.event.Event.OrganizationEvent.OrganizationDeletedEvent](#hibereventeventorganizationeventorganizationdeletedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.message_summary | [ hiber.event.Event.OrganizationEvent.MessageSummaryEvent](#hibereventeventorganizationeventmessagesummaryevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.organization_event_configuration_updated | [ hiber.event.Event.OrganizationEvent.EventConfigurationUpdated](#hibereventeventorganizationeventeventconfigurationupdated) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.publisher_created | [ hiber.event.Event.PublisherEvent.CreatedEvent](#hibereventeventpublishereventcreatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.publisher_updated | [ hiber.event.Event.PublisherEvent.UpdatedEvent](#hibereventeventpublishereventupdatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.publisher_deleted | [ hiber.event.Event.PublisherEvent.DeletedEvent](#hibereventeventpublishereventdeletedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.publisher_auto_disabled | [ hiber.event.Event.PublisherEvent.AutoDisabledEvent](#hibereventeventpublishereventautodisabledevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.publisher_failed | [ hiber.event.Event.PublisherEvent.FailedEvent](#hibereventeventpublishereventfailedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.export_created | [ hiber.event.Event.ExportEvent.ExportCreatedEvent](#hibereventeventexporteventexportcreatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.export_ready | [ hiber.event.Event.ExportEvent.ExportReadyEvent](#hibereventeventexporteventexportreadyevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.export_failed | [ hiber.event.Event.ExportEvent.ExportFailedEvent](#hibereventeventexporteventexportfailedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.value | [ hiber.event.Event.ValueEvent](#hibereventeventvalueevent) |  |

### hiber.event.Event.AlarmEvent




### hiber.event.Event.AlarmEvent.AlarmIncidentEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| incident_identifier | [ string](#string) |  |
| alarm | [ hiber.alarm.AlarmIncident.Alarm](#hiberalarmalarmincidentalarm) | The alarm that produced the incident. |
| device | [ hiber.alarm.AlarmIncident.Device](#hiberalarmalarmincidentdevice) | The device that caused the incident. |
| details | [ hiber.alarm.AlarmIncident.Update](#hiberalarmalarmincidentupdate) | The status of the incident. |
|  **optional** message_id | [optional uint64](#uint64) | The id of the message that triggered this incident event, if any. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.AlarmEvent.AlarmTriggeredEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| device_number | [ string](#string) |  |
| device_external_device_id | [ string](#string) |  |
| message_id | [ uint64](#uint64) | The id of the device that triggered the alarm, if any. |
| alarm_identifier | [ string](#string) | The identifier of the alarm. |
| alarm_description | [ string](#string) | The description of the alarm. |
| error_messages | [map hiber.event.Event.AlarmEvent.AlarmTriggeredEvent.ErrorMessagesEntry](#hibereventeventalarmeventalarmtriggeredeventerrormessagesentry) | The filled in error message(s) for the failing checks in the alarm. |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The highest health level caused by the failing checks in this alarm, for the device (and organization). |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **resolved_status**.resolved_at | [ hiber.Timestamp](#hibertimestamp) | Whether this event was resolved. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **resolved_status**.resolve_identifier | [ string](#string) | The identifier to use when resolving this event. Only present when not resolved |
| health_level_after_resolved | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | Optional health that this alarm event causes after it has been resolved. |
| health_level_after_resolved_until | [ hiber.Timestamp](#hibertimestamp) | How long the optional health that this alarm event causes after it has been resolved lasts. |

### hiber.event.Event.AlarmEvent.AlarmTriggeredEvent.ErrorMessagesEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ string](#string) |  |

### hiber.event.Event.AlarmEvent.CreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| created | [ hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.AlarmEvent.DeletedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| deleted | [ string](#string) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.AlarmEvent.UpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| updated | [ hiber.event.Event.AlarmEvent.UpdatedEvent.Update](#hibereventeventalarmeventupdatedeventupdate) |  |
| alarm_identifier | [ string](#string) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.AlarmEvent.UpdatedEvent.Update



| Field | Type | Description |
| ----- | ---- | ----------- |
| deprecated_description | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <span class="deprecated deprecated-field">Deprecated</span>  |
|  **optional** description | [optional string](#string) |  |
| trigger_condition | [ string](#string) |  |
| checks | [ google.protobuf.Struct](#googleprotobufstruct) |  |
| update_default_health_level | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <span class="deprecated deprecated-field">Deprecated</span>  |
|  **optional** updated_default_health_level | [optional string](#string) |  |
| update_health_level_after_resolved | [ hiber.modem.alarm.ModemAlarm.HealthLevelAfterResolved](#hibermodemalarmmodemalarmhealthlevelafterresolved) |  |

### hiber.event.Event.AssignmentEvent




### hiber.event.Event.AssignmentEvent.AssignedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| created | [ hiber.assign.Assignment](#hiberassignassignment) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.AssignmentEvent.UnassignedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| removed | [ hiber.assign.Assignment](#hiberassignassignment) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.Device

The device data for this event, if it is related to a single device.

| Field | Type | Description |
| ----- | ---- | ----------- |
| number | [ string](#string) |  |
| name | [ string](#string) |  |
| identifier | [ string](#string) |  |

### hiber.event.Event.DeviceEvent




### hiber.event.Event.DeviceEvent.DeviceCreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| number | [ string](#string) |  |
| external_device_id | [ string](#string) | External device id for this device (e.g. a MAC address). |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |

### hiber.event.Event.DeviceEvent.DeviceInstalledEvent

When the device is marked as installed.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| number | [ string](#string) |  |
| external_device_id | [ string](#string) | External device id for this device (e.g. a MAC address). |
| time | [ hiber.Timestamp](#hibertimestamp) | The time this device was installed. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |

### hiber.event.Event.DeviceEvent.DeviceLocationUpdatedEvent

When a message comes in, the device's location is updated automatically. This event is generated whenever the
device's location is updated

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| number | [ string](#string) |  |
| external_device_id | [ string](#string) | External device id for this device (e.g. a MAC address). |
| location | [ hiber.Location](#hiberlocation) | The updated location for this device. |
| updated_at | [ hiber.Timestamp](#hibertimestamp) | The device time of the first message with the new location. |
| time | [ hiber.Timestamp](#hibertimestamp) | The time this event was generated on the server, after the message was received. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |

### hiber.event.Event.DeviceEvent.DeviceUpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| number | [ string](#string) |  |
| external_device_id | [ string](#string) | External device id for this device (e.g. a MAC address). |
| display_name | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <span class="deprecated deprecated-field">Deprecated</span>  |
|  **optional** updated_display_name | [optional string](#string) |  |
| peripherals | [map hiber.event.Event.DeviceEvent.DeviceUpdatedEvent.PeripheralsEntry](#hibereventeventdeviceeventdeviceupdatedeventperipheralsentry) |  |
| notes | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <span class="deprecated deprecated-field">Deprecated</span>  |
|  **optional** updated_notes | [optional string](#string) |  |
|  **optional** device_type | [optional string](#string) |  |
| secure_notes_updated | [ bool](#bool) |  |
| health_warning_period | [ hiber.Duration](#hiberduration) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |

### hiber.event.Event.DeviceEvent.DeviceUpdatedEvent.PeripheralsEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ string](#string) |  |

### hiber.event.Event.ExportEvent




### hiber.event.Event.ExportEvent.ExportCreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| export | [ hiber.export.Export](#hiberexportexport) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.ExportEvent.ExportFailedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| export | [ hiber.export.Export](#hiberexportexport) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.ExportEvent.ExportReadyEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| export | [ hiber.export.Export](#hiberexportexport) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.MessageBodyParserEvent

Events related to MessageBodyParsers.


### hiber.event.Event.MessageBodyParserEvent.CreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| created | [ hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.MessageBodyParserEvent.DeletedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| deleted | [ string](#string) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.MessageBodyParserEvent.UpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| updated_name | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <span class="deprecated deprecated-field">Deprecated</span>  |
|  **optional** name | [optional string](#string) |  |
| updated_content_ksy | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <span class="deprecated deprecated-field">Deprecated</span>  |
|  **optional** content_ksy | [optional string](#string) |  |
| updated_simple_parser | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser](#hibermodemmessagebodyparsersimplemodemmessagebodyparser) |  |
| updated_available_to_child_organizations | [ hiber.Filter.ChildOrganizations.Update](#hiberfilterchildorganizationsupdate) | <span class="deprecated deprecated-field">Deprecated</span>  |
|  **optional** available_to_child_organizations | [optional hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.MessageEvent




### hiber.event.Event.MessageEvent.MessageBodyParsedEvent

This event is generated whenever a message is parsed successfully by an assigned body parser.
If multiple body parsers are assigned to a device, multiple DeviceMessageBodyParsedEvent events will
be produced by an incoming message.
For the total result of all assigned parsers, see the DeviceMessageReceivedEvent, which is produced
after all body parsers have been applied.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| device_number | [ string](#string) |  |
| device_external_device_id | [ string](#string) | External device id for this device (e.g. a MAC address). |
| message_id | [ uint64](#uint64) | Id of the message that was parsed. |
| sent_at | [ hiber.Timestamp](#hibertimestamp) | Time the message was sent from the device. |
| parser_identifier | [ string](#string) | The identifier of the parser that parsed the body. |
| parser_name | [ string](#string) | The name of the parser that parsed the body. |
| parsed_message | [ google.protobuf.Struct](#googleprotobufstruct) | The resulting json from parsing the message body. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | The device's tags. |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.MessageEvent.MessageBodyReceivedEvent

This lightweight event is generated whenever a message comes in, after is has been decrypted.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| device_number | [ string](#string) |  |
| device_external_device_id | [ string](#string) | External device id for this device (e.g. a MAC address). |
| message_id | [ uint64](#uint64) | Id of the message that was parsed. |
| sent_at | [ hiber.Timestamp](#hibertimestamp) | Time the message was sent from the device. |
| body | [ hiber.BytesOrHex](#hiberbytesorhex) | Message body convenience object. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | The device's tags. |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.MessageEvent.MessageCannotBeParsedEvent

Triggered when a message cannot be parsed. This can have multiple reasons, for example, an invalid
message version.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| device_number | [ string](#string) |  |
| device_external_device_id | [ string](#string) | External device id for this device (e.g. a MAC address). |
| message_id | [ uint64](#uint64) | The message that cannot be parsed. This message may or may not be available in the system, depending one the reason it could not be parsed. |
| time | [ hiber.Timestamp](#hibertimestamp) | The moment this event was triggered. |
| reason | [ string](#string) | The reason this message could not be parsed. This could be, for example: - invalid message envelope, but with enough information to determine the device - all body parsers failed to parse the body of the message |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The health level caused for the device (and organization) by this event. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **resolved_status**.resolved | [ bool](#bool) | Whether this event was resolved. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **resolved_status**.resolve_identifier | [ string](#string) | The identifier to use when resolving this event. Only present when not resolved |

### hiber.event.Event.MessageEvent.MessageReceivedEvent

This event is generated whenever a message comes in, after is has been decrypted
and parsed (if any body parsers are configured for the device).

It contains the relevant data in the message object, including location and the
user-defined body.

If any body parser(s) are configured for the device, the device message object also contains
a ParsedBody for each of them.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| modem_number | [ string](#string) | <span class="deprecated deprecated-field">Deprecated</span>  |
| device_number | [ string](#string) |  |
| device_external_device_id | [ string](#string) | External device id for this device (e.g. a MAC address). |
| message | [ hiber.modem.ModemMessage](#hibermodemmodemmessage) | The received message, including parsed body. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | The device's tags. |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.OrganizationEvent




### hiber.event.Event.OrganizationEvent.EventConfigurationUpdated



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| message_summary_update | [ hiber.event.Event.OrganizationEvent.EventConfigurationUpdated.MessageSummaryUpdate](#hibereventeventorganizationeventeventconfigurationupdatedmessagesummaryupdate) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.OrganizationEvent.EventConfigurationUpdated.MessageSummaryUpdate



| Field | Type | Description |
| ----- | ---- | ----------- |
| enabled | [ hiber.UpdateBoolean](#hiberupdateboolean) | <span class="deprecated deprecated-field">Deprecated</span>  |
|  **optional** state | [optional bool](#bool) |  |
|  **optional** period | [optional hiber.Duration](#hiberduration) |  |
|  **optional** align_to_time | [optional hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.OrganizationEvent.MessageSummaryEvent

Message summary event that is sent when it has been configured for the organization.
The period is configurable, using the EventConfiguration.
This event is disabled by default.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| message_count | [repeated hiber.event.Event.OrganizationEvent.MessageSummaryEvent.MessageCount](#hibereventeventorganizationeventmessagesummaryeventmessagecount) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| time_range | [ hiber.TimeRange](#hibertimerange) |  |

### hiber.event.Event.OrganizationEvent.MessageSummaryEvent.MessageCount



| Field | Type | Description |
| ----- | ---- | ----------- |
| device | [ string](#string) |  |
| source | [ hiber.modem.ModemMessage.Source](#hibermodemmodemmessagesource) |  |
| amount | [ int32](#int32) |  |

### hiber.event.Event.OrganizationEvent.OrganizationCreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| parent_organization | [ string](#string) |  |
| created | [ hiber.organization.Organization](#hiberorganizationorganization) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.OrganizationEvent.OrganizationDeletedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| parent_organization | [ string](#string) |  |
| deleted_organization | [ string](#string) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.OrganizationEvent.OrganizationUpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
|  **optional** display_name_updated | [optional string](#string) |  |
|  **optional** vat_number_updated | [optional string](#string) |  |
|  **optional** address_updated | [optional hiber.organization.Organization.Address](#hiberorganizationorganizationaddress) |  |
| is_business_updated | [ hiber.UpdateBoolean](#hiberupdateboolean) | <span class="deprecated deprecated-field">Deprecated</span>  |
|  **optional** business_updated | [optional bool](#bool) |  |
|  **optional** billing_name_updated | [optional string](#string) |  |
|  **optional** billing_address_updated | [optional hiber.organization.Organization.Address](#hiberorganizationorganizationaddress) |  |
|  **optional** contact_updated | [optional hiber.organization.Organization.Contact](#hiberorganizationorganizationcontact) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| features_added | [repeated hiber.organization.Organization.Feature](#hiberorganizationorganizationfeature) |  |
| features_removed | [repeated hiber.organization.Organization.Feature](#hiberorganizationorganizationfeature) |  |

### hiber.event.Event.ProcessPointEvent




### hiber.event.Event.ProcessPointEvent.ProcessPointCreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| process_point_identifier | [ string](#string) |  |
| process_point | [ hiber.processpoint.ProcessPoint](#hiberprocesspointprocesspoint) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |

### hiber.event.Event.ProcessPointEvent.ProcessPointDeletedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| deleted | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |

### hiber.event.Event.ProcessPointEvent.ProcessPointUpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| updated | [ hiber.event.Event.ProcessPointEvent.ProcessPointUpdatedEvent.Update](#hibereventeventprocesspointeventprocesspointupdatedeventupdate) |  |
| process_point_identifier | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |

### hiber.event.Event.ProcessPointEvent.ProcessPointUpdatedEvent.Update



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** name | [optional string](#string) |  |
|  **optional** description | [optional string](#string) |  |
|  **optional** notes | [optional string](#string) |  |
|  **optional** time_zone | [optional string](#string) |  |
|  **optional** expected_transmission_rate | [optional uint32](#uint32) |  |
|  **optional** type | [optional hiber.processpoint.ProcessPoint.Type](#hiberprocesspointprocesspointtype) |  |
|  **optional** metadata | [optional google.protobuf.Struct](#googleprotobufstruct) |  |
|  **optional** location | [optional hiber.Location](#hiberlocation) |  |
| files | [repeated hiber.file.File](#hiberfilefile) |  |

### hiber.event.Event.PublisherEvent




### hiber.event.Event.PublisherEvent.AutoDisabledEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| id | [ int64](#int64) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The health level caused for the publisher (and organization) by this event. |

### hiber.event.Event.PublisherEvent.CreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| created | [ hiber.publisher.Publisher](#hiberpublisherpublisher) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.PublisherEvent.DeletedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| deleted | [ hiber.publisher.Publisher](#hiberpublisherpublisher) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.PublisherEvent.FailedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| reason | [ string](#string) |  |
| failed | [ hiber.publisher.Publisher](#hiberpublisherpublisher) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The health level caused for the publisher (and organization) by this event. |

### hiber.event.Event.PublisherEvent.UpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| deprecated_updated_description | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <span class="deprecated deprecated-field">Deprecated</span>  |
|  **optional** updated_description | [optional string](#string) |  |
| partial_update_data | [ hiber.publisher.Publisher.Data](#hiberpublisherpublisherdata) | <span class="deprecated deprecated-field">Deprecated</span> Deprecated in favor of the new updated_data field |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **updated_data**.webhook | [ hiber.event.Event.PublisherEvent.UpdatedEvent.WebhookUpdate](#hibereventeventpublishereventupdatedeventwebhookupdate) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **updated_data**.mqtt | [ hiber.event.Event.PublisherEvent.UpdatedEvent.MQTTUpdate](#hibereventeventpublishereventupdatedeventmqttupdate) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **updated_data**.email | [ hiber.event.Event.PublisherEvent.UpdatedEvent.EmailUpdate](#hibereventeventpublishereventupdatedeventemailupdate) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **updated_data**.slack | [ hiber.event.Event.PublisherEvent.UpdatedEvent.SlackUpdate](#hibereventeventpublishereventupdatedeventslackupdate) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **updated_data**.shell_ssip | [ hiber.event.Event.PublisherEvent.UpdatedEvent.ShellSsipUpdate](#hibereventeventpublishereventupdatedeventshellssipupdate) |  |
| deprecated_updated_event_filter | [ hiber.Filter.Events.Update](#hiberfiltereventsupdate) | <span class="deprecated deprecated-field">Deprecated</span>  |
|  **optional** updated_event_filter | [optional hiber.Filter.Events](#hiberfilterevents) |  |
| deprecated_updated_modem_filter | [ hiber.Filter.Modems.Update](#hiberfiltermodemsupdate) | <span class="deprecated deprecated-field">Deprecated</span>  |
|  **optional** updated_modem_filter | [optional hiber.Filter.Modems](#hiberfiltermodems) |  |
| deprecated_updated_tag_filter | [ hiber.Filter.Tags.Update](#hiberfiltertagsupdate) | <span class="deprecated deprecated-field">Deprecated</span>  |
|  **optional** updated_tag_filter | [optional hiber.Filter.Tags](#hiberfiltertags) |  |
| deprecated_updated_active_state | [ hiber.UpdateBoolean](#hiberupdateboolean) | <span class="deprecated deprecated-field">Deprecated</span>  |
|  **optional** updated_active_state | [optional bool](#bool) |  |
| health_warning_period | [ hiber.Duration](#hiberduration) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.PublisherEvent.UpdatedEvent.EmailUpdate




### hiber.event.Event.PublisherEvent.UpdatedEvent.MQTTUpdate



| Field | Type | Description |
| ----- | ---- | ----------- |
| url | [ string](#string) |  |
| content_type | [ hiber.integration.mqtt.MQTTPublisher.ContentType](#hiberintegrationmqttmqttpublishercontenttype) |  |
| topic | [ string](#string) |  |
| qos | [ hiber.integration.mqtt.MQTTPublisher.Data.QoS](#hiberintegrationmqttmqttpublisherdataqos) |  |
| deprecated_identifier | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <span class="deprecated deprecated-field">Deprecated</span>  |
|  **optional** identifier | [optional string](#string) |  |
| deprecated_username | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <span class="deprecated deprecated-field">Deprecated</span>  |
|  **optional** username | [optional string](#string) |  |
| deprecated_password | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <span class="deprecated deprecated-field">Deprecated</span>  |
|  **optional** password | [optional string](#string) |  |
| deprecated_certificate_id | [ hiber.UpdateOptionalId](#hiberupdateoptionalid) | <span class="deprecated deprecated-field">Deprecated</span>  |
|  **optional** certificate_id | [optional int64](#int64) |  |

### hiber.event.Event.PublisherEvent.UpdatedEvent.ShellSsipUpdate




### hiber.event.Event.PublisherEvent.UpdatedEvent.SlackUpdate




### hiber.event.Event.PublisherEvent.UpdatedEvent.WebhookUpdate



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** url | [optional string](#string) |  |
| deprecated_secret | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <span class="deprecated deprecated-field">Deprecated</span>  |
|  **optional** secret | [optional string](#string) |  |
|  **optional** content_type | [optional hiber.webhook.Webhook.ContentType](#hiberwebhookwebhookcontenttype) |  |
| deprecated_certificate_id | [ hiber.UpdateOptionalId](#hiberupdateoptionalid) | <span class="deprecated deprecated-field">Deprecated</span>  |
|  **optional** certificate_id | [optional int64](#int64) |  |

### hiber.event.Event.TokenEvent




### hiber.event.Event.TokenEvent.TokenCreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| token | [ hiber.token.Token](#hibertokentoken) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.TokenEvent.TokenDeletedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| token | [ hiber.token.Token](#hibertokentoken) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.TokenEvent.TokenExpiredEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| token | [ hiber.token.Token](#hibertokentoken) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.TokenEvent.TokenExpiryWarningEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| token | [ hiber.token.Token](#hibertokentoken) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The health level caused for the organization by this event. |

### hiber.event.Event.TransferEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| transfer | [ hiber.transfer.Transfer](#hibertransfertransfer) |  |

### hiber.event.Event.UserEvent




### hiber.event.Event.UserEvent.UserAccessRequestEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| user | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |

### hiber.event.Event.UserEvent.UserAddedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| user | [ string](#string) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.UserEvent.UserInvitedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| email | [ string](#string) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.UserEvent.UserPermissionsUpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| user | [ string](#string) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| actor | [ string](#string) |  |
| permissions_added | [repeated string](#string) |  |
| permissions_removed | [repeated string](#string) |  |
| roles_added | [repeated string](#string) |  |
| roles_removed | [repeated string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.UserEvent.UserRemovedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| user | [ string](#string) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.UserEvent.UserUpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| user | [ string](#string) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.UserEvent.UserValidationUpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| email_validation_regex | [ string](#string) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.event.Event.ValueEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| device_number | [ string](#string) | Number for the device that produced this value. |
| device_external_identifier | [ string](#string) | External device identifier (e.g. a MAC address) for the device that produced this value. |
| device_name | [ string](#string) | Name of the device that produced this value. |
| message_id | [ uint64](#uint64) | Id of the message that was parsed. |
| parser_identifier | [ string](#string) | The identifier of the parser that parsed the value. |
| field | [ string](#string) | The parser field the value was produced for. |
| process_point_identifier | [ string](#string) | Process point that this value belongs to. |
| process_point_name | [ string](#string) | Name of the process point that this value belongs to. |
| process_point_type | [ hiber.processpoint.ProcessPoint.Type](#hiberprocesspointprocesspointtype) | Name of the process point that this value belongs to. |
| value_time | [ hiber.Timestamp](#hibertimestamp) | When the value was measured, sent or received (first available option). |
| event_time | [ hiber.Timestamp](#hibertimestamp) | When the value event was created. This is typically different from the value time because of delays. |
| value | [ hiber.value.Value](#hibervaluevalue) | Actual value, with type and unit. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |

### hiber.event.EventConfiguration

Configuration for configurable events.
Some events are disable by default, or can be configured in different ways. Their configuration is available here.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| message_summary_configuration | [ hiber.event.EventConfiguration.MessageSummaryConfiguration](#hibereventeventconfigurationmessagesummaryconfiguration) |  |
| event_health_level_configuration | [repeated hiber.event.EventConfiguration.EventHealthLevelConfiguration](#hibereventeventconfigurationeventhealthlevelconfiguration) | List of event-types that have a health-level associated with them. Ignored when updating. |

### hiber.event.EventConfiguration.EventHealthLevelConfiguration

Details the health level configuration for an event-type.
Health of the system can be influenced by multiple things, among which certain events.
When an event that has health associated with it,
said health level will be applied to the part of the system it refers to.
For instance, an event about not being able to parse device messages, will influence device health.
An event about a failing parser, will affect parser health.

In general, when multiple events affect the health level of a subsystem,
the most severe health will be applied.

When an expiry duration is set, events will no longer affect health of the subsystem after the configured period.
Health levels reset to the least severe applicable level, typically "Ok".

For instance, an event might not be relevant anymore after 5 days.
By setting expiry to "5d", the event will resolve automatically 5 days after the last event happened.
Depending on other factors that influence device health,
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

### hiber.event.EventConfiguration.MessageSummaryConfiguration

When enabled, this sends a MessageSummaryEvent periodically.
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
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |

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
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional hiber.event.EventSelection](#hibereventeventselection) | Select the events to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |

### hiber.event.EventHistory.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ hiber.event.EventHistory.Request](#hibereventeventhistoryrequest) |  |
| events | [repeated hiber.event.Event](#hibereventevent) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### hiber.event.EventSelection

Selection object for Event list and stream. Filter events on device, webhook, time and error state, and
paginate the list.
Events are returned bundled by default. this means that, instead of the details, you get a list of bundles,
one per event type, with the count.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** events | [optional hiber.Filter.Events](#hiberfilterevents) |  |
|  **optional** modems | [optional hiber.Filter.Modems](#hiberfiltermodems) |  |
|  **optional** publishers | [optional hiber.Filter.Publishers](#hiberfilterpublishers) |  |
|  **optional** tags | [optional hiber.Filter.Tags](#hiberfiltertags) |  |
|  **optional** time_range | [optional hiber.TimeRange](#hibertimerange) |  |
| alarm_identifiers | [repeated string](#string) | Filter events by alarm identifier(s). |
| alarm_incident_identifiers | [repeated string](#string) | Filter events by alarm incident identifier(s). |
| health_levels | [repeated string](#string) | Filter events by actual configured health level. |
|  **optional** include_resolved_events | [optional bool](#bool) | By default, events that have been resolved are not listed. |
|  **optional** unbundled_events | [optional bool](#bool) | <span class="deprecated deprecated-field">Deprecated</span> When not set, no unbundled events are returned. When set, returns unbundled events per type, paginated per type. Deprecated: use unbundled_events on ListEventsRequest |
|  **optional** errors_only | [optional bool](#bool) | <span class="deprecated deprecated-field">Deprecated</span> Return only events that cause the default Error health. Deprecated: use health_levels with custom health levels instead. |
|  **optional** warnings_only | [optional bool](#bool) | <span class="deprecated deprecated-field">Deprecated</span> Return only events that cause the default Warning health. Deprecated: use health_levels with custom health levels instead. |

### hiber.event.EventStreamRequest

Creates a stream for new events, matching the provided selection.

Note: streams are limited to one per user due to GRPC limitations.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional hiber.event.EventSelection](#hibereventeventselection) | Select the events to stream. Optional, when omitted or empty everything is included. |
|  **optional** child_organizations | [optional hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | Include events from child organizations, if requested. This is only available for streaming, listing events can only be listed per organization. Keep in mind that filtering events using the selection is limited. Filtering on tags or publishers, for example, can only apply to the parent organization. |

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
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional hiber.event.EventSelection](#hibereventeventselection) | Select the events to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) | Pagination is applied per event type on unbundled events. It is not necessary for bundled events. |
|  **optional** sort | [optional hiber.event.ListEventsRequest.Sort](#hibereventlisteventsrequestsort) |  |
|  **optional** unbundled_events | [optional bool](#bool) | When not set, bundled/grouped events are returned. When set, returns unbundled events per type, paginated per type. Overrides unbundled_events in EventSelection message. |

### hiber.event.ListEventsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ hiber.event.ListEventsRequest](#hibereventlisteventsrequest) |  |
| events | [repeated hiber.event.BundledEvent](#hibereventbundledevent) |  |
| unbundled_events | [repeated hiber.event.ListEventsRequest.Response.EventTypeResponse](#hibereventlisteventsrequestresponseeventtyperesponse) |  |

### hiber.event.ListEventsRequest.Response.EventTypeResponse



| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.EventType](#hibereventtype) |  |
| unbundled_events | [repeated hiber.event.Event](#hibereventevent) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### hiber.event.MarkEventsResolved

Mark a selection of events as resolved.


### hiber.event.MarkEventsResolved.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.event.EventSelection](#hibereventeventselection) | Selection of events to resolve. |

### hiber.event.MarkEventsResolved.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| resolved | [ uint32](#uint32) | The amount of events that were resolved. |
| request | [ hiber.event.MarkEventsResolved.Request](#hibereventmarkeventsresolvedrequest) | The original request, echoed back with any applied corrections. |

### hiber.event.ModemHealthEvents

Get the list of events that affect device health, chronologically (by default, from now backwards in time).

Only returns the Event with first-level fields set, event details are not included in the response
(the oneof is not set).


### hiber.event.ModemHealthEvents.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional hiber.event.EventSelection](#hibereventeventselection) | Select the events to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |

### hiber.event.ModemHealthEvents.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ hiber.event.ModemHealthEvents.Request](#hibereventmodemhealtheventsrequest) |  |
| events | [repeated hiber.event.Event](#hibereventevent) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### hiber.event.ResolveEvent

Resolve a resolvable event using its resolve_identifier.


### hiber.event.ResolveEvent.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| resolve_identifier | [ string](#string) | The resolve identifier of the event you wish to resolve. |

### hiber.event.ResolveEvent.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| resolved | [ uint32](#uint32) | The amount of events that were resolved. |

### hiber.event.UpdateEventHealthConfiguration




### hiber.event.UpdateEventHealthConfiguration.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
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
|  **optional** expiry | [optional hiber.Duration](#hiberduration) | After the expiry duration, the event will not affect health anymore. Clear for manual resolving of events. |
| deprecated_expiry | [ hiber.UpdateOptionalDuration](#hiberupdateoptionalduration) | <span class="deprecated deprecated-field">Deprecated</span>  |


### Enums
#### hiber.event.ListEventsRequest.Sort


| Name | Description | Number |
| ---- | ----------- | ------ |
| TIME_DESCENDING |  | 0 |
| TIME_ASCENDING |  | 1 |
| DEVICE_NUMBER_ASC |  | 2 |
| DEVICE_NUMBER_DESC |  | 3 |
| DEVICE_NUMBER_SPECIFIED |  | 4 |



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

### hiber.IntRange



| Field | Type | Description |
| ----- | ---- | ----------- |
| start | [ uint32](#uint32) |  |
| end | [ uint32](#uint32) |  |

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
|  **optional** items_on_page | [optional hiber.IntRange](#hiberintrange) | The indices of the first and last items on the page, if any. For example, on the second page of size 10, this is 11 - 20. |

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

### hiber.TimeWindow

Time window to split a time range, e.g. per hour, per day, per week, etc.

| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **window**.interval | [ hiber.TimeWindow.IntervalWindow](#hibertimewindowintervalwindow) | Simple interval to use for windowing, e.g. every 2 hours or 24 hours or 5 minutes. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **window**.calendar | [ hiber.TimeWindow.CalendarWindow](#hibertimewindowcalendarwindow) | Calendar-based time window to use for windowing, e.g. per day, week, month, etc, for a given time zone. |

### hiber.TimeWindow.CalendarWindow

Calendar-based time window to use for windowing, e.g. per day, week, month, etc, for a given time zone.

| Field | Type | Description |
| ----- | ---- | ----------- |
| window | [ hiber.CalendarPeriod](#hibercalendarperiod) | The calendar-based window to use, e.g. daily or monthly. |
| time_zone | [ string](#string) | The time zone to use for the calendar window. |

### hiber.TimeWindow.IntervalWindow

Interval-based time window to use for windowing, e.g. every 2 hours or 24 hours or 5 minutes.

| Field | Type | Description |
| ----- | ---- | ----------- |
| interval | [ hiber.Duration](#hiberduration) | Simple interval to use for windowing, e.g. every 2 hours or 24 hours or 5 minutes. |
|  **optional** align_to | [optional hiber.Timestamp](#hibertimestamp) | Alignment for the interval repetition, e.g. every 5 minutes from 12:03 (resulting in 12:08, 12:13, etc). Defaults to any given time in the request where this is used, or else midnight today in UTC. |

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
#### hiber.CalendarPeriod
A period of time represented on a calendar, in a time zone.
Includes DST transitions, meaning that DAY can be 23 or 25 hours, etc.

| Name | Description | Number |
| ---- | ----------- | ------ |
| CALENDAR_PERIOD_UNSPECIFIED | Undefined period, raises an error. | 0 |
| DAY | A day on the calendar, in a given time zone. Not guaranteed to be 24 hours (e.g. around DST transitions). | 1 |
| WEEK | A week. Weeks begin on Monday, following [ISO 8601](https://en.wikipedia.org/wiki/ISO_week_date). For a week starting on Sunday, use WEEK_STARTING_SUNDAY. | 2 |
| WEEK_STARTING_SUNDAY | A week, starting on Sunday. For a week starting on Monday, use WEEK. | 3 |
| MONTH | A month. | 4 |
| QUARTER | A quarter. Quarters start on dates 1-Jan, 1-Apr, 1-Jul, and 1-Oct of each year. | 5 |
| HALF | A half-year. Half-years start on dates 1-Jan and 1-Jul. | 6 |
| YEAR | A year. | 7 |

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
| PROCESS_POINT_CREATED | A new process point was created in your organization. | 73 |
| PROCESS_POINT_UPDATED | An process point in your organization was updated (e.g. renamed, tagged). | 74 |
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
| ALARM_INCIDENT | An alarm incident in your organizations. Represents the moment the incident started and ended (chain of ALARM_TRIGGERED). Depending on the alarm, this may mean that a device sent a (series of) message(s) with a value (e.g. pressure) outside of the expected range, or moved out of the expected area. | 81 |
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
| USER_UPDATED | A user was updated | 60 |
| USER_PERMISSIONS_UPDATED | A user's permissions and/or roles were updated | 61 |
| TOKEN_CREATED | A new token was created for your organization. | 31 |
| TOKEN_EXPIRY_WARNING | A token in your organization will expire within 2 weeks. | 25 |
| TOKEN_EXPIRED | A token in your organization has expired. | 26 |
| TOKEN_DELETED | A token in your organization was deleted. | 32 |
| EXPORT_CREATED | A new export was started for your organization, exporting data (e.g. messages) to a file. | 65 |
| EXPORT_READY | An export in your organization has completed and the resulting file with data (e.g. messages as CSV) is ready to be downloaded. | 66 |
| EXPORT_FAILED | An export in your organization has failed (typically because of incorrect data selection). | 67 |
| VALUE | A new value. | 80 |

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
| ANGLE_DEGREES_ARC |  | 56 |

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

