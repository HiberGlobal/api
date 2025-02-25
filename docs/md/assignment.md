# assignment.proto



#### This file was generated from [assignment.proto](https://github.com/HiberGlobal/api/blob/master/assignment.proto).

## Table of Contents

- Services
  - [AssignmentService](#assignmentservice)

- Messages
  - [Assign](#assign)
  - [Assign.Request](#assignrequest)
  - [Assign.Request.AlarmParametersEntry](#assignrequestalarmparametersentry)
  - [Assign.Response](#assignresponse)
  - [Assignment](#assignment)
  - [Assignment.AdditionalConfiguration](#assignmentadditionalconfiguration)
  - [Assignment.AdditionalConfiguration.AssetDeviceAssignment](#assignmentadditionalconfigurationassetdeviceassignment)
  - [Assignment.AdditionalConfiguration.FieldsByJsonPath](#assignmentadditionalconfigurationfieldsbyjsonpath)
  - [Assignment.AlarmAssignment](#assignmentalarmassignment)
  - [Assignment.ModemMessageBodyParserAssignment](#assignmentmodemmessagebodyparserassignment)
  - [AssignmentSelection](#assignmentselection)
  - [AssignmentSelection.AssignmentTypes](#assignmentselectionassignmenttypes)
  - [DeleteAssignment](#deleteassignment)
  - [DeleteAssignment.Request](#deleteassignmentrequest)
  - [DeleteAssignment.Response](#deleteassignmentresponse)
  - [ListAlarmAssignments](#listalarmassignments)
  - [ListAlarmAssignments.Request](#listalarmassignmentsrequest)
  - [ListAlarmAssignments.Response](#listalarmassignmentsresponse)
  - [ListAlarmAssignments.Response.AlarmAssignment](#listalarmassignmentsresponsealarmassignment)
  - [ListAlarmAssignments.Response.AlarmAssignment.ToAsset](#listalarmassignmentsresponsealarmassignmenttoasset)
  - [ListAlarmAssignments.Response.AlarmAssignment.ToModem](#listalarmassignmentsresponsealarmassignmenttomodem)
  - [ListAlarmAssignments.Response.AlarmAssignment.ToTag](#listalarmassignmentsresponsealarmassignmenttotag)
  - [ListAssetAssignments](#listassetassignments)
  - [ListAssetAssignments.Request](#listassetassignmentsrequest)
  - [ListAssetAssignments.Response](#listassetassignmentsresponse)
  - [ListAssetAssignments.Response.AssetAssignment](#listassetassignmentsresponseassetassignment)
  - [ListAssignments](#listassignments)
  - [ListAssignments.Request](#listassignmentsrequest)
  - [ListAssignments.Response](#listassignmentsresponse)
  - [ListModemAssignments](#listmodemassignments)
  - [ListModemAssignments.Request](#listmodemassignmentsrequest)
  - [ListModemAssignments.Response](#listmodemassignmentsresponse)
  - [ListModemAssignments.Response.ModemAssignment](#listmodemassignmentsresponsemodemassignment)
  - [ListModemMessageBodyParserAssignments](#listmodemmessagebodyparserassignments)
  - [ListModemMessageBodyParserAssignments.Request](#listmodemmessagebodyparserassignmentsrequest)
  - [ListModemMessageBodyParserAssignments.Response](#listmodemmessagebodyparserassignmentsresponse)
  - [ListModemMessageBodyParserAssignments.Response.ModemMessageBodyParserAssignment](#listmodemmessagebodyparserassignmentsresponsemodemmessagebodyparserassignment)
  - [ListTagAssignments](#listtagassignments)
  - [ListTagAssignments.Request](#listtagassignmentsrequest)
  - [ListTagAssignments.Response](#listtagassignmentsresponse)
  - [ListTagAssignments.Response.TagAssignment](#listtagassignmentsresponsetagassignment)
  - [Unassign](#unassign)
  - [Unassign.Request](#unassignrequest)
  - [Unassign.Response](#unassignresponse)

- Enums
  - [AssignmentType](#assignmenttype)

- Referenced messages from [asset.proto](#referenced-messages-from-assetproto)
  - [hiber.asset.Asset](#hiberassetasset)
  - [hiber.asset.Asset.AssignedDevice](#hiberassetassetassigneddevice)
  - [hiber.asset.AssetSelection](#hiberassetassetselection)

    - [hiber.asset.Asset.Type](#hiberassetassettype)

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

- Referenced messages from [tag.proto](#referenced-messages-from-tagproto)
  - [hiber.tag.Tag](#hibertagtag)
  - [hiber.tag.Tag.Label](#hibertagtaglabel)
  - [hiber.tag.TagSelection](#hibertagtagselection)


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


## AssignmentService


### List
> **rpc** List([ListAssignments.Request](#listassignmentsrequest))
    [ListAssignments.Response](#listassignmentsresponse)

List assignments.

### Assign
> **rpc** Assign([Assign.Request](#assignrequest))
    [Assign.Response](#assignresponse)

Assign something, like an alarm to a modem.

### Unassign
> **rpc** Unassign([Unassign.Request](#unassignrequest))
    [Unassign.Response](#unassignresponse)

End an assignment, like an alarm to a modem.

### Delete
> **rpc** Delete([DeleteAssignment.Request](#deleteassignmentrequest))
    [DeleteAssignment.Response](#deleteassignmentresponse)

Delete an assignment, even if it has a time range.

### AssetAssignments
> **rpc** AssetAssignments([ListAssetAssignments.Request](#listassetassignmentsrequest))
    [ListAssetAssignments.Response](#listassetassignmentsresponse)

List assets with the devices and tags they are assigned to.

### ModemAssignments
> **rpc** ModemAssignments([ListModemAssignments.Request](#listmodemassignmentsrequest))
    [ListModemAssignments.Response](#listmodemassignmentsresponse)

List modems with tags, alarms and parsers assigned to them.

### TagAssignments
> **rpc** TagAssignments([ListTagAssignments.Request](#listtagassignmentsrequest))
    [ListTagAssignments.Response](#listtagassignmentsresponse)

List tags with the modems, alarms and parsers they are assigned to.

### AlarmAssignments
> **rpc** AlarmAssignments([ListAlarmAssignments.Request](#listalarmassignmentsrequest))
    [ListAlarmAssignments.Response](#listalarmassignmentsresponse)

List alarms with the modems and parsers they are assigned to.

### ModemMessageBodyParserAssignments
> **rpc** ModemMessageBodyParserAssignments([ListModemMessageBodyParserAssignments.Request](#listmodemmessagebodyparserassignmentsrequest))
    [ListModemMessageBodyParserAssignments.Response](#listmodemmessagebodyparserassignmentsresponse)

List alarms with the modems and parsers they are assigned to.


## Messages

### Assign

Add assignments.


### Assign.Request



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
| alarm_parameters | [map Assign.Request.AlarmParametersEntry](#assignrequestalarmparametersentry) | <strong>Deprecated.</strong> The alarm parameters, by alarm identifier, if any, overriding any default values in the alarm(s). |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **additional_configuration**.asset_device | [ Assignment.AdditionalConfiguration.AssetDeviceAssignment](#assignmentadditionalconfigurationassetdeviceassignment) | Additional configuration for assignment between Asset and Device/Modem. |
|  **optional** override_time | [optional hiber.Timestamp](#hibertimestamp) | Time that the assignment should be active. This sets the assignment to start in the past, but would not have effect in the past for assignments like parsers and alarms (they will only be triggered for new messages / values). It would however work for assets having access to device data. This is not allowed to be a value in the future at the moment. |
|  **optional** end_time | [optional hiber.Timestamp](#hibertimestamp) | Time that the assignment ended. This marks the assignment as ended at the given moment in the past, but would not have effect in the past for assignments like parsers and alarms (e.g. no alarm events are removed). It would however work for assets having access to device data. This is not allowed to be a value in the future at the moment. |
|  **optional** override_conflicting_assignments | [optional bool](#bool) | Instead of throwing an error when there are conflicting assignments, unassign the conflicting assignments with the given time (override_time or now) and then making the assignment. |
|  **optional** override_conflicting_assignments_allow_delete | [optional bool](#bool) | When overriding assignments, we may run into a case where a previous assignment would be completely replaced. Since this is questionable, doing so required an additional opt-in with this flag. |

### Assign.Request.AlarmParametersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ google.protobuf.Struct](#googleprotobufstruct) |  |

### Assign.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| assigned | [repeated Assignment](#assignment) |  |
| request | [ Assign.Request](#assignrequest) |  |

### Assignment

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
| type | [ AssignmentType](#assignmenttype) | The type of assignment. This is a helper enum to indicate which fields are set. |
| start | [ hiber.Timestamp](#hibertimestamp) | Time this assignment started. This is always in the past. |
|  **optional** end | [optional hiber.Timestamp](#hibertimestamp) | Time this assignment ended, if it has ended. Inactive assignments that no longer have an effect may be cleaned up automatically. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign**.assign_parser | [ Assignment.ModemMessageBodyParserAssignment](#assignmentmodemmessagebodyparserassignment) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign**.assign_alarm | [ Assignment.AlarmAssignment](#assignmentalarmassignment) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign**.assign_modem | [ string](#string) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign**.assign_asset | [ string](#string) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **to**.to_modem | [ string](#string) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **to**.to_parser | [ Assignment.ModemMessageBodyParserAssignment](#assignmentmodemmessagebodyparserassignment) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **to**.to_tag | [ hiber.tag.Tag](#hibertagtag) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **to**.to_asset | [ string](#string) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **additional_configuration**.asset_device | [ Assignment.AdditionalConfiguration.AssetDeviceAssignment](#assignmentadditionalconfigurationassetdeviceassignment) | Additional configuration for assignment between Asset and Device/Modem. |

### Assignment.AdditionalConfiguration




### Assignment.AdditionalConfiguration.AssetDeviceAssignment



| Field | Type | Description |
| ----- | ---- | ----------- |
| shared_fields | [ Assignment.AdditionalConfiguration.FieldsByJsonPath](#assignmentadditionalconfigurationfieldsbyjsonpath) | Specify the fields that are shared with the Asset. If nothing is specified, all fields are shared with the asset by default. |

### Assignment.AdditionalConfiguration.FieldsByJsonPath

Select the fields, defined as a list of json paths.
Fields are produced by the device's assigned parsers. See field.proto for more information.

| Field | Type | Description |
| ----- | ---- | ----------- |
| fields | [repeated string](#string) | List of json paths specifying fields. See field.proto for more information. |

### Assignment.AlarmAssignment



| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) |  |
| name | [ string](#string) |  |
| description | [ string](#string) |  |
| parameters | [ google.protobuf.Struct](#googleprotobufstruct) | <strong>Deprecated.</strong>  |

### Assignment.ModemMessageBodyParserAssignment



| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) |  |
| name | [ string](#string) |  |
| owner_organization | [ string](#string) |  |

### AssignmentSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** assets | [optional hiber.asset.AssetSelection](#hiberassetassetselection) | Select the assets to return the assignments for. Optional, when omitted or empty everything is included. |
|  **optional** modems | [optional hiber.modem.ModemSelection](#hibermodemmodemselection) | Select the modems to return the assignments for. Optional, when omitted or empty everything is included. |
|  **optional** modem_alarms | [optional hiber.modem.alarm.ModemAlarmSelection](#hibermodemalarmmodemalarmselection) | Select the alarms to return the assignments for. Optional, when omitted or empty everything is included. |
|  **optional** modem_message_body_parsers | [optional hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) | Select the message body parsers to return the assignments for. Optional, when omitted or empty everything is included. |
|  **optional** tags | [optional hiber.tag.TagSelection](#hibertagtagselection) | Select the tags to return the assignments for. Optional, when omitted or empty everything is included. |
|  **optional** types | [optional AssignmentSelection.AssignmentTypes](#assignmentselectionassignmenttypes) | Select by type of assignment. |

### AssignmentSelection.AssignmentTypes



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated AssignmentType](#assignmenttype) |  |
| exclude | [repeated AssignmentType](#assignmenttype) |  |

### DeleteAssignment




### DeleteAssignment.Request



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

### DeleteAssignment.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| deleted | [repeated Assignment](#assignment) |  |
| request | [ DeleteAssignment.Request](#deleteassignmentrequest) |  |

### ListAlarmAssignments




### ListAlarmAssignments.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional AssignmentSelection](#assignmentselection) | Select the assignments to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |
|  **optional** include_child_organizations | [optional hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | Whether to include modems from child organizations in this list (and which organizations). |
|  **optional** include_alarms_without_assignments | [optional bool](#bool) | Whether to include alarms that are in the selection and have no assignments. |
|  **optional** apply_unit_preferences | [optional bool](#bool) | Apply your UnitPreferences to the alarm checks. For example, if a temperature check is configured in kelvin, but your unit preferences specify celsius for temperature, the check value will be converted to celsius instead. |

### ListAlarmAssignments.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| alarms | [repeated ListAlarmAssignments.Response.AlarmAssignment](#listalarmassignmentsresponsealarmassignment) |  |
| request | [ ListAlarmAssignments.Request](#listalarmassignmentsrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### ListAlarmAssignments.Response.AlarmAssignment

Things that an alarm is assigned to.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| alarm | [ hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) |  |
| modems | [repeated ListAlarmAssignments.Response.AlarmAssignment.ToModem](#listalarmassignmentsresponsealarmassignmenttomodem) | The modem numbers this alarm is assigned to, with the alarm parameters. |
| tags | [repeated ListAlarmAssignments.Response.AlarmAssignment.ToTag](#listalarmassignmentsresponsealarmassignmenttotag) | The tags this alarm is assigned to, with the alarm parameters. |
| assets | [repeated ListAlarmAssignments.Response.AlarmAssignment.ToAsset](#listalarmassignmentsresponsealarmassignmenttoasset) | The assets this alarm is assigned to, with the alarm parameters. |

### ListAlarmAssignments.Response.AlarmAssignment.ToAsset



| Field | Type | Description |
| ----- | ---- | ----------- |
| asset_identifier | [ string](#string) |  |
| parameters | [ google.protobuf.Struct](#googleprotobufstruct) | <strong>Deprecated.</strong>  |

### ListAlarmAssignments.Response.AlarmAssignment.ToModem



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem_number | [ string](#string) |  |
| parameters | [ google.protobuf.Struct](#googleprotobufstruct) | <strong>Deprecated.</strong>  |

### ListAlarmAssignments.Response.AlarmAssignment.ToTag



| Field | Type | Description |
| ----- | ---- | ----------- |
| tag | [ hiber.tag.Tag](#hibertagtag) |  |
| parameters | [ google.protobuf.Struct](#googleprotobufstruct) | <strong>Deprecated.</strong>  |

### ListAssetAssignments




### ListAssetAssignments.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional AssignmentSelection](#assignmentselection) | Select the assignments to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |
|  **optional** include_assets_without_assignments | [optional bool](#bool) | Whether to include assets that are in the selection and have no assignments. |
|  **optional** include_alarm_details | [optional bool](#bool) | Whether to include the full alarms that are assigned, instead of just assignment. |
|  **optional** apply_unit_preferences | [optional bool](#bool) | Apply your UnitPreferences to the alarm checks. For example, if a temperature check is configured in kelvin, but your unit preferences specify celsius for temperature, the check value will be converted to celsius instead. |

### ListAssetAssignments.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| assets | [repeated ListAssetAssignments.Response.AssetAssignment](#listassetassignmentsresponseassetassignment) |  |
| request | [ ListAssetAssignments.Request](#listassetassignmentsrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### ListAssetAssignments.Response.AssetAssignment

Things that an alarm is assigned to.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| asset_identifier | [ string](#string) |  |
| devices | [repeated string](#string) | The devices assigned to this asset. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | The tags for this asset. |
| alarms | [repeated Assignment.AlarmAssignment](#assignmentalarmassignment) | The identifiers and parameters of the alarms that are assigned to this asset. |
| alarm_details | [repeated hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) | The alarms that are assigned to this asset, if you have permission to view them. |

### ListAssignments




### ListAssignments.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional AssignmentSelection](#assignmentselection) | Select the assignments to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |
|  **optional** include_inactive_assignments | [optional bool](#bool) | Include assignments that are no longer active. |

### ListAssignments.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| assignments | [repeated Assignment](#assignment) | The assignments as identifiers in the selection. |
| request | [ ListAssignments.Request](#listassignmentsrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### ListModemAssignments




### ListModemAssignments.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional AssignmentSelection](#assignmentselection) | Select the assignments to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |
|  **optional** include_alarm_details | [optional bool](#bool) | Whether to include the full alarms that are assigned, instead of just assignment. |
|  **optional** include_message_body_parser_details | [optional bool](#bool) | Whether to include the full parsers that are assigned, instead of just assignment. |
|  **optional** include_message_body_parser_content | [optional bool](#bool) | Whether to include, for example, the message body parser ksy content in the result. Excluded by default to save data. |
|  **optional** include_modems_without_assignments | [optional bool](#bool) | Whether to include modems that are in the selection and have no assignments. |
|  **optional** apply_unit_preferences | [optional bool](#bool) | Apply your UnitPreferences to the alarm checks. For example, if a temperature check is configured in kelvin, but your unit preferences specify celsius for temperature, the check value will be converted to celsius instead. |

### ListModemAssignments.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [repeated ListModemAssignments.Response.ModemAssignment](#listmodemassignmentsresponsemodemassignment) |  |
| request | [ ListModemAssignments.Request](#listmodemassignmentsrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### ListModemAssignments.Response.ModemAssignment

Things that are assigned to a modem.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| modem_number | [ string](#string) |  |
| message_body_parsers | [repeated Assignment.ModemMessageBodyParserAssignment](#assignmentmodemmessagebodyparserassignment) | The identifiers of the message body parsers that are assigned to this modem. |
| alarms | [repeated Assignment.AlarmAssignment](#assignmentalarmassignment) | The identifiers and parameters of the alarms that are assigned to this modem. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | The tags for this modem. |
| message_body_parser_details | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser) | The details of the parsers assigned to this modem. |
| alarm_details | [repeated hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) | The alarms that are assigned to this modem, if you have permission to view them. |
| asset_identifiers | [repeated string](#string) | The assets assigned to this device. |

### ListModemMessageBodyParserAssignments




### ListModemMessageBodyParserAssignments.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional AssignmentSelection](#assignmentselection) | Select the assignments to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |
|  **optional** include_child_organizations | [optional hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | Whether to include modems from child organizations in this list (and which organizations). |
|  **optional** include_parser_without_assignments | [optional bool](#bool) | Whether to include alarms that are in the selection and have no assignments. |

### ListModemMessageBodyParserAssignments.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| parsers | [repeated ListModemMessageBodyParserAssignments.Response.ModemMessageBodyParserAssignment](#listmodemmessagebodyparserassignmentsresponsemodemmessagebodyparserassignment) |  |
| request | [ ListModemMessageBodyParserAssignments.Request](#listmodemmessagebodyparserassignmentsrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### ListModemMessageBodyParserAssignments.Response.ModemMessageBodyParserAssignment

Things that an alarm is assigned to.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| message_body_parser | [ hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser) |  |
| modems | [repeated string](#string) | The modem numbers this parser is assigned to. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | The tags this parser is assigned to. |

### ListTagAssignments




### ListTagAssignments.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional AssignmentSelection](#assignmentselection) | Select the assignments to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |
|  **optional** include_alarm_details | [optional bool](#bool) | Whether to include the full alarms that are assigned, instead of just assignment. |
|  **optional** include_message_body_parser_details | [optional bool](#bool) | Whether to include the full parsers that are assigned, instead of just assignment. |
|  **optional** include_message_body_parser_content | [optional bool](#bool) | Whether to include, for example, the message body parser ksy content in the result. Excluded by default to save data. |
|  **optional** include_tags_without_assignments | [optional bool](#bool) | Whether to include alarms that are in the selection and have no assignments. |
|  **optional** apply_unit_preferences | [optional bool](#bool) | Apply your UnitPreferences to the alarm checks. For example, if a temperature check is configured in kelvin, but your unit preferences specify celsius for temperature, the check value will be converted to celsius instead. |

### ListTagAssignments.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| tags | [repeated ListTagAssignments.Response.TagAssignment](#listtagassignmentsresponsetagassignment) |  |
| request | [ ListTagAssignments.Request](#listtagassignmentsrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### ListTagAssignments.Response.TagAssignment

Things that an alarm is assigned to.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| tag | [ hiber.tag.Tag](#hibertagtag) |  |
| modems | [repeated string](#string) | The modems with this tag. |
| message_body_parsers | [repeated Assignment.ModemMessageBodyParserAssignment](#assignmentmodemmessagebodyparserassignment) | The identifiers of the message body parsers that are assigned to this tag. |
| alarms | [repeated Assignment.AlarmAssignment](#assignmentalarmassignment) | The identifiers and parameters of the alarms that are assigned to this tag. |
| message_body_parser_details | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser) | The details of the parsers assigned to this tag. |
| alarm_details | [repeated hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) | The alarms that are assigned to this tag, if you have permission to view them. |
| asset_identifiers | [repeated string](#string) | The assets assigned to this tag. |

### Unassign

Remove a assignment.


### Unassign.Request



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
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **time**.override_time | [ hiber.Timestamp](#hibertimestamp) | Time that the assignment ended. This marks the assignment as ended at the given moment in the past, but would not have effect in the past for assignments like parsers and alarms (e.g. no alarm events are removed). It would however work for assets having access to device data. This is not allowed to be a value in the future at the moment. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **time**.remove_time | [ bool](#bool) | Remove time from the assignment, if any. Effectively deletes the assignment if it was set with a time. Setting this to true makes this identical to using the Delete rpc. |

### Unassign.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| unassigned | [repeated Assignment](#assignment) |  |
| request | [ Unassign.Request](#unassignrequest) |  |


## Enums
### AssignmentType
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
different type of data (e.g. one sensor for pressure and one for flow).

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
| location | [ hiber.Location](#hiberlocation) | Location for the asset. |
| files | [repeated hiber.file.File](#hiberfilefile) | Files for this asset. Typically an image of a place. See the File.media_type for more information. |

### hiber.asset.Asset.AssignedDevice

A device assigned to this asset.
Non-operational values that the device produces will be linked to this asset
(e.g. pressure, but not battery level).

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
| files | [repeated hiber.file.File](#hiberfilefile) | Files for this tag. Typically an image of the device installation. See the File.media_type for more information. |

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
| HEALTH | Health sorted from least to most severe (e.g. OK, WARNING, ERROR). | 10 |
| HEALTH_DESC | Health sorted from most to least severe (e.g. ERROR, WARNING, OK). | 11 |
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

A check is a specification of how things should be, e.g. "a value should be within this range".
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
If the minimum is higher than the maximum (e.g. 30..10), this is automatically converted into a
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
If the minimum is higher than the maximum (e.g. 30..10), this is automatically converted into a
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
| organization_display_name | [ string](#string) | The display name of the organization that created the parser. |
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
| terminator | [ bytes](#bytes) | Specify a terminator that marks the point the field terminates, optionally, and we should continue to the next field. This is typically a single byte (e.g. 0x00). This can be combined with a size to limit the amounts of bytes that are parsed. |

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
| replace_data_fields | [repeated hiber.field.Field](#hiberfieldfield) | Replace fields to the data fields list. |
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



## Referenced messages from tag.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [tag.proto](https://github.com/HiberGlobal/api/blob/master/tag.proto).


### hiber.tag.Tag

Tag in your organization.
Tags can be assigned to devices and assets to group them together or mark a certain property.

A Tag has three parts: its id in your organization, a Label that describes how it should be displayed, and
Metadata (which is only included when using the TagService) with additional information.

| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int64](#int64) |  |
| label | [ hiber.tag.Tag.Label](#hibertagtaglabel) | The label to display for this tag. |
|  **optional** metadata | [optional hiber.tag.Tag.Metadata](#hibertagtagmetadata) | Metadata for this tag. This is typically not included in calls where the tag is repeated a lot, like the device list. Use the TagService.List call to get the tags with Metadata. |

### hiber.tag.Tag.Label

Label for a tag, containing all the information needed to display it.

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
|  **optional** location | [optional hiber.LocationSelection](#hiberlocationselection) |  |


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

