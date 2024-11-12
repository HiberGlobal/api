# event.proto



#### This file was generated from [event.proto](https://github.com/HiberGlobal/api/blob/master/event.proto).

## Table of Contents

- Services
  - [EventService](#eventservice)

- Messages
  - [BundledEvent](#bundledevent)
  - [BundledEvent.ApproximatedAmount](#bundledeventapproximatedamount)
  - [BundledEvent.ExactAmount](#bundledeventexactamount)
  - [Event](#event)
  - [Event.AlarmEvent](#eventalarmevent)
  - [Event.AlarmEvent.AlarmTriggeredEvent](#eventalarmeventalarmtriggeredevent)
  - [Event.AlarmEvent.AlarmTriggeredEvent.ErrorMessagesEntry](#eventalarmeventalarmtriggeredeventerrormessagesentry)
  - [Event.AlarmEvent.CreatedEvent](#eventalarmeventcreatedevent)
  - [Event.AlarmEvent.DeletedEvent](#eventalarmeventdeletedevent)
  - [Event.AlarmEvent.UpdatedEvent](#eventalarmeventupdatedevent)
  - [Event.AlarmEvent.UpdatedEvent.Update](#eventalarmeventupdatedeventupdate)
  - [Event.AssetEvent](#eventassetevent)
  - [Event.AssetEvent.AssetCreatedEvent](#eventasseteventassetcreatedevent)
  - [Event.AssetEvent.AssetDeletedEvent](#eventasseteventassetdeletedevent)
  - [Event.AssetEvent.AssetUpdatedEvent](#eventasseteventassetupdatedevent)
  - [Event.AssetEvent.AssetUpdatedEvent.Update](#eventasseteventassetupdatedeventupdate)
  - [Event.AssignmentEvent](#eventassignmentevent)
  - [Event.AssignmentEvent.AssignedEvent](#eventassignmenteventassignedevent)
  - [Event.AssignmentEvent.UnassignedEvent](#eventassignmenteventunassignedevent)
  - [Event.Device](#eventdevice)
  - [Event.DeviceEvent](#eventdeviceevent)
  - [Event.DeviceEvent.DeviceCreatedEvent](#eventdeviceeventdevicecreatedevent)
  - [Event.DeviceEvent.DeviceInstalledEvent](#eventdeviceeventdeviceinstalledevent)
  - [Event.DeviceEvent.DeviceLocationUpdatedEvent](#eventdeviceeventdevicelocationupdatedevent)
  - [Event.DeviceEvent.DeviceUpdatedEvent](#eventdeviceeventdeviceupdatedevent)
  - [Event.DeviceEvent.DeviceUpdatedEvent.PeripheralsEntry](#eventdeviceeventdeviceupdatedeventperipheralsentry)
  - [Event.ExportEvent](#eventexportevent)
  - [Event.ExportEvent.ExportCreatedEvent](#eventexporteventexportcreatedevent)
  - [Event.ExportEvent.ExportFailedEvent](#eventexporteventexportfailedevent)
  - [Event.ExportEvent.ExportReadyEvent](#eventexporteventexportreadyevent)
  - [Event.MessageBodyParserEvent](#eventmessagebodyparserevent)
  - [Event.MessageBodyParserEvent.CreatedEvent](#eventmessagebodyparsereventcreatedevent)
  - [Event.MessageBodyParserEvent.DeletedEvent](#eventmessagebodyparsereventdeletedevent)
  - [Event.MessageBodyParserEvent.UpdatedEvent](#eventmessagebodyparsereventupdatedevent)
  - [Event.MessageEvent](#eventmessageevent)
  - [Event.MessageEvent.MessageBodyParsedEvent](#eventmessageeventmessagebodyparsedevent)
  - [Event.MessageEvent.MessageBodyReceivedEvent](#eventmessageeventmessagebodyreceivedevent)
  - [Event.MessageEvent.MessageCannotBeParsedEvent](#eventmessageeventmessagecannotbeparsedevent)
  - [Event.MessageEvent.MessageReceivedEvent](#eventmessageeventmessagereceivedevent)
  - [Event.OrganizationEvent](#eventorganizationevent)
  - [Event.OrganizationEvent.EventConfigurationUpdated](#eventorganizationeventeventconfigurationupdated)
  - [Event.OrganizationEvent.EventConfigurationUpdated.MessageSummaryUpdate](#eventorganizationeventeventconfigurationupdatedmessagesummaryupdate)
  - [Event.OrganizationEvent.MessageSummaryEvent](#eventorganizationeventmessagesummaryevent)
  - [Event.OrganizationEvent.MessageSummaryEvent.MessageCount](#eventorganizationeventmessagesummaryeventmessagecount)
  - [Event.OrganizationEvent.OrganizationCreatedEvent](#eventorganizationeventorganizationcreatedevent)
  - [Event.OrganizationEvent.OrganizationDeletedEvent](#eventorganizationeventorganizationdeletedevent)
  - [Event.OrganizationEvent.OrganizationUpdatedEvent](#eventorganizationeventorganizationupdatedevent)
  - [Event.PublisherEvent](#eventpublisherevent)
  - [Event.PublisherEvent.AutoDisabledEvent](#eventpublishereventautodisabledevent)
  - [Event.PublisherEvent.CreatedEvent](#eventpublishereventcreatedevent)
  - [Event.PublisherEvent.DeletedEvent](#eventpublishereventdeletedevent)
  - [Event.PublisherEvent.FailedEvent](#eventpublishereventfailedevent)
  - [Event.PublisherEvent.UpdatedEvent](#eventpublishereventupdatedevent)
  - [Event.PublisherEvent.UpdatedEvent.EmailUpdate](#eventpublishereventupdatedeventemailupdate)
  - [Event.PublisherEvent.UpdatedEvent.MQTTUpdate](#eventpublishereventupdatedeventmqttupdate)
  - [Event.PublisherEvent.UpdatedEvent.ShellSsipUpdate](#eventpublishereventupdatedeventshellssipupdate)
  - [Event.PublisherEvent.UpdatedEvent.SlackUpdate](#eventpublishereventupdatedeventslackupdate)
  - [Event.PublisherEvent.UpdatedEvent.WebhookUpdate](#eventpublishereventupdatedeventwebhookupdate)
  - [Event.TokenEvent](#eventtokenevent)
  - [Event.TokenEvent.TokenCreatedEvent](#eventtokeneventtokencreatedevent)
  - [Event.TokenEvent.TokenDeletedEvent](#eventtokeneventtokendeletedevent)
  - [Event.TokenEvent.TokenExpiredEvent](#eventtokeneventtokenexpiredevent)
  - [Event.TokenEvent.TokenExpiryWarningEvent](#eventtokeneventtokenexpirywarningevent)
  - [Event.TransferEvent](#eventtransferevent)
  - [Event.UserEvent](#eventuserevent)
  - [Event.UserEvent.UserAccessRequestEvent](#eventusereventuseraccessrequestevent)
  - [Event.UserEvent.UserAddedEvent](#eventusereventuseraddedevent)
  - [Event.UserEvent.UserInvitedEvent](#eventusereventuserinvitedevent)
  - [Event.UserEvent.UserRemovedEvent](#eventusereventuserremovedevent)
  - [Event.UserEvent.UserValidationUpdatedEvent](#eventusereventuservalidationupdatedevent)
  - [EventConfiguration](#eventconfiguration)
  - [EventConfiguration.EventHealthLevelConfiguration](#eventconfigurationeventhealthlevelconfiguration)
  - [EventConfiguration.MessageSummaryConfiguration](#eventconfigurationmessagesummaryconfiguration)
  - [EventConfiguration.Request](#eventconfigurationrequest)
  - [EventHistory](#eventhistory)
  - [EventHistory.Request](#eventhistoryrequest)
  - [EventHistory.Response](#eventhistoryresponse)
  - [EventSelection](#eventselection)
  - [EventStreamRequest](#eventstreamrequest)
  - [ListEventsRequest](#listeventsrequest)
  - [ListEventsRequest.Response](#listeventsrequestresponse)
  - [ListEventsRequest.Response.EventTypeResponse](#listeventsrequestresponseeventtyperesponse)
  - [MarkEventsResolved](#markeventsresolved)
  - [MarkEventsResolved.Request](#markeventsresolvedrequest)
  - [MarkEventsResolved.Response](#markeventsresolvedresponse)
  - [ModemHealthEvents](#modemhealthevents)
  - [ModemHealthEvents.Request](#modemhealtheventsrequest)
  - [ModemHealthEvents.Response](#modemhealtheventsresponse)
  - [ResolveEvent](#resolveevent)
  - [ResolveEvent.Request](#resolveeventrequest)
  - [ResolveEvent.Response](#resolveeventresponse)
  - [UpdateEventHealthConfiguration](#updateeventhealthconfiguration)
  - [UpdateEventHealthConfiguration.Request](#updateeventhealthconfigurationrequest)
  - [UpdateEventHealthConfiguration.Response](#updateeventhealthconfigurationresponse)
  - [UpdateEventHealthConfiguration.UpdateEventHealth](#updateeventhealthconfigurationupdateeventhealth)

- Enums
  - [ListEventsRequest.Sort](#listeventsrequestsort)

- Referenced messages from [assignment.proto](#referenced-messages-from-assignmentproto)
  - [hiber.assign.Assign](#hiberassignassign)
  - [hiber.assign.Assign.Request](#hiberassignassignrequest)
  - [hiber.assign.Assign.Request.AlarmParametersEntry](#hiberassignassignrequestalarmparametersentry)
  - [hiber.assign.Assign.Response](#hiberassignassignresponse)
  - [hiber.assign.Assignment](#hiberassignassignment)
  - [hiber.assign.Assignment.AlarmAssignment](#hiberassignassignmentalarmassignment)
  - [hiber.assign.Assignment.ModemMessageBodyParserAssignment](#hiberassignassignmentmodemmessagebodyparserassignment)
  - [hiber.assign.AssignmentSelection](#hiberassignassignmentselection)
  - [hiber.assign.AssignmentSelection.AssignmentTypes](#hiberassignassignmentselectionassignmenttypes)
  - [hiber.assign.DeleteAssignment](#hiberassigndeleteassignment)
  - [hiber.assign.DeleteAssignment.Request](#hiberassigndeleteassignmentrequest)
  - [hiber.assign.DeleteAssignment.Response](#hiberassigndeleteassignmentresponse)
  - [hiber.assign.ListAlarmAssignments](#hiberassignlistalarmassignments)
  - [hiber.assign.ListAlarmAssignments.Request](#hiberassignlistalarmassignmentsrequest)
  - [hiber.assign.ListAlarmAssignments.Response](#hiberassignlistalarmassignmentsresponse)
  - [hiber.assign.ListAlarmAssignments.Response.AlarmAssignment](#hiberassignlistalarmassignmentsresponsealarmassignment)
  - [hiber.assign.ListAlarmAssignments.Response.AlarmAssignment.ToAsset](#hiberassignlistalarmassignmentsresponsealarmassignmenttoasset)
  - [hiber.assign.ListAlarmAssignments.Response.AlarmAssignment.ToModem](#hiberassignlistalarmassignmentsresponsealarmassignmenttomodem)
  - [hiber.assign.ListAlarmAssignments.Response.AlarmAssignment.ToTag](#hiberassignlistalarmassignmentsresponsealarmassignmenttotag)
  - [hiber.assign.ListAssetAssignments](#hiberassignlistassetassignments)
  - [hiber.assign.ListAssetAssignments.Request](#hiberassignlistassetassignmentsrequest)
  - [hiber.assign.ListAssetAssignments.Response](#hiberassignlistassetassignmentsresponse)
  - [hiber.assign.ListAssetAssignments.Response.AssetAssignment](#hiberassignlistassetassignmentsresponseassetassignment)
  - [hiber.assign.ListAssignments](#hiberassignlistassignments)
  - [hiber.assign.ListAssignments.Request](#hiberassignlistassignmentsrequest)
  - [hiber.assign.ListAssignments.Response](#hiberassignlistassignmentsresponse)
  - [hiber.assign.ListModemAssignments](#hiberassignlistmodemassignments)
  - [hiber.assign.ListModemAssignments.Request](#hiberassignlistmodemassignmentsrequest)
  - [hiber.assign.ListModemAssignments.Response](#hiberassignlistmodemassignmentsresponse)
  - [hiber.assign.ListModemAssignments.Response.ModemAssignment](#hiberassignlistmodemassignmentsresponsemodemassignment)
  - [hiber.assign.ListModemMessageBodyParserAssignments](#hiberassignlistmodemmessagebodyparserassignments)
  - [hiber.assign.ListModemMessageBodyParserAssignments.Request](#hiberassignlistmodemmessagebodyparserassignmentsrequest)
  - [hiber.assign.ListModemMessageBodyParserAssignments.Response](#hiberassignlistmodemmessagebodyparserassignmentsresponse)
  - [hiber.assign.ListModemMessageBodyParserAssignments.Response.ModemMessageBodyParserAssignment](#hiberassignlistmodemmessagebodyparserassignmentsresponsemodemmessagebodyparserassignment)
  - [hiber.assign.ListTagAssignments](#hiberassignlisttagassignments)
  - [hiber.assign.ListTagAssignments.Request](#hiberassignlisttagassignmentsrequest)
  - [hiber.assign.ListTagAssignments.Response](#hiberassignlisttagassignmentsresponse)
  - [hiber.assign.ListTagAssignments.Response.TagAssignment](#hiberassignlisttagassignmentsresponsetagassignment)
  - [hiber.assign.Unassign](#hiberassignunassign)
  - [hiber.assign.Unassign.Request](#hiberassignunassignrequest)
  - [hiber.assign.Unassign.Response](#hiberassignunassignresponse)
  - Enums
    - [hiber.assign.AssignmentType](#hiberassignassignmenttype)

- Referenced messages from [asset.proto](#referenced-messages-from-assetproto)
  - [hiber.asset.Asset](#hiberassetasset)
  - [hiber.asset.Asset.AssignedDevice](#hiberassetassetassigneddevice)
  - [hiber.asset.AssetSelection](#hiberassetassetselection)

    - [hiber.asset.Asset.Type](#hiberassetassettype)

- Referenced messages from [export.proto](#referenced-messages-from-exportproto)
  - [hiber.export.AvailableFieldsForExport](#hiberexportavailablefieldsforexport)
  - [hiber.export.AvailableFieldsForExport.Request](#hiberexportavailablefieldsforexportrequest)
  - [hiber.export.AvailableFieldsForExport.Response](#hiberexportavailablefieldsforexportresponse)
  - [hiber.export.CreateExport](#hiberexportcreateexport)
  - [hiber.export.CreateExport.Request](#hiberexportcreateexportrequest)
  - [hiber.export.CreateExport.Response](#hiberexportcreateexportresponse)
  - [hiber.export.DeleteExport](#hiberexportdeleteexport)
  - [hiber.export.DeleteExport.Request](#hiberexportdeleteexportrequest)
  - [hiber.export.DeleteExport.Response](#hiberexportdeleteexportresponse)
  - [hiber.export.Export](#hiberexportexport)
  - [hiber.export.Export.Configuration](#hiberexportexportconfiguration)
  - [hiber.export.Export.Configuration.AssetValues](#hiberexportexportconfigurationassetvalues)
  - [hiber.export.Export.Configuration.ModemMessages](#hiberexportexportconfigurationmodemmessages)
  - [hiber.export.Export.File](#hiberexportexportfile)
  - [hiber.export.Export.Format](#hiberexportexportformat)
  - [hiber.export.Export.Format.Csv](#hiberexportexportformatcsv)
  - [hiber.export.Export.Format.Csv.Column](#hiberexportexportformatcsvcolumn)
  - [hiber.export.Export.Format.Json](#hiberexportexportformatjson)
  - [hiber.export.Export.Format.Json.CustomFieldsEntry](#hiberexportexportformatjsoncustomfieldsentry)
  - [hiber.export.ExportSelection](#hiberexportexportselection)
  - [hiber.export.ExtendExportDownloadExpiry](#hiberexportextendexportdownloadexpiry)
  - [hiber.export.ExtendExportDownloadExpiry.Request](#hiberexportextendexportdownloadexpiryrequest)
  - [hiber.export.ExtendExportDownloadExpiry.Response](#hiberexportextendexportdownloadexpiryresponse)
  - [hiber.export.ListExports](#hiberexportlistexports)
  - [hiber.export.ListExports.Request](#hiberexportlistexportsrequest)
  - [hiber.export.ListExports.Response](#hiberexportlistexportsresponse)

    - [hiber.export.Export.Format.Type](#hiberexportexportformattype)
    - [hiber.export.Export.Status](#hiberexportexportstatus)

- Referenced messages from [health.proto](#referenced-messages-from-healthproto)
  - [hiber.health.HealthLevel](#hiberhealthhealthlevel)
  - [hiber.health.HealthLevelSelection](#hiberhealthhealthlevelselection)


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

- Referenced messages from [modem.proto](#referenced-messages-from-modemproto)
  - [hiber.modem.Modem](#hibermodemmodem)
  - [hiber.modem.ModemSelection](#hibermodemmodemselection)

    - [hiber.modem.ListModemsRequest.Sort](#hibermodemlistmodemsrequestsort)
    - [hiber.modem.Modem.Lifecycle](#hibermodemmodemlifecycle)
    - [hiber.modem.Modem.Type](#hibermodemmodemtype)
    - [hiber.modem.ModemMessage.Source](#hibermodemmodemmessagesource)

- Referenced messages from [modem_alarm.proto](#referenced-messages-from-modem_alarmproto)
  - [hiber.modem.alarm.AssignModemAlarms](#hibermodemalarmassignmodemalarms)
  - [hiber.modem.alarm.AssignModemAlarms.Request](#hibermodemalarmassignmodemalarmsrequest)
  - [hiber.modem.alarm.AssignModemAlarms.Request.ParametersEntry](#hibermodemalarmassignmodemalarmsrequestparametersentry)
  - [hiber.modem.alarm.AssignModemAlarms.Response](#hibermodemalarmassignmodemalarmsresponse)
  - [hiber.modem.alarm.AssignedModemAlarm](#hibermodemalarmassignedmodemalarm)
  - [hiber.modem.alarm.CreateModemAlarm](#hibermodemalarmcreatemodemalarm)
  - [hiber.modem.alarm.CreateModemAlarm.Request](#hibermodemalarmcreatemodemalarmrequest)
  - [hiber.modem.alarm.CreateModemAlarm.Response](#hibermodemalarmcreatemodemalarmresponse)
  - [hiber.modem.alarm.DeleteModemAlarm](#hibermodemalarmdeletemodemalarm)
  - [hiber.modem.alarm.DeleteModemAlarm.Request](#hibermodemalarmdeletemodemalarmrequest)
  - [hiber.modem.alarm.DeleteModemAlarm.Response](#hibermodemalarmdeletemodemalarmresponse)
  - [hiber.modem.alarm.ListModemAlarms](#hibermodemalarmlistmodemalarms)
  - [hiber.modem.alarm.ListModemAlarms.Request](#hibermodemalarmlistmodemalarmsrequest)
  - [hiber.modem.alarm.ListModemAlarms.Response](#hibermodemalarmlistmodemalarmsresponse)
  - [hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm)
  - [hiber.modem.alarm.ModemAlarm.Check](#hibermodemalarmmodemalarmcheck)
  - [hiber.modem.alarm.ModemAlarm.Check.DelayCheck](#hibermodemalarmmodemalarmcheckdelaycheck)
  - [hiber.modem.alarm.ModemAlarm.Check.FieldCheck](#hibermodemalarmmodemalarmcheckfieldcheck)
  - [hiber.modem.alarm.ModemAlarm.Check.FieldCheck.AllowedCheck](#hibermodemalarmmodemalarmcheckfieldcheckallowedcheck)
  - [hiber.modem.alarm.ModemAlarm.Check.FieldCheck.BlockedCheck](#hibermodemalarmmodemalarmcheckfieldcheckblockedcheck)
  - [hiber.modem.alarm.ModemAlarm.Check.FieldCheck.BlockedRangeCheck](#hibermodemalarmmodemalarmcheckfieldcheckblockedrangecheck)
  - [hiber.modem.alarm.ModemAlarm.Check.FieldCheck.DeltaCheck](#hibermodemalarmmodemalarmcheckfieldcheckdeltacheck)
  - [hiber.modem.alarm.ModemAlarm.Check.FieldCheck.EqualsCheck](#hibermodemalarmmodemalarmcheckfieldcheckequalscheck)
  - [hiber.modem.alarm.ModemAlarm.Check.FieldCheck.MaximumCheck](#hibermodemalarmmodemalarmcheckfieldcheckmaximumcheck)
  - [hiber.modem.alarm.ModemAlarm.Check.FieldCheck.MinimumCheck](#hibermodemalarmmodemalarmcheckfieldcheckminimumcheck)
  - [hiber.modem.alarm.ModemAlarm.Check.FieldCheck.ThresholdCheck](#hibermodemalarmmodemalarmcheckfieldcheckthresholdcheck)
  - [hiber.modem.alarm.ModemAlarm.Check.InactivityCheck](#hibermodemalarmmodemalarmcheckinactivitycheck)
  - [hiber.modem.alarm.ModemAlarm.Check.LocationCheck](#hibermodemalarmmodemalarmchecklocationcheck)
  - [hiber.modem.alarm.ModemAlarm.HealthLevelAfterResolved](#hibermodemalarmmodemalarmhealthlevelafterresolved)
  - [hiber.modem.alarm.ModemAlarmSelection](#hibermodemalarmmodemalarmselection)
  - [hiber.modem.alarm.TestModemAlarmTestParameters](#hibermodemalarmtestmodemalarmtestparameters)
  - [hiber.modem.alarm.TestModemAlarmTestParameters.Request](#hibermodemalarmtestmodemalarmtestparametersrequest)
  - [hiber.modem.alarm.TestModemAlarmTestParameters.Response](#hibermodemalarmtestmodemalarmtestparametersresponse)
  - [hiber.modem.alarm.UnassignModemAlarms](#hibermodemalarmunassignmodemalarms)
  - [hiber.modem.alarm.UnassignModemAlarms.Request](#hibermodemalarmunassignmodemalarmsrequest)
  - [hiber.modem.alarm.UnassignModemAlarms.Response](#hibermodemalarmunassignmodemalarmsresponse)
  - [hiber.modem.alarm.UpdateModemAlarm](#hibermodemalarmupdatemodemalarm)
  - [hiber.modem.alarm.UpdateModemAlarm.Request](#hibermodemalarmupdatemodemalarmrequest)
  - [hiber.modem.alarm.UpdateModemAlarm.Request.UpdateChecksEntry](#hibermodemalarmupdatemodemalarmrequestupdatechecksentry)
  - [hiber.modem.alarm.UpdateModemAlarm.Response](#hibermodemalarmupdatemodemalarmresponse)
  - [hiber.modem.alarm.UpdateModemAlarmAddCheck](#hibermodemalarmupdatemodemalarmaddcheck)
  - [hiber.modem.alarm.UpdateModemAlarmAddCheck.Request](#hibermodemalarmupdatemodemalarmaddcheckrequest)
  - [hiber.modem.alarm.UpdateModemAlarmAddCheck.Response](#hibermodemalarmupdatemodemalarmaddcheckresponse)
  - [hiber.modem.alarm.UpdateModemAlarmRemoveCheck](#hibermodemalarmupdatemodemalarmremovecheck)
  - [hiber.modem.alarm.UpdateModemAlarmRemoveCheck.Request](#hibermodemalarmupdatemodemalarmremovecheckrequest)
  - [hiber.modem.alarm.UpdateModemAlarmRemoveCheck.Response](#hibermodemalarmupdatemodemalarmremovecheckresponse)
  - [hiber.modem.alarm.UpdateModemAlarmUpdateCheck](#hibermodemalarmupdatemodemalarmupdatecheck)
  - [hiber.modem.alarm.UpdateModemAlarmUpdateCheck.Request](#hibermodemalarmupdatemodemalarmupdatecheckrequest)
  - [hiber.modem.alarm.UpdateModemAlarmUpdateCheck.Response](#hibermodemalarmupdatemodemalarmupdatecheckresponse)

    - [hiber.modem.alarm.ModemAlarm.TriggerCondition](#hibermodemalarmmodemalarmtriggercondition)

- Referenced messages from [modem_message_body_parser.proto](#referenced-messages-from-modem_message_body_parserproto)
  - [hiber.modem.message.bodyparser.AssignModemMessageBodyParsers](#hibermodemmessagebodyparserassignmodemmessagebodyparsers)
  - [hiber.modem.message.bodyparser.AssignModemMessageBodyParsers.Request](#hibermodemmessagebodyparserassignmodemmessagebodyparsersrequest)
  - [hiber.modem.message.bodyparser.AssignModemMessageBodyParsers.Response](#hibermodemmessagebodyparserassignmodemmessagebodyparsersresponse)
  - [hiber.modem.message.bodyparser.AssignedModemMessageBodyParser](#hibermodemmessagebodyparserassignedmodemmessagebodyparser)
  - [hiber.modem.message.bodyparser.CreateSimpleModemMessageBodyParserRequest](#hibermodemmessagebodyparsercreatesimplemodemmessagebodyparserrequest)
  - [hiber.modem.message.bodyparser.DeleteModemMessageBodyParserRequest](#hibermodemmessagebodyparserdeletemodemmessagebodyparserrequest)
  - [hiber.modem.message.bodyparser.DeleteModemMessageBodyParserRequest.Response](#hibermodemmessagebodyparserdeletemodemmessagebodyparserrequestresponse)
  - [hiber.modem.message.bodyparser.ListModemMessageBodyParsersRequest](#hibermodemmessagebodyparserlistmodemmessagebodyparsersrequest)
  - [hiber.modem.message.bodyparser.ListModemMessageBodyParsersRequest.Response](#hibermodemmessagebodyparserlistmodemmessagebodyparsersrequestresponse)
  - [hiber.modem.message.bodyparser.MakeModemMessageBodyParserAvailableToChildOrganizationRequest](#hibermodemmessagebodyparsermakemodemmessagebodyparseravailabletochildorganizationrequest)
  - [hiber.modem.message.bodyparser.MakeModemMessageBodyParserUnavailableToChildOrganizationRequest](#hibermodemmessagebodyparsermakemodemmessagebodyparserunavailabletochildorganizationrequest)
  - [hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser)
  - [hiber.modem.message.bodyparser.ModemMessageBodyParser.AvailableToChildOrganizations](#hibermodemmessagebodyparsermodemmessagebodyparseravailabletochildorganizations)
  - [hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafields)
  - [hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields.LocationFields](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafieldslocationfields)
  - [hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields.RequireMessageMetadataEntry](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafieldsrequiremessagemetadataentry)
  - [hiber.modem.message.bodyparser.ModemMessageBodyParser.RequireMessageMetadataEntry](#hibermodemmessagebodyparsermodemmessagebodyparserrequiremessagemetadataentry)
  - [hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection)
  - [hiber.modem.message.bodyparser.RenameModemMessageBodyParserRequest](#hibermodemmessagebodyparserrenamemodemmessagebodyparserrequest)
  - [hiber.modem.message.bodyparser.RetryModemMessageBodyParsing](#hibermodemmessagebodyparserretrymodemmessagebodyparsing)
  - [hiber.modem.message.bodyparser.RetryModemMessageBodyParsing.Request](#hibermodemmessagebodyparserretrymodemmessagebodyparsingrequest)
  - [hiber.modem.message.bodyparser.RetryModemMessageBodyParsing.Response](#hibermodemmessagebodyparserretrymodemmessagebodyparsingresponse)
  - [hiber.modem.message.bodyparser.SimpleModemMessageBodyParser](#hibermodemmessagebodyparsersimplemodemmessagebodyparser)
  - [hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.DelimitedSize](#hibermodemmessagebodyparsersimplemodemmessagebodyparserdelimitedsize)
  - [hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfield)
  - [hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Bytes](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfieldbytes)
  - [hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Float](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfieldfloat)
  - [hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Integer](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfieldinteger)
  - [hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.String](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfieldstring)
  - [hiber.modem.message.bodyparser.TestModemMessageBodyParserRequest](#hibermodemmessagebodyparsertestmodemmessagebodyparserrequest)
  - [hiber.modem.message.bodyparser.TestModemMessageBodyParserRequest.Response](#hibermodemmessagebodyparsertestmodemmessagebodyparserrequestresponse)
  - [hiber.modem.message.bodyparser.UnassignModemMessageBodyParsers](#hibermodemmessagebodyparserunassignmodemmessagebodyparsers)
  - [hiber.modem.message.bodyparser.UnassignModemMessageBodyParsers.Request](#hibermodemmessagebodyparserunassignmodemmessagebodyparsersrequest)
  - [hiber.modem.message.bodyparser.UnassignModemMessageBodyParsers.Response](#hibermodemmessagebodyparserunassignmodemmessagebodyparsersresponse)
  - [hiber.modem.message.bodyparser.UpdateChildOrganizationAvailabilityRequest](#hibermodemmessagebodyparserupdatechildorganizationavailabilityrequest)
  - [hiber.modem.message.bodyparser.UpdateSimpleModemMessageBodyParserRequest](#hibermodemmessagebodyparserupdatesimplemodemmessagebodyparserrequest)
  - [hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest](#hibermodemmessagebodyparserupdateuploadedmodemmessagebodyparserrequest)
  - [hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields](#hibermodemmessagebodyparserupdateuploadedmodemmessagebodyparserrequestmetadatafields)
  - [hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields.AddRequireMessageMetadataEntry](#hibermodemmessagebodyparserupdateuploadedmodemmessagebodyparserrequestmetadatafieldsaddrequiremessagemetadataentry)
  - [hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields.ReplaceRequireMessageMetadataEntry](#hibermodemmessagebodyparserupdateuploadedmodemmessagebodyparserrequestmetadatafieldsreplacerequiremessagemetadataentry)
  - [hiber.modem.message.bodyparser.UploadModemMessageBodyParserRequest](#hibermodemmessagebodyparseruploadmodemmessagebodyparserrequest)
  - [hiber.modem.message.bodyparser.UploadModemMessageBodyParserRequest.RequireMessageMetadataEntry](#hibermodemmessagebodyparseruploadmodemmessagebodyparserrequestrequiremessagemetadataentry)

    - [hiber.modem.message.bodyparser.ModemMessageBodyParser.PostProcessing](#hibermodemmessagebodyparsermodemmessagebodyparserpostprocessing)
    - [hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Endian](#hibermodemmessagebodyparsersimplemodemmessagebodyparserendian)

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

- Referenced messages from [publisher.proto](#referenced-messages-from-publisherproto)
  - [hiber.publisher.Publisher](#hiberpublisherpublisher)
  - [hiber.publisher.Publisher.Data](#hiberpublisherpublisherdata)
  - [hiber.publisher.Publisher.Data.HTTPConfig](#hiberpublisherpublisherdatahttpconfig)
  - [hiber.publisher.Publisher.Data.MQTTConfig](#hiberpublisherpublisherdatamqttconfig)
  - [hiber.publisher.Publisher.Data.ShellSsipConfig](#hiberpublisherpublisherdatashellssipconfig)
  - [hiber.publisher.Publisher.Filters](#hiberpublisherpublisherfilters)
  - [hiber.publisher.UpdatePublisherRequest](#hiberpublisherupdatepublisherrequest)
  - [hiber.publisher.UpdatePublisherRequest.UpdateModems](#hiberpublisherupdatepublisherrequestupdatemodems)

    - [hiber.publisher.Publisher.ContentType](#hiberpublisherpublishercontenttype)
    - [hiber.publisher.Publisher.Data.MQTTConfig.QoS](#hiberpublisherpublisherdatamqttconfigqos)
    - [hiber.publisher.Publisher.Type](#hiberpublisherpublishertype)

- Referenced messages from [tag.proto](#referenced-messages-from-tagproto)
  - [hiber.tag.Tag](#hibertagtag)
  - [hiber.tag.Tag.Label](#hibertagtaglabel)
  - [hiber.tag.TagSelection](#hibertagtagselection)


- Referenced messages from [token.proto](#referenced-messages-from-tokenproto)
  - [hiber.token.CreateTokenRequest](#hibertokencreatetokenrequest)
  - [hiber.token.CreateTokenRequest.Response](#hibertokencreatetokenrequestresponse)
  - [hiber.token.DeleteTokenRequest](#hibertokendeletetokenrequest)
  - [hiber.token.DeleteTokenRequest.Response](#hibertokendeletetokenrequestresponse)
  - [hiber.token.ListTokensRequest](#hibertokenlisttokensrequest)
  - [hiber.token.ListTokensRequest.Response](#hibertokenlisttokensrequestresponse)
  - [hiber.token.Token](#hibertokentoken)
  - [hiber.token.Token.UserDetails](#hibertokentokenuserdetails)
  - [hiber.token.TokenSelection](#hibertokentokenselection)
  - [hiber.token.UpdateTokenOrganizationPermissionsRequest](#hibertokenupdatetokenorganizationpermissionsrequest)
  - [hiber.token.UpdateTokenOrganizationPermissionsRequest.Response](#hibertokenupdatetokenorganizationpermissionsrequestresponse)
  - [hiber.token.UpdateTokenRoles](#hibertokenupdatetokenroles)
  - [hiber.token.UpdateTokenRoles.Request](#hibertokenupdatetokenrolesrequest)
  - [hiber.token.UpdateTokenRoles.Request.ModifyRoles](#hibertokenupdatetokenrolesrequestmodifyroles)
  - [hiber.token.UpdateTokenRoles.Request.ReplaceRoles](#hibertokenupdatetokenrolesrequestreplaceroles)
  - [hiber.token.UpdateTokenRoles.Response](#hibertokenupdatetokenrolesresponse)
  - [hiber.token.UpdateTokenUserPermissionsRequest](#hibertokenupdatetokenuserpermissionsrequest)
  - [hiber.token.UpdateTokenUserPermissionsRequest.Response](#hibertokenupdatetokenuserpermissionsrequestresponse)

    - [hiber.token.Token.Type](#hibertokentokentype)

- Referenced messages from [transfer.proto](#referenced-messages-from-transferproto)
  - [hiber.transfer.Transfer](#hibertransfertransfer)
  - [hiber.transfer.Transfer.Devices](#hibertransfertransferdevices)

    - [hiber.transfer.Transfer.Type](#hibertransfertransfertype)

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


## EventService
Events are used in a number of ways in the api. With this service you can
search, list and stream them for your own purposes.

Events are filtered by permission, i.e. if you cannot access the users, you would not see user-related events.
Requesting user-related events explicitly if you cannot access the users will return an error.

### List
> **rpc** List([ListEventsRequest](#listeventsrequest))
    [ListEventsRequest.Response](#listeventsrequestresponse)



### Stream
> **rpc** Stream([EventStreamRequest](#eventstreamrequest))
    [Event](#event)



### History
> **rpc** History([EventHistory.Request](#eventhistoryrequest))
    [EventHistory.Response](#eventhistoryresponse)



### ModemHealth
> **rpc** ModemHealth([ModemHealthEvents.Request](#modemhealtheventsrequest))
    [ModemHealthEvents.Response](#modemhealtheventsresponse)



### Resolve
> **rpc** Resolve([ResolveEvent.Request](#resolveeventrequest))
    [ResolveEvent.Response](#resolveeventresponse)



### MarkResolved
> **rpc** MarkResolved([MarkEventsResolved.Request](#markeventsresolvedrequest))
    [MarkEventsResolved.Response](#markeventsresolvedresponse)



### GetEventConfiguration
> **rpc** GetEventConfiguration([EventConfiguration.Request](#eventconfigurationrequest))
    [EventConfiguration](#eventconfiguration)



### UpdateEventConfiguration
> **rpc** UpdateEventConfiguration([EventConfiguration](#eventconfiguration))
    [EventConfiguration](#eventconfiguration)



### UpdateEventHealthConfiguration
> **rpc** UpdateEventHealthConfiguration([UpdateEventHealthConfiguration.Request](#updateeventhealthconfigurationrequest))
    [UpdateEventHealthConfiguration.Response](#updateeventhealthconfigurationresponse)




## Messages

### BundledEvent

A bundle/set of events, all of the same event-type.

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.EventType](#hibereventtype) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **amount**.exact_amount | [ BundledEvent.ExactAmount](#bundledeventexactamount) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **amount**.approximated_amount | [ BundledEvent.ApproximatedAmount](#bundledeventapproximatedamount) |  |
| deprecated_amount | [ int32](#int32) | <strong>Deprecated.</strong> Deprecated in favour of using the amount field that is either an ExactAmount or ApproximatedAmount |
| deprecated_last_event | [ hiber.Timestamp](#hibertimestamp) | <strong>Deprecated.</strong> Deprecated in favour of using the amount field that is either an ExactAmount or ApproximatedAmount. since `last_event` is not available when using approximation (we don't know the actual last event), this field is only present when getting an ExactAmount. |
| deprecated_approximated_amount | [ bool](#bool) | <strong>Deprecated.</strong> Indicates that the amount is an approximation, and not an exact value. Some events will be approximated to avoid a large number of events affecting the request time. Deprecated in favour of using the oneof_amount field that is either an ExactAmount or ApproximatedAmount |

### BundledEvent.ApproximatedAmount

Indicates that the amount is an approximation, and not an exact value.
Some events will be approximated to avoid a large number of events affecting the request time.
Because of the nature of approximation, we don't have a "last" event, so no timestamp is available.

| Field | Type | Description |
| ----- | ---- | ----------- |
| amount | [ int32](#int32) |  |

### BundledEvent.ExactAmount

Indicates that the amount is an exact count, and not an approximated value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| amount | [ int32](#int32) |  |
| last_event | [ hiber.Timestamp](#hibertimestamp) |  |

### Event

Generic Event object, used in streams where events are mixed. Protobuf provides helper methods to extract
the contained object.

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.EventType](#hibereventtype) | Time of the event. |
| time | [ hiber.Timestamp](#hibertimestamp) | Time of the event. |
| is_error | [ bool](#bool) | <strong>Deprecated.</strong> Whether this event causes the 'Error' health level. If your organization does not use the default health levels, this field will be omitted. Use health_level instead. |
| is_warning | [ bool](#bool) | <strong>Deprecated.</strong> Whether this event causes the 'Warning' health level. If your organization does not use the default health levels, this field will be omitted. Use health_level instead. |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The health level caused by this event. This health generally applies to either a device, a token or a publisher, and is also applied to the organization health. Not every event affects health, so this field might be empty. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **resolved_status**.resolved | [ bool](#bool) | Whether this event was resolved. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **resolved_status**.resolve_identifier | [ string](#string) | The identifier to use when resolving this event. Only present when not resolved, and only available for some event types. |
| title | [ string](#string) | Short text describing the event. |
| description | [ string](#string) | Longer text describing the event in more detail. |
| device | [ Event.Device](#eventdevice) | The device data for this event, if it is related to a single device. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | The tags for this event, if any. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.asset_created | [ Event.AssetEvent.AssetCreatedEvent](#eventasseteventassetcreatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.asset_updated | [ Event.AssetEvent.AssetUpdatedEvent](#eventasseteventassetupdatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.asset_deleted | [ Event.AssetEvent.AssetDeletedEvent](#eventasseteventassetdeletedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.device_created | [ Event.DeviceEvent.DeviceCreatedEvent](#eventdeviceeventdevicecreatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.device_updated | [ Event.DeviceEvent.DeviceUpdatedEvent](#eventdeviceeventdeviceupdatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.device_location_updated | [ Event.DeviceEvent.DeviceLocationUpdatedEvent](#eventdeviceeventdevicelocationupdatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.device_installed | [ Event.DeviceEvent.DeviceInstalledEvent](#eventdeviceeventdeviceinstalledevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.message_received | [ Event.MessageEvent.MessageReceivedEvent](#eventmessageeventmessagereceivedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.message_body_received | [ Event.MessageEvent.MessageBodyReceivedEvent](#eventmessageeventmessagebodyreceivedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.message_body_parsed | [ Event.MessageEvent.MessageBodyParsedEvent](#eventmessageeventmessagebodyparsedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.message_cannot_be_parsed | [ Event.MessageEvent.MessageCannotBeParsedEvent](#eventmessageeventmessagecannotbeparsedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.message_body_parser_created | [ Event.MessageBodyParserEvent.CreatedEvent](#eventmessagebodyparsereventcreatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.message_body_parser_updated | [ Event.MessageBodyParserEvent.UpdatedEvent](#eventmessagebodyparsereventupdatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.message_body_parser_deleted | [ Event.MessageBodyParserEvent.DeletedEvent](#eventmessagebodyparsereventdeletedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.alarm_triggered | [ Event.AlarmEvent.AlarmTriggeredEvent](#eventalarmeventalarmtriggeredevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.alarm_created | [ Event.AlarmEvent.CreatedEvent](#eventalarmeventcreatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.alarm_updated | [ Event.AlarmEvent.UpdatedEvent](#eventalarmeventupdatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.alarm_deleted | [ Event.AlarmEvent.DeletedEvent](#eventalarmeventdeletedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.assigned | [ Event.AssignmentEvent.AssignedEvent](#eventassignmenteventassignedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.unassigned | [ Event.AssignmentEvent.UnassignedEvent](#eventassignmenteventunassignedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.user_added | [ Event.UserEvent.UserAddedEvent](#eventusereventuseraddedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.user_removed | [ Event.UserEvent.UserRemovedEvent](#eventusereventuserremovedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.user_invited | [ Event.UserEvent.UserInvitedEvent](#eventusereventuserinvitedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.user_access_request | [ Event.UserEvent.UserAccessRequestEvent](#eventusereventuseraccessrequestevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.user_validation_updated | [ Event.UserEvent.UserValidationUpdatedEvent](#eventusereventuservalidationupdatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.transfer | [ Event.TransferEvent](#eventtransferevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.token_expiry_warning | [ Event.TokenEvent.TokenExpiryWarningEvent](#eventtokeneventtokenexpirywarningevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.token_expired | [ Event.TokenEvent.TokenExpiredEvent](#eventtokeneventtokenexpiredevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.token_created | [ Event.TokenEvent.TokenCreatedEvent](#eventtokeneventtokencreatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.token_deleted | [ Event.TokenEvent.TokenDeletedEvent](#eventtokeneventtokendeletedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.organization_created | [ Event.OrganizationEvent.OrganizationCreatedEvent](#eventorganizationeventorganizationcreatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.organization_updated | [ Event.OrganizationEvent.OrganizationUpdatedEvent](#eventorganizationeventorganizationupdatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.organization_deleted | [ Event.OrganizationEvent.OrganizationDeletedEvent](#eventorganizationeventorganizationdeletedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.message_summary | [ Event.OrganizationEvent.MessageSummaryEvent](#eventorganizationeventmessagesummaryevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.organization_event_configuration_updated | [ Event.OrganizationEvent.EventConfigurationUpdated](#eventorganizationeventeventconfigurationupdated) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.publisher_created | [ Event.PublisherEvent.CreatedEvent](#eventpublishereventcreatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.publisher_updated | [ Event.PublisherEvent.UpdatedEvent](#eventpublishereventupdatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.publisher_deleted | [ Event.PublisherEvent.DeletedEvent](#eventpublishereventdeletedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.publisher_auto_disabled | [ Event.PublisherEvent.AutoDisabledEvent](#eventpublishereventautodisabledevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.publisher_failed | [ Event.PublisherEvent.FailedEvent](#eventpublishereventfailedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.export_created | [ Event.ExportEvent.ExportCreatedEvent](#eventexporteventexportcreatedevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.export_ready | [ Event.ExportEvent.ExportReadyEvent](#eventexporteventexportreadyevent) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.export_failed | [ Event.ExportEvent.ExportFailedEvent](#eventexporteventexportfailedevent) |  |

### Event.AlarmEvent




### Event.AlarmEvent.AlarmTriggeredEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| device_number | [ string](#string) |  |
| device_external_device_id | [ string](#string) |  |
| message_id | [ uint64](#uint64) | The id of the device that triggered the alarm, if any. |
| alarm_identifier | [ string](#string) | The identifier of the alarm. |
| alarm_description | [ string](#string) | The description of the alarm. |
| error_messages | [map Event.AlarmEvent.AlarmTriggeredEvent.ErrorMessagesEntry](#eventalarmeventalarmtriggeredeventerrormessagesentry) | The filled in error message(s) for the failing checks in the alarm. |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The highest health level caused by the failing checks in this alarm, for the device (and organization). |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **resolved_status**.resolved_at | [ hiber.Timestamp](#hibertimestamp) | Whether this event was resolved. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **resolved_status**.resolve_identifier | [ string](#string) | The identifier to use when resolving this event. Only present when not resolved |
| health_level_after_resolved | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | Optional health that this alarm event causes after it has been resolved. |
| health_level_after_resolved_until | [ hiber.Timestamp](#hibertimestamp) | How long the optional health that this alarm event causes after it has been resolved lasts. |

### Event.AlarmEvent.AlarmTriggeredEvent.ErrorMessagesEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ string](#string) |  |

### Event.AlarmEvent.CreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| created | [ hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### Event.AlarmEvent.DeletedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| deleted | [ string](#string) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### Event.AlarmEvent.UpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| updated | [ Event.AlarmEvent.UpdatedEvent.Update](#eventalarmeventupdatedeventupdate) |  |
| alarm_identifier | [ string](#string) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### Event.AlarmEvent.UpdatedEvent.Update



| Field | Type | Description |
| ----- | ---- | ----------- |
| deprecated_description | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
|  **optional** description | [optional string](#string) |  |
| trigger_condition | [ string](#string) |  |
| checks | [ google.protobuf.Struct](#googleprotobufstruct) |  |
| update_default_health_level | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
|  **optional** updated_default_health_level | [optional string](#string) |  |
| update_health_level_after_resolved | [ hiber.modem.alarm.ModemAlarm.HealthLevelAfterResolved](#hibermodemalarmmodemalarmhealthlevelafterresolved) |  |

### Event.AssetEvent




### Event.AssetEvent.AssetCreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| asset_identifier | [ string](#string) |  |
| asset | [ hiber.asset.Asset](#hiberassetasset) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |

### Event.AssetEvent.AssetDeletedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| deleted | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |

### Event.AssetEvent.AssetUpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| updated | [ Event.AssetEvent.AssetUpdatedEvent.Update](#eventasseteventassetupdatedeventupdate) |  |
| asset_identifier | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |

### Event.AssetEvent.AssetUpdatedEvent.Update



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** name | [optional string](#string) |  |
|  **optional** description | [optional string](#string) |  |
|  **optional** notes | [optional string](#string) |  |
|  **optional** time_zone | [optional string](#string) |  |
|  **optional** expected_transmission_rate | [optional uint32](#uint32) |  |
|  **optional** type | [optional hiber.asset.Asset.Type](#hiberassetassettype) |  |
|  **optional** metadata | [optional google.protobuf.Struct](#googleprotobufstruct) |  |

### Event.AssignmentEvent




### Event.AssignmentEvent.AssignedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| created | [ hiber.assign.Assignment](#hiberassignassignment) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### Event.AssignmentEvent.UnassignedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| removed | [ hiber.assign.Assignment](#hiberassignassignment) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### Event.Device

The device data for this event, if it is related to a single device.

| Field | Type | Description |
| ----- | ---- | ----------- |
| number | [ string](#string) |  |
| name | [ string](#string) |  |
| identifier | [ string](#string) |  |

### Event.DeviceEvent




### Event.DeviceEvent.DeviceCreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| number | [ string](#string) |  |
| external_device_id | [ string](#string) | External device id for this device (e.g. a MAC address). |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |

### Event.DeviceEvent.DeviceInstalledEvent

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

### Event.DeviceEvent.DeviceLocationUpdatedEvent

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

### Event.DeviceEvent.DeviceUpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| number | [ string](#string) |  |
| external_device_id | [ string](#string) | External device id for this device (e.g. a MAC address). |
| display_name | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
|  **optional** updated_display_name | [optional string](#string) |  |
| peripherals | [map Event.DeviceEvent.DeviceUpdatedEvent.PeripheralsEntry](#eventdeviceeventdeviceupdatedeventperipheralsentry) |  |
| notes | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
|  **optional** updated_notes | [optional string](#string) |  |
|  **optional** device_type | [optional string](#string) |  |
| secure_notes_updated | [ bool](#bool) |  |
| health_warning_period | [ hiber.Duration](#hiberduration) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |

### Event.DeviceEvent.DeviceUpdatedEvent.PeripheralsEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ string](#string) |  |

### Event.ExportEvent




### Event.ExportEvent.ExportCreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| export | [ hiber.export.Export](#hiberexportexport) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### Event.ExportEvent.ExportFailedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| export | [ hiber.export.Export](#hiberexportexport) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### Event.ExportEvent.ExportReadyEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| export | [ hiber.export.Export](#hiberexportexport) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### Event.MessageBodyParserEvent

Events related to MessageBodyParsers.


### Event.MessageBodyParserEvent.CreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| created | [ hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### Event.MessageBodyParserEvent.DeletedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| deleted | [ string](#string) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### Event.MessageBodyParserEvent.UpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| updated_name | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
|  **optional** name | [optional string](#string) |  |
| updated_content_ksy | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
|  **optional** content_ksy | [optional string](#string) |  |
| updated_simple_parser | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser](#hibermodemmessagebodyparsersimplemodemmessagebodyparser) |  |
| updated_available_to_child_organizations | [ hiber.Filter.ChildOrganizations.Update](#hiberfilterchildorganizationsupdate) | <strong>Deprecated.</strong>  |
|  **optional** available_to_child_organizations | [optional hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### Event.MessageEvent




### Event.MessageEvent.MessageBodyParsedEvent

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

### Event.MessageEvent.MessageBodyReceivedEvent

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

### Event.MessageEvent.MessageCannotBeParsedEvent

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

### Event.MessageEvent.MessageReceivedEvent

This event is generated whenever a message comes in, after is has been decrypted
and parsed (if any body parsers are configured for the device).

It contains the relevant data in the message object, including location and the
user-defined body.

If any body parser(s) are configured for the device, the device message object also contains
a ParsedBody for each of them.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| modem_number | [ string](#string) | <strong>Deprecated.</strong>  |
| device_number | [ string](#string) |  |
| device_external_device_id | [ string](#string) | External device id for this device (e.g. a MAC address). |
| message | [ hiber.modem.ModemMessage](#hibermodemmodemmessage) | The received message, including parsed body. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | The device's tags. |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### Event.OrganizationEvent




### Event.OrganizationEvent.EventConfigurationUpdated



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| message_summary_update | [ Event.OrganizationEvent.EventConfigurationUpdated.MessageSummaryUpdate](#eventorganizationeventeventconfigurationupdatedmessagesummaryupdate) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### Event.OrganizationEvent.EventConfigurationUpdated.MessageSummaryUpdate



| Field | Type | Description |
| ----- | ---- | ----------- |
| enabled | [ hiber.UpdateBoolean](#hiberupdateboolean) | <strong>Deprecated.</strong>  |
|  **optional** state | [optional bool](#bool) |  |
|  **optional** period | [optional hiber.Duration](#hiberduration) |  |
|  **optional** align_to_time | [optional hiber.Timestamp](#hibertimestamp) |  |

### Event.OrganizationEvent.MessageSummaryEvent

Message summary event that is sent when it has been configured for the organization.
The period is configurable, using the EventConfiguration.
This event is disabled by default.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| message_count | [repeated Event.OrganizationEvent.MessageSummaryEvent.MessageCount](#eventorganizationeventmessagesummaryeventmessagecount) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| time_range | [ hiber.TimeRange](#hibertimerange) |  |

### Event.OrganizationEvent.MessageSummaryEvent.MessageCount



| Field | Type | Description |
| ----- | ---- | ----------- |
| device | [ string](#string) |  |
| source | [ hiber.modem.ModemMessage.Source](#hibermodemmodemmessagesource) |  |
| amount | [ int32](#int32) |  |

### Event.OrganizationEvent.OrganizationCreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| parent_organization | [ string](#string) |  |
| created | [ hiber.organization.Organization](#hiberorganizationorganization) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| avatar | [ hiber.Avatar](#hiberavatar) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### Event.OrganizationEvent.OrganizationDeletedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| parent_organization | [ string](#string) |  |
| deleted_organization | [ string](#string) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### Event.OrganizationEvent.OrganizationUpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
|  **optional** display_name_updated | [optional string](#string) |  |
|  **optional** vat_number_updated | [optional string](#string) |  |
|  **optional** address_updated | [optional hiber.organization.Organization.Address](#hiberorganizationorganizationaddress) |  |
| is_business_updated | [ hiber.UpdateBoolean](#hiberupdateboolean) | <strong>Deprecated.</strong>  |
|  **optional** business_updated | [optional bool](#bool) |  |
|  **optional** billing_name_updated | [optional string](#string) |  |
|  **optional** billing_address_updated | [optional hiber.organization.Organization.Address](#hiberorganizationorganizationaddress) |  |
|  **optional** contact_updated | [optional hiber.organization.Organization.Contact](#hiberorganizationorganizationcontact) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| features_added | [repeated hiber.organization.Organization.Feature](#hiberorganizationorganizationfeature) |  |
| features_removed | [repeated hiber.organization.Organization.Feature](#hiberorganizationorganizationfeature) |  |

### Event.PublisherEvent




### Event.PublisherEvent.AutoDisabledEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| id | [ int64](#int64) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The health level caused for the publisher (and organization) by this event. |

### Event.PublisherEvent.CreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| created | [ hiber.publisher.Publisher](#hiberpublisherpublisher) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### Event.PublisherEvent.DeletedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| deleted | [ hiber.publisher.Publisher](#hiberpublisherpublisher) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### Event.PublisherEvent.FailedEvent



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

### Event.PublisherEvent.UpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| deprecated_updated_description | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
|  **optional** updated_description | [optional string](#string) |  |
| partial_update_data | [ hiber.publisher.Publisher.Data](#hiberpublisherpublisherdata) | <strong>Deprecated.</strong> Deprecated in favor of the new updated_data field |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **updated_data**.webhook | [ Event.PublisherEvent.UpdatedEvent.WebhookUpdate](#eventpublishereventupdatedeventwebhookupdate) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **updated_data**.mqtt | [ Event.PublisherEvent.UpdatedEvent.MQTTUpdate](#eventpublishereventupdatedeventmqttupdate) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **updated_data**.email | [ Event.PublisherEvent.UpdatedEvent.EmailUpdate](#eventpublishereventupdatedeventemailupdate) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **updated_data**.slack | [ Event.PublisherEvent.UpdatedEvent.SlackUpdate](#eventpublishereventupdatedeventslackupdate) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **updated_data**.shell_ssip | [ Event.PublisherEvent.UpdatedEvent.ShellSsipUpdate](#eventpublishereventupdatedeventshellssipupdate) |  |
| deprecated_updated_event_filter | [ hiber.Filter.Events.Update](#hiberfiltereventsupdate) | <strong>Deprecated.</strong>  |
|  **optional** updated_event_filter | [optional hiber.Filter.Events](#hiberfilterevents) |  |
| deprecated_updated_modem_filter | [ hiber.Filter.Modems.Update](#hiberfiltermodemsupdate) | <strong>Deprecated.</strong>  |
|  **optional** updated_modem_filter | [optional hiber.Filter.Modems](#hiberfiltermodems) |  |
| deprecated_updated_tag_filter | [ hiber.Filter.Tags.Update](#hiberfiltertagsupdate) | <strong>Deprecated.</strong>  |
|  **optional** updated_tag_filter | [optional hiber.Filter.Tags](#hiberfiltertags) |  |
| deprecated_updated_active_state | [ hiber.UpdateBoolean](#hiberupdateboolean) | <strong>Deprecated.</strong>  |
|  **optional** updated_active_state | [optional bool](#bool) |  |
| health_warning_period | [ hiber.Duration](#hiberduration) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### Event.PublisherEvent.UpdatedEvent.EmailUpdate




### Event.PublisherEvent.UpdatedEvent.MQTTUpdate



| Field | Type | Description |
| ----- | ---- | ----------- |
| url | [ string](#string) |  |
| content_type | [ hiber.integration.mqtt.MQTTPublisher.ContentType](#hiberintegrationmqttmqttpublishercontenttype) |  |
| topic | [ string](#string) |  |
| qos | [ hiber.integration.mqtt.MQTTPublisher.Data.QoS](#hiberintegrationmqttmqttpublisherdataqos) |  |
| deprecated_identifier | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
|  **optional** identifier | [optional string](#string) |  |
| deprecated_username | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
|  **optional** username | [optional string](#string) |  |
| deprecated_password | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
|  **optional** password | [optional string](#string) |  |
| deprecated_certificate_id | [ hiber.UpdateOptionalId](#hiberupdateoptionalid) | <strong>Deprecated.</strong>  |
|  **optional** certificate_id | [optional int64](#int64) |  |

### Event.PublisherEvent.UpdatedEvent.ShellSsipUpdate




### Event.PublisherEvent.UpdatedEvent.SlackUpdate




### Event.PublisherEvent.UpdatedEvent.WebhookUpdate



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** url | [optional string](#string) |  |
| deprecated_secret | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
|  **optional** secret | [optional string](#string) |  |
|  **optional** content_type | [optional hiber.webhook.Webhook.ContentType](#hiberwebhookwebhookcontenttype) |  |
| deprecated_certificate_id | [ hiber.UpdateOptionalId](#hiberupdateoptionalid) | <strong>Deprecated.</strong>  |
|  **optional** certificate_id | [optional int64](#int64) |  |

### Event.TokenEvent




### Event.TokenEvent.TokenCreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| token | [ hiber.token.Token](#hibertokentoken) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### Event.TokenEvent.TokenDeletedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| token | [ hiber.token.Token](#hibertokentoken) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### Event.TokenEvent.TokenExpiredEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| token | [ hiber.token.Token](#hibertokentoken) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### Event.TokenEvent.TokenExpiryWarningEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| token | [ hiber.token.Token](#hibertokentoken) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The health level caused for the organization by this event. |

### Event.TransferEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| transfer | [ hiber.transfer.Transfer](#hibertransfertransfer) |  |

### Event.UserEvent




### Event.UserEvent.UserAccessRequestEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| user | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |

### Event.UserEvent.UserAddedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| user | [ string](#string) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### Event.UserEvent.UserInvitedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| email | [ string](#string) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### Event.UserEvent.UserRemovedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| user | [ string](#string) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### Event.UserEvent.UserValidationUpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| email_validation_regex | [ string](#string) |  |
| title | [ string](#string) |  |
| description | [ string](#string) |  |
| time | [ hiber.Timestamp](#hibertimestamp) |  |

### EventConfiguration

Configuration for configurable events.
Some events are disable by default, or can be configured in different ways. Their configuration is available here.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| message_summary_configuration | [ EventConfiguration.MessageSummaryConfiguration](#eventconfigurationmessagesummaryconfiguration) |  |
| event_health_level_configuration | [repeated EventConfiguration.EventHealthLevelConfiguration](#eventconfigurationeventhealthlevelconfiguration) | List of event-types that have a health-level associated with them. Ignored when updating. |

### EventConfiguration.EventHealthLevelConfiguration

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

### EventConfiguration.MessageSummaryConfiguration

When enabled, this sends a MessageSummaryEvent periodically.
For example, you can configure the message summary to be a daily message, aligned to midnight in your time zone.

| Field | Type | Description |
| ----- | ---- | ----------- |
| enabled | [ bool](#bool) | The message summary event is disabled by default. |
| period | [ hiber.Duration](#hiberduration) | The period to send the message summary event for. The event can be sent every hour, day, etc. |
| align_to_time | [ hiber.Timestamp](#hibertimestamp) | Align the period to given time. For example, an hourly period sends can be aligned to 0:00 to send every whole hour. A weekly period can be aligned to send at a specific time on Monday by aligning to a timestamp on a Monday. If a textual time zone is configured in this timestamp, it is used as well and should shift with changes like daylight saving time automatically. |
| include_empty_summaries | [ bool](#bool) | Send an event, even if the summary does not contain any information |

### EventConfiguration.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |

### EventHistory

Get the history of events that match the given filter, chronologically (by default, from now backwards in time).

Only returns the Event with first-level fields set, event details are not included in the response
(the oneof is not set).


### EventHistory.Request

Selection for which events to include the response.
Using the EventSelection you'll be able to filter on specific types, or other properties of events.
The Pagination object will let you limit the number of events returned.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional EventSelection](#eventselection) | Select the events to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |

### EventHistory.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ EventHistory.Request](#eventhistoryrequest) |  |
| events | [repeated Event](#event) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### EventSelection

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
| health_levels | [repeated string](#string) | Filter events by actual configured health level. |
|  **optional** include_resolved_events | [optional bool](#bool) | By default, events that have been resolved are not listed. |
|  **optional** unbundled_events | [optional bool](#bool) | <strong>Deprecated.</strong> When not set, no unbundled events are returned. When set, returns unbundled events per type, paginated per type. Deprecated: use unbundled_events on ListEventsRequest |
|  **optional** errors_only | [optional bool](#bool) | <strong>Deprecated.</strong> Return only events that cause the default Error health. Deprecated: use health_levels with custom health levels instead. |
|  **optional** warnings_only | [optional bool](#bool) | <strong>Deprecated.</strong> Return only events that cause the default Warning health. Deprecated: use health_levels with custom health levels instead. |

### EventStreamRequest

Creates a stream for new events, matching the provided selection.

Note: streams are limited to one per user due to GRPC limitations.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional EventSelection](#eventselection) | Select the events to stream. Optional, when omitted or empty everything is included. |
|  **optional** child_organizations | [optional hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | Include events from child organizations, if requested. This is only available for streaming, listing events can only be listed per organization. Keep in mind that filtering events using the selection is limited. Filtering on tags or publishers, for example, can only apply to the parent organization. |

### ListEventsRequest

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
|  **optional** selection | [optional EventSelection](#eventselection) | Select the events to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) | Pagination is applied per event type on unbundled events. It is not necessary for bundled events. |
|  **optional** sort | [optional ListEventsRequest.Sort](#listeventsrequestsort) |  |
|  **optional** unbundled_events | [optional bool](#bool) | When not set, bundled/grouped events are returned. When set, returns unbundled events per type, paginated per type. Overrides unbundled_events in EventSelection message. |

### ListEventsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ ListEventsRequest](#listeventsrequest) |  |
| events | [repeated BundledEvent](#bundledevent) |  |
| unbundled_events | [repeated ListEventsRequest.Response.EventTypeResponse](#listeventsrequestresponseeventtyperesponse) |  |

### ListEventsRequest.Response.EventTypeResponse



| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.EventType](#hibereventtype) |  |
| unbundled_events | [repeated Event](#event) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### MarkEventsResolved

Mark a selection of events as resolved.


### MarkEventsResolved.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ EventSelection](#eventselection) | Selection of events to resolve. |

### MarkEventsResolved.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| resolved | [ uint32](#uint32) | The amount of events that were resolved. |
| request | [ MarkEventsResolved.Request](#markeventsresolvedrequest) | The original request, echoed back with any applied corrections. |

### ModemHealthEvents

Get the list of events that affect device health, chronologically (by default, from now backwards in time).

Only returns the Event with first-level fields set, event details are not included in the response
(the oneof is not set).


### ModemHealthEvents.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional EventSelection](#eventselection) | Select the events to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |

### ModemHealthEvents.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ ModemHealthEvents.Request](#modemhealtheventsrequest) |  |
| events | [repeated Event](#event) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### ResolveEvent

Resolve a resolvable event using its resolve_identifier.


### ResolveEvent.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| resolve_identifier | [ string](#string) | The resolve identifier of the event you wish to resolve. |

### ResolveEvent.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| resolved | [ uint32](#uint32) | The amount of events that were resolved. |

### UpdateEventHealthConfiguration




### UpdateEventHealthConfiguration.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| updates | [repeated UpdateEventHealthConfiguration.UpdateEventHealth](#updateeventhealthconfigurationupdateeventhealth) | List of event-types to update health for. When listing same event twice, behaviour is undefined. |

### UpdateEventHealthConfiguration.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ UpdateEventHealthConfiguration.Request](#updateeventhealthconfigurationrequest) | The original request, echoed back. |
| event_configuration | [ EventConfiguration](#eventconfiguration) | The updated event configuration. |

### UpdateEventHealthConfiguration.UpdateEventHealth

Updates health-level configuration for a specific event-type.
To find available health-level names, use HealthService/List(ListHealthLevels.Request).
To clear an existing expiry, set `updated` true and leave `duration` to be the default value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.EventType](#hibereventtype) | When set, events of this type will affect the system with the configured health level. |
| level | [ string](#string) | The health level to produce when the event happens, by name. |
|  **optional** expiry | [optional hiber.Duration](#hiberduration) | After the expiry duration, the event will not affect health anymore. Clear for manual resolving of events. |
| deprecated_expiry | [ hiber.UpdateOptionalDuration](#hiberupdateoptionalduration) | <strong>Deprecated.</strong>  |


## Enums
### ListEventsRequest.Sort


| Name | Description | Number |
| ---- | ----------- | ------ |
| TIME_DESCENDING |  | 0 |
| TIME_ASCENDING |  | 1 |
| DEVICE_NUMBER_ASC |  | 2 |
| DEVICE_NUMBER_DESC |  | 3 |
| DEVICE_NUMBER_SPECIFIED |  | 4 |



## Referenced messages from assignment.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [assignment.proto](https://github.com/HiberGlobal/api/blob/master/assignment.proto).


### hiber.assign.Assign

Add assignments.


### hiber.assign.Assign.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign**.assign_parsers | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign**.assign_alarms | [ hiber.modem.alarm.ModemAlarmSelection](#hibermodemalarmmodemalarmselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign**.assign_modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign**.assign_assets | [ hiber.asset.AssetSelection](#hiberassetassetselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **to**.to_modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **to**.to_tags | [ hiber.tag.TagSelection](#hibertagtagselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **to**.to_assets | [ hiber.asset.AssetSelection](#hiberassetassetselection) |  |
| alarm_parameters | [map hiber.assign.Assign.Request.AlarmParametersEntry](#hiberassignassignrequestalarmparametersentry) | The alarm parameters, by alarm identifier, if any, overriding any default values in the alarm(s). |
|  **optional** override_time | [optional hiber.Timestamp](#hibertimestamp) | Time that the assignment should be active. This sets the assignment to start in the past, but would not have effect in the past for assignments like parsers and alarms (they will only be triggered for new messages / values). It would however work for assets having access to device data. This is not allowed to be a value in the future at the moment. |
|  **optional** end_time | [optional hiber.Timestamp](#hibertimestamp) | Time that the assignment ended. This marks the assignment as ended at the given moment in the past, but would not have effect in the past for assignments like parsers and alarms (i.e. no alarm events are removed). It would however work for assets having access to device data. This is not allowed to be a value in the future at the moment. |
|  **optional** override_conflicting_assignments | [optional bool](#bool) | Instead of throwing an error when there are conflicting assignments, unassign the conflicting assignments with the given time (override_time or now) and then making the assignment. |

### hiber.assign.Assign.Request.AlarmParametersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ google.protobuf.Struct](#googleprotobufstruct) |  |

### hiber.assign.Assign.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| assigned | [repeated hiber.assign.Assignment](#hiberassignassignment) |  |
| request | [ hiber.assign.Assign.Request](#hiberassignassignrequest) |  |

### hiber.assign.Assignment

An assignment assigning one thing to another.

Assignment is transitive: when an alarm or parser is assigned to a tag, and the tag is assigned to a modem,
  the alarm or parser is considered assigned to that modem.
This only works in one direction, though. Assigning the alarm or parser to the modem directly does not also assign
the tag.

Assignment can have a custom start and end time.
This can extend into the past, but would not have effect in the past for assignments like parsers.
It would however work for assets having access to device data.
This can also extend into the future, but while the unassigned event will be produced, the assignment will
still be visible until the given time.

Assignments that are no longer active (end time is in the past) and that no longer have an effect
(currently only asset device assignment has an ongoing effect) may be cleaned up automatically.

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.assign.AssignmentType](#hiberassignassignmenttype) | The type of assignment. This is a helper enum to indicate which fields are set. |
| start | [ hiber.Timestamp](#hibertimestamp) | Time this assignment started. This is always in the past. |
|  **optional** end | [optional hiber.Timestamp](#hibertimestamp) | Time this assignment ended, if it has ended. Inactive assignments that no longer have an effect may be cleaned up automatically. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign**.assign_parser | [ hiber.assign.Assignment.ModemMessageBodyParserAssignment](#hiberassignassignmentmodemmessagebodyparserassignment) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign**.assign_alarm | [ hiber.assign.Assignment.AlarmAssignment](#hiberassignassignmentalarmassignment) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign**.assign_modem | [ string](#string) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign**.assign_asset | [ string](#string) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **to**.to_modem | [ string](#string) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **to**.to_parser | [ hiber.assign.Assignment.ModemMessageBodyParserAssignment](#hiberassignassignmentmodemmessagebodyparserassignment) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **to**.to_tag | [ hiber.tag.Tag](#hibertagtag) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **to**.to_asset | [ string](#string) |  |

### hiber.assign.Assignment.AlarmAssignment



| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) |  |
| name | [ string](#string) |  |
| description | [ string](#string) |  |
| parameters | [ google.protobuf.Struct](#googleprotobufstruct) |  |

### hiber.assign.Assignment.ModemMessageBodyParserAssignment



| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) |  |
| name | [ string](#string) |  |
| owner_organization | [ string](#string) |  |

### hiber.assign.AssignmentSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** assets | [optional hiber.asset.AssetSelection](#hiberassetassetselection) | Select the assets to return the assignments for. Optional, when omitted or empty everything is included. |
|  **optional** modems | [optional hiber.modem.ModemSelection](#hibermodemmodemselection) | Select the modems to return the assignments for. Optional, when omitted or empty everything is included. |
|  **optional** modem_alarms | [optional hiber.modem.alarm.ModemAlarmSelection](#hibermodemalarmmodemalarmselection) | Select the alarms to return the assignments for. Optional, when omitted or empty everything is included. |
|  **optional** modem_message_body_parsers | [optional hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) | Select the message body parsers to return the assignments for. Optional, when omitted or empty everything is included. |
|  **optional** tags | [optional hiber.tag.TagSelection](#hibertagtagselection) | Select the tags to return the assignments for. Optional, when omitted or empty everything is included. |
|  **optional** types | [optional hiber.assign.AssignmentSelection.AssignmentTypes](#hiberassignassignmentselectionassignmenttypes) | Select by type of assignment. |

### hiber.assign.AssignmentSelection.AssignmentTypes



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated hiber.assign.AssignmentType](#hiberassignassignmenttype) |  |
| exclude | [repeated hiber.assign.AssignmentType](#hiberassignassignmenttype) |  |

### hiber.assign.DeleteAssignment




### hiber.assign.DeleteAssignment.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unassign**.unassign_parsers | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unassign**.unassign_alarms | [ hiber.modem.alarm.ModemAlarmSelection](#hibermodemalarmmodemalarmselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unassign**.unassign_modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unassign**.unassign_assets | [ hiber.asset.AssetSelection](#hiberassetassetselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **from**.from_modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **from**.from_tags | [ hiber.tag.TagSelection](#hibertagtagselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **from**.from_assets | [ hiber.asset.AssetSelection](#hiberassetassetselection) |  |

### hiber.assign.DeleteAssignment.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| deleted | [repeated hiber.assign.Assignment](#hiberassignassignment) |  |
| request | [ hiber.assign.DeleteAssignment.Request](#hiberassigndeleteassignmentrequest) |  |

### hiber.assign.ListAlarmAssignments




### hiber.assign.ListAlarmAssignments.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional hiber.assign.AssignmentSelection](#hiberassignassignmentselection) | Select the assignments to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |
|  **optional** include_child_organizations | [optional hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | Whether to include modems from child organizations in this list (and which organizations). |
|  **optional** include_alarms_without_assignments | [optional bool](#bool) | Whether to include alarms that are in the selection and have no assignments. |
|  **optional** apply_unit_preferences | [optional bool](#bool) | Apply your UnitPreferences to the alarm checks. For example, if a temperature check is configured in kelvin, but your unit preferences specify celsius for temperature, the check value will be converted to celsius instead. |

### hiber.assign.ListAlarmAssignments.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| alarms | [repeated hiber.assign.ListAlarmAssignments.Response.AlarmAssignment](#hiberassignlistalarmassignmentsresponsealarmassignment) |  |
| request | [ hiber.assign.ListAlarmAssignments.Request](#hiberassignlistalarmassignmentsrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### hiber.assign.ListAlarmAssignments.Response.AlarmAssignment

Things that an alarm is assigned to.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| alarm | [ hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) |  |
| modems | [repeated hiber.assign.ListAlarmAssignments.Response.AlarmAssignment.ToModem](#hiberassignlistalarmassignmentsresponsealarmassignmenttomodem) | The modem numbers this alarm is assigned to, with the alarm parameters. |
| tags | [repeated hiber.assign.ListAlarmAssignments.Response.AlarmAssignment.ToTag](#hiberassignlistalarmassignmentsresponsealarmassignmenttotag) | The tags this alarm is assigned to, with the alarm parameters. |
| assets | [repeated hiber.assign.ListAlarmAssignments.Response.AlarmAssignment.ToAsset](#hiberassignlistalarmassignmentsresponsealarmassignmenttoasset) | The assets this alarm is assigned to, with the alarm parameters. |

### hiber.assign.ListAlarmAssignments.Response.AlarmAssignment.ToAsset



| Field | Type | Description |
| ----- | ---- | ----------- |
| asset_identifier | [ string](#string) |  |
| parameters | [ google.protobuf.Struct](#googleprotobufstruct) |  |

### hiber.assign.ListAlarmAssignments.Response.AlarmAssignment.ToModem



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem_number | [ string](#string) |  |
| parameters | [ google.protobuf.Struct](#googleprotobufstruct) |  |

### hiber.assign.ListAlarmAssignments.Response.AlarmAssignment.ToTag



| Field | Type | Description |
| ----- | ---- | ----------- |
| tag | [ hiber.tag.Tag](#hibertagtag) |  |
| parameters | [ google.protobuf.Struct](#googleprotobufstruct) |  |

### hiber.assign.ListAssetAssignments




### hiber.assign.ListAssetAssignments.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional hiber.assign.AssignmentSelection](#hiberassignassignmentselection) | Select the assignments to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |
|  **optional** include_assets_without_assignments | [optional bool](#bool) | Whether to include assets that are in the selection and have no assignments. |
|  **optional** include_alarm_details | [optional bool](#bool) | Whether to include the full alarms that are assigned, instead of just assignment. |
|  **optional** apply_unit_preferences | [optional bool](#bool) | Apply your UnitPreferences to the alarm checks. For example, if a temperature check is configured in kelvin, but your unit preferences specify celsius for temperature, the check value will be converted to celsius instead. |

### hiber.assign.ListAssetAssignments.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| assets | [repeated hiber.assign.ListAssetAssignments.Response.AssetAssignment](#hiberassignlistassetassignmentsresponseassetassignment) |  |
| request | [ hiber.assign.ListAssetAssignments.Request](#hiberassignlistassetassignmentsrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### hiber.assign.ListAssetAssignments.Response.AssetAssignment

Things that an alarm is assigned to.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| asset_identifier | [ string](#string) |  |
| devices | [repeated string](#string) | The devices assigned to this asset. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | The tags for this asset. |
| alarms | [repeated hiber.assign.Assignment.AlarmAssignment](#hiberassignassignmentalarmassignment) | The identifiers and parameters of the alarms that are assigned to this asset. |
| alarm_details | [repeated hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) | The alarms that are assigned to this asset, if you have permission to view them. |

### hiber.assign.ListAssignments




### hiber.assign.ListAssignments.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional hiber.assign.AssignmentSelection](#hiberassignassignmentselection) | Select the assignments to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |
|  **optional** include_inactive_assignments | [optional bool](#bool) | Include assignments that are no longer active. |

### hiber.assign.ListAssignments.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| assignments | [repeated hiber.assign.Assignment](#hiberassignassignment) | The assignments as identifiers in the selection. |
| request | [ hiber.assign.ListAssignments.Request](#hiberassignlistassignmentsrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### hiber.assign.ListModemAssignments




### hiber.assign.ListModemAssignments.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional hiber.assign.AssignmentSelection](#hiberassignassignmentselection) | Select the assignments to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |
|  **optional** include_alarm_details | [optional bool](#bool) | Whether to include the full alarms that are assigned, instead of just assignment. |
|  **optional** include_message_body_parser_details | [optional bool](#bool) | Whether to include the full parsers that are assigned, instead of just assignment. |
|  **optional** include_message_body_parser_content | [optional bool](#bool) | Whether to include, for example, the message body parser ksy content in the result. Excluded by default to save data. |
|  **optional** include_modems_without_assignments | [optional bool](#bool) | Whether to include modems that are in the selection and have no assignments. |
|  **optional** apply_unit_preferences | [optional bool](#bool) | Apply your UnitPreferences to the alarm checks. For example, if a temperature check is configured in kelvin, but your unit preferences specify celsius for temperature, the check value will be converted to celsius instead. |

### hiber.assign.ListModemAssignments.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [repeated hiber.assign.ListModemAssignments.Response.ModemAssignment](#hiberassignlistmodemassignmentsresponsemodemassignment) |  |
| request | [ hiber.assign.ListModemAssignments.Request](#hiberassignlistmodemassignmentsrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### hiber.assign.ListModemAssignments.Response.ModemAssignment

Things that are assigned to a modem.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| modem_number | [ string](#string) |  |
| message_body_parsers | [repeated hiber.assign.Assignment.ModemMessageBodyParserAssignment](#hiberassignassignmentmodemmessagebodyparserassignment) | The identifiers of the message body parsers that are assigned to this modem. |
| alarms | [repeated hiber.assign.Assignment.AlarmAssignment](#hiberassignassignmentalarmassignment) | The identifiers and parameters of the alarms that are assigned to this modem. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | The tags for this modem. |
| message_body_parser_details | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser) | The details of the parsers assigned to this modem. |
| alarm_details | [repeated hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) | The alarms that are assigned to this modem, if you have permission to view them. |
| asset_identifiers | [repeated string](#string) | The assets assigned to this device. |

### hiber.assign.ListModemMessageBodyParserAssignments




### hiber.assign.ListModemMessageBodyParserAssignments.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional hiber.assign.AssignmentSelection](#hiberassignassignmentselection) | Select the assignments to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |
|  **optional** include_child_organizations | [optional hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | Whether to include modems from child organizations in this list (and which organizations). |
|  **optional** include_parser_without_assignments | [optional bool](#bool) | Whether to include alarms that are in the selection and have no assignments. |

### hiber.assign.ListModemMessageBodyParserAssignments.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| parsers | [repeated hiber.assign.ListModemMessageBodyParserAssignments.Response.ModemMessageBodyParserAssignment](#hiberassignlistmodemmessagebodyparserassignmentsresponsemodemmessagebodyparserassignment) |  |
| request | [ hiber.assign.ListModemMessageBodyParserAssignments.Request](#hiberassignlistmodemmessagebodyparserassignmentsrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### hiber.assign.ListModemMessageBodyParserAssignments.Response.ModemMessageBodyParserAssignment

Things that an alarm is assigned to.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| message_body_parser | [ hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser) |  |
| modems | [repeated string](#string) | The modem numbers this alarm is assigned to, with the alarm parameters. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | The tags this alarm is assigned to, with the alarm parameters. |

### hiber.assign.ListTagAssignments




### hiber.assign.ListTagAssignments.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional hiber.assign.AssignmentSelection](#hiberassignassignmentselection) | Select the assignments to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |
|  **optional** include_alarm_details | [optional bool](#bool) | Whether to include the full alarms that are assigned, instead of just assignment. |
|  **optional** include_message_body_parser_details | [optional bool](#bool) | Whether to include the full parsers that are assigned, instead of just assignment. |
|  **optional** include_message_body_parser_content | [optional bool](#bool) | Whether to include, for example, the message body parser ksy content in the result. Excluded by default to save data. |
|  **optional** include_tags_without_assignments | [optional bool](#bool) | Whether to include alarms that are in the selection and have no assignments. |
|  **optional** apply_unit_preferences | [optional bool](#bool) | Apply your UnitPreferences to the alarm checks. For example, if a temperature check is configured in kelvin, but your unit preferences specify celsius for temperature, the check value will be converted to celsius instead. |

### hiber.assign.ListTagAssignments.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| tags | [repeated hiber.assign.ListTagAssignments.Response.TagAssignment](#hiberassignlisttagassignmentsresponsetagassignment) |  |
| request | [ hiber.assign.ListTagAssignments.Request](#hiberassignlisttagassignmentsrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### hiber.assign.ListTagAssignments.Response.TagAssignment

Things that an alarm is assigned to.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| tag | [ hiber.tag.Tag](#hibertagtag) |  |
| modems | [repeated string](#string) | The modems with this tag. |
| message_body_parsers | [repeated hiber.assign.Assignment.ModemMessageBodyParserAssignment](#hiberassignassignmentmodemmessagebodyparserassignment) | The identifiers of the message body parsers that are assigned to this tag. |
| alarms | [repeated hiber.assign.Assignment.AlarmAssignment](#hiberassignassignmentalarmassignment) | The identifiers and parameters of the alarms that are assigned to this tag. |
| message_body_parser_details | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser) | The details of the parsers assigned to this tag. |
| alarm_details | [repeated hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) | The alarms that are assigned to this tag, if you have permission to view them. |
| asset_identifiers | [repeated string](#string) | The assets assigned to this tag. |

### hiber.assign.Unassign

Remove a assignment.


### hiber.assign.Unassign.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unassign**.unassign_parsers | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unassign**.unassign_alarms | [ hiber.modem.alarm.ModemAlarmSelection](#hibermodemalarmmodemalarmselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unassign**.unassign_modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unassign**.unassign_assets | [ hiber.asset.AssetSelection](#hiberassetassetselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **from**.from_modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **from**.from_tags | [ hiber.tag.TagSelection](#hibertagtagselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **from**.from_assets | [ hiber.asset.AssetSelection](#hiberassetassetselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **time**.override_time | [ hiber.Timestamp](#hibertimestamp) | Time that the assignment ended. This marks the assignment as ended at the given moment in the past, but would not have effect in the past for assignments like parsers and alarms (i.e. no alarm events are removed). It would however work for assets having access to device data. This is not allowed to be a value in the future at the moment. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **time**.remove_time | [ bool](#bool) | Remove time from the assignment, if any. Effectively deletes the assignment if it was set with a time. Setting this to true makes this identical to using the Delete rpc. |

### hiber.assign.Unassign.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| unassigned | [repeated hiber.assign.Assignment](#hiberassignassignment) |  |
| request | [ hiber.assign.Unassign.Request](#hiberassignunassignrequest) |  |


### Enums
#### hiber.assign.AssignmentType
The types of assignment available, like assigning a message body parser to a modem.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT |  | 0 |
| ASSIGNS_MESSAGE_BODY_PARSER_TO_MODEM | Assignment that assigns a message body parser to a modem. | 1 |
| ASSIGNS_ALARM_TO_MODEM | Assignment that assigns a modem alarm to a modem. | 2 |
| ASSIGNS_ALARM_TO_ASSET | Assignment that assigns an alarm to an asset. | 9 |
| ASSIGNS_MODEM_TO_TAG | Assignment that assigns a modem to a tag. | 4 |
| ASSIGNS_MESSAGE_BODY_PARSER_TO_TAG | Assignment that assigns a message body parser to a tag, effectively assigning it to all modems with that tag. | 5 |
| ASSIGNS_ALARM_TO_TAG | Assignment that assigns a modem alarm to a tag, effectively assigning it to all modems with that tag. | 6 |
| ASSIGNS_ASSET_TO_TAG | Assignment that assigns an asset to a tag. | 7 |
| ASSIGNS_ASSET_TO_DEVICE | Assignment that assigns an asset to a device. | 8 |



## Referenced messages from asset.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [asset.proto](https://github.com/HiberGlobal/api/blob/master/asset.proto).


### hiber.asset.Asset

Assets are things that collect the data produced by devices.
Devices are assigned to assets to handle data ownership.
When a device is replaced, the data flow for the asset continues with the data from the new device.
Multiple devices can be assigned to an asset, though it is advisable to only do so when they send
different type of data (i.e. one sensor for pressure and one for flow).

For example, if you have a Well, you might have assets for Annulus A and the tubing head.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) |  |
| name | [ string](#string) | Name of the asset |
|  **optional** type | [optional hiber.asset.Asset.Type](#hiberassetassettype) | Type of the asset, if any of the predefined types applies. |
|  **optional** description | [optional string](#string) | Longer detailed description of the asset. |
|  **optional** notes | [optional string](#string) | Multiline notes field that can be used to add additional information to an asset. |
|  **optional** time_zone | [optional string](#string) | Optional time zone for the asset. This can, for example, be used to calculate SLAs on a daily basis, adjusted by time zone. |
|  **optional** expected_transmission_rate | [optional hiber.value.Value.Numeric.Rate](#hibervaluevaluenumericrate) | The expected transmission rate for this asset. |
| metadata | [ google.protobuf.Struct](#googleprotobufstruct) | Metadata for the asset. This can be automatically populated from linked devices or manually added. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | Tags assigned to this asset |
| devices | [repeated hiber.asset.Asset.AssignedDevice](#hiberassetassetassigneddevice) | Devices assigned to this asset |
| inactive_devices | [repeated hiber.asset.Asset.AssignedDevice](#hiberassetassetassigneddevice) | Devices that were assigned to this asset in the past |
| organization | [ string](#string) | The organization that owns this asset. Typically only relevant if child organizations are included. |

### hiber.asset.Asset.AssignedDevice

A device assigned to this asset.
Non-operational values that the device produces will be linked to this asset
(i.e. pressure, but not battery level).

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

### hiber.asset.AssetSelection

Selection object for assets.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifiers | [repeated string](#string) | Select assets by identifier. |
| search | [repeated string](#string) | Search assets by (partial, case insensitive) identifier, name, description, notes and time zone. |
| types | [repeated hiber.asset.Asset.Type](#hiberassetassettype) | Select assets by type. |
|  **optional** filter_by_tags | [optional hiber.tag.TagSelection](#hibertagtagselection) | Select assets by tags |


### Enums
#### hiber.asset.Asset.Type
Predefined assets types that can be used to say something about the data.
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



## Referenced messages from export.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [export.proto](https://github.com/HiberGlobal/api/blob/master/export.proto).


### hiber.export.AvailableFieldsForExport




### hiber.export.AvailableFieldsForExport.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **configuration**.modem_message | [ hiber.export.Export.Configuration.ModemMessages](#hiberexportexportconfigurationmodemmessages) | Get the fields for modem messages, with optional specific fields for the selected modems, based on assigned parsers. Time range is ignored for this request. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **configuration**.asset_values | [ hiber.export.Export.Configuration.AssetValues](#hiberexportexportconfigurationassetvalues) | Get the fields for asset values. Time range is ignored for this request. |

### hiber.export.AvailableFieldsForExport.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| json_paths | [repeated string](#string) | All json paths that are available for json field mapping. |
| csv_columns | [repeated hiber.export.Export.Format.Csv.Column](#hiberexportexportformatcsvcolumn) | Available CSV columns, pre-named with suggested names. |

### hiber.export.CreateExport




### hiber.export.CreateExport.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| name | [ string](#string) |  |
| format | [ hiber.export.Export.Format](#hiberexportexportformat) | The format for the export. |
| configuration | [ hiber.export.Export.Configuration](#hiberexportexportconfiguration) | Specific configuration for the export. |
|  **optional** email_subscribe | [optional bool](#bool) | Subscribe to email updates to get an email with links when the export is ready. |

### hiber.export.CreateExport.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| created | [ hiber.export.Export](#hiberexportexport) |  |
| request | [ hiber.export.CreateExport.Request](#hiberexportcreateexportrequest) |  |

### hiber.export.DeleteExport




### hiber.export.DeleteExport.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) |  |

### hiber.export.DeleteExport.Response




### hiber.export.Export

An export created by this organization.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) | Identifier for this export. |
| name | [ string](#string) | The name given for this export. |
| status | [ hiber.export.Export.Status](#hiberexportexportstatus) | Status of this export. Whether it's available, expired or still processing. |
| urls | [repeated hiber.export.Export.File](#hiberexportexportfile) | When the status is READY, the downloadable file(s) in the export. The file may be a single url, or may be split into multiple parts, each with a unique url. |
| expires_at | [ hiber.Timestamp](#hibertimestamp) | When the export expires. Only set when the status is READY or EXPIRED. |
| format | [ hiber.export.Export.Format](#hiberexportexportformat) | The format for the export. |
| configuration | [ hiber.export.Export.Configuration](#hiberexportexportconfiguration) | Specific configuration for the export. |
| error | [ string](#string) | When the status is FAILED, this error message contains details on the reason of the failure. |

### hiber.export.Export.Configuration

The configuration for the export, which determines what data is exported.

| Field | Type | Description |
| ----- | ---- | ----------- |
| expires_in | [ hiber.Duration](#hiberduration) | The time urls will be available after the moment the export has the READY status. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.modem_message | [ hiber.export.Export.Configuration.ModemMessages](#hiberexportexportconfigurationmodemmessages) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.asset_values | [ hiber.export.Export.Configuration.AssetValues](#hiberexportexportconfigurationassetvalues) |  |

### hiber.export.Export.Configuration.AssetValues

Export values for a set of assets.

| Field | Type | Description |
| ----- | ---- | ----------- |
| asset_identifiers | [repeated string](#string) |  |
| time_range | [ hiber.TimeRange](#hibertimerange) |  |

### hiber.export.Export.Configuration.ModemMessages

Export modem messages for a set of modems.

| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [repeated string](#string) |  |
| time_range | [ hiber.TimeRange](#hibertimerange) |  |

### hiber.export.Export.File

Downloadable file.

| Field | Type | Description |
| ----- | ---- | ----------- |
| name | [ string](#string) |  |
| url | [ string](#string) |  |

### hiber.export.Export.Format

The format for the export.

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.export.Export.Format.Type](#hiberexportexportformattype) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **configuration**.json | [ hiber.export.Export.Format.Json](#hiberexportexportformatjson) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **configuration**.csv | [ hiber.export.Export.Format.Csv](#hiberexportexportformatcsv) |  |

### hiber.export.Export.Format.Csv

CSV (comma separated values) format for export.

| Field | Type | Description |
| ----- | ---- | ----------- |
| columns | [repeated hiber.export.Export.Format.Csv.Column](#hiberexportexportformatcsvcolumn) | The columns in the CSV, with their mapping. Columns in CSV are a flat structure, while the data is generally nested, so a mapping is required to flatten it to simple columns. |
|  **optional** separator | [optional string](#string) | The separator character to use in the CSV. Default: , |
|  **optional** quote | [optional string](#string) | The quote character to use in the CSV. Default: " |
|  **optional** escape | [optional string](#string) | The escape character to use in the CSV. Default: " |
|  **optional** newline | [optional string](#string) | The newlines to use in the CSV. Default: \n |

### hiber.export.Export.Format.Csv.Column



| Field | Type | Description |
| ----- | ---- | ----------- |
| name | [ string](#string) | Column name. |
| json_path | [ string](#string) | Column mapping from the nested structure to a value. |

### hiber.export.Export.Format.Json

Json format for export.

| Field | Type | Description |
| ----- | ---- | ----------- |
| custom_fields | [map hiber.export.Export.Format.Json.CustomFieldsEntry](#hiberexportexportformatjsoncustomfieldsentry) | Custom fields mapping, if a reduced json is desired. |
| compact | [ bool](#bool) | Whether the json should be formatted or as compact as possible. |

### hiber.export.Export.Format.Json.CustomFieldsEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ string](#string) |  |

### hiber.export.ExportSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| identifiers | [repeated string](#string) | Select by identifiers |
|  **optional** search | [optional string](#string) | Search through identifiers and urls |
|  **optional** include_expired | [optional bool](#bool) | Whether to include expired exports. |

### hiber.export.ExtendExportDownloadExpiry




### hiber.export.ExtendExportDownloadExpiry.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | Export identifier |
| extend_by | [ hiber.Duration](#hiberduration) | The time to extend the expiry with. |
| file | [repeated string](#string) | Extend the expiry for a specific file. If empty, all files are extended. |

### hiber.export.ExtendExportDownloadExpiry.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| export | [ hiber.export.Export](#hiberexportexport) |  |

### hiber.export.ListExports




### hiber.export.ListExports.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional hiber.export.ExportSelection](#hiberexportexportselection) | Select the exports to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |

### hiber.export.ListExports.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| exports | [repeated hiber.export.Export](#hiberexportexport) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |
| request | [ hiber.export.ListExports.Request](#hiberexportlistexportsrequest) |  |


### Enums
#### hiber.export.Export.Format.Type


| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT |  | 0 |
| JSON |  | 1 |
| CSV |  | 2 |

#### hiber.export.Export.Status


| Name | Description | Number |
| ---- | ----------- | ------ |
| READY | Files can be downloaded now | 0 |
| EXPIRED | Export has expired and is no longer available. | 1 |
| PROCESSING | Data is still being processed to create the export. | 2 |
| FAILED | The export failed. See the error message for more details. | 3 |



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
|  **optional** search | [optional string](#string) | Search for the given string in the levels and colors. |
| levels | [repeated string](#string) | Filter by exact levels. |


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
|  **optional** override_url_validation | [optional bool](#bool) | Set this flag to not parse the url or enforce mqtts. |

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
|  **optional** override_url_validation | [optional bool](#bool) | Set this flag to not parse the url or enforce mqtts. |

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
| organization | [ string](#string) |  |
| name | [ string](#string) | An optional descriptor given to the modem |
| location | [ hiber.Location](#hiberlocation) |  |
| last_message_id | [ uint64](#uint64) |  |
| last_message_received_at | [ hiber.Timestamp](#hibertimestamp) | Time the server has received the last message. |
| last_message_sent_at | [ hiber.Timestamp](#hibertimestamp) | Time the modem has sent the last message. |
| last_message_body | [ hiber.BytesOrHex](#hiberbytesorhex) | The body of the last message. |
| inactivity | [ hiber.Duration](#hiberduration) | The amount of time since the last message from this modem was received on the server. |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | Health level based on the modem alarm and some always-present alarms. |
| lifecycle | [ hiber.modem.Modem.Lifecycle](#hibermodemmodemlifecycle) |  |
| technical | [ hiber.modem.Modem.TechnicalData](#hibermodemmodemtechnicaldata) | additional information |
| peripherals | [ hiber.modem.Modem.Peripherals](#hibermodemmodemperipherals) |  |
| notes | [ string](#string) | Notes field that can be used to add additional information to a modem. |
| secure_notes | [ string](#string) | Secure notes field that can be used to add additional information to a modem, with limited accessibility. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| is_gateway | [ bool](#bool) | <strong>Deprecated.</strong> [DEPRECATED] Whether the modem is a gateway, it has been configured as a gateway and has connected devices. Use `type` instead. |
| is_device_connected_to_gateway | [ bool](#bool) | <strong>Deprecated.</strong> [DEPRECATED] Whether the modem is connected to a modem configured as a gateway. Use `type` instead. |
| connected_to_gateway | [ string](#string) | <strong>Deprecated.</strong> [DEPRECATED] The modem number that this modem is connected to, if any. Use `connected_device_info.connected_to_gateway` instead. |
| external_device_ids | [repeated string](#string) | <strong>Deprecated.</strong> [DEPRECATED] External device ids, if any. Use `connected_device_info.external_device_ids` instead. |
| type | [ hiber.modem.Modem.Type](#hibermodemmodemtype) | The type of modem. Used mainly to differentiate in the UI or to sort on. |
| gateway_info | [ hiber.modem.Modem.GatewayInfo](#hibermodemmodemgatewayinfo) | Additional information when this modem is a gateway. |
| connected_device_info | [ hiber.modem.Modem.ConnectedDeviceInfo](#hibermodemmodemconnecteddeviceinfo) | Additional information when this modem is a connected device. |
| metadata | [ google.protobuf.Struct](#googleprotobufstruct) | Modem metadata, typically extracted from messages. |
| time_zone | [ string](#string) | The timezone configured for the modem. |
| transmission_interval | [ hiber.Duration](#hiberduration) | The transmission interval for this modem, if configured. |
|  **optional** expected_transmission_rate | [optional hiber.value.Value.Numeric.Rate](#hibervaluevaluenumericrate) | The expected transmission rate for this modem. |
| numeric_value_types | [repeated hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype) | The numeric value types that this device produces. The device may produce other values (like battery level), but these are the primary value types. |

### hiber.modem.ModemSelection

Selection object for modems.
Filter modems by modem id, (child)organization, tags, activation status and time, service type and last message time.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** modems | [optional hiber.Filter.Modems](#hiberfiltermodems) |  |
|  **optional** free_text_search | [optional string](#string) |  |
|  **optional** only_active | [optional bool](#bool) | <strong>Deprecated.</strong> Use lifecycle filter instead. |
|  **optional** activated_in | [optional hiber.TimeRange](#hibertimerange) | <strong>Deprecated.</strong>  |
|  **optional** with_last_message_in | [optional hiber.TimeRange](#hibertimerange) |  |
| health_levels | [repeated string](#string) | Filter modems by health level. |
| lifecycles | [repeated hiber.modem.Modem.Lifecycle](#hibermodemmodemlifecycle) | Filter modems by lifecycle(s). Defaults to nominal lifecycles, excluding disabled or decommissioned modems. |
|  **optional** transfers | [optional hiber.modem.ModemSelection.Transfers](#hibermodemmodemselectiontransfers) |  |
| include_types | [repeated hiber.modem.Modem.Type](#hibermodemmodemtype) | Only include modems that have a type listed in types. In other words, when providing multiple types, this is an "OR" relationship. |
| exclude_types | [repeated hiber.modem.Modem.Type](#hibermodemmodemtype) | Exclude modems that have a type listed in types. |
|  **optional** device_types | [optional hiber.Filter.DeviceTypes](#hiberfilterdevicetypes) |  |
|  **optional** sensorBrands | [optional hiber.Filter.SensorBrands](#hiberfiltersensorbrands) |  |
|  **optional** identifiers | [optional hiber.Filter.ModemIdentifiers](#hiberfiltermodemidentifiers) |  |
|  **optional** only_gateways | [optional bool](#bool) | <strong>Deprecated.</strong> [DEPRECATED] Only list devices that are a gateway. Replaced by `types`. If you only want to have gateways in the result, create a selection with only `Modem.Type.GATEWAY` for `types`. |
|  **optional** only_has_external_device_ids | [optional bool](#bool) | <strong>Deprecated.</strong> [DEPRECATED] Only list devices that are a connected devices. Typically these are LoRaWAN sensors. Replaced by `types`. If you only want to have connected devices in the result, create a selection with only `Modem.Type.CONNECTED_DEVICE` for `types`. |
|  **optional** connected_to_gateways | [optional hiber.Filter.Modems](#hiberfiltermodems) |  |
| external_device_ids | [repeated string](#string) | <strong>Deprecated.</strong>  |
|  **optional** filter_by_tags | [optional hiber.tag.TagSelection](#hibertagtagselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **peripheral_selection**.peripherals | [ hiber.modem.ModemSelection.Peripherals](#hibermodemmodemselectionperipherals) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **peripheral_selection**.only_without_peripheral | [ bool](#bool) | When set to true, only modems that do not have any peripheral will be included in the result. |
|  **optional** only_connected_to_gateway | [optional bool](#bool) | Only select modems that are connected to a gateway (connected devices). |
|  **optional** not_connected_to_gateway | [optional bool](#bool) | Only select modems that are not connected to a gateway (i.e. gateways). |


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
| ACCEPTANCE_TESTING | Device is being tested by Hiber. Devices in this state are not visible to customers. | 0 |
| READY_TO_INSTALL | Device has passed Acceptance Testing and is ready be installed. When it sends it first message, it will automatically go to INSTALLED. Devices in this state are not visible to customers. | 8 |
| INSTALLED | Device is active and sending messages. | 1 |
| PAUSED | Device is paused and not sending messages. This should be of a temporary nature (e.g. a change to the installation is being made). On its next message, it will automatically go back to INSTALLED. Offline alarm checks will not be triggered for devices in this lifecycle. | 6 |
| DISABLED | Device is disabled and not sending messages. This is a more permanent version of PAUSED. Devices in this state are not visible to customers. | 5 |
| DECOMMISSIONED | Device is (going to be) removed from installation and will not return to installed status again. Devices in this state are not visible to customers. | 4 |
| DEFECTIVE | Device is defective and should not be used anymore. Devices in this state are typically RMA-ed and (should be) transferred to the RMA organization. Devices in this state are not visible to customers. | 7 |
| SPARE | Spare device sent to customer in case it is needed. | 9 |

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



## Referenced messages from modem_alarm.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [modem_alarm.proto](https://github.com/HiberGlobal/api/blob/master/modem_alarm.proto).


### hiber.modem.alarm.AssignModemAlarms

Add direct assignments.
If an overlapping assignment using a rule exists, it is shadowed by the direct assignment.

Simplified version of assign.AssignDirectly.


### hiber.modem.alarm.AssignModemAlarms.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarms | [ hiber.modem.alarm.ModemAlarmSelection](#hibermodemalarmmodemalarmselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign_to**.modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign_to**.assets | [ hiber.asset.AssetSelection](#hiberassetassetselection) |  |
| parameters | [map hiber.modem.alarm.AssignModemAlarms.Request.ParametersEntry](#hibermodemalarmassignmodemalarmsrequestparametersentry) | The alarm parameters, by alarm identifier, if any, overriding any default values in the alarm(s). |

### hiber.modem.alarm.AssignModemAlarms.Request.ParametersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ google.protobuf.Struct](#googleprotobufstruct) |  |

### hiber.modem.alarm.AssignModemAlarms.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| created | [repeated hiber.modem.alarm.AssignedModemAlarm](#hibermodemalarmassignedmodemalarm) |  |
| request | [ hiber.modem.alarm.AssignModemAlarms.Request](#hibermodemalarmassignmodemalarmsrequest) |  |

### hiber.modem.alarm.AssignedModemAlarm

Directly assigned modem alarm to a modem.

| Field | Type | Description |
| ----- | ---- | ----------- |
| alarm_identifier | [ string](#string) |  |
| modem_number | [ string](#string) |  |

### hiber.modem.alarm.CreateModemAlarm

Create a new alarm.

The request contains the option to add checks as well.
This is a shortcut for creating an alarm and then adding checks, and as such can result in multiple events:
- a created event on the alarm
- an update event on the alarm checks, iff any checks were added


### hiber.modem.alarm.CreateModemAlarm.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| name | [ string](#string) | A name for the alarm. |
|  **optional** description | [optional string](#string) | A short description of what the alarm should do. |
| trigger_condition | [ hiber.modem.alarm.ModemAlarm.TriggerCondition](#hibermodemalarmmodemalarmtriggercondition) | Condition determining when an alarm is triggered if it has multiple checks. |
| checks | [repeated hiber.modem.alarm.ModemAlarm.Check](#hibermodemalarmmodemalarmcheck) | The checks to add to this alarm. Shortcut for creating an alarm and then adding checks to it. |
|  **optional** default_health_level | [optional string](#string) | The default health level for this alarm. See ModemAlarm.default_health_level for more information. |
|  **optional** health_level_after_resolved | [optional hiber.modem.alarm.ModemAlarm.HealthLevelAfterResolved](#hibermodemalarmmodemalarmhealthlevelafterresolved) | The health level this alarm should cause after it is resolved. See ModemAlarm.health_level_after_resolved for more information. |

### hiber.modem.alarm.CreateModemAlarm.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| created | [ hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) | The created modem alarm. |

### hiber.modem.alarm.DeleteModemAlarm

Delete an alarm.


### hiber.modem.alarm.DeleteModemAlarm.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | Identifier of the modem alarm to delete. |

### hiber.modem.alarm.DeleteModemAlarm.Response




### hiber.modem.alarm.ListModemAlarms

List modem alarms in an organization.


### hiber.modem.alarm.ListModemAlarms.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional hiber.modem.alarm.ModemAlarmSelection](#hibermodemalarmmodemalarmselection) | Selection criteria for listing modem alarms. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) | Pagination for the returned alarms. |
|  **optional** apply_unit_preferences | [optional bool](#bool) | Apply your UnitPreferences to the alarm checks. For example, if a temperature check is configured in kelvin, but your unit preferences specify celsius for temperature, the check value will be converted to celsius instead. |

### hiber.modem.alarm.ListModemAlarms.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem_alarms | [repeated hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) | A list of modem alarms. |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | A pagination object, which can be used to go through the alarms. |
| request | [ hiber.modem.alarm.ListModemAlarms.Request](#hibermodemalarmlistmodemalarmsrequest) | The request made to list the given alarms. |

### hiber.modem.alarm.ModemAlarm

Alarm for a modem, monitoring message data, location or activity.

An alarm is a collection of checks that validate the correctness of a modem. For example, an alarm might
check that the modem is in a given location, or that a field in its messages is between certain values.

Health for an alarm event is determined by taking the most severe health level from the health_levels configured
on the failing checks, using this default for any checks that do not have a health_level configured.
This can be changed on assignment with the default_health_level parameter, to fit the needs of the organization.

Note, when an alarm is inherited the health levels may not match yours. If the health level matches one of
your health levels, that level is used. Otherwise, the catch-all health level is used.
See the health definition for more information on the catch-all health level (typically the most severe).
Note that the health level displayed here is the result of the steps above.

When assigned to a (set of) modem(s), an alarm can be customized using its parameters.
Parameters are based on the check fields, and are also used in the check error message template.
For the alarm parameters, check parameters are prefixed with the check identifier.

For example: An alarm with check A (field "healthy" equals 1) and check B (field "state" oneof ["OK", "ACTIVE"])
would have the following parameters:
{
  "A": {
    "expected": 1,
    "field.path": "healthy",
    "field.equals.expected": 1
  },
  "B": {
    "expected": ["OK", "ACTIVE"],
    "field.path": "state",
    "field.oneof.expected": ["OK", "ACTIVE"]
  }
}

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) | The identifier for this alarm. This identifier is globally unique. |
| name | [ string](#string) | Short name for this alarm (optional). |
| description | [ string](#string) | Longer description for this alarm (optional). |
| created_at | [ hiber.Timestamp](#hibertimestamp) | When this alarm was created. |
| updated_at | [ hiber.Timestamp](#hibertimestamp) | When this alarm was last updated. |
| trigger_condition | [ hiber.modem.alarm.ModemAlarm.TriggerCondition](#hibermodemalarmmodemalarmtriggercondition) | Condition determining when an alarm is triggered if it has multiple checks. |
| default_health_level | [ string](#string) | The default health level for checks in this alarm, if they have no health_level configured. |
| health_level_after_resolved | [ hiber.modem.alarm.ModemAlarm.HealthLevelAfterResolved](#hibermodemalarmmodemalarmhealthlevelafterresolved) | Allow the alarm to cause a health level for the modem even after it has been resolved. By configuring this, you can specify the modem health should be affected for a longer period. For example, when using an inactivity check, this could be used to configure modem health ERROR while inactive, lowering to INVESTIGATE for a day after a new message comes in. |
| checks | [repeated hiber.modem.alarm.ModemAlarm.Check](#hibermodemalarmmodemalarmcheck) | The checks in this alarm, that validate the state of the modem. |
| alarm_parameters | [ google.protobuf.Struct](#googleprotobufstruct) | Parameters for this alarm. This field displays all the parameters that can be set for the alarm on assignment, with their current value. |

### hiber.modem.alarm.ModemAlarm.Check

A check is a specification of how things should be, i.e. "a value should be within this range".
When it fails, it produces an event with:
- a custom health level, or the default defined in the alarm
- an error message, define from a template in the check

The error message template is a string with parameters for the relevant data.
The parameters are included as {parameter}, which gets replaced with the value.

The supported parameters are different per check, but the parameters below are always supported:
- modem:name: the modem name.
- modem:number: the modem number.
- message: the id of the message, if any.
- expected: a shortcut for the expected value(s), depending on the check:
  - inactivity check: expected duration
  - location check: expected area as [(bottom left), (top right)], and shape as [(point), (point), ..., (point)]
  - equals/minimum/maximum check: expected value
  - oneof check (allowed/blocked): expected values as [a, b, c]
  - threshold/delta check: expected range as minimum..maximum, extended with duration for delta check
- actual: the invalid actual value(s) for this check.

The checks below define other available parameters.

For example (using some parameters for specific checks):
- "Your device {modem} has left its designated area! It is now at {actual}."
- "Your device battery is at {actual}%, which is below the recommended minimum of {field.threshold.minimum}%."
- "Your device battery is draining faster than expected: {actual}% over the past {field.delta.period}."
- "Your device temperature has exceeded {value.threshold.maximum} degrees: {actual}."
- "Your device reported an unhealthy state {actual}. Healthy states are: {expected}."
- "Your device reported an unhealthy state {actual}. Healthy states are: {field.oneof.expected}."
- "Your device reported an unhealthy state {actual}. Please set it back to {expected}."
- "Your device reported an unhealthy state {actual}. Please set it back to {field.equals.expected}."
- "Unexpected value {actual} for field {field.path}!"

Numeric values can be formatted with an extra postfix on the parameters
- Round numeric values by adding ":.2f" (for 2 decimals). For example: "{actual:.3f}" (rounds to 3 decimals)
- Always sign numeric values (when rounded) by prefixing the format with a plus. For example: `{actual:+.3f}`
- This is applied to numeric fields and fields that can be numeric, like `{actual}` and `{expected}`.

| Field | Type | Description |
| ----- | ---- | ----------- |
| name | [ string](#string) | Name of this check, unique within the alarm. This is used to update or remove the check, and to determine the destination for any parameters. If omitted, a random name is generated based on the type of check. |
|  **optional** description | [optional string](#string) | Longer description for this check (optional). |
|  **optional** health_level | [optional string](#string) | The health level that this check would cause for a modem, when it fails. If not set, the alarm default is used. |
|  **optional** error_message_template | [optional string](#string) | The error message template for this check, with parameters that will be filled in based on the check. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.location | [ hiber.modem.alarm.ModemAlarm.Check.LocationCheck](#hibermodemalarmmodemalarmchecklocationcheck) | Check whether the device is in a given location. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.field | [ hiber.modem.alarm.ModemAlarm.Check.FieldCheck](#hibermodemalarmmodemalarmcheckfieldcheck) | Check that a message body field has a specified value. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.inactivity | [ hiber.modem.alarm.ModemAlarm.Check.InactivityCheck](#hibermodemalarmmodemalarmcheckinactivitycheck) | Check whether the device exceeds inactivity limits. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.delay | [ hiber.modem.alarm.ModemAlarm.Check.DelayCheck](#hibermodemalarmmodemalarmcheckdelaycheck) | Check whether a message delay exceeds delay limits. |

### hiber.modem.alarm.ModemAlarm.Check.DelayCheck

Check whether the message was delayed more than a configured limit.
The delay is the time between the message was sent (ModemMessage.sent_at) and the time it was
received on the server (ModemMessage.received_at).

Has the following parameters:
- delay.maximum: the maximum allowed delay

| Field | Type | Description |
| ----- | ---- | ----------- |
| maximum | [ hiber.Duration](#hiberduration) | The maximum value for the message delay (duration between sent and received time). |

### hiber.modem.alarm.ModemAlarm.Check.FieldCheck

A check that evaluates each new message, and checks selected field(s) in the parsed body.

When multiple fields are selected, the checks are applied to all of them individually.

See the Json Path documentation at https://goessner.net/articles/JsonPath/ for details on json path.
We currently do not allow filter expressions.

Simple examples selecting a field:
- $.my_field: a field in the root of the parsed object
- $.my_obj.my_field: a field in a deeper structure
- $.my_array[x].my_field: the field my_field of the element at index x is selected

Complex use cases are also possible, but they require a bit more understanding of json path logic:
- $.my_array.length(): the length of my_array is selected. Combine with an equals or threshold check,
to require that an array has a certain length.
- $.my_array..my_field: the array of my_field values (for all objects in my_array) is selected
- $.my_array[*].my_field: the array of my_field values (for all objects in my_array) is selected

Note that for the examples above, if they return an array, the entire array is used as the value
in the comparison for equals and oneof.

A check of this type has the following parameters (matches the fields):
- field.path: replace the path for this field
- field.ignoreFieldNotFound: replace the value for ignore_field_not_found

For the equals check:
- field.equals.expected: iff this is an equals check, replace the expected value

For the allowed check:
- field.allowed.allowed: iff this is an allowed check, replace the expected values

For the blocked check:
- field.blocked.blocked: iff this is a blocked check, replace the expected values

For the threshold check:
- field.threshold.expected: iff this is a threshold check, replace the expected range
- field.threshold.minimum: iff this is a threshold check, replace the expected minimum
- field.threshold.maximum: iff this is a threshold check, replace the expected maximum

For the delta check:
- field.delta.period: iff this is a delta check, replace the expected duration
- field.delta.threshold.expected: iff this is a delta check, replace the expected range
- field.delta.threshold.minimum: iff this is a delta check, replace the expected minimum
- field.delta.threshold.maximum: iff this is a delta check, replace the expected maximum

All of the parameters above can be used in the error message template.

The delta check also adds a few additional error message variables:
- {field.delta.previous}: the previous value for the field
- {field.delta.difference} (also {actual}): the difference between previous and current value for the field
- {field.delta.current}: the current value for the field

| Field | Type | Description |
| ----- | ---- | ----------- |
| path | [ string](#string) | Select the field(s) that this check is applied to, using a json path. |
| ignore_field_not_found | [ bool](#bool) | Whether to ignore this check if the field is not found. This can be useful if your path selects multiple values in an array, like my_array[*].value, and not all entries have the field, or when fields are omitted if they have a default value. |
|  **optional** unit | [optional hiber.field.Field.Numeric.Unit](#hiberfieldfieldnumericunit) | The unit that this alarm check is using. The field's values will automatically be converted into this unit before the check is applied. Note: unit is not currently available in the alarm_parameters. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.equals | [ hiber.modem.alarm.ModemAlarm.Check.FieldCheck.EqualsCheck](#hibermodemalarmmodemalarmcheckfieldcheckequalscheck) | Check that a field equals a value. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.allowed | [ hiber.modem.alarm.ModemAlarm.Check.FieldCheck.AllowedCheck](#hibermodemalarmmodemalarmcheckfieldcheckallowedcheck) | Check that a field equals one of a set of values. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.blocked | [ hiber.modem.alarm.ModemAlarm.Check.FieldCheck.BlockedCheck](#hibermodemalarmmodemalarmcheckfieldcheckblockedcheck) | Check that a field does not equal one of a set of values. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.minimum | [ hiber.modem.alarm.ModemAlarm.Check.FieldCheck.MinimumCheck](#hibermodemalarmmodemalarmcheckfieldcheckminimumcheck) | Chech that a field is higher than the given value. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.maximum | [ hiber.modem.alarm.ModemAlarm.Check.FieldCheck.MaximumCheck](#hibermodemalarmmodemalarmcheckfieldcheckmaximumcheck) | Check that a field is lower than the given value. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.threshold | [ hiber.modem.alarm.ModemAlarm.Check.FieldCheck.ThresholdCheck](#hibermodemalarmmodemalarmcheckfieldcheckthresholdcheck) | Check that a field is within a given numeric range. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.blocked_range | [ hiber.modem.alarm.ModemAlarm.Check.FieldCheck.BlockedRangeCheck](#hibermodemalarmmodemalarmcheckfieldcheckblockedrangecheck) | Check that a field is not in a given numeric range. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.delta | [ hiber.modem.alarm.ModemAlarm.Check.FieldCheck.DeltaCheck](#hibermodemalarmmodemalarmcheckfieldcheckdeltacheck) | Check that a field's difference in value over a given period is within a specified numeric range. |

### hiber.modem.alarm.ModemAlarm.Check.FieldCheck.AllowedCheck

Check that the field is in a set of expected values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| allowed | [repeated google.protobuf.Value](#googleprotobufvalue) | The list of allowed values, one of which should match the field value. |

### hiber.modem.alarm.ModemAlarm.Check.FieldCheck.BlockedCheck

Check that the field is not in a set of blocked values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| blocked | [repeated google.protobuf.Value](#googleprotobufvalue) | The list of blocked values; the field should not match any of them. |

### hiber.modem.alarm.ModemAlarm.Check.FieldCheck.BlockedRangeCheck

Check that the field is outside of a range.
If the minimum is higher than the maximum (i.e. 30..10), this is automatically converted into a
ThresholdCheck.

| Field | Type | Description |
| ----- | ---- | ----------- |
| blocked | [ hiber.DoubleRange](#hiberdoublerange) | The range the value must not be in. |

### hiber.modem.alarm.ModemAlarm.Check.FieldCheck.DeltaCheck

A check that evaluates the differences in values over time, for the selected field(s) in the parsed body.

| Field | Type | Description |
| ----- | ---- | ----------- |
| period | [ hiber.Duration](#hiberduration) | The period to evaluate when determining the value difference. |
| threshold | [ hiber.modem.alarm.ModemAlarm.Check.FieldCheck.ThresholdCheck](#hibermodemalarmmodemalarmcheckfieldcheckthresholdcheck) | Check that the delta is within a given numeric range. |
| encrypted | [ bool](#bool) | Whether the field data should be encrypted in cache storage. Delta checks use a cache for field from messages that are affected by a delta check. Encrypting the individual field values is (relatively) computationally expensive and may lead to a slightly delayed alarm event. In the future, some delta features may only be available to unencrypted values due to performance issues. |
| ignore_previous_value_not_found | [ bool](#bool) | Whether to ignore this check if the previous value is not found (i.e. there is no history). |

### hiber.modem.alarm.ModemAlarm.Check.FieldCheck.EqualsCheck

Check that the field is equal to the given value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| expected | [ google.protobuf.Value](#googleprotobufvalue) | The expected value a field should have. |

### hiber.modem.alarm.ModemAlarm.Check.FieldCheck.MaximumCheck

Check that the field is lower than the given value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| maximum | [ double](#double) | The maximum numeric value the field should have. |

### hiber.modem.alarm.ModemAlarm.Check.FieldCheck.MinimumCheck

Check that the field is higher than the given value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| minimum | [ double](#double) | The minimum numeric value the field should have. |

### hiber.modem.alarm.ModemAlarm.Check.FieldCheck.ThresholdCheck

Check that the field is above a minimum threshold and under a maximum threshold.
If the minimum is higher than the maximum (i.e. 30..10), this is automatically converted into a
BlockedRangeCheck.

| Field | Type | Description |
| ----- | ---- | ----------- |
| expected | [ hiber.DoubleRange](#hiberdoublerange) | The range the value must be in. |
| minimum | [ double](#double) | The minimum expected value, available separately for convenience and check parameters. |
| maximum | [ double](#double) | The maximum expected value, available separately for convenience and check parameters. |

### hiber.modem.alarm.ModemAlarm.Check.InactivityCheck

Check whether the device exceeds inactivity limits.

Has the following parameters:
- inactivity.maximum: the maximum allowed inactivity

| Field | Type | Description |
| ----- | ---- | ----------- |
| maximum | [ hiber.Duration](#hiberduration) | The maximum value for the modem's inactivity (time since last message was received on the server). |

### hiber.modem.alarm.ModemAlarm.Check.LocationCheck

Check that the device location is within a given area.

Has the following parameters:
- location.expected: replace the referenced named location
- location.named: replace the referenced named location

| Field | Type | Description |
| ----- | ---- | ----------- |
| named | [ string](#string) | Specify the name of a named location (NamedLocation) that the device must be in. |

### hiber.modem.alarm.ModemAlarm.HealthLevelAfterResolved

Allow the alarm to cause a health level for the modem even after a new message has come in.

Typically, an alarm event only affects the modem health while it is from the last message from that modem.
By configuring this, you can specify the modem health should be affected for a longer period.

For example, when using an inactivity check, this could be used to configure modem health ERROR while
inactive, lowering to INVESTIGATE for a day after a new message comes in.

| Field | Type | Description |
| ----- | ---- | ----------- |
| health_level | [ string](#string) | The health level that this check would cause for a modem, when the original failure is resolved. |
| period | [ hiber.Duration](#hiberduration) | The amount of time that this health level would be active. |

### hiber.modem.alarm.ModemAlarmSelection

Selection criteria for listing modem alarms in an organization. If no options are provided, all modem alarms
are valid.

If values are provided both for identifiers and search, then only alarms are selected that match both criteria.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifiers | [repeated string](#string) | Selects alarms by the given list of alarm identifiers. |
|  **optional** search | [optional string](#string) | Search for the given string in identifier, description, fields and values. |

### hiber.modem.alarm.TestModemAlarmTestParameters

Test a set of parameters on a modem alarm, to see the result when they are applied during assignment.


### hiber.modem.alarm.TestModemAlarmTestParameters.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarm_identifier | [ string](#string) | The identifier of the alarm on which to test parameters. |
| parameters | [ google.protobuf.Struct](#googleprotobufstruct) | The parameters of the alarm that are changed. |

### hiber.modem.alarm.TestModemAlarmTestParameters.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| result | [ hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) |  |

### hiber.modem.alarm.UnassignModemAlarms

Remove a direct assignment.
If an overlapping assignment using a rule exists, it is not affected, except that it is longer shadowed.

Simplified version of assign.UnassignDirectly.


### hiber.modem.alarm.UnassignModemAlarms.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarms | [ hiber.modem.alarm.ModemAlarmSelection](#hibermodemalarmmodemalarmselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unassign_from**.modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unassign_from**.assets | [ hiber.asset.AssetSelection](#hiberassetassetselection) |  |

### hiber.modem.alarm.UnassignModemAlarms.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| removed_direct_assignments | [repeated hiber.modem.alarm.AssignedModemAlarm](#hibermodemalarmassignedmodemalarm) |  |
| request | [ hiber.modem.alarm.UnassignModemAlarms.Request](#hibermodemalarmunassignmodemalarmsrequest) |  |

### hiber.modem.alarm.UpdateModemAlarm

Update the alarm, iff you are the owner or can impersonate the owner organization.

The request contains the option to add, remove or update checks as well.
This is a shortcut for updating an alarm and then adding, removing and/or updating checks,
and as such can result in multiple events:
- an update event on the alarm, iff there were any non-check changes to the alarm.
- an update event on the alarm checks, iff there were any check addition, updates or deletions


### hiber.modem.alarm.UpdateModemAlarm.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifiers of the alarm to update |
|  **optional** update_name | [optional hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong> Update the name, optionally. |
|  **optional** name | [optional string](#string) |  |
|  **optional** update_description | [optional hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong> Update the description, optionally. |
|  **optional** description | [optional string](#string) |  |
|  **optional** update_trigger_condition | [optional hiber.modem.alarm.ModemAlarm.TriggerCondition](#hibermodemalarmmodemalarmtriggercondition) | Update the trigger condition, optionally. |
|  **optional** update_default_health_level | [optional hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong> Update the default health level, optionally. |
|  **optional** default_health_level | [optional string](#string) |  |
|  **optional** update_health_level_after_resolved | [optional hiber.modem.alarm.ModemAlarm.HealthLevelAfterResolved](#hibermodemalarmmodemalarmhealthlevelafterresolved) | Update the health after resolved, optionally. |
|  **optional** remove_health_level_after_resolved | [optional bool](#bool) | Remove the health after resolved, optionally. |
| add_checks | [repeated hiber.modem.alarm.ModemAlarm.Check](#hibermodemalarmmodemalarmcheck) | The checks to add to this alarm. Shortcut for updating an alarm and then adding checks to it. |
| update_checks | [map hiber.modem.alarm.UpdateModemAlarm.Request.UpdateChecksEntry](#hibermodemalarmupdatemodemalarmrequestupdatechecksentry) | The checks to update in this alarm. Shortcut for updating an alarm and then updating checks. |
| delete_checks | [repeated string](#string) | The checks to remove from this alarm. Shortcut for updating an alarm and then removing checks. |

### hiber.modem.alarm.UpdateModemAlarm.Request.UpdateChecksEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ hiber.modem.alarm.ModemAlarm.Check](#hibermodemalarmmodemalarmcheck) |  |

### hiber.modem.alarm.UpdateModemAlarm.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) |  |

### hiber.modem.alarm.UpdateModemAlarmAddCheck

Add a check to the alarm, iff you are the owner or can impersonate the owner organization.


### hiber.modem.alarm.UpdateModemAlarmAddCheck.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarm_identifier | [ string](#string) | The identifier of the alarm to which the check is added. |
| check | [ hiber.modem.alarm.ModemAlarm.Check](#hibermodemalarmmodemalarmcheck) | The check to add to the Modem Alarm. Identifier of the check must be unique within the alarm. |

### hiber.modem.alarm.UpdateModemAlarmAddCheck.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) |  |

### hiber.modem.alarm.UpdateModemAlarmRemoveCheck

Remove a check from an alarm.


### hiber.modem.alarm.UpdateModemAlarmRemoveCheck.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarm_identifier | [ string](#string) | The identifier of the alarm from which to remove the check. |
| check_identifier | [ string](#string) | The identifier of the check to remove. |

### hiber.modem.alarm.UpdateModemAlarmRemoveCheck.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) |  |

### hiber.modem.alarm.UpdateModemAlarmUpdateCheck

Update a check of an alarm.

Only the values of a check can be updated, e.g., it is not possible to change an inactivity check to a location
check.


### hiber.modem.alarm.UpdateModemAlarmUpdateCheck.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarm_identifier | [ string](#string) | The identifier of the alarm of which to update the check. |
| check_identifier | [ string](#string) | The identifier of the check to update. |
| update_check | [ hiber.modem.alarm.ModemAlarm.Check](#hibermodemalarmmodemalarmcheck) | The new values for the check of this alarm. |
| test_parameters_only | [ bool](#bool) | If set, the update is not actually saved, but only applied and returned. This is a convenience to easily test parameters for a check similar to TestModemAlarmTestParameters. |

### hiber.modem.alarm.UpdateModemAlarmUpdateCheck.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) |  |


### Enums
#### hiber.modem.alarm.ModemAlarm.TriggerCondition
Condition determining when an alarm is triggered if it has multiple checks.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | Defaults to the current value when updating, or to ANY_CHECK_FAILED when creating. | 0 |
| ANY_CHECK_FAILED | Trigger the alarm when any of the checks fail. This is useful when providing a single device health alarm, that checks, for example, battery, operating temperature, etc. and should trigger when any of those are outside the expected range. | 1 |
| ALL_CHECKS_FAILED | Trigger the alarm only when all checks fail. This is useful when creating a combined alarm, where several data points factor into the decisions to trigger the alarm, for example, combining a check on the current value with a delta check on the historical values, to trigger only if the value is high for a longer period. | 2 |



## Referenced messages from modem_message_body_parser.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [modem_message_body_parser.proto](https://github.com/HiberGlobal/api/blob/master/modem_message_body_parser.proto).


### hiber.modem.message.bodyparser.AssignModemMessageBodyParsers

Add direct assignments.
If an overlapping assignment using a rule exists, it is shadowed by the direct assignment.

Simplified version of assign.AssignDirectly.


### hiber.modem.message.bodyparser.AssignModemMessageBodyParsers.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| assign_parsers | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) |  |
| to_modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) |  |

### hiber.modem.message.bodyparser.AssignModemMessageBodyParsers.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| created | [repeated hiber.modem.message.bodyparser.AssignedModemMessageBodyParser](#hibermodemmessagebodyparserassignedmodemmessagebodyparser) |  |
| request | [ hiber.modem.message.bodyparser.AssignModemMessageBodyParsers.Request](#hibermodemmessagebodyparserassignmodemmessagebodyparsersrequest) |  |

### hiber.modem.message.bodyparser.AssignedModemMessageBodyParser

Directly assigned modem message parser to a modem.

| Field | Type | Description |
| ----- | ---- | ----------- |
| parser_identifier | [ string](#string) |  |
| modem_number | [ string](#string) |  |

### hiber.modem.message.bodyparser.CreateSimpleModemMessageBodyParserRequest

Create a simple modem message parser, which generates a .ksy specification.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| parser | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser](#hibermodemmessagebodyparsersimplemodemmessagebodyparser) |  |

### hiber.modem.message.bodyparser.DeleteModemMessageBodyParserRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) | A selection of parsers to be deleted. |

### hiber.modem.message.bodyparser.DeleteModemMessageBodyParserRequest.Response




### hiber.modem.message.bodyparser.ListModemMessageBodyParsersRequest

List the parser your organizations has access to. This may include inherited parsers.

If include_content is not set, this call may omit parser specifications, like the ksy, since those are
typically larger multi-line strings.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) | Select the parsers to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |
|  **optional** exclude_content | [optional bool](#bool) | Whether to omit the content in the resulting ModemMessageBodyParsers. |

### hiber.modem.message.bodyparser.ListModemMessageBodyParsersRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| parsers | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |
| request | [ hiber.modem.message.bodyparser.ListModemMessageBodyParsersRequest](#hibermodemmessagebodyparserlistmodemmessagebodyparsersrequest) |  |

### hiber.modem.message.bodyparser.MakeModemMessageBodyParserAvailableToChildOrganizationRequest

Make this parser available to a specific child organizations.

This will
- when the organization is on the exclude list, remove it
- when the includeAll flag is false, add it to the include list (if not already present)

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the parser that should be updated. |
| available_to | [repeated string](#string) | The child organization(s) that the parser should be available to. |

### hiber.modem.message.bodyparser.MakeModemMessageBodyParserUnavailableToChildOrganizationRequest

Make this parser unavailable to a specific child organizations.

This will
- when the organization is on the include list, remove it
- when the includeAll flag is true, add it to the exclude list (if not already present)

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the parser that should be updated. |
| unavailable_to | [repeated string](#string) | The child organization(s) that the parser should be unavailable to. |

### hiber.modem.message.bodyparser.ModemMessageBodyParser

Modem message body parser. This defines a parsing strategy for the body of a message.
A parser can be defined in two ways: using a .ksy (Kaitai struct https://kaitai.io/) file or using the simple parser.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) | The globally (across organizations) unique identifier for this parser. |
| organization | [ string](#string) | The organization that created the parser. |
| name | [ string](#string) | The name for this parser. |
| content_ksy | [ string](#string) | The content of this parsers script. If simple_parser is set, this content is generated from that definition. This field may be omitted by the list call to save data. |
| simple_parser | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser](#hibermodemmessagebodyparsersimplemodemmessagebodyparser) | The simple parser this .ksy was generated from, if it was generated from a simple parser. This field may be omitted on demand to save data in the list call. |
| data_fields | [repeated hiber.field.Field](#hiberfieldfield) | Fields in the parsed result that contain data. Data fields are cached for efficient retrieval and allow all kinds of processing. |
| metadata_fields | [ hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafields) | Fields in the parsed result that contain metadata, and special things like a location. |
| available_to_child_organizations | [ hiber.modem.message.bodyparser.ModemMessageBodyParser.AvailableToChildOrganizations](#hibermodemmessagebodyparsermodemmessagebodyparseravailabletochildorganizations) | If set, this parser is available to your child organizations, as a Provided parser. |
| post_processing | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser.PostProcessing](#hibermodemmessagebodyparsermodemmessagebodyparserpostprocessing) | <strong>Deprecated.</strong> The list of post-processing steps applied to the result of this parser. |
| require_message_metadata | [map hiber.modem.message.bodyparser.ModemMessageBodyParser.RequireMessageMetadataEntry](#hibermodemmessagebodyparsermodemmessagebodyparserrequiremessagemetadataentry) | <strong>Deprecated.</strong> In order to use this parser on a message, the metadata on the message must match the given requirement here. The key of the map is the json-path to look for in the message metadata, the value of the map is the json to expect at that json-path. Deprecated: use metadata_fields.require_message_metadata |

### hiber.modem.message.bodyparser.ModemMessageBodyParser.AvailableToChildOrganizations

A modem message body parser with this object is available to child organizations.
This means the child organization can use it, but not update or delete it.

| Field | Type | Description |
| ----- | ---- | ----------- |
| child_organizations | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) |  |

### hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields

Fields in the parsed result that match common things that can be processed by the system,
like a location or battery percentage.

| Field | Type | Description |
| ----- | ---- | ----------- |
| location_fields | [ hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields.LocationFields](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafieldslocationfields) | Specify a pair of fields in the message body that contain location data, which will update the modem location and the map. |
| message_metadata_fields | [repeated string](#string) | Custom metadata fields, which will be added to the message metadata json. |
| modem_metadata_fields | [repeated string](#string) | Custom metadata fields, which will be added to the modem metadata json. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **measured_at_field**.measured_at_time_field | [ string](#string) | Field that contains the time (epoch seconds) to use for the values extracted from the message. If not set, sent time is used. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **measured_at_field**.measured_at_offset_field | [ string](#string) | Field that contains the time offset (second before sent time) to use for the values extracted from the message. If not set, sent time is used. |
| require_message_metadata | [map hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields.RequireMessageMetadataEntry](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafieldsrequiremessagemetadataentry) | In order to use this parser on a message, the metadata on the message must match the given requirement here. The key of the map is the json-path to look for in the message metadata, the value of the map is the json to expect at that json-path. |

### hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields.LocationFields



| Field | Type | Description |
| ----- | ---- | ----------- |
| latitude | [ string](#string) |  |
| longitude | [ string](#string) |  |

### hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields.RequireMessageMetadataEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ google.protobuf.Value](#googleprotobufvalue) |  |

### hiber.modem.message.bodyparser.ModemMessageBodyParser.RequireMessageMetadataEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ google.protobuf.Value](#googleprotobufvalue) |  |

### hiber.modem.message.bodyparser.ModemMessageBodyParserSelection

Selection object for parsers. Used to select which parser to list, assign, etc.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifiers | [repeated string](#string) | Filter parsers by their identifiers. |
|  **optional** search | [optional string](#string) | Find parsers by searching for this text in the name, content_ksy, data fields or simple parser definition. |
|  **optional** only_simple | [optional bool](#bool) | Only return simple parsers, created using SimpleModemMessageBodyParser. |
|  **optional** only_ksy_file | [optional bool](#bool) | Only return parsers created from an uploaded .ksy file. |
|  **optional** only_owned_parsers | [optional bool](#bool) | Exclude parsers that are not owned by your organization (those that you did not create yourself). |
| owner_organizations | [repeated string](#string) | Only return parsers that were created by the given parent organizations. |
| has_data_fields | [repeated string](#string) | Only return parsers that have one of the given data fields This only works when the fields are marked explicitly using the data fields option. |

### hiber.modem.message.bodyparser.RenameModemMessageBodyParserRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the parser that should be updated. |
| name | [ string](#string) | The new name for this parser. |

### hiber.modem.message.bodyparser.RetryModemMessageBodyParsing

Retry a message, parsing it with all the currently assigned parsers that are in the given selection.
If the message was previously parsed by any of those parsers, the previous result is replaced.


### hiber.modem.message.bodyparser.RetryModemMessageBodyParsing.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| modem_message_ids | [repeated uint64](#uint64) | The messages to parse. |
| parser_selection | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) | A selection of parsers to apply, if they are assigned. |
| suppress_events | [ bool](#bool) | Re-parsing messages causes new events to be sent out. Set suppress_events to true to prevent that. |

### hiber.modem.message.bodyparser.RetryModemMessageBodyParsing.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| parsed_messages | [repeated hiber.modem.ModemMessage.ParsedBody](#hibermodemmodemmessageparsedbody) |  |

### hiber.modem.message.bodyparser.SimpleModemMessageBodyParser

Simple modem message body parser. This can be used a convenient way to create a .ksy parser.

| Field | Type | Description |
| ----- | ---- | ----------- |
| name | [ string](#string) | Parser name. When this structure is used as a custom type inside a parser, this name is a reduced to a value containing only lowercase letters, numbers and underscores, like field names. |
| documentation | [ string](#string) | A short, single line description of the field. |
| fields | [repeated hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfield) | The fields in this object. |
| default_endian | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Endian](#hibermodemmessagebodyparsersimplemodemmessagebodyparserendian) | Sets a default endianness for this parser's fields and any fields in custom types. |
| default_text_encoding | [ string](#string) | Sets a default string encoding for this parser's fields and any fields in custom types. |
| custom_types | [repeated hiber.modem.message.bodyparser.SimpleModemMessageBodyParser](#hibermodemmessagebodyparsersimplemodemmessagebodyparser) | A list of custom types used for custom types fields. Each is effectively a simple parser, and can have its own custom types again, which can only be used within that parser structure. The parser name is used for custom type fields. |

### hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.DelimitedSize

Delimited size definition, used for Bytes and Text.

| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **size**.size_bytes | [ int32](#int32) | Specifies the number of bytes in this field. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **size**.end_of_stream | [ bool](#bool) | Specifies that this field parses all bytes until the end of the stream. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **size**.field_name | [ string](#string) | Specifies the number of bytes in this field using the value of an Integer field. This integer field must be parsed before this field is parsed. |
| terminator | [ bytes](#bytes) | Specify a terminator that marks the point the field terminates, optionally, and we should continue to the next field. This is typically a single byte (i.e. 0x00). This can be combined with a size to limit the amounts of bytes that are parsed. |

### hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field



| Field | Type | Description |
| ----- | ---- | ----------- |
| name | [ string](#string) | Field name. This is a reduced to a value containing only lowercase letters, numbers and underscores. |
| documentation | [ string](#string) | A short, single line description of the field. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.integer | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Integer](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfieldinteger) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.float | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Float](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfieldfloat) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.bytes | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Bytes](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfieldbytes) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.string | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.String](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfieldstring) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.magic | [ bytes](#bytes) | Specify an expected magic sequence (some bytes that are always the same). |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.custom_type | [ string](#string) | Specify a custom type name. |

### hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Bytes



| Field | Type | Description |
| ----- | ---- | ----------- |
| size | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.DelimitedSize](#hibermodemmessagebodyparsersimplemodemmessagebodyparserdelimitedsize) |  |

### hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Float



| Field | Type | Description |
| ----- | ---- | ----------- |
| size_bytes | [ int32](#int32) | Specifies the size of this floating point number in bytes. |
| endian | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Endian](#hibermodemmessagebodyparsersimplemodemmessagebodyparserendian) | Specifies endian encoding for this field. This can be omitted if default endianness specified. |

### hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Integer



| Field | Type | Description |
| ----- | ---- | ----------- |
| size_bytes | [ int32](#int32) | Specifies the size of this integer in bytes. |
| signed | [ bool](#bool) | Specifies whether this integer is signed or unsigned. |
| endian | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Endian](#hibermodemmessagebodyparsersimplemodemmessagebodyparserendian) | Specifies endian encoding for this field. This can be omitted if default endianness specified. |

### hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.String



| Field | Type | Description |
| ----- | ---- | ----------- |
| size | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.DelimitedSize](#hibermodemmessagebodyparsersimplemodemmessagebodyparserdelimitedsize) |  |
| encoding | [ string](#string) | Specifies encoding for the string. This can be omitted if default encoding specified. |

### hiber.modem.message.bodyparser.TestModemMessageBodyParserRequest

Test a parsers on a message.

This method provides a number of options and can be used in multiple ways:
- Test a real message or an uploaded message body.
- Test using an existing parser, an ksy definition or a simple parser definition.

This can be used to test a parser with a modem's past messages, before assigning it,
or while developing a parser to validate it with an expected body.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **parser**.identifier | [ string](#string) | The identifier of the parser you want to test. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **parser**.content_ksy | [ string](#string) | A ksy definition you want to test. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **parser**.simple_parser | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser](#hibermodemmessagebodyparsersimplemodemmessagebodyparser) | A simple parser definition you want to test. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.parse_bytes | [ hiber.BytesOrHex](#hiberbytesorhex) | A byte array (message body) to parse. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.modem_message_id | [ uint64](#uint64) | The id of an existing message, testing the parser on its body. |

### hiber.modem.message.bodyparser.TestModemMessageBodyParserRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **result**.parsed | [ google.protobuf.Struct](#googleprotobufstruct) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **result**.error | [ string](#string) |  |

### hiber.modem.message.bodyparser.UnassignModemMessageBodyParsers

Remove a direct assignment.
If an overlapping assignment using a rule exists, it is not affected, except that it is longer shadowed.

Simplified version of assign.UnassignDirectly.


### hiber.modem.message.bodyparser.UnassignModemMessageBodyParsers.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| unassign_parsers | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) |  |
| from_modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) |  |

### hiber.modem.message.bodyparser.UnassignModemMessageBodyParsers.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| removed_direct_assignments | [repeated hiber.modem.message.bodyparser.AssignedModemMessageBodyParser](#hibermodemmessagebodyparserassignedmodemmessagebodyparser) |  |
| request | [ hiber.modem.message.bodyparser.UnassignModemMessageBodyParsers.Request](#hibermodemmessagebodyparserunassignmodemmessagebodyparsersrequest) |  |

### hiber.modem.message.bodyparser.UpdateChildOrganizationAvailabilityRequest

Update the child availability for a parser.
Parsers can be made available to child organizations, which means that they can be viewed in,
and assigned to modems in, child organizations.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the parser that should be updated. |
| available_to_child_organizations | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | The new child organization availability filter for this parser. |

### hiber.modem.message.bodyparser.UpdateSimpleModemMessageBodyParserRequest

Update a simple modem message parser, updating the generated .ksy specification.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the parser that should be updated. |
| parser | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser](#hibermodemmessagebodyparsersimplemodemmessagebodyparser) |  |

### hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest

Upload an updated body parser from a .ksy file, replacing the previous file.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the parser that should be updated. |
|  **optional** name | [optional string](#string) | If set, changes the name of the parser. |
|  **optional** content_ksy | [optional string](#string) | The new ksy definition for this parser. |
| add_data_fields | [repeated hiber.field.Field](#hiberfieldfield) | Add fields to the data fields list. |
| remove_data_fields | [repeated string](#string) | Remove fields from the data fields list. |
|  **optional** metadata_fields | [optional hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields](#hibermodemmessagebodyparserupdateuploadedmodemmessagebodyparserrequestmetadatafields) | Fields in the parsed result that match special things that can be processed by the system, like a location. |
| add_post_processing | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser.PostProcessing](#hibermodemmessagebodyparsermodemmessagebodyparserpostprocessing) | <strong>Deprecated.</strong> Add a post-processing step to the result of this parser. |
| remove_post_processing | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser.PostProcessing](#hibermodemmessagebodyparsermodemmessagebodyparserpostprocessing) | <strong>Deprecated.</strong> Remove a post-processing step to the result of this parser. |

### hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** update_location_fields | [optional hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields.LocationFields](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafieldslocationfields) | Update the location fields. |
| add_message_metadata_fields | [repeated string](#string) | Add fields to the message metadata fields list. |
| remove_message_metadata_fields | [repeated string](#string) | Remove fields from the message metadata fields list. |
| replace_message_metadata_fields | [repeated string](#string) | Replace the message metadata fields list. |
| add_modem_metadata_fields | [repeated string](#string) | Add fields to the modem metadata fields list. |
| remove_modem_metadata_fields | [repeated string](#string) | Remove fields from the modem metadata fields list. |
| replace_modem_metadata_fields | [repeated string](#string) | Replace the modem metadata fields list. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **measured_at_field**.measured_at_time_field | [ string](#string) | Update the custom field to extract to measured_at time. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **measured_at_field**.deprecated_measured_at_time_field | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **measured_at_field**.measured_at_offset_field | [ string](#string) | Update the custom field to extract to measured_at offset from the sent_at time in seconds. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **measured_at_field**.deprecated_measured_at_offset_field | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
| add_require_message_metadata | [map hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields.AddRequireMessageMetadataEntry](#hibermodemmessagebodyparserupdateuploadedmodemmessagebodyparserrequestmetadatafieldsaddrequiremessagemetadataentry) | In order to use this parser on a message, the metadata on the message must match the given requirement here. The key of the map is the json-path to look for in the message metadata, the value of the map is the json to expect at that json-path. |
| remove_require_message_metadata | [repeated string](#string) | Remove a requirement for the metadata. Remove by listing the json-path here. |
| replace_require_message_metadata | [map hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields.ReplaceRequireMessageMetadataEntry](#hibermodemmessagebodyparserupdateuploadedmodemmessagebodyparserrequestmetadatafieldsreplacerequiremessagemetadataentry) | Replaces the entire configuration for required message metadata. |

### hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields.AddRequireMessageMetadataEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ google.protobuf.Value](#googleprotobufvalue) |  |

### hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields.ReplaceRequireMessageMetadataEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ google.protobuf.Value](#googleprotobufvalue) |  |

### hiber.modem.message.bodyparser.UploadModemMessageBodyParserRequest

Upload a new body parser from a .ksy file.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| name | [ string](#string) | A descriptive name for this parser. |
| content_ksy | [ string](#string) | The ksy definition for this parser. |
| data_fields | [repeated hiber.field.Field](#hiberfieldfield) | Fields in the parsed result that contain data. This can be useful to track which fields could be plotted, etc. |
|  **optional** metadata_fields | [optional hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafields) | Fields in the parsed result that match special things that can be processed by the system, like a location. |
| post_processing | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser.PostProcessing](#hibermodemmessagebodyparsermodemmessagebodyparserpostprocessing) |  |
| require_message_metadata | [map hiber.modem.message.bodyparser.UploadModemMessageBodyParserRequest.RequireMessageMetadataEntry](#hibermodemmessagebodyparseruploadmodemmessagebodyparserrequestrequiremessagemetadataentry) | In order to use this parser on a message, the metadata on the message must match the given requirement here. The key of the map is the json-path to look for in the message metadata, the value of the map is the json to expect at that json-path. |

### hiber.modem.message.bodyparser.UploadModemMessageBodyParserRequest.RequireMessageMetadataEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ google.protobuf.Value](#googleprotobufvalue) |  |


### Enums
#### hiber.modem.message.bodyparser.ModemMessageBodyParser.PostProcessing
The type of post-processing to be applied to the result of this parser.

| Name | Description | Number |
| ---- | ----------- | ------ |
| NOTHING |  | 0 |

#### hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Endian


| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT |  | 0 |
| LITTLE_ENDIAN |  | 1 |
| BIG_ENDIAN |  | 2 |



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
|  **optional** avatar | [optional hiber.Avatar](#hiberavatar) | The avatar image representing this organization. Usually the logo. |
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
| value | [ hiber.Avatar](#hiberavatar) |  |

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
| MODEM_CREATION | Required to manually create modems using the ModemService. | 4 |
| EARLY_ACCESS | Used for organizations that get early access to features. | 5 |
| EXPERIMENTAL | Used for organizations that get access to experimental features. e.g. feature work in progress. | 6 |
| ASSETS | Access the list of assets in Mission Control. | 10 |
| ASSET_DASHBOARD | Use the new assets as primary data owner in Mission Control dashboards. | 11 |



## Referenced messages from publisher.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [publisher.proto](https://github.com/HiberGlobal/api/blob/master/publisher.proto).


### hiber.publisher.Publisher

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
| deprecated_data | [ hiber.publisher.Publisher.Data](#hiberpublisherpublisherdata) | <strong>Deprecated.</strong> This field remains for backwards compatibility, but it should not be used. |
| filters | [ hiber.publisher.Publisher.Filters](#hiberpublisherpublisherfilters) |  |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| health | [ hiber.Health](#hiberhealth) |  |
| type | [ hiber.publisher.Publisher.Type](#hiberpublisherpublishertype) |  |
| in_cooldown_until | [ hiber.Timestamp](#hibertimestamp) |  |
| disabled | [ bool](#bool) |  |
| created_by | [ string](#string) | Id of the user that created this publisher |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.http | [ hiber.webhook.Webhook.WebhookData](#hiberwebhookwebhookwebhookdata) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.mqtt | [ hiber.integration.mqtt.MQTTPublisher.Data](#hiberintegrationmqttmqttpublisherdata) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.email | [ hiber.email.EmailNotificationPreferences](#hiberemailemailnotificationpreferences) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.slack | [ hiber.integration.slack.SlackPublisher.Data](#hiberintegrationslackslackpublisherdata) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.shell_ssip | [ hiber.publisher.Publisher.Data.ShellSsipConfig](#hiberpublisherpublisherdatashellssipconfig) |  |

### hiber.publisher.Publisher.Data

<strong>Deprecated.</strong> This type remains for backwards compatibility, but it should not be used.

| Field | Type | Description |
| ----- | ---- | ----------- |
| url | [ string](#string) |  |
|  **optional** content_type | [optional hiber.publisher.Publisher.ContentType](#hiberpublisherpublishercontenttype) |  |
|  **optional** disabled | [optional bool](#bool) |  |
|  **optional** certificate_id | [optional int64](#int64) |  |
|  **optional** certificate_name | [optional string](#string) |  |
|  **optional** ca_certificate_id | [optional int64](#int64) |  |
|  **optional** ca_certificate_name | [optional string](#string) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **config**.http | [ hiber.publisher.Publisher.Data.HTTPConfig](#hiberpublisherpublisherdatahttpconfig) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **config**.mqtt | [ hiber.publisher.Publisher.Data.MQTTConfig](#hiberpublisherpublisherdatamqttconfig) |  |

### hiber.publisher.Publisher.Data.HTTPConfig

<strong>Deprecated.</strong> This field remains for backwards compatibility, but it should not be used.

| Field | Type | Description |
| ----- | ---- | ----------- |
| secret | [ string](#string) | Used to generate the HMAC-SHA256 header on every publisher call, which you can use to verify the message. The HMAC-SHA256 header is calculated with the message body and this secret. There are many examples of how to do this in different languages, for example: https://github.com/danharper/hmac-examples |

### hiber.publisher.Publisher.Data.MQTTConfig

<strong>Deprecated.</strong> This field remains for backwards compatibility, but it should not be used.

| Field | Type | Description |
| ----- | ---- | ----------- |
| topic | [ string](#string) |  |
| qos | [ hiber.publisher.Publisher.Data.MQTTConfig.QoS](#hiberpublisherpublisherdatamqttconfigqos) |  |
| username | [ string](#string) | Optional username to authenticate with. |
| password | [ string](#string) | Optional password to authenticate with. Requires username to be set. |
| identifier | [ string](#string) | Identifier used by the MQTT client. Defaults to "hiber". |

### hiber.publisher.Publisher.Data.ShellSsipConfig



| Field | Type | Description |
| ----- | ---- | ----------- |
| url | [ string](#string) |  |
| tenant_id | [ string](#string) |  |
| resource_id | [ string](#string) |  |

### hiber.publisher.Publisher.Filters



| Field | Type | Description |
| ----- | ---- | ----------- |
| event_types | [ hiber.Filter.Events](#hiberfilterevents) |  |
| modem_numbers | [ hiber.Filter.Modems](#hiberfiltermodems) |  |
| tags | [ hiber.Filter.Tags](#hiberfiltertags) |  |

### hiber.publisher.UpdatePublisherRequest

<strong>Deprecated.</strong> 


### hiber.publisher.UpdatePublisherRequest.UpdateModems

<strong>Deprecated.</strong> 

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.Filter.Modems](#hiberfiltermodems) |  |


### Enums
#### hiber.publisher.Publisher.ContentType
<strong>Deprecated.</strong> This type remains for backwards compatibility, but it should not be used.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT |  | 0 |
| JSON |  | 1 |
| PROTO |  | 2 |

#### hiber.publisher.Publisher.Data.MQTTConfig.QoS


| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT |  | 0 |
| AT_MOST_ONCE | Qos level 0 | 1 |
| AT_LEAST_ONCE | Qos level 1 | 2 |
| EXACTLY_ONCE | Qos level 2 | 3 |

#### hiber.publisher.Publisher.Type


| Name | Description | Number |
| ---- | ----------- | ------ |
| HTTP |  | 0 |
| MQTT |  | 1 |
| EMAIL |  | 3 |
| SLACK |  | 4 |
| SHELL_SSIP |  | 5 |



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


## Referenced messages from token.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [token.proto](https://github.com/HiberGlobal/api/blob/master/token.proto).


### hiber.token.CreateTokenRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| name | [ string](#string) |  |
| type | [ hiber.token.Token.Type](#hibertokentokentype) |  |
| expires_at | [ hiber.Timestamp](#hibertimestamp) |  |
|  **optional** user_permissions | [optional hiber.Filter.UserPermissions](#hiberfilteruserpermissions) |  |
| organization_permissions | [ hiber.Filter.OrganizationPermissions](#hiberfilterorganizationpermissions) | Permissions the new token should get. |
|  **optional** roles | [optional hiber.Filter.Roles](#hiberfilterroles) | Roles the new token should get. |
|  **optional** for_user_id | [optional string](#string) | Optionally, if you have the USERS_MANAGE permission, you can make a token for another user. If you do, you cannot grant it permissions they do not have, not can you grant it any user permissions. |
|  **optional** minimize | [optional bool](#bool) | Optionally, attempt to minimize the token size as much as possible. |
|  **optional** limit_impersonation | [optional hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | Optionally, limit the organizations that the token is allowed to impersonate. |

### hiber.token.CreateTokenRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| token | [ string](#string) |  |
| created | [ hiber.token.Token](#hibertokentoken) |  |

### hiber.token.DeleteTokenRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| token_id | [ int64](#int64) |  |

### hiber.token.DeleteTokenRequest.Response




### hiber.token.ListTokensRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional hiber.token.TokenSelection](#hibertokentokenselection) | Select the tokens to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |

### hiber.token.ListTokensRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| tokens | [repeated hiber.token.Token](#hibertokentoken) |  |
| request | [ hiber.token.ListTokensRequest](#hibertokenlisttokensrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### hiber.token.Token



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) |  |
| name | [ string](#string) |  |
| user_id | [ string](#string) |  |
| user_details | [ hiber.token.Token.UserDetails](#hibertokentokenuserdetails) |  |
| organization | [ string](#string) |  |
| expires_at | [ hiber.Timestamp](#hibertimestamp) |  |
| user_permissions | [repeated hiber.UserPermission](#hiberuserpermission) |  |
| organization_permissions | [repeated hiber.OrganizationPermission](#hiberorganizationpermission) |  |
| roles | [repeated string](#string) |  |
| type | [ hiber.token.Token.Type](#hibertokentokentype) |  |
|  **optional** last_used | [optional hiber.Date](#hiberdate) | Date that the token was last used. |
| used_for_this_call | [ bool](#bool) | Set if the current request is made with this token. |
|  **optional** limit_impersonation | [optional hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | Optionally, limit the organizations that the token is allowed to impersonate. |

### hiber.token.Token.UserDetails



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) |  |
| email | [ string](#string) |  |
| name | [ string](#string) |  |

### hiber.token.TokenSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** users | [optional hiber.Filter.Users](#hiberfilterusers) |  |
|  **optional** name | [optional string](#string) |  |
|  **optional** include_expired | [optional bool](#bool) |  |
|  **optional** roles | [optional hiber.Filter.Roles](#hiberfilterroles) |  |
| type | [repeated hiber.token.Token.Type](#hibertokentokentype) |  |

### hiber.token.UpdateTokenOrganizationPermissionsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| token_ids | [repeated int64](#int64) |  |
|  **optional** replace_organization_permissions | [optional hiber.Filter.OrganizationPermissions](#hiberfilterorganizationpermissions) | Completely replace the organization permission for the selected token(s) with this set. |
| add_organization_permissions | [repeated hiber.OrganizationPermission](#hiberorganizationpermission) | Add organization permissions to the token. |
| remove_organization_permissions | [repeated hiber.OrganizationPermission](#hiberorganizationpermission) | Remove organization permissions from the token. Ensures the permissions is no longer on the token (even if you also add it using add_organization_permissions). |

### hiber.token.UpdateTokenOrganizationPermissionsRequest.Response




### hiber.token.UpdateTokenRoles




### hiber.token.UpdateTokenRoles.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| token_ids | [repeated int64](#int64) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **update**.modify | [ hiber.token.UpdateTokenRoles.Request.ModifyRoles](#hibertokenupdatetokenrolesrequestmodifyroles) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **update**.replace | [ hiber.token.UpdateTokenRoles.Request.ReplaceRoles](#hibertokenupdatetokenrolesrequestreplaceroles) |  |

### hiber.token.UpdateTokenRoles.Request.ModifyRoles

Grant and remove roles on the current roles the tokens have.

| Field | Type | Description |
| ----- | ---- | ----------- |
| add | [repeated string](#string) | Grant roles in addition to the current roles the tokens have. |
| remove | [repeated string](#string) | Remove roles from the current roles the tokens have. |

### hiber.token.UpdateTokenRoles.Request.ReplaceRoles

Completely replace the roles the tokens have.

| Field | Type | Description |
| ----- | ---- | ----------- |
| roles | [repeated string](#string) |  |

### hiber.token.UpdateTokenRoles.Response




### hiber.token.UpdateTokenUserPermissionsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| token_ids | [repeated int64](#int64) |  |
|  **optional** replace_user_permissions | [optional hiber.Filter.UserPermissions](#hiberfilteruserpermissions) | Completely replace the user permission for the selected token(s) with this set. |
| add_user_permissions | [repeated hiber.UserPermission](#hiberuserpermission) | Add user permissions to the token. |
| remove_user_permissions | [repeated hiber.UserPermission](#hiberuserpermission) | Remove user permissions from the token. |

### hiber.token.UpdateTokenUserPermissionsRequest.Response





### Enums
#### hiber.token.Token.Type


| Name | Description | Number |
| ---- | ----------- | ------ |
| SPECIFIC | A token with a specific set of permissions, given when the token is created. | 0 |
| PERSONAL | A personal access token has the permissions of the creator. When the creator gains or loses permissions, this applies to the token as well. | 1 |



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

