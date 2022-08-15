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
  - [Event.AssignmentEvent](#eventassignmentevent)
  - [Event.AssignmentEvent.AssignedEvent](#eventassignmenteventassignedevent)
  - [Event.AssignmentEvent.UnassignedEvent](#eventassignmenteventunassignedevent)
  - [Event.ExportEvent](#eventexportevent)
  - [Event.ExportEvent.ExportCreatedEvent](#eventexporteventexportcreatedevent)
  - [Event.ExportEvent.ExportFailedEvent](#eventexporteventexportfailedevent)
  - [Event.ExportEvent.ExportReadyEvent](#eventexporteventexportreadyevent)
  - [Event.Modem](#eventmodem)
  - [Event.ModemEvent](#eventmodemevent)
  - [Event.ModemEvent.AlarmEvent](#eventmodemeventalarmevent)
  - [Event.ModemEvent.AlarmEvent.CreatedEvent](#eventmodemeventalarmeventcreatedevent)
  - [Event.ModemEvent.AlarmEvent.DeletedEvent](#eventmodemeventalarmeventdeletedevent)
  - [Event.ModemEvent.AlarmEvent.ModemAlarmEvent](#eventmodemeventalarmeventmodemalarmevent)
  - [Event.ModemEvent.AlarmEvent.ModemAlarmEvent.ErrorMessagesEntry](#eventmodemeventalarmeventmodemalarmeventerrormessagesentry)
  - [Event.ModemEvent.AlarmEvent.UpdatedEvent](#eventmodemeventalarmeventupdatedevent)
  - [Event.ModemEvent.AlarmEvent.UpdatedEvent.Update](#eventmodemeventalarmeventupdatedeventupdate)
  - [Event.ModemEvent.ClaimEvent](#eventmodemeventclaimevent)
  - [Event.ModemEvent.ClaimEvent.ModemClaimedEvent](#eventmodemeventclaimeventmodemclaimedevent)
  - [Event.ModemEvent.MessageBodyParserEvent](#eventmodemeventmessagebodyparserevent)
  - [Event.ModemEvent.MessageBodyParserEvent.CreatedEvent](#eventmodemeventmessagebodyparsereventcreatedevent)
  - [Event.ModemEvent.MessageBodyParserEvent.DeletedEvent](#eventmodemeventmessagebodyparsereventdeletedevent)
  - [Event.ModemEvent.MessageBodyParserEvent.UpdatedEvent](#eventmodemeventmessagebodyparsereventupdatedevent)
  - [Event.ModemEvent.MessageEvent](#eventmodemeventmessageevent)
  - [Event.ModemEvent.MessageEvent.ModemMessageBodyParsedEvent](#eventmodemeventmessageeventmodemmessagebodyparsedevent)
  - [Event.ModemEvent.MessageEvent.ModemMessageBodyReceivedEvent](#eventmodemeventmessageeventmodemmessagebodyreceivedevent)
  - [Event.ModemEvent.MessageEvent.ModemMessageCannotBeParsedEvent](#eventmodemeventmessageeventmodemmessagecannotbeparsedevent)
  - [Event.ModemEvent.MessageEvent.ModemMessageReceivedEvent](#eventmodemeventmessageeventmodemmessagereceivedevent)
  - [Event.ModemEvent.ModemActivatedEvent](#eventmodemeventmodemactivatedevent)
  - [Event.ModemEvent.ModemCreatedEvent](#eventmodemeventmodemcreatedevent)
  - [Event.ModemEvent.ModemLocationUpdatedEvent](#eventmodemeventmodemlocationupdatedevent)
  - [Event.ModemEvent.ModemUpdatedEvent](#eventmodemeventmodemupdatedevent)
  - [Event.ModemEvent.ModemUpdatedEvent.PeripheralsEntry](#eventmodemeventmodemupdatedeventperipheralsentry)
  - [Event.ModemTransferEvent](#eventmodemtransferevent)
  - [Event.ModemTransferEvent.ModemTransferCancelledEvent](#eventmodemtransfereventmodemtransfercancelledevent)
  - [Event.ModemTransferEvent.ModemTransferNotReceivedEvent](#eventmodemtransfereventmodemtransfernotreceivedevent)
  - [Event.ModemTransferEvent.ModemTransferReceivedEvent](#eventmodemtransfereventmodemtransferreceivedevent)
  - [Event.ModemTransferEvent.ModemTransferReturnTransferStartedEvent](#eventmodemtransfereventmodemtransferreturntransferstartedevent)
  - [Event.ModemTransferEvent.ModemTransferStartedEvent](#eventmodemtransfereventmodemtransferstartedevent)
  - [Event.OrganizationEvent](#eventorganizationevent)
  - [Event.OrganizationEvent.EventConfigurationUpdated](#eventorganizationeventeventconfigurationupdated)
  - [Event.OrganizationEvent.EventConfigurationUpdated.ModemMessageSummaryUpdate](#eventorganizationeventeventconfigurationupdatedmodemmessagesummaryupdate)
  - [Event.OrganizationEvent.ModemMessageSummaryEvent](#eventorganizationeventmodemmessagesummaryevent)
  - [Event.OrganizationEvent.ModemMessageSummaryEvent.MessageCount](#eventorganizationeventmodemmessagesummaryeventmessagecount)
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
  - [Event.PublisherEvent.UpdatedEvent.WebhookUpdate](#eventpublishereventupdatedeventwebhookupdate)
  - [Event.TokenEvent](#eventtokenevent)
  - [Event.TokenEvent.TokenCreatedEvent](#eventtokeneventtokencreatedevent)
  - [Event.TokenEvent.TokenDeletedEvent](#eventtokeneventtokendeletedevent)
  - [Event.TokenEvent.TokenExpiredEvent](#eventtokeneventtokenexpiredevent)
  - [Event.TokenEvent.TokenExpiryWarningEvent](#eventtokeneventtokenexpirywarningevent)
  - [Event.UserEvent](#eventuserevent)
  - [Event.UserEvent.UserAccessRequestEvent](#eventusereventuseraccessrequestevent)
  - [Event.UserEvent.UserAddedEvent](#eventusereventuseraddedevent)
  - [Event.UserEvent.UserInvitedEvent](#eventusereventuserinvitedevent)
  - [Event.UserEvent.UserRemovedEvent](#eventusereventuserremovedevent)
  - [Event.UserEvent.UserValidationUpdatedEvent](#eventusereventuservalidationupdatedevent)
  - [EventConfiguration](#eventconfiguration)
  - [EventConfiguration.EventHealthLevelConfiguration](#eventconfigurationeventhealthlevelconfiguration)
  - [EventConfiguration.ModemMessageSummaryConfiguration](#eventconfigurationmodemmessagesummaryconfiguration)
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
  - [hiber.assign.Assignment.ModemAlarmAssignment](#hiberassignassignmentmodemalarmassignment)
  - [hiber.assign.Assignment.ModemMessageBodyParserAssignment](#hiberassignassignmentmodemmessagebodyparserassignment)
  - [hiber.assign.AssignmentSelection](#hiberassignassignmentselection)
  - [hiber.assign.AssignmentSelection.AssignmentTypes](#hiberassignassignmentselectionassignmenttypes)
  - [hiber.assign.ListAlarmAssignments](#hiberassignlistalarmassignments)
  - [hiber.assign.ListAlarmAssignments.Request](#hiberassignlistalarmassignmentsrequest)
  - [hiber.assign.ListAlarmAssignments.Response](#hiberassignlistalarmassignmentsresponse)
  - [hiber.assign.ListAlarmAssignments.Response.AlarmAssignment](#hiberassignlistalarmassignmentsresponsealarmassignment)
  - [hiber.assign.ListAlarmAssignments.Response.AlarmAssignment.ToModem](#hiberassignlistalarmassignmentsresponsealarmassignmenttomodem)
  - [hiber.assign.ListAlarmAssignments.Response.AlarmAssignment.ToTag](#hiberassignlistalarmassignmentsresponsealarmassignmenttotag)
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
  - [hiber.Filter.Events](#hiberfilterevents)
  - [hiber.Filter.Events.Update](#hiberfiltereventsupdate)
  - [hiber.Filter.Modems](#hiberfiltermodems)
  - [hiber.Filter.Modems.Update](#hiberfiltermodemsupdate)
  - [hiber.Filter.OrganizationPermissions](#hiberfilterorganizationpermissions)
  - [hiber.Filter.Organizations](#hiberfilterorganizations)
  - [hiber.Filter.Publishers](#hiberfilterpublishers)
  - [hiber.Filter.Tags](#hiberfiltertags)
  - [hiber.Filter.Tags.Update](#hiberfiltertagsupdate)
  - [hiber.Filter.UserPermissions](#hiberfilteruserpermissions)
  - [hiber.Filter.Users](#hiberfilterusers)
  - [hiber.Filter.Webhooks](#hiberfilterwebhooks)
  - [hiber.Location](#hiberlocation)
  - [hiber.LocationSelection](#hiberlocationselection)
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
    - [hiber.modem.Modem.Peripherals.HiberAntenna](#hibermodemmodemperipheralshiberantenna)
    - [hiber.modem.Modem.Status](#hibermodemmodemstatus)
    - [hiber.modem.Modem.Transfer.Status](#hibermodemmodemtransferstatus)
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
  - [hiber.modem.alarm.MakeModemAlarmAvailableToChildOrganizationRequest](#hibermodemalarmmakemodemalarmavailabletochildorganizationrequest)
  - [hiber.modem.alarm.MakeModemAlarmUnavailableToChildOrganizationRequest](#hibermodemalarmmakemodemalarmunavailabletochildorganizationrequest)
  - [hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm)
  - [hiber.modem.alarm.ModemAlarm.Check](#hibermodemalarmmodemalarmcheck)
  - [hiber.modem.alarm.ModemAlarm.Check.DelayCheck](#hibermodemalarmmodemalarmcheckdelaycheck)
  - [hiber.modem.alarm.ModemAlarm.Check.FieldCheck](#hibermodemalarmmodemalarmcheckfieldcheck)
  - [hiber.modem.alarm.ModemAlarm.Check.FieldCheck.AllowedCheck](#hibermodemalarmmodemalarmcheckfieldcheckallowedcheck)
  - [hiber.modem.alarm.ModemAlarm.Check.FieldCheck.BlockedCheck](#hibermodemalarmmodemalarmcheckfieldcheckblockedcheck)
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
  - [hiber.modem.alarm.UpdateModemAlarmAvailability](#hibermodemalarmupdatemodemalarmavailability)
  - [hiber.modem.alarm.UpdateModemAlarmAvailability.Request](#hibermodemalarmupdatemodemalarmavailabilityrequest)
  - [hiber.modem.alarm.UpdateModemAlarmAvailability.Response](#hibermodemalarmupdatemodemalarmavailabilityresponse)
  - [hiber.modem.alarm.UpdateModemAlarmRemoveCheck](#hibermodemalarmupdatemodemalarmremovecheck)
  - [hiber.modem.alarm.UpdateModemAlarmRemoveCheck.Request](#hibermodemalarmupdatemodemalarmremovecheckrequest)
  - [hiber.modem.alarm.UpdateModemAlarmRemoveCheck.Response](#hibermodemalarmupdatemodemalarmremovecheckresponse)
  - [hiber.modem.alarm.UpdateModemAlarmUpdateCheck](#hibermodemalarmupdatemodemalarmupdatecheck)
  - [hiber.modem.alarm.UpdateModemAlarmUpdateCheck.Request](#hibermodemalarmupdatemodemalarmupdatecheckrequest)
  - [hiber.modem.alarm.UpdateModemAlarmUpdateCheck.Request.UpdateUsingParametersEntry](#hibermodemalarmupdatemodemalarmupdatecheckrequestupdateusingparametersentry)
  - [hiber.modem.alarm.UpdateModemAlarmUpdateCheck.Response](#hibermodemalarmupdatemodemalarmupdatecheckresponse)

    - [hiber.modem.alarm.ModemAlarm.TriggerCondition](#hibermodemalarmmodemalarmtriggercondition)

- Referenced messages from [modem_claim.proto](#referenced-messages-from-modem_claimproto)
  - [hiber.modem.ClaimModemRequest](#hibermodemclaimmodemrequest)
  - [hiber.modem.ClaimModemRequest.ClaimModem](#hibermodemclaimmodemrequestclaimmodem)
  - [hiber.modem.ClaimModemRequest.Response](#hibermodemclaimmodemrequestresponse)
  - [hiber.modem.ListModemClaimsRequest](#hibermodemlistmodemclaimsrequest)
  - [hiber.modem.ListModemClaimsRequest.Response](#hibermodemlistmodemclaimsrequestresponse)
  - [hiber.modem.ModemClaim](#hibermodemmodemclaim)
  - [hiber.modem.ModemClaimSelection](#hibermodemmodemclaimselection)


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
  - [hiber.modem.message.bodyparser.UploadModemMessageBodyParserRequest](#hibermodemmessagebodyparseruploadmodemmessagebodyparserrequest)

    - [hiber.modem.message.bodyparser.ModemMessageBodyParser.PostProcessing](#hibermodemmessagebodyparsermodemmessagebodyparserpostprocessing)
    - [hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Endian](#hibermodemmessagebodyparsersimplemodemmessagebodyparserendian)

- Referenced messages from [modem_transfer.proto](#referenced-messages-from-modem_transferproto)
  - [hiber.modem.CancelModemTransferRequest](#hibermodemcancelmodemtransferrequest)
  - [hiber.modem.CancelModemTransferRequest.Response](#hibermodemcancelmodemtransferrequestresponse)
  - [hiber.modem.DeleteModemTransferReturnLinesRequest](#hibermodemdeletemodemtransferreturnlinesrequest)
  - [hiber.modem.DeleteModemTransferReturnLinesRequest.Response](#hibermodemdeletemodemtransferreturnlinesrequestresponse)
  - [hiber.modem.ListModemTransferReturnLinesRequest](#hibermodemlistmodemtransferreturnlinesrequest)
  - [hiber.modem.ListModemTransferReturnLinesRequest.Response](#hibermodemlistmodemtransferreturnlinesrequestresponse)
  - [hiber.modem.ListModemTransfersRequest](#hibermodemlistmodemtransfersrequest)
  - [hiber.modem.ListModemTransfersRequest.Response](#hibermodemlistmodemtransfersrequestresponse)
  - [hiber.modem.ModemTransfer](#hibermodemmodemtransfer)
  - [hiber.modem.ModemTransferReturnLine](#hibermodemmodemtransferreturnline)
  - [hiber.modem.ModemTransferSelection](#hibermodemmodemtransferselection)
  - [hiber.modem.NotReceivedModemTransferRequest](#hibermodemnotreceivedmodemtransferrequest)
  - [hiber.modem.NotReceivedModemTransferRequest.Response](#hibermodemnotreceivedmodemtransferrequestresponse)
  - [hiber.modem.PrepareModemForReturnRequest](#hibermodempreparemodemforreturnrequest)
  - [hiber.modem.PrepareModemForReturnRequest.Response](#hibermodempreparemodemforreturnrequestresponse)
  - [hiber.modem.ReceivedModemTransferRequest](#hibermodemreceivedmodemtransferrequest)
  - [hiber.modem.ReceivedModemTransferRequest.Response](#hibermodemreceivedmodemtransferrequestresponse)
  - [hiber.modem.SendReturnRequest](#hibermodemsendreturnrequest)
  - [hiber.modem.SendReturnRequest.Response](#hibermodemsendreturnrequestresponse)
  - [hiber.modem.TransferModemsRequest](#hibermodemtransfermodemsrequest)
  - [hiber.modem.TransferModemsRequest.Response](#hibermodemtransfermodemsrequestresponse)

    - [hiber.modem.ModemTransfer.Status](#hibermodemmodemtransferstatus)
    - [hiber.modem.ModemTransfer.Type](#hibermodemmodemtransfertype)
    - [hiber.modem.ModemTransferReturnLine.Reason](#hibermodemmodemtransferreturnlinereason)
    - [hiber.modem.TransferModemsRequest.DataTransferMode](#hibermodemtransfermodemsrequestdatatransfermode)
    - [hiber.modem.TransferModemsRequest.GatewayTransferMode](#hibermodemtransfermodemsrequestgatewaytransfermode)

- Referenced messages from [organization.proto](#referenced-messages-from-organizationproto)
  - [hiber.organization.CreateOrganizationRequest](#hiberorganizationcreateorganizationrequest)
  - [hiber.organization.DeleteOrganizationConfirmationRequest](#hiberorganizationdeleteorganizationconfirmationrequest)
  - [hiber.organization.DeleteOrganizationConfirmationRequest.Response](#hiberorganizationdeleteorganizationconfirmationrequestresponse)
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
  - [hiber.token.TokenSelection](#hibertokentokenselection)
  - [hiber.token.UpdateTokenOrganizationPermissionsRequest](#hibertokenupdatetokenorganizationpermissionsrequest)
  - [hiber.token.UpdateTokenOrganizationPermissionsRequest.Response](#hibertokenupdatetokenorganizationpermissionsrequestresponse)
  - [hiber.token.UpdateTokenUserPermissionsRequest](#hibertokenupdatetokenuserpermissionsrequest)
  - [hiber.token.UpdateTokenUserPermissionsRequest.Response](#hibertokenupdatetokenuserpermissionsrequestresponse)


- Referenced messages from [user.proto](#referenced-messages-from-userproto)
  - [hiber.user.ApproveUserRequest](#hiberuserapproveuserrequest)
  - [hiber.user.ApproveUserRequest.Response](#hiberuserapproveuserrequestresponse)
  - [hiber.user.CreateUserRequest](#hiberusercreateuserrequest)
  - [hiber.user.CreateUsersRequest](#hiberusercreateusersrequest)
  - [hiber.user.CreateUsersRequest.Response](#hiberusercreateusersrequestresponse)
  - [hiber.user.GetUserValidationRequest](#hiberusergetuservalidationrequest)
  - [hiber.user.InviteUserRequest](#hiberuserinviteuserrequest)
  - [hiber.user.InviteUserRequest.Response](#hiberuserinviteuserrequestresponse)
  - [hiber.user.ListAccessRequestsRequest](#hiberuserlistaccessrequestsrequest)
  - [hiber.user.ListAccessRequestsRequest.Response](#hiberuserlistaccessrequestsrequestresponse)
  - [hiber.user.ListInvitationsRequest](#hiberuserlistinvitationsrequest)
  - [hiber.user.ListInvitationsRequest.Response](#hiberuserlistinvitationsrequestresponse)
  - [hiber.user.ListUsersRequest](#hiberuserlistusersrequest)
  - [hiber.user.ListUsersRequest.Response](#hiberuserlistusersrequestresponse)
  - [hiber.user.RemoveUserRequest](#hiberuserremoveuserrequest)
  - [hiber.user.RemoveUserRequest.Response](#hiberuserremoveuserrequestresponse)
  - [hiber.user.ResetUserPasswordRequest](#hiberuserresetuserpasswordrequest)
  - [hiber.user.ResetUserPasswordRequest.Response](#hiberuserresetuserpasswordrequestresponse)
  - [hiber.user.TestUserValidationRequest](#hiberusertestuservalidationrequest)
  - [hiber.user.TestUserValidationRequest.Response](#hiberusertestuservalidationrequestresponse)
  - [hiber.user.UpdateUserPermissionsRequest](#hiberuserupdateuserpermissionsrequest)
  - [hiber.user.UpdateUserPermissionsRequest.Response](#hiberuserupdateuserpermissionsrequestresponse)
  - [hiber.user.UpdateUserValidationRequest](#hiberuserupdateuservalidationrequest)
  - [hiber.user.User](#hiberuseruser)
  - [hiber.user.UserActivitySummaryRequest](#hiberuseruseractivitysummaryrequest)
  - [hiber.user.UserActivitySummaryRequest.Response](#hiberuseruseractivitysummaryrequestresponse)
  - [hiber.user.UserActivitySummaryRequest.Response.UserActivitySummary](#hiberuseruseractivitysummaryrequestresponseuseractivitysummary)
  - [hiber.user.UserSelection](#hiberuseruserselection)
  - [hiber.user.UserValidation](#hiberuseruservalidation)
  - Enums
    - [hiber.user.UserSort](#hiberuserusersort)

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

- [Scalar Value Types](#scalar-value-types)


## EventService
Events are used in a number of ways in the api. With this service you can
search, list and stream them for your own purposes

### List
> **rpc** List([ListEventsRequest](#listeventsrequest))
    [ListEventsRequest.Response](#listeventsrequestresponse)



### Stream
> **rpc** Stream([EventStreamRequest](#eventstreamrequest))
    [Event](#event)



### Resolve
> **rpc** Resolve([ResolveEvent.Request](#resolveeventrequest))
    [ResolveEvent.Response](#resolveeventresponse)



### MarkResolved
> **rpc** MarkResolved([MarkEventsResolved.Request](#markeventsresolvedrequest))
    [MarkEventsResolved.Response](#markeventsresolvedresponse)



### History
> **rpc** History([EventHistory.Request](#eventhistoryrequest))
    [EventHistory.Response](#eventhistoryresponse)



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
| type | [ hiber.EventType](#hibereventtype) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **amount**.exact_amount | [ BundledEvent.ExactAmount](#bundledeventexactamount) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **amount**.approximated_amount | [ BundledEvent.ApproximatedAmount](#bundledeventapproximatedamount) | none |
| deprecated_amount | [ int32](#int32) | Deprecated in favour of using the amount field that is either an ExactAmount or ApproximatedAmount |
| deprecated_last_event | [ hiber.Timestamp](#hibertimestamp) | Deprecated in favour of using the amount field that is either an ExactAmount or ApproximatedAmount. since `last_event` is not available when using approximation (we don't know the actual last event), this field is only present when getting an ExactAmount. |
| deprecated_approximated_amount | [ bool](#bool) | Indicates that the amount is an approximation, and not an exact value. Some events will be approximated to avoid a large number of events affecting the request time.

Deprecated in favour of using the oneof_amount field that is either an ExactAmount or ApproximatedAmount |

### BundledEvent.ApproximatedAmount

Indicates that the amount is an approximation, and not an exact value.
Some events will be approximated to avoid a large number of events affecting the request time.
Because of the nature of approximation, we don't have a "last" event, so no timestamp is available.

| Field | Type | Description |
| ----- | ---- | ----------- |
| amount | [ int32](#int32) | none |

### BundledEvent.ExactAmount

Indicates that the amount is an exact count, and not an approximated value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| amount | [ int32](#int32) | none |
| last_event | [ hiber.Timestamp](#hibertimestamp) | none |

### Event

Generic Event object, used in streams where events are mixed. Protobuf provides helper methods to extract
the contained object.

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.EventType](#hibereventtype) | Time of the event. |
| time | [ hiber.Timestamp](#hibertimestamp) | Time of the event. |
| is_error | [ bool](#bool) | Whether this event causes the 'Error' health level. If your organization does not use the default health levels, this field will be omitted. Use health_level instead. |
| is_warning | [ bool](#bool) | Whether this event causes the 'Warning' health level. If your organization does not use the default health levels, this field will be omitted. Use health_level instead. |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The health level caused by this event. This health generally applies to either a modem, a token or a publisher, and is also applied to the organization health. Not every event affects health, so this field might be empty. |
| title | [ string](#string) | Short text describing the event. |
| description | [ string](#string) | Longer text describing the event in more detail. |
| modem | [ Event.Modem](#eventmodem) | The modem number for this event, if it is related to a single modem. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_created | [ Event.ModemEvent.ModemCreatedEvent](#eventmodemeventmodemcreatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_updated | [ Event.ModemEvent.ModemUpdatedEvent](#eventmodemeventmodemupdatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_location_updated | [ Event.ModemEvent.ModemLocationUpdatedEvent](#eventmodemeventmodemlocationupdatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_activated | [ Event.ModemEvent.ModemActivatedEvent](#eventmodemeventmodemactivatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_message_received | [ Event.ModemEvent.MessageEvent.ModemMessageReceivedEvent](#eventmodemeventmessageeventmodemmessagereceivedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_message_body_received | [ Event.ModemEvent.MessageEvent.ModemMessageBodyReceivedEvent](#eventmodemeventmessageeventmodemmessagebodyreceivedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_message_body_parsed | [ Event.ModemEvent.MessageEvent.ModemMessageBodyParsedEvent](#eventmodemeventmessageeventmodemmessagebodyparsedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_message_cannot_be_parsed | [ Event.ModemEvent.MessageEvent.ModemMessageCannotBeParsedEvent](#eventmodemeventmessageeventmodemmessagecannotbeparsedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_message_body_parser_created | [ Event.ModemEvent.MessageBodyParserEvent.CreatedEvent](#eventmodemeventmessagebodyparsereventcreatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_message_body_parser_updated | [ Event.ModemEvent.MessageBodyParserEvent.UpdatedEvent](#eventmodemeventmessagebodyparsereventupdatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_message_body_parser_deleted | [ Event.ModemEvent.MessageBodyParserEvent.DeletedEvent](#eventmodemeventmessagebodyparsereventdeletedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_alarm | [ Event.ModemEvent.AlarmEvent.ModemAlarmEvent](#eventmodemeventalarmeventmodemalarmevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_alarm_created | [ Event.ModemEvent.AlarmEvent.CreatedEvent](#eventmodemeventalarmeventcreatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_alarm_updated | [ Event.ModemEvent.AlarmEvent.UpdatedEvent](#eventmodemeventalarmeventupdatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_alarm_deleted | [ Event.ModemEvent.AlarmEvent.DeletedEvent](#eventmodemeventalarmeventdeletedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.assigned | [ Event.AssignmentEvent.AssignedEvent](#eventassignmenteventassignedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.unassigned | [ Event.AssignmentEvent.UnassignedEvent](#eventassignmenteventunassignedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.user_added | [ Event.UserEvent.UserAddedEvent](#eventusereventuseraddedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.user_removed | [ Event.UserEvent.UserRemovedEvent](#eventusereventuserremovedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.user_invited | [ Event.UserEvent.UserInvitedEvent](#eventusereventuserinvitedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.user_access_request | [ Event.UserEvent.UserAccessRequestEvent](#eventusereventuseraccessrequestevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.user_validation_updated | [ Event.UserEvent.UserValidationUpdatedEvent](#eventusereventuservalidationupdatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_transfer_started | [ Event.ModemTransferEvent.ModemTransferStartedEvent](#eventmodemtransfereventmodemtransferstartedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_transfer_cancelled | [ Event.ModemTransferEvent.ModemTransferCancelledEvent](#eventmodemtransfereventmodemtransfercancelledevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_transfer_received | [ Event.ModemTransferEvent.ModemTransferReceivedEvent](#eventmodemtransfereventmodemtransferreceivedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_transfer_not_received | [ Event.ModemTransferEvent.ModemTransferNotReceivedEvent](#eventmodemtransfereventmodemtransfernotreceivedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_transfer_return_transfer_started | [ Event.ModemTransferEvent.ModemTransferReturnTransferStartedEvent](#eventmodemtransfereventmodemtransferreturntransferstartedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_claimed_event | [ Event.ModemEvent.ClaimEvent.ModemClaimedEvent](#eventmodemeventclaimeventmodemclaimedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.token_expiry_warning | [ Event.TokenEvent.TokenExpiryWarningEvent](#eventtokeneventtokenexpirywarningevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.token_expired | [ Event.TokenEvent.TokenExpiredEvent](#eventtokeneventtokenexpiredevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.token_created | [ Event.TokenEvent.TokenCreatedEvent](#eventtokeneventtokencreatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.token_deleted | [ Event.TokenEvent.TokenDeletedEvent](#eventtokeneventtokendeletedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.organization_created | [ Event.OrganizationEvent.OrganizationCreatedEvent](#eventorganizationeventorganizationcreatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.organization_updated | [ Event.OrganizationEvent.OrganizationUpdatedEvent](#eventorganizationeventorganizationupdatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.organization_deleted | [ Event.OrganizationEvent.OrganizationDeletedEvent](#eventorganizationeventorganizationdeletedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.modem_message_summary | [ Event.OrganizationEvent.ModemMessageSummaryEvent](#eventorganizationeventmodemmessagesummaryevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.organization_event_configuration_updated | [ Event.OrganizationEvent.EventConfigurationUpdated](#eventorganizationeventeventconfigurationupdated) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.publisher_created | [ Event.PublisherEvent.CreatedEvent](#eventpublishereventcreatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.publisher_updated | [ Event.PublisherEvent.UpdatedEvent](#eventpublishereventupdatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.publisher_deleted | [ Event.PublisherEvent.DeletedEvent](#eventpublishereventdeletedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.publisher_auto_disabled | [ Event.PublisherEvent.AutoDisabledEvent](#eventpublishereventautodisabledevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.publisher_failed | [ Event.PublisherEvent.FailedEvent](#eventpublishereventfailedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.export_created | [ Event.ExportEvent.ExportCreatedEvent](#eventexporteventexportcreatedevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.export_ready | [ Event.ExportEvent.ExportReadyEvent](#eventexporteventexportreadyevent) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **event**.export_failed | [ Event.ExportEvent.ExportFailedEvent](#eventexporteventexportfailedevent) | none |

### Event.AssignmentEvent




### Event.AssignmentEvent.AssignedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| created | [ hiber.assign.Assignment](#hiberassignassignment) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### Event.AssignmentEvent.UnassignedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| removed | [ hiber.assign.Assignment](#hiberassignassignment) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### Event.ExportEvent




### Event.ExportEvent.ExportCreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| export | [ hiber.export.Export](#hiberexportexport) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### Event.ExportEvent.ExportFailedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| export | [ hiber.export.Export](#hiberexportexport) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### Event.ExportEvent.ExportReadyEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| export | [ hiber.export.Export](#hiberexportexport) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### Event.Modem

The modem data for this event, if it is related to a single modem.

| Field | Type | Description |
| ----- | ---- | ----------- |
| number | [ string](#string) | none |
| name | [ string](#string) | none |
| identifier | [ string](#string) | none |

### Event.ModemEvent




### Event.ModemEvent.AlarmEvent




### Event.ModemEvent.AlarmEvent.CreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| created | [ hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### Event.ModemEvent.AlarmEvent.DeletedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| deleted | [ string](#string) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### Event.ModemEvent.AlarmEvent.ModemAlarmEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| modem_number | [ string](#string) | none |
| modem_external_device_id | [ string](#string) | none |
| modem_message_id | [ uint64](#uint64) | The id of the modem that triggered the alarm, if any. |
| alarm_identifier | [ string](#string) | The identifier of the alarm. |
| alarm_description | [ string](#string) | The description of the alarm. |
| error_messages | [map Event.ModemEvent.AlarmEvent.ModemAlarmEvent.ErrorMessagesEntry](#eventmodemeventalarmeventmodemalarmeventerrormessagesentry) | The filled in error message(s) for the failing checks in the alarm. |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The highest health level caused by the failing checks in this alarm, for the modem (and organization). |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| resolved_at | [ hiber.Timestamp](#hibertimestamp) | When this alarm event was resolved. |
| health_level_after_resolved | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | Optional health that this alarm event causes after it has been resolved. |
| health_level_after_resolved_until | [ hiber.Timestamp](#hibertimestamp) | How long the optional health that this alarm event causes after it has been resolved lasts. |

### Event.ModemEvent.AlarmEvent.ModemAlarmEvent.ErrorMessagesEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ string](#string) | none |

### Event.ModemEvent.AlarmEvent.UpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| updated | [ Event.ModemEvent.AlarmEvent.UpdatedEvent.Update](#eventmodemeventalarmeventupdatedeventupdate) | none |
| alarm_identifier | [ string](#string) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### Event.ModemEvent.AlarmEvent.UpdatedEvent.Update



| Field | Type | Description |
| ----- | ---- | ----------- |
| description | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| trigger_condition | [ string](#string) | none |
| available_to_child_organizations | [ hiber.Filter.ChildOrganizations.Update](#hiberfilterchildorganizationsupdate) | none |
| checks | [ google.protobuf.Struct](#googleprotobufstruct) | none |
| update_default_health_level | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| update_health_level_after_resolved | [ hiber.modem.alarm.ModemAlarm.HealthLevelAfterResolved](#hibermodemalarmmodemalarmhealthlevelafterresolved) | none |

### Event.ModemEvent.ClaimEvent




### Event.ModemEvent.ClaimEvent.ModemClaimedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| modem_number | [ string](#string) | none |
| modem_external_device_id | [ string](#string) | External device id for this modem (e.g. a MAC address). |
| claim | [ hiber.modem.ModemClaim](#hibermodemmodemclaim) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |

### Event.ModemEvent.MessageBodyParserEvent

Events related to ModemMessageBodyParsers.


### Event.ModemEvent.MessageBodyParserEvent.CreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| created | [ hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### Event.ModemEvent.MessageBodyParserEvent.DeletedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| deleted | [ string](#string) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### Event.ModemEvent.MessageBodyParserEvent.UpdatedEvent



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

### Event.ModemEvent.MessageEvent




### Event.ModemEvent.MessageEvent.ModemMessageBodyParsedEvent

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

### Event.ModemEvent.MessageEvent.ModemMessageBodyReceivedEvent

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

### Event.ModemEvent.MessageEvent.ModemMessageCannotBeParsedEvent

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

### Event.ModemEvent.MessageEvent.ModemMessageReceivedEvent

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

### Event.ModemEvent.ModemActivatedEvent

When the first _real_ message for a modem comes in, the modem is considered to be activated.
A _real_ message is:
- a message received through a modem, on an environment that has real modems (hiber.cloud)
- any test message, on an environment that only has simulated modems (dev.hiber.global)

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| modem_number | [ string](#string) | none |
| modem_external_device_id | [ string](#string) | External device id for this modem (e.g. a MAC address). |
| message_id | [ uint64](#uint64) | The id of the mesasge that activated this modem. |
| time | [ hiber.Timestamp](#hibertimestamp) | The time this modem was activated in the system. |
| sent_at | [ hiber.Timestamp](#hibertimestamp) | The time this modem sent the message that activated it. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |

### Event.ModemEvent.ModemCreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| modem_number | [ string](#string) | none |
| modem_external_device_id | [ string](#string) | External device id for this modem (e.g. a MAC address). |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |

### Event.ModemEvent.ModemLocationUpdatedEvent

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

### Event.ModemEvent.ModemUpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| modem_number | [ string](#string) | none |
| modem_external_device_id | [ string](#string) | External device id for this modem (e.g. a MAC address). |
| display_name | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| antenna | [ hiber.modem.Modem.Peripherals.HiberAntenna](#hibermodemmodemperipheralshiberantenna) | none |
| custom_antenna | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| gps | [ hiber.UpdateBoolean](#hiberupdateboolean) | none |
| location | [ hiber.Location](#hiberlocation) | none |
| peripherals | [map Event.ModemEvent.ModemUpdatedEvent.PeripheralsEntry](#eventmodemeventmodemupdatedeventperipheralsentry) | none |
| notes | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| secure_notes_updated | [ bool](#bool) | none |
| health_warning_period | [ hiber.Duration](#hiberduration) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |

### Event.ModemEvent.ModemUpdatedEvent.PeripheralsEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ string](#string) | none |

### Event.ModemTransferEvent




### Event.ModemTransferEvent.ModemTransferCancelledEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| transfer | [ hiber.modem.ModemTransfer](#hibermodemmodemtransfer) | none |
| organization | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |

### Event.ModemTransferEvent.ModemTransferNotReceivedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| transfer | [ hiber.modem.ModemTransfer](#hibermodemmodemtransfer) | none |
| organization | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The health level caused for the modem (and organization) by this event. |

### Event.ModemTransferEvent.ModemTransferReceivedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| transfer | [ hiber.modem.ModemTransfer](#hibermodemmodemtransfer) | none |
| organization | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |

### Event.ModemTransferEvent.ModemTransferReturnTransferStartedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| return_transfer | [ hiber.modem.ModemTransfer](#hibermodemmodemtransfer) | none |
| original_transfer | [ hiber.modem.ModemTransfer](#hibermodemmodemtransfer) | none |
| return_lines | [repeated hiber.modem.ModemTransferReturnLine](#hibermodemmodemtransferreturnline) | none |
| organization | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The health level caused for the modem (and organization) by this event. |

### Event.ModemTransferEvent.ModemTransferStartedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| transfer | [ hiber.modem.ModemTransfer](#hibermodemmodemtransfer) | none |
| organization | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |

### Event.OrganizationEvent




### Event.OrganizationEvent.EventConfigurationUpdated



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| modem_message_summary_update | [ Event.OrganizationEvent.EventConfigurationUpdated.ModemMessageSummaryUpdate](#eventorganizationeventeventconfigurationupdatedmodemmessagesummaryupdate) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### Event.OrganizationEvent.EventConfigurationUpdated.ModemMessageSummaryUpdate



| Field | Type | Description |
| ----- | ---- | ----------- |
| enabled | [ hiber.UpdateBoolean](#hiberupdateboolean) | none |
| period | [ hiber.Duration](#hiberduration) | none |
| align_to_time | [ hiber.Timestamp](#hibertimestamp) | none |

### Event.OrganizationEvent.ModemMessageSummaryEvent

Message summary event that is sent when it has been configured for the organization.
The period is configurable, using the EventConfiguration.
This event is disabled by default.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| message_count | [repeated Event.OrganizationEvent.ModemMessageSummaryEvent.MessageCount](#eventorganizationeventmodemmessagesummaryeventmessagecount) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| time_range | [ hiber.TimeRange](#hibertimerange) | none |

### Event.OrganizationEvent.ModemMessageSummaryEvent.MessageCount



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem | [ string](#string) | none |
| source | [ hiber.modem.ModemMessage.Source](#hibermodemmodemmessagesource) | none |
| amount | [ int32](#int32) | none |

### Event.OrganizationEvent.OrganizationCreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| parent_organization | [ string](#string) | none |
| created | [ hiber.organization.Organization](#hiberorganizationorganization) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| avatar | [ hiber.Avatar](#hiberavatar) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### Event.OrganizationEvent.OrganizationDeletedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| parent_organization | [ string](#string) | none |
| deleted_organization | [ string](#string) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### Event.OrganizationEvent.OrganizationUpdatedEvent



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

### Event.PublisherEvent




### Event.PublisherEvent.AutoDisabledEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| id | [ int64](#int64) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The health level caused for the publisher (and organization) by this event. |

### Event.PublisherEvent.CreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| created | [ hiber.publisher.Publisher](#hiberpublisherpublisher) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### Event.PublisherEvent.DeletedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| deleted | [ hiber.publisher.Publisher](#hiberpublisherpublisher) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### Event.PublisherEvent.FailedEvent



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

### Event.PublisherEvent.UpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| updated_description | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| partial_update_data | [ hiber.publisher.Publisher.Data](#hiberpublisherpublisherdata) | Deprecated in favor of the new updated_data field |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **updated_data**.webhook | [ Event.PublisherEvent.UpdatedEvent.WebhookUpdate](#eventpublishereventupdatedeventwebhookupdate) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **updated_data**.mqtt | [ Event.PublisherEvent.UpdatedEvent.MQTTUpdate](#eventpublishereventupdatedeventmqttupdate) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **updated_data**.email | [ Event.PublisherEvent.UpdatedEvent.EmailUpdate](#eventpublishereventupdatedeventemailupdate) | none |
| updated_event_filter | [ hiber.Filter.Events.Update](#hiberfiltereventsupdate) | none |
| updated_modem_filter | [ hiber.Filter.Modems.Update](#hiberfiltermodemsupdate) | none |
| updated_tag_filter | [ hiber.Filter.Tags.Update](#hiberfiltertagsupdate) | none |
| updated_active_state | [ hiber.UpdateBoolean](#hiberupdateboolean) | none |
| health_warning_period | [ hiber.Duration](#hiberduration) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### Event.PublisherEvent.UpdatedEvent.EmailUpdate




### Event.PublisherEvent.UpdatedEvent.MQTTUpdate



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

### Event.PublisherEvent.UpdatedEvent.WebhookUpdate



| Field | Type | Description |
| ----- | ---- | ----------- |
| url | [ string](#string) | none |
| secret | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |
| content_type | [ hiber.webhook.Webhook.ContentType](#hiberwebhookwebhookcontenttype) | none |
| certificate_id | [ hiber.UpdateOptionalId](#hiberupdateoptionalid) | none |

### Event.TokenEvent




### Event.TokenEvent.TokenCreatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| token | [ hiber.token.Token](#hibertokentoken) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### Event.TokenEvent.TokenDeletedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| token | [ hiber.token.Token](#hibertokentoken) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### Event.TokenEvent.TokenExpiredEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| token | [ hiber.token.Token](#hibertokentoken) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### Event.TokenEvent.TokenExpiryWarningEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| token | [ hiber.token.Token](#hibertokentoken) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The health level caused for the organization by this event. |

### Event.UserEvent




### Event.UserEvent.UserAccessRequestEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| user | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |

### Event.UserEvent.UserAddedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| user | [ string](#string) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### Event.UserEvent.UserInvitedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| email | [ string](#string) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### Event.UserEvent.UserRemovedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| user | [ string](#string) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### Event.UserEvent.UserValidationUpdatedEvent



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| email_validation_regex | [ string](#string) | none |
| title | [ string](#string) | none |
| description | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |

### EventConfiguration

Configuration for configurable events.
Some events are disable by default, or can be configured in different ways. Their configuration is available here.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| modem_message_summary_configuration | [ EventConfiguration.ModemMessageSummaryConfiguration](#eventconfigurationmodemmessagesummaryconfiguration) | none |
| event_health_level_configuration | [repeated EventConfiguration.EventHealthLevelConfiguration](#eventconfigurationeventhealthlevelconfiguration) | List of event-types that have a health-level associated with them. Ignored when updating. |

### EventConfiguration.EventHealthLevelConfiguration

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

### EventConfiguration.ModemMessageSummaryConfiguration

When enabled, this sends a ModemMessageSummaryEvent periodically.
For example, you can configure the message summary to be a daily message, aligned to midnight in your time zone.

| Field | Type | Description |
| ----- | ---- | ----------- |
| enabled | [ bool](#bool) | The message summary event is disabled by default. |
| period | [ hiber.Duration](#hiberduration) | The period to send the message summary event for. The event can be sent every hour, day, etc. |
| align_to_time | [ hiber.Timestamp](#hibertimestamp) | Align the period to given time. For example, an hourly period sends can be aligned to 0:00 to send every whole hour. A weekly period can be aligned to send at a specific time on Monday by aligning to a timestamp on a Monday.

If a textual time zone is configured in this timestamp, it is used as well and should shift with changes like daylight saving time automatically. |
| include_empty_summaries | [ bool](#bool) | Send an event, even if the summary does not contain any information |

### EventConfiguration.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |

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
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ EventSelection](#eventselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |

### EventHistory.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ EventHistory.Request](#eventhistoryrequest) | none |
| events | [repeated Event](#event) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### EventSelection

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

### EventStreamRequest

Creates a stream for new events, matching the provided selection.

Note: streams are limited to one per user due to GRPC limitations.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ EventSelection](#eventselection) | The selection for the events. |
| child_organizations | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | Include events from child organizations, if requested. This is only available for streaming, listing events can only be listed per organization.

Keep in mind that filtering events using the selection is limited. Filtering on tags or publishers, for example, can only apply to the parent organization. |

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
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ EventSelection](#eventselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | Pagination is applied per event type on unbundled events. It is not necessary for bundled events. |
| sort | [ ListEventsRequest.Sort](#listeventsrequestsort) | none |
| unbundled_events | [ bool](#bool) | When not set, bundled/grouped events are returned. When set, returns unbundled events per type, paginated per type. Overrides unbundled_events in EventSelection message. |

### ListEventsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ ListEventsRequest](#listeventsrequest) | none |
| events | [repeated BundledEvent](#bundledevent) | none |
| unbundled_events | [repeated ListEventsRequest.Response.EventTypeResponse](#listeventsrequestresponseeventtyperesponse) | none |

### ListEventsRequest.Response.EventTypeResponse



| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.EventType](#hibereventtype) | none |
| unbundled_events | [repeated Event](#event) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### MarkEventsResolved

Mark a selection of events as resolved.


### MarkEventsResolved.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ EventSelection](#eventselection) | Selection of events to resolve. |

### MarkEventsResolved.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| resolved | [ uint32](#uint32) | The amount of events that were resolved. |
| request | [ MarkEventsResolved.Request](#markeventsresolvedrequest) | The original request, echoed back with any applied corrections. |

### ResolveEvent

Resolve a resolvable event using its resolve_identifier.


### ResolveEvent.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| resolve_identifier | [ string](#string) | The resolve identifier of the event you wish to resolve. |

### ResolveEvent.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| event | [ Event](#event) | none |

### UpdateEventHealthConfiguration




### UpdateEventHealthConfiguration.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
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
| expiry | [ hiber.UpdateOptionalDuration](#hiberupdateoptionalduration) | After the expiry duration, the event will not affect health anymore. Clear for manual resolving of events. |


## Enums
### ListEventsRequest.Sort


| Name | Description | Number |
| ---- | ----------- | ------ |
| TIME_DESCENDING | none | 0 |
| TIME_ASCENDING | none | 1 |
| MODEM_NUMBER_ASC | none | 2 |
| MODEM_NUMBER_DESC | none | 3 |
| MODEM_NUMBER_SPECIFIED | none | 4 |



## Referenced messages from assignment.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [assignment.proto](https://github.com/HiberGlobal/api/blob/master/assignment.proto).


### hiber.assign.Assign

Add assignments.


### hiber.assign.Assign.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign**.assign_parsers | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign**.assign_alarms | [ hiber.modem.alarm.ModemAlarmSelection](#hibermodemalarmmodemalarmselection) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign**.assign_modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **to**.to_modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **to**.to_tags | [ hiber.tag.TagSelection](#hibertagtagselection) | none |
| alarm_parameters | [map hiber.assign.Assign.Request.AlarmParametersEntry](#hiberassignassignrequestalarmparametersentry) | The alarm parameters, by alarm identifier, if any, overriding any default values in the alarm(s). |

### hiber.assign.Assign.Request.AlarmParametersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ google.protobuf.Struct](#googleprotobufstruct) | none |

### hiber.assign.Assign.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| assigned | [repeated hiber.assign.Assignment](#hiberassignassignment) | none |
| request | [ hiber.assign.Assign.Request](#hiberassignassignrequest) | none |

### hiber.assign.Assignment

An assignment assigning one thing to another.

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.assign.AssignmentType](#hiberassignassignmenttype) | The type of assignment. This is a helper enum to indicate which fields are set. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign**.assign_parser | [ hiber.assign.Assignment.ModemMessageBodyParserAssignment](#hiberassignassignmentmodemmessagebodyparserassignment) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign**.assign_alarm | [ hiber.assign.Assignment.ModemAlarmAssignment](#hiberassignassignmentmodemalarmassignment) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign**.assign_modem | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **to**.to_modem | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **to**.to_parser | [ hiber.assign.Assignment.ModemMessageBodyParserAssignment](#hiberassignassignmentmodemmessagebodyparserassignment) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **to**.to_tag | [ hiber.tag.Tag](#hibertagtag) | none |

### hiber.assign.Assignment.ModemAlarmAssignment



| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) | none |
| name | [ string](#string) | none |
| description | [ string](#string) | none |
| parameters | [ google.protobuf.Struct](#googleprotobufstruct) | none |
| owner_organization | [ string](#string) | none |

### hiber.assign.Assignment.ModemMessageBodyParserAssignment



| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) | none |
| name | [ string](#string) | none |
| owner_organization | [ string](#string) | none |

### hiber.assign.AssignmentSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | Select the modems to return the assignments for. |
| modem_alarms | [ hiber.modem.alarm.ModemAlarmSelection](#hibermodemalarmmodemalarmselection) | Select the alarms to return the assignments for. |
| modem_message_body_parsers | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) | Select the message body parsers to return the assignments for. |
| tags | [ hiber.tag.TagSelection](#hibertagtagselection) | Select the tags to return the assignments for. |
| types | [ hiber.assign.AssignmentSelection.AssignmentTypes](#hiberassignassignmentselectionassignmenttypes) | Select by type of assignment. |

### hiber.assign.AssignmentSelection.AssignmentTypes



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated hiber.assign.AssignmentType](#hiberassignassignmenttype) | none |
| exclude | [repeated hiber.assign.AssignmentType](#hiberassignassignmenttype) | none |

### hiber.assign.ListAlarmAssignments




### hiber.assign.ListAlarmAssignments.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.assign.AssignmentSelection](#hiberassignassignmentselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |
| include_child_organizations | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | Whether to include alarms and modems from child organizations in this list (and which organizations). |
| include_alarms_without_assignments | [ bool](#bool) | Whether to include alarms that are in the selection and have no assignments. |
| apply_unit_preferences | [ bool](#bool) | Apply your UnitPreferences to the alarm checks. For example, if a temperature check is configured in kelvin, but your unit preferences specify celsius for temperature, the check value will be converted to celsius instead. |

### hiber.assign.ListAlarmAssignments.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| alarms | [repeated hiber.assign.ListAlarmAssignments.Response.AlarmAssignment](#hiberassignlistalarmassignmentsresponsealarmassignment) | none |
| request | [ hiber.assign.ListAlarmAssignments.Request](#hiberassignlistalarmassignmentsrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### hiber.assign.ListAlarmAssignments.Response.AlarmAssignment

Things that an alarm is assigned to.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| alarm | [ hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) | none |
| modems | [repeated hiber.assign.ListAlarmAssignments.Response.AlarmAssignment.ToModem](#hiberassignlistalarmassignmentsresponsealarmassignmenttomodem) | The modem numbers this alarm is assigned to, with the alarm parameters. |
| tags | [repeated hiber.assign.ListAlarmAssignments.Response.AlarmAssignment.ToTag](#hiberassignlistalarmassignmentsresponsealarmassignmenttotag) | The tags this alarm is assigned to, with the alarm parameters. |

### hiber.assign.ListAlarmAssignments.Response.AlarmAssignment.ToModem



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem_number | [ string](#string) | none |
| parameters | [ google.protobuf.Struct](#googleprotobufstruct) | none |

### hiber.assign.ListAlarmAssignments.Response.AlarmAssignment.ToTag



| Field | Type | Description |
| ----- | ---- | ----------- |
| tag | [ hiber.tag.Tag](#hibertagtag) | none |
| parameters | [ google.protobuf.Struct](#googleprotobufstruct) | none |

### hiber.assign.ListAssignments




### hiber.assign.ListAssignments.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.assign.AssignmentSelection](#hiberassignassignmentselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |

### hiber.assign.ListAssignments.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| assignments | [repeated hiber.assign.Assignment](#hiberassignassignment) | The assignments as identifiers in the selection. |
| request | [ hiber.assign.ListAssignments.Request](#hiberassignlistassignmentsrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### hiber.assign.ListModemAssignments




### hiber.assign.ListModemAssignments.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.assign.AssignmentSelection](#hiberassignassignmentselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |
| include_alarm_details | [ bool](#bool) | Whether to include the full alarms that are assigned, instead of just assignment. |
| include_message_body_parser_details | [ bool](#bool) | Whether to include the full parsers that are assigned, instead of just assignment. |
| include_message_body_parser_content | [ bool](#bool) | Whether to include, for example, the message body parser ksy content in the result. Excluded by default to save data. |
| include_modems_without_assignments | [ bool](#bool) | Whether to include modems that are in the selection and have no assignments. |
| apply_unit_preferences | [ bool](#bool) | Apply your UnitPreferences to the alarm checks. For example, if a temperature check is configured in kelvin, but your unit preferences specify celsius for temperature, the check value will be converted to celsius instead. |

### hiber.assign.ListModemAssignments.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [repeated hiber.assign.ListModemAssignments.Response.ModemAssignment](#hiberassignlistmodemassignmentsresponsemodemassignment) | none |
| request | [ hiber.assign.ListModemAssignments.Request](#hiberassignlistmodemassignmentsrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### hiber.assign.ListModemAssignments.Response.ModemAssignment

Things that are assigned to a modem.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| modem_number | [ string](#string) | none |
| message_body_parsers | [repeated hiber.assign.Assignment.ModemMessageBodyParserAssignment](#hiberassignassignmentmodemmessagebodyparserassignment) | The identifiers of the message body parsers that are assigned to this modem. |
| alarms | [repeated hiber.assign.Assignment.ModemAlarmAssignment](#hiberassignassignmentmodemalarmassignment) | The identifiers and parameters of the alarms that are assigned to this modem. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | The tags for this modem. |
| message_body_parser_details | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser) | The details of the parsers assigned to this modem. |
| alarm_details | [repeated hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) | The alarms that are assigned to this modem, if you have permission to view them. |

### hiber.assign.ListModemMessageBodyParserAssignments




### hiber.assign.ListModemMessageBodyParserAssignments.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.assign.AssignmentSelection](#hiberassignassignmentselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |
| include_child_organizations | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | Whether to include modems from child organizations in this list (and which organizations). |
| include_parser_without_assignments | [ bool](#bool) | Whether to include alarms that are in the selection and have no assignments. |

### hiber.assign.ListModemMessageBodyParserAssignments.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| parsers | [repeated hiber.assign.ListModemMessageBodyParserAssignments.Response.ModemMessageBodyParserAssignment](#hiberassignlistmodemmessagebodyparserassignmentsresponsemodemmessagebodyparserassignment) | none |
| request | [ hiber.assign.ListModemMessageBodyParserAssignments.Request](#hiberassignlistmodemmessagebodyparserassignmentsrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### hiber.assign.ListModemMessageBodyParserAssignments.Response.ModemMessageBodyParserAssignment

Things that an alarm is assigned to.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| message_body_parser | [ hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser) | none |
| modems | [repeated string](#string) | The modem numbers this alarm is assigned to, with the alarm parameters. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | The tags this alarm is assigned to, with the alarm parameters. |

### hiber.assign.ListTagAssignments




### hiber.assign.ListTagAssignments.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.assign.AssignmentSelection](#hiberassignassignmentselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |
| include_alarm_details | [ bool](#bool) | Whether to include the full alarms that are assigned, instead of just assignment. |
| include_message_body_parser_details | [ bool](#bool) | Whether to include the full parsers that are assigned, instead of just assignment. |
| include_message_body_parser_content | [ bool](#bool) | Whether to include, for example, the message body parser ksy content in the result. Excluded by default to save data. |
| include_tags_without_assignments | [ bool](#bool) | Whether to include alarms that are in the selection and have no assignments. |
| apply_unit_preferences | [ bool](#bool) | Apply your UnitPreferences to the alarm checks. For example, if a temperature check is configured in kelvin, but your unit preferences specify celsius for temperature, the check value will be converted to celsius instead. |

### hiber.assign.ListTagAssignments.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| tags | [repeated hiber.assign.ListTagAssignments.Response.TagAssignment](#hiberassignlisttagassignmentsresponsetagassignment) | none |
| request | [ hiber.assign.ListTagAssignments.Request](#hiberassignlisttagassignmentsrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### hiber.assign.ListTagAssignments.Response.TagAssignment

Things that an alarm is assigned to.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| tag | [ hiber.tag.Tag](#hibertagtag) | none |
| modems | [repeated string](#string) | The modems with this tag. |
| message_body_parsers | [repeated hiber.assign.Assignment.ModemMessageBodyParserAssignment](#hiberassignassignmentmodemmessagebodyparserassignment) | The identifiers of the message body parsers that are assigned to this modem. |
| alarms | [repeated hiber.assign.Assignment.ModemAlarmAssignment](#hiberassignassignmentmodemalarmassignment) | The identifiers and parameters of the alarms that are assigned to this modem. |
| message_body_parser_details | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser) | The details of the parsers assigned to this modem. |
| alarm_details | [repeated hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) | The alarms that are assigned to this modem, if you have permission to view them. |

### hiber.assign.Unassign

Remove a assignment.


### hiber.assign.Unassign.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unassign**.unassign_parsers | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unassign**.unassign_alarms | [ hiber.modem.alarm.ModemAlarmSelection](#hibermodemalarmmodemalarmselection) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unassign**.unassign_modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **from**.from_modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **from**.from_tags | [ hiber.tag.TagSelection](#hibertagtagselection) | none |

### hiber.assign.Unassign.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| unassigned | [repeated hiber.assign.Assignment](#hiberassignassignment) | none |
| request | [ hiber.assign.Unassign.Request](#hiberassignunassignrequest) | none |


### Enums
#### hiber.assign.AssignmentType
Supported assignment types:
- assign a message body parser to a modem
- assign a message body parser to a tag
- assign a modem alarm to a modem
- assign a modem alarm to a tag
- assign a modem to a tag

Assignment is transitive: when an alarm or parser is assigned to a tag, and the tag is assigned to a modem,
  the alarm or parser is considered assigned to that modem.
This only works in one direction, though. Assigning the alarm or parser to the modem directly does not also assign
the tag.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | none | 0 |
| ASSIGNS_MESSAGE_BODY_PARSER_TO_MODEM | Assignment that assigns a message body parser to a modem. | 1 |
| ASSIGNS_ALARM_TO_MODEM | Assignment that assigns a modem alarm to a modem. | 2 |
| ASSIGNS_MODEM_TO_TAG | Assignment that assigns a modem to a tag. | 4 |
| ASSIGNS_MESSAGE_BODY_PARSER_TO_TAG | Assignment that assigns a message body parser to a tag, effectively assigning it to all modems with that tag. | 5 |
| ASSIGNS_ALARM_TO_TAG | Assignment that assigns a modem alarm to a tag, effectively assigning it to all modems with that tag. | 6 |



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

Specify which organizations to get data from. By default, data is only retrieved for the current organization, but
using ChildOrganizations we can specify to include a number of, or all, sub-organizations.

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

### hiber.Filter.Publishers



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated int64](#int64) | none |
| exclude | [repeated int64](#int64) | none |
| only_active | [ bool](#bool) | none |

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
| MODEM_TRANSFER_STARTED | none | 17 |
| MODEM_TRANSFER_RECEIVED | none | 18 |
| MODEM_TRANSFER_CANCELLED | none | 19 |
| MODEM_TRANSFER_NOT_RECEIVED | none | 20 |
| MODEM_TRANSFER_RETURN_TRANSFER_STARTED | none | 21 |
| MODEM_CLAIMED | none | 22 |
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



## Referenced messages from export.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [export.proto](https://github.com/HiberGlobal/api/blob/master/export.proto).


### hiber.export.AvailableFieldsForExport




### hiber.export.AvailableFieldsForExport.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **configuration**.modem_message | [ hiber.export.Export.Configuration.ModemMessages](#hiberexportexportconfigurationmodemmessages) | Get the fields for modem messages, with optional specific fields for the selected modems, based on assigned parsers. Time range is ignored for this request. |

### hiber.export.AvailableFieldsForExport.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| json_paths | [repeated string](#string) | All json paths that are available for json field mapping. |
| csv_columns | [repeated hiber.export.Export.Format.Csv.Column](#hiberexportexportformatcsvcolumn) | Available CSV columns, pre-named with suggested names. |

### hiber.export.CreateExport




### hiber.export.CreateExport.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| name | [ string](#string) | none |
| format | [ hiber.export.Export.Format](#hiberexportexportformat) | The format for the export. |
| configuration | [ hiber.export.Export.Configuration](#hiberexportexportconfiguration) | Specific configuration for the export. |
| email_subscribe | [ bool](#bool) | Subscribe to email updates to get an email with links when the export is ready. |

### hiber.export.CreateExport.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| created | [ hiber.export.Export](#hiberexportexport) | none |
| request | [ hiber.export.CreateExport.Request](#hiberexportcreateexportrequest) | none |

### hiber.export.DeleteExport




### hiber.export.DeleteExport.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | none |

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
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.modem_message | [ hiber.export.Export.Configuration.ModemMessages](#hiberexportexportconfigurationmodemmessages) | none |

### hiber.export.Export.Configuration.ModemMessages

Export modem messages for a set of modems.

| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [repeated string](#string) | none |
| time_range | [ hiber.TimeRange](#hibertimerange) | none |

### hiber.export.Export.File

Downloadable file.

| Field | Type | Description |
| ----- | ---- | ----------- |
| name | [ string](#string) | none |
| url | [ string](#string) | none |

### hiber.export.Export.Format

The format for the export.

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.export.Export.Format.Type](#hiberexportexportformattype) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **configuration**.json | [ hiber.export.Export.Format.Json](#hiberexportexportformatjson) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **configuration**.csv | [ hiber.export.Export.Format.Csv](#hiberexportexportformatcsv) | none |

### hiber.export.Export.Format.Csv

CSV (comma separated values) format for export.

| Field | Type | Description |
| ----- | ---- | ----------- |
| columns | [repeated hiber.export.Export.Format.Csv.Column](#hiberexportexportformatcsvcolumn) | The columns in the CSV, with their mapping. Columns in CSV are a flat structure, while the data is generally nested, so a mapping is required to flatten it to simple columns. |
| separator | [ string](#string) | The separator character to use in the CSV. |
| quote | [ string](#string) | The quote character to use in the CSV. |
| escape | [ string](#string) | The escape character to use in the CSV. |
| newline | [ string](#string) | The newlines to use in the CSV. |

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
| key | [ string](#string) | none |
| value | [ string](#string) | none |

### hiber.export.ExportSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| identifiers | [repeated string](#string) | Select by identifiers |
| search | [ string](#string) | Search through identifiers and urls |
| include_expired | [ bool](#bool) | Whether to include expired exports. |

### hiber.export.ExtendExportDownloadExpiry




### hiber.export.ExtendExportDownloadExpiry.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | Export identifier |
| extend_by | [ hiber.Duration](#hiberduration) | The time to extend the expiry with. |
| file | [repeated string](#string) | Extend the expiry for a specific file. If empty, all files are extended. |

### hiber.export.ExtendExportDownloadExpiry.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| export | [ hiber.export.Export](#hiberexportexport) | none |

### hiber.export.ListExports




### hiber.export.ListExports.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.export.ExportSelection](#hiberexportexportselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |

### hiber.export.ListExports.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| exports | [repeated hiber.export.Export](#hiberexportexport) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |
| request | [ hiber.export.ListExports.Request](#hiberexportlistexportsrequest) | none |


### Enums
#### hiber.export.Export.Format.Type


| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | none | 0 |
| JSON | none | 1 |
| CSV | none | 2 |

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
| color | [ string](#string) | Default color for the health level, as a string that represents a valid CSS3 color. DEPRECATED: Maps to the color named "text" in color_data. |
| color_data | [map hiber.health.HealthLevel.ColorDataEntry](#hiberhealthhealthlevelcolordataentry) | Map of named colors, where key is the name and the value is a valid CSS3 color definition. |
| severity | [ int64](#int64) | A unique numeric value equal to the index of this health level in the list of health levels sorted by ascending severity (starting at 1). This means higher numbers denote a more severe health. This value cannot be used when creating or updating. To change the severity for a health level, reorder all health levels. |
| catch_all | [ bool](#bool) | Precisely one health level can be assigned as a catch-all for any unknown health levels from alarms (or Hiber systems), which can happen when a device manufacturer has provided alarms for your device (e.g. a low battery alarm). By default, unknown health levels map to the level of the highest severity, unless another level is marked as catch-all. |

### hiber.health.HealthLevelSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| search | [ string](#string) | Search for the given string in the levels and colors. |
| levels | [repeated string](#string) | Filter by exact levels. |


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
| health | [ hiber.Health](#hiberhealth) | Deprecated health based on the number of error and warning events this modem has received in the past 30 days Uses the OK, WARNING, ERROR format. |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | Health level based on the modem alarm and some always-present alarms. |
| status | [ hiber.modem.Modem.Status](#hibermodemmodemstatus) | none |
| active_subscription | [ hiber.modem.Modem.ActiveSubscription](#hibermodemmodemactivesubscription) | additional information |
| technical | [ hiber.modem.Modem.TechnicalData](#hibermodemmodemtechnicaldata) | none |
| peripherals | [ hiber.modem.Modem.Peripherals](#hibermodemmodemperipherals) | none |
| in_transfer | [ hiber.modem.Modem.Transfer](#hibermodemmodemtransfer) | none |
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

### hiber.modem.ModemSelection

Selection object for modems.
Filter modems by modem id, (child)organization, tags, activation status and time, service type and last message time.

| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [ hiber.Filter.Modems](#hiberfiltermodems) | none |
| free_text_search | [ string](#string) | none |
| only_active | [ bool](#bool) | none |
| activated_in | [ hiber.TimeRange](#hibertimerange) | none |
| with_last_message_in | [ hiber.TimeRange](#hibertimerange) | none |
| with_service_type | [repeated hiber.organization.subscription.ServiceType](#hiberorganizationsubscriptionservicetype) | none |
| health | [repeated hiber.Health](#hiberhealth) | Deprecated health that uses the OK, WARNING, ERROR format. |
| health_levels | [repeated string](#string) | Filter modems by health level. |
| status | [repeated hiber.modem.Modem.Status](#hibermodemmodemstatus) | Filter modems by status(es). Defaults to nominal statuses, excluding disabled, dead, lost or damaged modems. |
| transfers | [ hiber.modem.ModemSelection.Transfers](#hibermodemmodemselectiontransfers) | none |
| include_types | [repeated hiber.modem.Modem.Type](#hibermodemmodemtype) | Only include modems that have a type listed in types. In other words, when providing multiple types, this is an "OR" relationship. |
| exclude_types | [repeated hiber.modem.Modem.Type](#hibermodemmodemtype) | Exclude modems that have a type listed in types. |
| only_gateways | [ bool](#bool) | [DEPRECATED] Only list devices that are a gateway. Replaced by `types`. If you only want to have gateways in the result, create a selection with only `Modem.Type.GATEWAY` for `types`. |
| only_has_external_device_ids | [ bool](#bool) | [DEPRECATED] Only list devices that are a connected devices. Typically these are LoRaWAN sensors. Replaced by `types`. If you only want to have connected devices in the result, create a selection with only `Modem.Type.CONNECTED_DEVICE` for `types`. |
| connected_to_gateways | [ hiber.Filter.Modems](#hiberfiltermodems) | none |
| external_device_ids | [repeated string](#string) | none |
| filter_by_tags | [ hiber.tag.TagSelection](#hibertagtagselection) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **peripheral_selection**.peripherals | [ hiber.modem.ModemSelection.Peripherals](#hibermodemmodemselectionperipherals) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **peripheral_selection**.only_without_peripheral | [ bool](#bool) | When set to true, only modems that do not have any peripheral will be included in the result. |


### Enums
#### hiber.modem.ListModemsRequest.Sort
Sorting options for the results.

| Name | Description | Number |
| ---- | ----------- | ------ |
| LAST_MESSAGE_RECEIVED | none | 0 |
| LAST_MESSAGE_RECEIVED_INVERTED | none | 1 |
| MODEM_NUMBER_ASC | Sort numerically on the number of the modem. | 2 |
| MODEM_NUMBER_DESC | none | 3 |
| STATUS_ASC | none | 4 |
| STATUS_DESC | none | 5 |
| MODEM_NAME_ASC | Sort alphabetically on the name of the modem. De default name of the modem is its HEX number | 6 |
| MODEM_NAME_DESC | none | 7 |
| ORGANIZATION_ASC | Sort alphabetically on the name of the organization that owns the modem | 8 |
| ORGANIZATION_DESC | none | 9 |
| HEALTH | Health sorted from least to most severe (i.e. OK, WARNING, ERROR). | 10 |
| HEALTH_DESC | Health sorted from most to least severe (i.e. ERROR, WARNING, OK). | 11 |

#### hiber.modem.Modem.Peripherals.HiberAntenna
A Hiber antenna is required for the modem to function.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | none | 0 |
| HIBER_PANDA | none | 1 |
| HIBER_GRIZZLY | none | 2 |
| HIBER_BLACK | none | 3 |
| CUSTOM | none | 4 |

#### hiber.modem.Modem.Status
Modem statuses for its lifecycle.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | Modem is in your inventory, but not deployed or active. | 0 |
| ACTIVE | Modem is active and sending messages. See health for more details on its health, based on the past messages. | 1 |
| DAMAGED | none | 2 |
| LOST | none | 3 |
| DEAD | none | 4 |
| DISABLED | none | 5 |

#### hiber.modem.Modem.Transfer.Status


| Name | Description | Number |
| ---- | ----------- | ------ |
| NONE | none | 0 |
| INBOUND | Modem has been shipped or transferred to you and is inbound. When you mark the transfer as received, the modems are added to your organization. If you encounter any issues, you can mark modems for return using the ModemTransferReturnService. | 1 |
| OUTBOUND | Modem has been shipped or transferred by you and is outbound. When the transfer is received, the modems are removed from your organization, though the recipient may still return them later. | 2 |
| RETURNING | You shipped this modem to another organization, but they are returning it. When you mark the transfer as received, the modems are added back to your organization. | 3 |

#### hiber.modem.Modem.Type
The effective type of this modem.
Type can depend on the hardware itself as well as network topology.

| Name | Description | Number |
| ---- | ----------- | ------ |
| OTHER | A device of which the specific type is not known | 0 |
| DIRECT | A devices that directly connects to the satellite | 1 |
| GATEWAY | A device that can receive messages from sensors in the field and relay them (directly) to the satellite. Typically a LoRaWAN hub. Note that gateways also send messages themselves (e.g. a daily heartbeat). | 2 |
| CONNECTED_DEVICE | A sensor that can (only) send data to a gateway. Typically using a LoRaWAN connection. | 3 |

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
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarms | [ hiber.modem.alarm.ModemAlarmSelection](#hibermodemalarmmodemalarmselection) | none |
| modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | none |
| parameters | [map hiber.modem.alarm.AssignModemAlarms.Request.ParametersEntry](#hibermodemalarmassignmodemalarmsrequestparametersentry) | The alarm parameters, by alarm identifier, if any, overriding any default values in the alarm(s). |

### hiber.modem.alarm.AssignModemAlarms.Request.ParametersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ google.protobuf.Struct](#googleprotobufstruct) | none |

### hiber.modem.alarm.AssignModemAlarms.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| created | [repeated hiber.modem.alarm.AssignedModemAlarm](#hibermodemalarmassignedmodemalarm) | none |
| request | [ hiber.modem.alarm.AssignModemAlarms.Request](#hibermodemalarmassignmodemalarmsrequest) | none |

### hiber.modem.alarm.AssignedModemAlarm

Directly assigned modem alarm to a modem.

| Field | Type | Description |
| ----- | ---- | ----------- |
| alarm_identifier | [ string](#string) | none |
| modem_number | [ string](#string) | none |

### hiber.modem.alarm.CreateModemAlarm

Create a new alarm.

The request contains the option to add checks as well.
This is a shortcut for creating an alarm and then adding checks, and as such can result in multiple events:
- a created event on the alarm
- an update event on the alarm checks, iff any checks were added


### hiber.modem.alarm.CreateModemAlarm.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| name | [ string](#string) | A name for the alarm. |
| description | [ string](#string) | A short description of what the alarm should do. |
| trigger_condition | [ hiber.modem.alarm.ModemAlarm.TriggerCondition](#hibermodemalarmmodemalarmtriggercondition) | Condition determining when an alarm is triggered if it has multiple checks. |
| checks | [repeated hiber.modem.alarm.ModemAlarm.Check](#hibermodemalarmmodemalarmcheck) | The checks to add to this alarm. Shortcut for creating an alarm and then adding checks to it. |
| default_health_level | [ string](#string) | The default health level for this alarm. See ModemAlarm.default_health_level for more information. |
| health_level_after_resolved | [ hiber.modem.alarm.ModemAlarm.HealthLevelAfterResolved](#hibermodemalarmmodemalarmhealthlevelafterresolved) | The health level this alarm should cause after it is resolved. See ModemAlarm.health_level_after_resolved for more information. |

### hiber.modem.alarm.CreateModemAlarm.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| created | [ hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) | none |

### hiber.modem.alarm.DeleteModemAlarm




### hiber.modem.alarm.DeleteModemAlarm.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | none |

### hiber.modem.alarm.DeleteModemAlarm.Response




### hiber.modem.alarm.ListModemAlarms




### hiber.modem.alarm.ListModemAlarms.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.modem.alarm.ModemAlarmSelection](#hibermodemalarmmodemalarmselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |
| apply_unit_preferences | [ bool](#bool) | Apply your UnitPreferences to the alarm checks. For example, if a temperature check is configured in kelvin, but your unit preferences specify celsius for temperature, the check value will be converted to celsius instead. |

### hiber.modem.alarm.ListModemAlarms.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem_alarms | [repeated hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |
| request | [ hiber.modem.alarm.ListModemAlarms.Request](#hibermodemalarmlistmodemalarmsrequest) | none |

### hiber.modem.alarm.MakeModemAlarmAvailableToChildOrganizationRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the alarm that should be updated. |
| available_to | [repeated string](#string) | The child organization(s) that the alarm should be available to. This will - when the organization is on the exclude list, remove it - when the includeAll flag is false, add it to the include list (if not already present) |

### hiber.modem.alarm.MakeModemAlarmUnavailableToChildOrganizationRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the alarm that should be updated. |
| unavailable_to | [repeated string](#string) | The child organization(s) that the alarm should be unavailable to. This will - when the organization is on the include list, remove it - when the includeAll flag is true, add it to the exclude list (if not already present) |

### hiber.modem.alarm.ModemAlarm

Alarm for a modem, monitoring message data, location or activity.

An alarm is a collection of checks that validate the correctness of a modem. For example, an alarm might
check that the modem is in a given location, or that a field in its messages is between certain values.

Health for an alarm event is determined by taking the most severe health level from the health_levels configured
on the failing checks, using this default for any checks that do not have a health_level configured.
This can be changed on assignment with the default_health_level parameter, to fit the needs of the organization.

Note, when an alarm is inherited the health levels may not match yours. If the health level matches one of
your health levels, that level is used. Otherwise, the catch-all health level is used.
See the health definition for more information on the catch all health level (typically the most severe).
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
| identifier | [ string](#string) | The identifier for this alarm. This identifier is globally unique, since the alarm can be shared to child organizations. |
| name | [ string](#string) | Short name for this alarm (optional). |
| description | [ string](#string) | Longer description for this alarm (optional). |
| created_at | [ hiber.Timestamp](#hibertimestamp) | When this alarm was created. |
| updated_at | [ hiber.Timestamp](#hibertimestamp) | When this alarm was last updated. |
| available_to_child_organizations | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | Availability to child organizations. This alarm can be shared to child organizations, so it can be assigned to their modems, either directly or automatically over all selected child organizations. Only the owner organization is able to edit the alarm. |
| trigger_condition | [ hiber.modem.alarm.ModemAlarm.TriggerCondition](#hibermodemalarmmodemalarmtriggercondition) | Condition determining when an alarm is triggered if it has multiple checks. |
| default_health_level | [ string](#string) | The default health level for checks in this alarm, if they have no health_level configured. |
| health_level_after_resolved | [ hiber.modem.alarm.ModemAlarm.HealthLevelAfterResolved](#hibermodemalarmmodemalarmhealthlevelafterresolved) | Allow the alarm to cause a health level for the modem even after it has been resolved. By configuring this, you can specify the modem health should be affected for a longer period. For example, when using an inactivity check, this would could be used to configure modem health ERROR while inactive, lowering to INVESTIGATE for a day after a new message comes in. |
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
- modem: the modem number.
- message: the id of the message, if any.
- expected: a shortcut for the expected value(s), depending on the check:
  - equals check: expected value
  - oneof check: expected values as [a, b, c]
  - threshold check: expected range as minimum..maximum
  - location check: expected area as [(bottom left), (top right)], and shape as [(point), (point), ..., (point)]
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
| description | [ string](#string) | Longer description for this check (optional). |
| health_level | [ string](#string) | The health level that this check would cause for a modem, when it fails. If not set, the alarm default is used. |
| error_message_template | [ string](#string) | The error message template for this check, with parameters that will be filled in based on the check. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.location | [ hiber.modem.alarm.ModemAlarm.Check.LocationCheck](#hibermodemalarmmodemalarmchecklocationcheck) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.field | [ hiber.modem.alarm.ModemAlarm.Check.FieldCheck](#hibermodemalarmmodemalarmcheckfieldcheck) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.inactivity | [ hiber.modem.alarm.ModemAlarm.Check.InactivityCheck](#hibermodemalarmmodemalarmcheckinactivitycheck) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.delay | [ hiber.modem.alarm.ModemAlarm.Check.DelayCheck](#hibermodemalarmmodemalarmcheckdelaycheck) | none |

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

Note that this for the examples above, if they return an array, the entire array is used as the value
in the comparison for equals and oneof.

A check of this type has the following parameters (matches the fields):
- field.path: replace the path for this field
- field.ignoreFieldNotFound: replace the value for ignore_field_not_found

For the equals check:
- field.equals.expected: iff this is an equals check, replace the expected value

For the oneof check:
- field.oneof.expected: iff this is a oneof check, replace the expected values

For the threshold check:
- field.threshold.expected: iff this is a threshold check, replace the expected range
- field.threshold.minimum: iff this is a threshold check, replace the expected minimum
- field.threshold.maximum: iff this is a threshold check, replace the expected maximum

For the delta check:
- field.delta.period:
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
| unit | [ hiber.field.Field.Numeric.Unit](#hiberfieldfieldnumericunit) | The unit that this alarm check is using. The field's values will automatically be converted into this unit before the check is applied.

Note: unit is not currently available in the alarm_parameters. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.equals | [ hiber.modem.alarm.ModemAlarm.Check.FieldCheck.EqualsCheck](#hibermodemalarmmodemalarmcheckfieldcheckequalscheck) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.allowed | [ hiber.modem.alarm.ModemAlarm.Check.FieldCheck.AllowedCheck](#hibermodemalarmmodemalarmcheckfieldcheckallowedcheck) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.blocked | [ hiber.modem.alarm.ModemAlarm.Check.FieldCheck.BlockedCheck](#hibermodemalarmmodemalarmcheckfieldcheckblockedcheck) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.minimum | [ hiber.modem.alarm.ModemAlarm.Check.FieldCheck.MinimumCheck](#hibermodemalarmmodemalarmcheckfieldcheckminimumcheck) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.maximum | [ hiber.modem.alarm.ModemAlarm.Check.FieldCheck.MaximumCheck](#hibermodemalarmmodemalarmcheckfieldcheckmaximumcheck) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.threshold | [ hiber.modem.alarm.ModemAlarm.Check.FieldCheck.ThresholdCheck](#hibermodemalarmmodemalarmcheckfieldcheckthresholdcheck) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.delta | [ hiber.modem.alarm.ModemAlarm.Check.FieldCheck.DeltaCheck](#hibermodemalarmmodemalarmcheckfieldcheckdeltacheck) | none |

### hiber.modem.alarm.ModemAlarm.Check.FieldCheck.AllowedCheck

Check that the field is in a set of expected values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| allowed | [repeated google.protobuf.Value](#googleprotobufvalue) | The list of allowed values, one of which should match the field value. |

### hiber.modem.alarm.ModemAlarm.Check.FieldCheck.BlockedCheck

Check that the field is not in a set of blocked values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| blocked | [repeated google.protobuf.Value](#googleprotobufvalue) | none |

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
| expected | [ google.protobuf.Value](#googleprotobufvalue) | none |

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

Check that the field is within a given numeric range.

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
| deprecated_maximum | [ hiber.Duration](#hiberduration) | none |

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

For example, when using an inactivity check, this would could be used to configure modem health ERROR while
inactive, lowering to INVESTIGATE for a day after a new message comes in.

| Field | Type | Description |
| ----- | ---- | ----------- |
| health_level | [ string](#string) | The health level that this check would cause for a modem, when the original failure is resolved. |
| period | [ hiber.Duration](#hiberduration) | The amount of time that this health level would be active. |

### hiber.modem.alarm.ModemAlarmSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| identifiers | [repeated string](#string) | none |
| search | [ string](#string) | Search for the given string in identifier, description, fields and values. |
| owner_organizations | [repeated string](#string) | Only return alarms that were created by the given organizations. |
| only_owned_alarms | [ bool](#bool) | none |

### hiber.modem.alarm.TestModemAlarmTestParameters




### hiber.modem.alarm.TestModemAlarmTestParameters.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarm_identifier | [ string](#string) | none |
| parameters | [ google.protobuf.Struct](#googleprotobufstruct) | none |

### hiber.modem.alarm.TestModemAlarmTestParameters.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| result | [ hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) | none |

### hiber.modem.alarm.UnassignModemAlarms

Remove a direct assignment.
If an overlapping assignment using a rule exists, it is not affected, except that it is longer shadowed.

Simplified version of assign.UnassignDirectly.


### hiber.modem.alarm.UnassignModemAlarms.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarms | [ hiber.modem.alarm.ModemAlarmSelection](#hibermodemalarmmodemalarmselection) | none |
| modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | none |

### hiber.modem.alarm.UnassignModemAlarms.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| removed_direct_assignments | [repeated hiber.modem.alarm.AssignedModemAlarm](#hibermodemalarmassignedmodemalarm) | none |
| request | [ hiber.modem.alarm.UnassignModemAlarms.Request](#hibermodemalarmunassignmodemalarmsrequest) | none |

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
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifiers of the alarm to update |
| update_name | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | Update the name, optionally. |
| update_description | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | Update the description, optionally. |
| update_trigger_condition | [ hiber.modem.alarm.ModemAlarm.TriggerCondition](#hibermodemalarmmodemalarmtriggercondition) | Update the trigger condition, optionally. |
| update_default_health_level | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | Update the default health level, optionally. |
| update_health_level_after_resolved | [ hiber.modem.alarm.ModemAlarm.HealthLevelAfterResolved](#hibermodemalarmmodemalarmhealthlevelafterresolved) | Update the health after resolved, optionally. |
| remove_health_level_after_resolved | [ bool](#bool) | Remove the health after resolved, optionally. |
| add_checks | [repeated hiber.modem.alarm.ModemAlarm.Check](#hibermodemalarmmodemalarmcheck) | The checks to add to this alarm. Shortcut for updating an alarm and then adding checks to it. |
| update_checks | [map hiber.modem.alarm.UpdateModemAlarm.Request.UpdateChecksEntry](#hibermodemalarmupdatemodemalarmrequestupdatechecksentry) | The checks to update in this alarm. Shortcut for updating an alarm and then updating checks. |
| delete_checks | [repeated string](#string) | The checks to remove from this alarm. Shortcut for updating an alarm and then removing checks. |

### hiber.modem.alarm.UpdateModemAlarm.Request.UpdateChecksEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ hiber.modem.alarm.ModemAlarm.Check](#hibermodemalarmmodemalarmcheck) | none |

### hiber.modem.alarm.UpdateModemAlarm.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) | none |

### hiber.modem.alarm.UpdateModemAlarmAddCheck

Add a check to the alarm, iff you are the owner or can impersonate the owner organization.


### hiber.modem.alarm.UpdateModemAlarmAddCheck.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarm_identifier | [ string](#string) | none |
| check | [ hiber.modem.alarm.ModemAlarm.Check](#hibermodemalarmmodemalarmcheck) | The check to add to the Modem Alarm. Identifier must be unique within the alarm. |

### hiber.modem.alarm.UpdateModemAlarmAddCheck.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) | none |

### hiber.modem.alarm.UpdateModemAlarmAvailability




### hiber.modem.alarm.UpdateModemAlarmAvailability.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarm_identifier | [ string](#string) | none |
| replace_apply_to_child_organizations | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | The new set of child organizations that this rule applies to. Replaces the original value! |

### hiber.modem.alarm.UpdateModemAlarmAvailability.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) | none |

### hiber.modem.alarm.UpdateModemAlarmRemoveCheck




### hiber.modem.alarm.UpdateModemAlarmRemoveCheck.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarm_identifier | [ string](#string) | none |
| check_identifier | [ string](#string) | none |

### hiber.modem.alarm.UpdateModemAlarmRemoveCheck.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) | none |

### hiber.modem.alarm.UpdateModemAlarmUpdateCheck




### hiber.modem.alarm.UpdateModemAlarmUpdateCheck.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarm_identifier | [ string](#string) | none |
| check_identifier | [ string](#string) | none |
| update_check | [ hiber.modem.alarm.ModemAlarm.Check](#hibermodemalarmmodemalarmcheck) | none |
| update_using_parameters | [map hiber.modem.alarm.UpdateModemAlarmUpdateCheck.Request.UpdateUsingParametersEntry](#hibermodemalarmupdatemodemalarmupdatecheckrequestupdateusingparametersentry) | Use parameters to update the check, as it would be when they were added when the alarm was assigned. |
| test_parameters_only | [ bool](#bool) | If set, the update is not actually saved, but only applied and returned. This is a convenience to easily test parameters for a check similar to TestModemAlarmTestParameters. |

### hiber.modem.alarm.UpdateModemAlarmUpdateCheck.Request.UpdateUsingParametersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ google.protobuf.Value](#googleprotobufvalue) | none |

### hiber.modem.alarm.UpdateModemAlarmUpdateCheck.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) | none |


### Enums
#### hiber.modem.alarm.ModemAlarm.TriggerCondition
Condition determining when an alarm is triggered if it has multiple checks.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | Defaults to the current value when updating, or to ANY_CHECK_FAILED when creating. | 0 |
| ANY_CHECK_FAILED | Trigger the alarm when any of the checks fail. This is useful when providing a single device health alarm, that checks, for example, battery, operating temperature, etc. and should trigger when any of those are outside the expected range. | 1 |
| ALL_CHECKS_FAILED | Trigger the alarm only when all checks fail. This is useful when creating a combined alarm, where several data points factor into the decisions to trigger the alarm, for example, combining a check on the current value with a delta check on the historical values, to trigger only if the value is high for a longer period. | 2 |



## Referenced messages from modem_claim.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [modem_claim.proto](https://github.com/HiberGlobal/api/blob/master/modem_claim.proto).


### hiber.modem.ClaimModemRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| claims | [repeated hiber.modem.ClaimModemRequest.ClaimModem](#hibermodemclaimmodemrequestclaimmodem) | none |

### hiber.modem.ClaimModemRequest.ClaimModem



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem_number | [ string](#string) | none |
| verifier | [ string](#string) | none |

### hiber.modem.ClaimModemRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ hiber.modem.ClaimModemRequest](#hibermodemclaimmodemrequest) | none |
| claims | [repeated hiber.modem.ModemClaim](#hibermodemmodemclaim) | none |

### hiber.modem.ListModemClaimsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.modem.ModemClaimSelection](#hibermodemmodemclaimselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |

### hiber.modem.ListModemClaimsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| claims | [repeated hiber.modem.ModemClaim](#hibermodemmodemclaim) | none |
| request | [ hiber.modem.ListModemClaimsRequest](#hibermodemlistmodemclaimsrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### hiber.modem.ModemClaim



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem_number | [ string](#string) | none |
| created_at | [ hiber.Timestamp](#hibertimestamp) | none |
| claiming_organization | [ string](#string) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | Tags the modem had when it was claimed. |

### hiber.modem.ModemClaimSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [ hiber.Filter.Modems](#hiberfiltermodems) | none |
| time_range | [ hiber.TimeRange](#hibertimerange) | none |


### Enums


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
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| assign_parsers | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) | none |
| to_modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | none |

### hiber.modem.message.bodyparser.AssignModemMessageBodyParsers.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| created | [repeated hiber.modem.message.bodyparser.AssignedModemMessageBodyParser](#hibermodemmessagebodyparserassignedmodemmessagebodyparser) | none |
| request | [ hiber.modem.message.bodyparser.AssignModemMessageBodyParsers.Request](#hibermodemmessagebodyparserassignmodemmessagebodyparsersrequest) | none |

### hiber.modem.message.bodyparser.AssignedModemMessageBodyParser

Directly assigned modem message parser to a modem.

| Field | Type | Description |
| ----- | ---- | ----------- |
| parser_identifier | [ string](#string) | none |
| modem_number | [ string](#string) | none |

### hiber.modem.message.bodyparser.CreateSimpleModemMessageBodyParserRequest

Create a simple modem message parser, which generates a .ksy specification.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| parser | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser](#hibermodemmessagebodyparsersimplemodemmessagebodyparser) | none |

### hiber.modem.message.bodyparser.DeleteModemMessageBodyParserRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) | A selection of parsers to be deleted. |

### hiber.modem.message.bodyparser.DeleteModemMessageBodyParserRequest.Response




### hiber.modem.message.bodyparser.ListModemMessageBodyParsersRequest

List the parser your organizations has access to. This may include inherited parsers.

If include_content is not set, this call may omit parser specifications, like the ksy, since those are
typically larger multi-line strings.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |
| exclude_content | [ bool](#bool) | Whether to omit the content in the resulting ModemMessageBodyParsers. |

### hiber.modem.message.bodyparser.ListModemMessageBodyParsersRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| parsers | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |
| request | [ hiber.modem.message.bodyparser.ListModemMessageBodyParsersRequest](#hibermodemmessagebodyparserlistmodemmessagebodyparsersrequest) | none |

### hiber.modem.message.bodyparser.MakeModemMessageBodyParserAvailableToChildOrganizationRequest

Make this parser available to a specific child organizations.

This will
- when the organization is on the exclude list, remove it
- when the includeAll flag is false, add it to the include list (if not already present)

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the parser that should be updated. |
| available_to | [repeated string](#string) | The child organization(s) that the parser should be available to. |

### hiber.modem.message.bodyparser.MakeModemMessageBodyParserUnavailableToChildOrganizationRequest

Make this parser unavailable to a specific child organizations.

This will
- when the organization is on the include list, remove it
- when the includeAll flag is true, add it to the exclude list (if not already present)

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
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
| data_fields_deprecated | [repeated string](#string) | none |
| metadata_fields | [ hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafields) | Fields in the parsed result that contain metadata, and special things like a location. |
| available_to_child_organizations | [ hiber.modem.message.bodyparser.ModemMessageBodyParser.AvailableToChildOrganizations](#hibermodemmessagebodyparsermodemmessagebodyparseravailabletochildorganizations) | If set, this parser is available to your child organizations, as a Provided parser. |
| post_processing | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser.PostProcessing](#hibermodemmessagebodyparsermodemmessagebodyparserpostprocessing) | The list of post-processing steps applied to the result of this parser. |

### hiber.modem.message.bodyparser.ModemMessageBodyParser.AvailableToChildOrganizations

A modem message body parser with this object is available to child organizations.
This means the child organization can use it, but not update or delete it.

| Field | Type | Description |
| ----- | ---- | ----------- |
| child_organizations | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | none |

### hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields

Fields in the parsed result that match common things that can be processed by the system,
like a location or battery percentage.

| Field | Type | Description |
| ----- | ---- | ----------- |
| location_fields | [ hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields.LocationFields](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafieldslocationfields) | Specify a pair of fields in the message body that contain location data, which will update the modem location and the map. |
| message_metadata_fields | [repeated string](#string) | Custom metadata fields, which will be added to the message metadata json. |
| modem_metadata_fields | [repeated string](#string) | Custom metadata fields, which will be added to the modem metadata json. |

### hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields.LocationFields



| Field | Type | Description |
| ----- | ---- | ----------- |
| latitude | [ string](#string) | none |
| longitude | [ string](#string) | none |

### hiber.modem.message.bodyparser.ModemMessageBodyParserSelection

Selection object for parsers. Used to select which parser to list, assign, etc.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifiers | [repeated string](#string) | Filter parsers by their identifiers. |
| search | [ string](#string) | Find parsers by searching for this text in the name, content_ksy, data fields or simple parser definition. |
| only_simple | [ bool](#bool) | Only return simple parsers, created using SimpleModemMessageBodyParser. |
| only_ksy_file | [ bool](#bool) | Only return parsers created from an uploaded .ksy file. |
| only_owned_parsers | [ bool](#bool) | Exclude parsers that are not owned by your organization (those that you did not create yourself). |
| owner_organizations | [repeated string](#string) | Only return parsers that were created by the given parent organizations. |
| has_data_fields | [repeated string](#string) | Only return parsers that have one of the given data fields This only works when the fields are marked explicitly using the data fields option. |

### hiber.modem.message.bodyparser.RenameModemMessageBodyParserRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the parser that should be updated. |
| name | [ string](#string) | The new name for this parser. |

### hiber.modem.message.bodyparser.RetryModemMessageBodyParsing

Retry a message, parsing it with all the currently assigned parsers that are in the given selection.
If the message was previously parsed by any of those parsers, the previous result is replaced.


### hiber.modem.message.bodyparser.RetryModemMessageBodyParsing.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| modem_message_ids | [repeated uint64](#uint64) | The messages to parse. |
| parser_selection | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) | A selection of parsers to apply, if they are assigned. |

### hiber.modem.message.bodyparser.RetryModemMessageBodyParsing.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| parsed_messages | [repeated hiber.modem.ModemMessage.ParsedBody](#hibermodemmodemmessageparsedbody) | none |

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
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.integer | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Integer](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfieldinteger) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.float | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Float](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfieldfloat) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.bytes | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Bytes](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfieldbytes) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.string | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.String](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfieldstring) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.magic | [ bytes](#bytes) | Specify an expected magic sequence (some bytes that are always the same). |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.custom_type | [ string](#string) | Specify a custom type name. |

### hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Bytes



| Field | Type | Description |
| ----- | ---- | ----------- |
| size | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.DelimitedSize](#hibermodemmessagebodyparsersimplemodemmessagebodyparserdelimitedsize) | none |

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
| size | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.DelimitedSize](#hibermodemmessagebodyparsersimplemodemmessagebodyparserdelimitedsize) | none |
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
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **parser**.identifier | [ string](#string) | The identifier of the parser you want to test. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **parser**.content_ksy | [ string](#string) | A ksy definition you want to test. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **parser**.simple_parser | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser](#hibermodemmessagebodyparsersimplemodemmessagebodyparser) | A simple parser definition you want to test. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.parse_bytes | [ hiber.BytesOrHex](#hiberbytesorhex) | A byte array (message body) to parse. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.modem_message_id | [ uint64](#uint64) | The id of an existing message, testing the parser on its body. |

### hiber.modem.message.bodyparser.TestModemMessageBodyParserRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **result**.parsed | [ google.protobuf.Struct](#googleprotobufstruct) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **result**.error | [ string](#string) | none |

### hiber.modem.message.bodyparser.UnassignModemMessageBodyParsers

Remove a direct assignment.
If an overlapping assignment using a rule exists, it is not affected, except that it is longer shadowed.

Simplified version of assign.UnassignDirectly.


### hiber.modem.message.bodyparser.UnassignModemMessageBodyParsers.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| unassign_parsers | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) | none |
| from_modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | none |

### hiber.modem.message.bodyparser.UnassignModemMessageBodyParsers.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| removed_direct_assignments | [repeated hiber.modem.message.bodyparser.AssignedModemMessageBodyParser](#hibermodemmessagebodyparserassignedmodemmessagebodyparser) | none |
| request | [ hiber.modem.message.bodyparser.UnassignModemMessageBodyParsers.Request](#hibermodemmessagebodyparserunassignmodemmessagebodyparsersrequest) | none |

### hiber.modem.message.bodyparser.UpdateChildOrganizationAvailabilityRequest

Update the child availability for a parser.
Parsers can be made available to child organizations, which means that they can be viewed in,
and assigned to modems in, child organizations.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the parser that should be updated. |
| available_to_child_organizations | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | The new child organization availability filter for this parser. |

### hiber.modem.message.bodyparser.UpdateSimpleModemMessageBodyParserRequest

Update a simple modem message parser, updating the generated .ksy specification.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the parser that should be updated. |
| parser | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser](#hibermodemmessagebodyparsersimplemodemmessagebodyparser) | none |

### hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest

Upload an updated body parser from a .ksy file, replacing the previous file.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the parser that should be updated. |
| content_ksy | [ string](#string) | The new ksy definition for this parser. |
| add_data_fields | [repeated hiber.field.Field](#hiberfieldfield) | Add fields to the data fields list. |
| remove_data_fields | [repeated string](#string) | Remove fields from the data fields list. |
| metadata_fields | [ hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields](#hibermodemmessagebodyparserupdateuploadedmodemmessagebodyparserrequestmetadatafields) | Fields in the parsed result that match special things that can be processed by the system, like a location. |
| add_post_processing | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser.PostProcessing](#hibermodemmessagebodyparsermodemmessagebodyparserpostprocessing) | Add a post-processing step to the result of this parser. |
| remove_post_processing | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser.PostProcessing](#hibermodemmessagebodyparsermodemmessagebodyparserpostprocessing) | Remove a post-processing step to the result of this parser. |

### hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields



| Field | Type | Description |
| ----- | ---- | ----------- |
| update_location_fields | [ hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields.LocationFields](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafieldslocationfields) | Update the location fields. |
| add_message_metadata_fields | [repeated string](#string) | Add fields to the message metadata fields list. |
| remove_message_metadata_fields | [repeated string](#string) | Remove fields from the message metadata fields list. |
| replace_message_metadata_fields | [repeated string](#string) | Replace the message metadata fields list. |
| add_modem_metadata_fields | [repeated string](#string) | Add fields to the modem metadata fields list. |
| remove_modem_metadata_fields | [repeated string](#string) | Remove fields from the modem metadata fields list. |
| replace_modem_metadata_fields | [repeated string](#string) | Replace the modem metadata fields list. |

### hiber.modem.message.bodyparser.UploadModemMessageBodyParserRequest

Upload a new body parser from a .ksy file.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| name | [ string](#string) | A descriptive name for this parser. |
| content_ksy | [ string](#string) | The ksy definition for this parser. |
| data_fields | [repeated hiber.field.Field](#hiberfieldfield) | Fields in the parsed result that contain data. This can be useful to track which fields could be plotted, etc. |
| metadata_fields | [ hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafields) | Fields in the parsed result that match special things that can be processed by the system, like a location. |
| post_processing | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser.PostProcessing](#hibermodemmessagebodyparsermodemmessagebodyparserpostprocessing) | none |


### Enums
#### hiber.modem.message.bodyparser.ModemMessageBodyParser.PostProcessing
The type of post-processing to be applied to the result of this parser.

| Name | Description | Number |
| ---- | ----------- | ------ |
| NOTHING | none | 0 |
| EASYPULSE | none | 1 |

#### hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Endian


| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | none | 0 |
| LITTLE_ENDIAN | none | 1 |
| BIG_ENDIAN | none | 2 |



## Referenced messages from modem_transfer.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [modem_transfer.proto](https://github.com/HiberGlobal/api/blob/master/modem_transfer.proto).


### hiber.modem.CancelModemTransferRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.modem.ModemTransferSelection](#hibermodemmodemtransferselection) | none |

### hiber.modem.CancelModemTransferRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ hiber.modem.CancelModemTransferRequest](#hibermodemcancelmodemtransferrequest) | none |
| cancelled | [repeated hiber.modem.ModemTransfer](#hibermodemmodemtransfer) | none |

### hiber.modem.DeleteModemTransferReturnLinesRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| transfer_id | [ string](#string) | none |
| modem_numbers | [repeated string](#string) | none |

### hiber.modem.DeleteModemTransferReturnLinesRequest.Response




### hiber.modem.ListModemTransferReturnLinesRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.modem.ModemTransferSelection](#hibermodemmodemtransferselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |

### hiber.modem.ListModemTransferReturnLinesRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ hiber.modem.ListModemTransferReturnLinesRequest](#hibermodemlistmodemtransferreturnlinesrequest) | none |
| lines | [repeated hiber.modem.ModemTransferReturnLine](#hibermodemmodemtransferreturnline) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### hiber.modem.ListModemTransfersRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.modem.ModemTransferSelection](#hibermodemmodemtransferselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |

### hiber.modem.ListModemTransfersRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ hiber.modem.ListModemTransfersRequest](#hibermodemlistmodemtransfersrequest) | none |
| transfers | [repeated hiber.modem.ModemTransfer](#hibermodemmodemtransfer) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### hiber.modem.ModemTransfer



| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) | none |
| modem_numbers | [repeated string](#string) | none |
| type | [ hiber.modem.ModemTransfer.Type](#hibermodemmodemtransfertype) | none |
| status | [ hiber.modem.ModemTransfer.Status](#hibermodemmodemtransferstatus) | none |
| sender_organization | [ string](#string) | none |
| recipient_organization | [ string](#string) | none |
| return_transfers | [repeated string](#string) | none |
| return_for | [repeated string](#string) | none |
| tracking_information | [ string](#string) | none |
| created_at | [ hiber.Timestamp](#hibertimestamp) | none |
| received_at | [ hiber.Timestamp](#hibertimestamp) | none |
| cancelled_at | [ hiber.Timestamp](#hibertimestamp) | none |
| not_received_at | [ hiber.Timestamp](#hibertimestamp) | none |
| return_deadline | [ hiber.Timestamp](#hibertimestamp) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |

### hiber.modem.ModemTransferReturnLine



| Field | Type | Description |
| ----- | ---- | ----------- |
| original_transfer | [ string](#string) | none |
| return_transfer | [ string](#string) | none |
| modem_numbers | [repeated string](#string) | none |
| reason | [ hiber.modem.ModemTransferReturnLine.Reason](#hibermodemmodemtransferreturnlinereason) | none |
| comment | [ string](#string) | none |
| created_at | [ hiber.Timestamp](#hibertimestamp) | none |
| returned_at | [ hiber.Timestamp](#hibertimestamp) | none |
| return_deadline | [ hiber.Timestamp](#hibertimestamp) | none |

### hiber.modem.ModemTransferSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| identifiers | [repeated string](#string) | none |
| modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | none |
| senders | [repeated string](#string) | none |
| recipients | [repeated string](#string) | none |
| statuses | [repeated hiber.modem.ModemTransfer.Status](#hibermodemmodemtransferstatus) | none |
| created_in | [ hiber.TimeRange](#hibertimerange) | none |
| received_in | [ hiber.TimeRange](#hibertimerange) | none |
| not_received_in | [ hiber.TimeRange](#hibertimerange) | none |
| cancelled_in | [ hiber.TimeRange](#hibertimerange) | none |
| types | [repeated hiber.modem.ModemTransfer.Type](#hibermodemmodemtransfertype) | none |
| inbound_only | [ bool](#bool) | Convenience method to setting recipients = my organization. Will ignore any current value for recipients, since the only valid recipient is you. |
| outbound_only | [ bool](#bool) | Convenience method to setting senders = my organization. Will ignore any current value for senders, since the only valid sender is you. |

### hiber.modem.NotReceivedModemTransferRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.modem.ModemTransferSelection](#hibermodemmodemtransferselection) | none |

### hiber.modem.NotReceivedModemTransferRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ hiber.modem.NotReceivedModemTransferRequest](#hibermodemnotreceivedmodemtransferrequest) | none |
| not_received | [repeated hiber.modem.ModemTransfer](#hibermodemmodemtransfer) | none |

### hiber.modem.PrepareModemForReturnRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| transfer_id | [ string](#string) | The transfer id that you received the modems with, to be used to the return. If this is provided, only one return line is returned. If this is not provided, the given modem selection could match multiple transfers, so multiple return lines would be created. |
| selection | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | Selection of modems, received from the transfer above. |
| reason | [ hiber.modem.ModemTransferReturnLine.Reason](#hibermodemmodemtransferreturnlinereason) | The reason for the return. For the 'other' reason, a comment is required. |
| comment | [ string](#string) | Optional, unless the 'other' reason is selected. |
| replace_previous_comment | [ bool](#bool) | Use this to update the comment for a return line (using the same transfer_id and reason). |

### hiber.modem.PrepareModemForReturnRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ hiber.modem.PrepareModemForReturnRequest](#hibermodempreparemodemforreturnrequest) | none |
| modem_return_lines | [repeated hiber.modem.ModemTransferReturnLine](#hibermodemmodemtransferreturnline) | none |

### hiber.modem.ReceivedModemTransferRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.modem.ModemTransferSelection](#hibermodemmodemtransferselection) | none |

### hiber.modem.ReceivedModemTransferRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ hiber.modem.ReceivedModemTransferRequest](#hibermodemreceivedmodemtransferrequest) | none |
| received | [repeated hiber.modem.ModemTransfer](#hibermodemmodemtransfer) | none |

### hiber.modem.SendReturnRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.modem.ModemTransferSelection](#hibermodemmodemtransferselection) | none |
| tracking_information | [ string](#string) | none |

### hiber.modem.SendReturnRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ hiber.modem.SendReturnRequest](#hibermodemsendreturnrequest) | none |
| return_transfer | [ hiber.modem.ModemTransfer](#hibermodemmodemtransfer) | none |

### hiber.modem.TransferModemsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | The ModemSelection is automatically appended with a status filter for 'in stock' modems. Modems with a different status are ignored for the transfer. |
| recipient_organization | [ string](#string) | Existing organization to send the modems to. |
| create_recipient | [ hiber.organization.CreateOrganizationRequest](#hiberorganizationcreateorganizationrequest) | Create a new organization to transfer the modems to. |
| tracking_information | [ string](#string) | Optional tracking information, like package tracking codes |
| mark_received_automatically | [ bool](#bool) | Mark the transfer as received automatically. This only works if you're able to impersonate the recipient organization. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **gateway_and_external_devices**.allow_gateways_and_external_devices | [ bool](#bool) | When this value is not set to true, transferring gateways or modems with an external device id is not allowed. Gateways and external devices are connected to the current organization. Moving either a gateway or connected external device to another organization without moving the other can cause a number of issues.

Deprecated since 0.46. To allow gateways to be transferred without their external devices must now be done using `gateway_transfer_mode` |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **gateway_and_external_devices**.gateway_transfer_mode | [ hiber.modem.TransferModemsRequest.GatewayTransferMode](#hibermodemtransfermodemsrequestgatewaytransfermode) | Set the mode with which this gateway is transferred. It explicitly sets what needs to happen to external devices. This setting is mutually exclusive with the (now deprecated) setting `allow_gateways_and_external_devices`. |
| data_transfer_mode | [ hiber.modem.TransferModemsRequest.DataTransferMode](#hibermodemtransfermodemsrequestdatatransfermode) | What to do with the modem's data, like messages and events. |

### hiber.modem.TransferModemsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ hiber.modem.TransferModemsRequest](#hibermodemtransfermodemsrequest) | none |
| transfer | [ hiber.modem.ModemTransfer](#hibermodemmodemtransfer) | none |
| mark_received_automatically_failed | [ bool](#bool) | When marking a transfer to be received automatically, the calling entity must be able to impersonate the receiving entity. If this (or any other part of the marking the transfer as received) fails, this boolean will be set to true. It is the clients responsibility to check this boolean and inform the client. Note that the transfer itself is created and can still be accepted manually. |


### Enums
#### hiber.modem.ModemTransfer.Status


| Name | Description | Number |
| ---- | ----------- | ------ |
| IN_TRANSIT | none | 0 |
| RECEIVED | none | 1 |
| CANCELLED | none | 3 |
| NOT_RECEIVED | none | 4 |

#### hiber.modem.ModemTransfer.Type


| Name | Description | Number |
| ---- | ----------- | ------ |
| TRANSFER | none | 0 |
| RETURN | none | 1 |

#### hiber.modem.ModemTransferReturnLine.Reason


| Name | Description | Number |
| ---- | ----------- | ------ |
| OTHER | none | 0 |
| INVALID_RECIPIENT | none | 1 |
| INVALID_CONFIGURATION | none | 2 |
| DAMAGED | none | 3 |
| DEAD | none | 4 |
| MISSING | none | 5 |

#### hiber.modem.TransferModemsRequest.DataTransferMode
What to do with the messages, events and other related data.

| Name | Description | Number |
| ---- | ----------- | ------ |
| UNKNOWN | The API Will reject any request without an explicitly set DataTransferMode. | 0 |
| DELETE_DATA | Exclude messages and all events. The data will be deleted. | 1 |

#### hiber.modem.TransferModemsRequest.GatewayTransferMode
What to do with external devices on transferring a gateway.
This mode is evaluated twice: once when the transfer is created and once when the transfer is finalised.
When creating, a double check is done on whether or not your transfer contains gateways or external devices.
When finalising, the actual state of currently connected external devices is determined.
Note: Any *new* external devices that start transmitting after starting the transfer will be processed as well.

| Name | Description | Number |
| ---- | ----------- | ------ |
| NOTHING_SELECTED | Signifies that no selection has been made. This is not allowed for gateways, the client must explicitly choose what happens to external devices. | 0 |
| ORPHAN_EXTERNAL_DEVICES | When transferring a gateway, *orphan* all external devices. The devices are re-created in the recipient organization when they transmit through the gateway.

The old modem is unchanged, but can no longer receive new messages, unless it is connected to another gateway in the sender organization. Old messages from the modem remain in the sender organization under its old modem number. | 1 |
| DELETE_EXTERNAL_DEVICES | When transferring a gateway, mark all external devices as *DEAD*. The devices are re-created in the recipient organization when they transmit through the gateway.

Old messages from this device remain in the sender organization under its old modem, which is marked DEAD. DEAD modems are be automatically hidden, but can still be accessed. | 2 |
| TRANSFER_EXTERNAL_DEVICES | When transferring a gateway, *transfer* all external devices together with the gateway. This moves all existing external devices with the gateway, while they keep their modem number and messages. Old messages from this device will be available to the new owner. | 3 |



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

### hiber.organization.DeleteOrganizationConfirmationRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| parent_organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| organization_to_delete | [ string](#string) | The organization to delete. Required. |
| deletion_token | [ string](#string) | The deletion_token for deletion |

### hiber.organization.DeleteOrganizationConfirmationRequest.Response




### hiber.organization.DeleteOrganizationRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| parent_organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| organization_to_delete | [ string](#string) | The organization to delete. Required. |

### hiber.organization.DeleteOrganizationRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization_to_delete | [ string](#string) | none |
| deletion_token | [ string](#string) | Token to use with DeleteOrganizationConfirmationRequest. |
| organizations_to_be_deleted | [ hiber.organization.OrganizationTree](#hiberorganizationorganizationtree) | The organizations that will be deleted. |
| modems | [repeated string](#string) | The modems that will be moved to the parent organization. |

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
| EASYPULSE | A set of additional features to allow advanced tracking on the map. | 3 |
| EASYPULSE_SCORECARD | Used for an easypulse scorecard feature that we will introduce at a later point. | 7 |
| MODEM_CREATION | Required to manually create modems using the ModemService. | 4 |
| EARLY_ACCESS | Used for organizations that get early access to features. | 5 |
| EXPERIMENTAL | Used for organizations that get access to experimental features. e.g. feature work in progress. | 6 |
| BI_TOOLING_BETA | Integrate BI tooling in the Mission Control interface. | 8 |
| SINARMAS_SPECIFIC | none | 9 |



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
| id | [ int64](#int64) | none |
| description | [ string](#string) | none |
| deprecated_data | [ hiber.publisher.Publisher.Data](#hiberpublisherpublisherdata) | This field remains for backwards compatibility, but it should not be used. |
| filters | [ hiber.publisher.Publisher.Filters](#hiberpublisherpublisherfilters) | none |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | none |
| health | [ hiber.Health](#hiberhealth) | none |
| type | [ hiber.publisher.Publisher.Type](#hiberpublisherpublishertype) | none |
| in_cooldown_until | [ hiber.Timestamp](#hibertimestamp) | none |
| disabled | [ bool](#bool) | none |
| created_by | [ string](#string) | Firebase uid of the user that created this publisher |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.http | [ hiber.webhook.Webhook.WebhookData](#hiberwebhookwebhookwebhookdata) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.mqtt | [ hiber.integration.mqtt.MQTTPublisher.Data](#hiberintegrationmqttmqttpublisherdata) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.email | [ hiber.email.EmailNotificationPreferences](#hiberemailemailnotificationpreferences) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.slack | [ hiber.integration.slack.SlackPublisher.Data](#hiberintegrationslackslackpublisherdata) | none |

### hiber.publisher.Publisher.Data

This type remains for backwards compatibility, but it should not be used.

| Field | Type | Description |
| ----- | ---- | ----------- |
| url | [ string](#string) | none |
| content_type | [ hiber.publisher.Publisher.ContentType](#hiberpublisherpublishercontenttype) | none |
| disabled | [ bool](#bool) | none |
| certificate_id | [ int64](#int64) | none |
| certificate_name | [ string](#string) | none |
| ca_certificate_id | [ int64](#int64) | none |
| ca_certificate_name | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **config**.http | [ hiber.publisher.Publisher.Data.HTTPConfig](#hiberpublisherpublisherdatahttpconfig) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **config**.mqtt | [ hiber.publisher.Publisher.Data.MQTTConfig](#hiberpublisherpublisherdatamqttconfig) | none |

### hiber.publisher.Publisher.Data.HTTPConfig

This field remains for backwards compatibility, but it should not be used.

| Field | Type | Description |
| ----- | ---- | ----------- |
| secret | [ string](#string) | Used to generate the HMAC-SHA256 header on every publisher call, which you can use to verify the message. The HMAC-SHA256 header is calculated with the message body and this secret. There are many examples of how to do this in different languages, for example: https://github.com/danharper/hmac-examples |

### hiber.publisher.Publisher.Data.MQTTConfig

This field remains for backwards compatibility, but it should not be used.

| Field | Type | Description |
| ----- | ---- | ----------- |
| topic | [ string](#string) | none |
| qos | [ hiber.publisher.Publisher.Data.MQTTConfig.QoS](#hiberpublisherpublisherdatamqttconfigqos) | none |
| username | [ string](#string) | Optional username to authenticate with. |
| password | [ string](#string) | Optional password to authenticate with. Requires username to be set. |
| identifier | [ string](#string) | Identifier used by the MQTT client. Defaults to "hiber". |

### hiber.publisher.Publisher.Filters



| Field | Type | Description |
| ----- | ---- | ----------- |
| event_types | [ hiber.Filter.Events](#hiberfilterevents) | none |
| modem_numbers | [ hiber.Filter.Modems](#hiberfiltermodems) | none |
| tags | [ hiber.Filter.Tags](#hiberfiltertags) | none |

### hiber.publisher.UpdatePublisherRequest




### hiber.publisher.UpdatePublisherRequest.UpdateModems



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) | none |
| value | [ hiber.Filter.Modems](#hiberfiltermodems) | none |


### Enums
#### hiber.publisher.Publisher.ContentType
This type remains for backwards compatibility, but it should not be used.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | none | 0 |
| JSON | none | 1 |
| PROTO | none | 2 |

#### hiber.publisher.Publisher.Data.MQTTConfig.QoS


| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | none | 0 |
| AT_MOST_ONCE | Qos level 0 | 1 |
| AT_LEAST_ONCE | Qos level 1 | 2 |
| EXACTLY_ONCE | Qos level 2 | 3 |

#### hiber.publisher.Publisher.Type


| Name | Description | Number |
| ---- | ----------- | ------ |
| HTTP | none | 0 |
| MQTT | none | 1 |
| EMAIL | none | 3 |
| SLACK | none | 4 |



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


## Referenced messages from token.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [token.proto](https://github.com/HiberGlobal/api/blob/master/token.proto).


### hiber.token.CreateTokenRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| name | [ string](#string) | none |
| expires_at | [ hiber.Timestamp](#hibertimestamp) | none |
| user_permissions | [ hiber.Filter.UserPermissions](#hiberfilteruserpermissions) | none |
| organization_permissions | [ hiber.Filter.OrganizationPermissions](#hiberfilterorganizationpermissions) | none |

### hiber.token.CreateTokenRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| token | [ string](#string) | none |
| created | [ hiber.token.Token](#hibertokentoken) | none |

### hiber.token.DeleteTokenRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| token_id | [ int64](#int64) | none |

### hiber.token.DeleteTokenRequest.Response




### hiber.token.ListTokensRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.token.TokenSelection](#hibertokentokenselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |

### hiber.token.ListTokensRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| tokens | [repeated hiber.token.Token](#hibertokentoken) | none |
| request | [ hiber.token.ListTokensRequest](#hibertokenlisttokensrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### hiber.token.Token



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) | none |
| name | [ string](#string) | none |
| user_id | [ string](#string) | none |
| organization | [ string](#string) | none |
| expires_at | [ hiber.Timestamp](#hibertimestamp) | none |
| user_permissions | [repeated hiber.UserPermission](#hiberuserpermission) | none |
| organization_permissions | [repeated hiber.OrganizationPermission](#hiberorganizationpermission) | none |

### hiber.token.TokenSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| users | [ hiber.Filter.Users](#hiberfilterusers) | none |
| name | [ string](#string) | none |
| include_expired | [ bool](#bool) | none |

### hiber.token.UpdateTokenOrganizationPermissionsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| token_ids | [repeated int64](#int64) | none |
| replace_organization_permissions | [ hiber.Filter.OrganizationPermissions](#hiberfilterorganizationpermissions) | Completely replace the organization permission for the selected token(s) with this set. |
| add_organization_permissions | [repeated hiber.OrganizationPermission](#hiberorganizationpermission) | Add organization permissions to the token. |
| remove_organization_permissions | [repeated hiber.OrganizationPermission](#hiberorganizationpermission) | Remove organization permissions from the token. Ensures the permissions is no longer on the token (even if you also add it using add_organization_permissions). |

### hiber.token.UpdateTokenOrganizationPermissionsRequest.Response




### hiber.token.UpdateTokenUserPermissionsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| token_ids | [repeated int64](#int64) | none |
| replace_user_permissions | [ hiber.Filter.UserPermissions](#hiberfilteruserpermissions) | Completely replace the user permission for the selected token(s) with this set. |
| add_user_permissions | [repeated hiber.UserPermission](#hiberuserpermission) | Add user permissions to the token. |
| remove_user_permissions | [repeated hiber.UserPermission](#hiberuserpermission) | Remove user permissions from the token. |

### hiber.token.UpdateTokenUserPermissionsRequest.Response





### Enums


## Referenced messages from user.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [user.proto](https://github.com/HiberGlobal/api/blob/master/user.proto).


### hiber.user.ApproveUserRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| user_ids | [repeated string](#string) | none |
| permissions | [ hiber.Filter.OrganizationPermissions](#hiberfilterorganizationpermissions) | none |
| override_allow_no_permissions | [ bool](#bool) | By default, the server returns an error when you don't specify any permissions. Set this to true to allow it. |

### hiber.user.ApproveUserRequest.Response




### hiber.user.CreateUserRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| email | [ string](#string) | none |
| name | [ string](#string) | none |
| password | [ string](#string) | Optional. If no password is given, the account can only be accessed using a password reset. |
| permissions | [ hiber.Filter.OrganizationPermissions](#hiberfilterorganizationpermissions) | Permissions the new user should get. |
| send_verification_mail | [ bool](#bool) | Send an automated email prompting the user to verify their email address. |
| send_password_reset_mail | [ bool](#bool) | Send an automated email prompting the user to set a password. Recommended when password is not set. |
| allow_invite_instead | [ bool](#bool) | When the user cannot be created, (i.e. they already exist because they are in a different organization) we can send an invite instead, effectively calling InviteUserRequest with the email and permissions. Set this to true to allow this behaviour. |
| override_allow_no_permissions | [ bool](#bool) | By default, the server returns an error when you don't specify any permissions. Set this to true to allow it. |

### hiber.user.CreateUsersRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| users | [repeated hiber.user.CreateUserRequest](#hiberusercreateuserrequest) | Users to create. Allows for individual impersonation and mail settings. |
| permissions | [ hiber.Filter.OrganizationPermissions](#hiberfilterorganizationpermissions) | Set the permissions for all users. Can be replaced for specific settings in the CreateUserRequest. |
| send_verification_mail | [ bool](#bool) | Send an automated email prompting the users to verify their email addresses. If true, applies to all users. |
| send_password_reset_mail | [ bool](#bool) | Send an automated email prompting the users to set their password. If true, applies to all users. |

### hiber.user.CreateUsersRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| users | [repeated hiber.user.User](#hiberuseruser) | none |

### hiber.user.GetUserValidationRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |

### hiber.user.InviteUserRequest

Accept an invitation to an organization.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| email | [ string](#string) | The email address of the user you want to invite. |
| retry | [ bool](#bool) | Invite the user again, even if there is an open invite. This can be done a limited amount of times. |
| permissions | [ hiber.Filter.OrganizationPermissions](#hiberfilterorganizationpermissions) | none |
| override_allow_no_permissions | [ bool](#bool) | By default, the server returns an error when you don't specify any permissions. Set this to true to allow it. |

### hiber.user.InviteUserRequest.Response




### hiber.user.ListAccessRequestsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.user.UserSelection](#hiberuseruserselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |
| sort | [ hiber.user.UserSort](#hiberuserusersort) | none |

### hiber.user.ListAccessRequestsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| users | [repeated hiber.user.User](#hiberuseruser) | none |
| request | [ hiber.user.ListAccessRequestsRequest](#hiberuserlistaccessrequestsrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### hiber.user.ListInvitationsRequest

List all invited users (email addresses).

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| search | [ string](#string) | Search the invited email addresses. |
| include_accepted | [ bool](#bool) | Whether to include invitations that were already accepted. |

### hiber.user.ListInvitationsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| emails | [repeated string](#string) | none |

### hiber.user.ListUsersRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.user.UserSelection](#hiberuseruserselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |
| sort | [ hiber.user.UserSort](#hiberuserusersort) | none |

### hiber.user.ListUsersRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| users | [repeated hiber.user.User](#hiberuseruser) | none |
| request | [ hiber.user.ListUsersRequest](#hiberuserlistusersrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### hiber.user.RemoveUserRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| user_ids | [repeated string](#string) | none |
| remove_all_tokens | [ bool](#bool) | Remove all tokens created by this user. If this is not set, only the tokens with user permissions are removed. |

### hiber.user.RemoveUserRequest.Response




### hiber.user.ResetUserPasswordRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| user_id | [ string](#string) | none |

### hiber.user.ResetUserPasswordRequest.Response




### hiber.user.TestUserValidationRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **validate**.selection | [ hiber.user.UserSelection](#hiberuseruserselection) | Test with existing user(s). |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **validate**.email_address | [ string](#string) | Test with a given email address. |
| custom_validation | [ hiber.user.UserValidation](#hiberuseruservalidation) | Test the given validation instead of the validation configured for your organization. |

### hiber.user.TestUserValidationRequest.Response




### hiber.user.UpdateUserPermissionsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| user_ids | [repeated string](#string) | none |
| new_permissions | [ hiber.Filter.OrganizationPermissions](#hiberfilterorganizationpermissions) | The previous permissions are replaced! |
| override_allow_no_permissions | [ bool](#bool) | By default, the server returns an error when you don't specify any permissions. Set this to true to allow it. |

### hiber.user.UpdateUserPermissionsRequest.Response




### hiber.user.UpdateUserValidationRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| email_validation_regex | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | none |

### hiber.user.User



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | none |
| email | [ string](#string) | none |
| name | [ string](#string) | none |
| permissions | [ hiber.Filter.OrganizationPermissions](#hiberfilterorganizationpermissions) | none |

### hiber.user.UserActivitySummaryRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| user_id | [ string](#string) | The user to request activity for. |
| dates | [repeated hiber.Date](#hiberdate) | The dates to request user activity for. |
| child_organizations | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | Include activity for child organizations. |

### hiber.user.UserActivitySummaryRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| summaries | [repeated hiber.user.UserActivitySummaryRequest.Response.UserActivitySummary](#hiberuseruseractivitysummaryrequestresponseuseractivitysummary) | none |

### hiber.user.UserActivitySummaryRequest.Response.UserActivitySummary



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| user_id | [ string](#string) | none |
| date | [ hiber.Date](#hiberdate) | none |
| actions | [repeated string](#string) | none |
| total_requests | [ uint32](#uint32) | none |

### hiber.user.UserSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| user_ids | [repeated string](#string) | none |
| by_email | [ string](#string) | none |
| by_name | [ string](#string) | none |
| search | [ string](#string) | none |

### hiber.user.UserValidation



| Field | Type | Description |
| ----- | ---- | ----------- |
| email_validation_regex | [ string](#string) | none |


### Enums
#### hiber.user.UserSort


| Name | Description | Number |
| ---- | ----------- | ------ |
| EMAIL_ASC | none | 0 |
| EMAIL_DESC | none | 1 |
| NAME_ASC | none | 2 |
| NAME_DESC | none | 3 |



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
| in_cooldown_until | [ hiber.Timestamp](#hibertimestamp) | When the webhook call fails, it enters cooldown, so as not to overload a failing server or spend unnecessary time on an incorrectly configured webhook. When the first call after the cooldown time has passed fails again, the cooldown is increased as follows: 1m, 2m, 5m, 10m, 15m, 30m, 1h, 3h, 6h, 12h, 24h

To disable the cooldown, use EnableWebhookRequest to re-enable it. |

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

