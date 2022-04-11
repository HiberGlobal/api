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
  - [Assignment.ModemAlarmAssignment](#assignmentmodemalarmassignment)
  - [Assignment.ModemMessageBodyParserAssignment](#assignmentmodemmessagebodyparserassignment)
  - [AssignmentSelection](#assignmentselection)
  - [AssignmentSelection.AssignmentTypes](#assignmentselectionassignmenttypes)
  - [ListAlarmAssignments](#listalarmassignments)
  - [ListAlarmAssignments.Request](#listalarmassignmentsrequest)
  - [ListAlarmAssignments.Response](#listalarmassignmentsresponse)
  - [ListAlarmAssignments.Response.AlarmAssignment](#listalarmassignmentsresponsealarmassignment)
  - [ListAlarmAssignments.Response.AlarmAssignment.ToModem](#listalarmassignmentsresponsealarmassignmenttomodem)
  - [ListAlarmAssignments.Response.AlarmAssignment.ToTag](#listalarmassignmentsresponsealarmassignmenttotag)
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

    - [hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Endian](#hibermodemmessagebodyparsersimplemodemmessagebodyparserendian)

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
  - [hiber.modem.alarm.ModemAlarm.Check.FieldCheck.DeltaCheck](#hibermodemalarmmodemalarmcheckfieldcheckdeltacheck)
  - [hiber.modem.alarm.ModemAlarm.Check.FieldCheck.EqualsCheck](#hibermodemalarmmodemalarmcheckfieldcheckequalscheck)
  - [hiber.modem.alarm.ModemAlarm.Check.FieldCheck.MaximumCheck](#hibermodemalarmmodemalarmcheckfieldcheckmaximumcheck)
  - [hiber.modem.alarm.ModemAlarm.Check.FieldCheck.MinimumCheck](#hibermodemalarmmodemalarmcheckfieldcheckminimumcheck)
  - [hiber.modem.alarm.ModemAlarm.Check.FieldCheck.OneOfCheck](#hibermodemalarmmodemalarmcheckfieldcheckoneofcheck)
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

Remove an assignment, like an alarm to a modem.

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
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign**.assign_parsers | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign**.assign_alarms | [ hiber.modem.alarm.ModemAlarmSelection](#hibermodemalarmmodemalarmselection) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign**.assign_modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **to**.to_modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **to**.to_tags | [ hiber.tag.TagSelection](#hibertagtagselection) | none |
| alarm_parameters | [map Assign.Request.AlarmParametersEntry](#assignrequestalarmparametersentry) | The alarm parameters, by alarm identifier, if any, overriding any default values in the alarm(s). |

### Assign.Request.AlarmParametersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ google.protobuf.Struct](#googleprotobufstruct) | none |

### Assign.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| assigned | [repeated Assignment](#assignment) | none |
| request | [ Assign.Request](#assignrequest) | none |

### Assignment

An assignment assigning one thing to another.

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ AssignmentType](#assignmenttype) | The type of assignment. This is a helper enum to indicate which fields are set. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign**.assign_parser | [ Assignment.ModemMessageBodyParserAssignment](#assignmentmodemmessagebodyparserassignment) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign**.assign_alarm | [ Assignment.ModemAlarmAssignment](#assignmentmodemalarmassignment) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign**.assign_modem | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **to**.to_modem | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **to**.to_parser | [ Assignment.ModemMessageBodyParserAssignment](#assignmentmodemmessagebodyparserassignment) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **to**.to_tag | [ hiber.tag.Tag](#hibertagtag) | none |

### Assignment.ModemAlarmAssignment



| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) | none |
| name | [ string](#string) | none |
| description | [ string](#string) | none |
| parameters | [ google.protobuf.Struct](#googleprotobufstruct) | none |
| owner_organization | [ string](#string) | none |

### Assignment.ModemMessageBodyParserAssignment



| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) | none |
| name | [ string](#string) | none |
| owner_organization | [ string](#string) | none |

### AssignmentSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | Select the modems to return the assignments for. |
| modem_alarms | [ hiber.modem.alarm.ModemAlarmSelection](#hibermodemalarmmodemalarmselection) | Select the alarms to return the assignments for. |
| modem_message_body_parsers | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) | Select the message body parsers to return the assignments for. |
| tags | [ hiber.tag.TagSelection](#hibertagtagselection) | Select the tags to return the assignments for. |
| types | [ AssignmentSelection.AssignmentTypes](#assignmentselectionassignmenttypes) | Select by type of assignment. |

### AssignmentSelection.AssignmentTypes



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated AssignmentType](#assignmenttype) | none |
| exclude | [repeated AssignmentType](#assignmenttype) | none |

### ListAlarmAssignments




### ListAlarmAssignments.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ AssignmentSelection](#assignmentselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |
| include_child_organizations | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | Whether to include alarms and modems from child organizations in this list (and which organizations). |
| include_alarms_without_assignments | [ bool](#bool) | Whether to include alarms that are in the selection and have no assignments. |
| apply_unit_preferences | [ bool](#bool) | Apply your UnitPreferences to the alarm checks. For example, if a temperature check is configured in kelvin, but your unit preferences specify celsius for temperature, the check value will be converted to celsius instead. |

### ListAlarmAssignments.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| alarms | [repeated ListAlarmAssignments.Response.AlarmAssignment](#listalarmassignmentsresponsealarmassignment) | none |
| request | [ ListAlarmAssignments.Request](#listalarmassignmentsrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### ListAlarmAssignments.Response.AlarmAssignment

Things that an alarm is assigned to.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| alarm | [ hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) | none |
| modems | [repeated ListAlarmAssignments.Response.AlarmAssignment.ToModem](#listalarmassignmentsresponsealarmassignmenttomodem) | The modem numbers this alarm is assigned to, with the alarm parameters. |
| tags | [repeated ListAlarmAssignments.Response.AlarmAssignment.ToTag](#listalarmassignmentsresponsealarmassignmenttotag) | The tags this alarm is assigned to, with the alarm parameters. |

### ListAlarmAssignments.Response.AlarmAssignment.ToModem



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem_number | [ string](#string) | none |
| parameters | [ google.protobuf.Struct](#googleprotobufstruct) | none |

### ListAlarmAssignments.Response.AlarmAssignment.ToTag



| Field | Type | Description |
| ----- | ---- | ----------- |
| tag | [ hiber.tag.Tag](#hibertagtag) | none |
| parameters | [ google.protobuf.Struct](#googleprotobufstruct) | none |

### ListAssignments




### ListAssignments.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ AssignmentSelection](#assignmentselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |

### ListAssignments.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| assignments | [repeated Assignment](#assignment) | The assignments as identifiers in the selection. |
| request | [ ListAssignments.Request](#listassignmentsrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### ListModemAssignments




### ListModemAssignments.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ AssignmentSelection](#assignmentselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |
| include_alarm_details | [ bool](#bool) | Whether to include the full alarms that are assigned, instead of just assignment. |
| include_message_body_parser_details | [ bool](#bool) | Whether to include the full parsers that are assigned, instead of just assignment. |
| include_message_body_parser_content | [ bool](#bool) | Whether to include, for example, the message body parser ksy content in the result. Excluded by default to save data. |
| include_modems_in_child_organizations | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | Whether to include modems from child organizations in this list (and which organizations). |
| include_modems_without_assignments | [ bool](#bool) | Whether to include modems that are in the selection and have no assignments. |
| apply_unit_preferences | [ bool](#bool) | Apply your UnitPreferences to the alarm checks. For example, if a temperature check is configured in kelvin, but your unit preferences specify celsius for temperature, the check value will be converted to celsius instead. |

### ListModemAssignments.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [repeated ListModemAssignments.Response.ModemAssignment](#listmodemassignmentsresponsemodemassignment) | none |
| request | [ ListModemAssignments.Request](#listmodemassignmentsrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### ListModemAssignments.Response.ModemAssignment

Things that are assigned to a modem.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| modem_number | [ string](#string) | none |
| message_body_parsers | [repeated Assignment.ModemMessageBodyParserAssignment](#assignmentmodemmessagebodyparserassignment) | The identifiers of the message body parsers that are assigned to this modem. |
| alarms | [repeated Assignment.ModemAlarmAssignment](#assignmentmodemalarmassignment) | The identifiers and parameters of the alarms that are assigned to this modem. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | The tags for this modem. |
| message_body_parser_details | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser) | The details of the parsers assigned to this modem. |
| alarm_details | [repeated hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) | The alarms that are assigned to this modem, if you have permission to view them. |

### ListModemMessageBodyParserAssignments




### ListModemMessageBodyParserAssignments.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ AssignmentSelection](#assignmentselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |
| include_child_organizations | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | Whether to include alarms and modems from child organizations in this list (and which organizations). |
| include_parser_without_assignments | [ bool](#bool) | Whether to include alarms that are in the selection and have no assignments. |

### ListModemMessageBodyParserAssignments.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| parsers | [repeated ListModemMessageBodyParserAssignments.Response.ModemMessageBodyParserAssignment](#listmodemmessagebodyparserassignmentsresponsemodemmessagebodyparserassignment) | none |
| request | [ ListModemMessageBodyParserAssignments.Request](#listmodemmessagebodyparserassignmentsrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### ListModemMessageBodyParserAssignments.Response.ModemMessageBodyParserAssignment

Things that an alarm is assigned to.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| message_body_parser | [ hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser) | none |
| modems | [repeated string](#string) | The modem numbers this alarm is assigned to, with the alarm parameters. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | The tags this alarm is assigned to, with the alarm parameters. |

### ListTagAssignments




### ListTagAssignments.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ AssignmentSelection](#assignmentselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |
| include_alarm_details | [ bool](#bool) | Whether to include the full alarms that are assigned, instead of just assignment. |
| include_message_body_parser_details | [ bool](#bool) | Whether to include the full parsers that are assigned, instead of just assignment. |
| include_message_body_parser_content | [ bool](#bool) | Whether to include, for example, the message body parser ksy content in the result. Excluded by default to save data. |
| include_child_organizations | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | Whether to include alarms and modems from child organizations in this list (and which organizations). |
| include_tags_without_assignments | [ bool](#bool) | Whether to include alarms that are in the selection and have no assignments. |
| apply_unit_preferences | [ bool](#bool) | Apply your UnitPreferences to the alarm checks. For example, if a temperature check is configured in kelvin, but your unit preferences specify celsius for temperature, the check value will be converted to celsius instead. |

### ListTagAssignments.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| tags | [repeated ListTagAssignments.Response.TagAssignment](#listtagassignmentsresponsetagassignment) | none |
| request | [ ListTagAssignments.Request](#listtagassignmentsrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### ListTagAssignments.Response.TagAssignment

Things that an alarm is assigned to.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| tag | [ hiber.tag.Tag](#hibertagtag) | none |
| modems | [repeated string](#string) | The modems with this tag. |
| message_body_parsers | [repeated Assignment.ModemMessageBodyParserAssignment](#assignmentmodemmessagebodyparserassignment) | The identifiers of the message body parsers that are assigned to this modem. |
| alarms | [repeated Assignment.ModemAlarmAssignment](#assignmentmodemalarmassignment) | The identifiers and parameters of the alarms that are assigned to this modem. |
| message_body_parser_details | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser) | The details of the parsers assigned to this modem. |
| alarm_details | [repeated hiber.modem.alarm.ModemAlarm](#hibermodemalarmmodemalarm) | The alarms that are assigned to this modem, if you have permission to view them. |

### Unassign

Remove a assignment.


### Unassign.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unassign**.unassign_parsers | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unassign**.unassign_alarms | [ hiber.modem.alarm.ModemAlarmSelection](#hibermodemalarmmodemalarmselection) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unassign**.unassign_modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **from**.from_modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **from**.from_tags | [ hiber.tag.TagSelection](#hibertagtagselection) | none |

### Unassign.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| unassigned | [repeated Assignment](#assignment) | none |
| request | [ Unassign.Request](#unassignrequest) | none |


## Enums
### AssignmentType
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
| data_fields | [repeated hiber.value.Field](#hibervaluefield) | Fields in the parsed result that contain data. Data fields are cached for efficient retrieval and allow all kinds of processing. |
| data_fields_deprecated | [repeated string](#string) | none |
| metadata_fields | [ hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafields) | Fields in the parsed result that contain metadata, and special things like a location. |
| available_to_child_organizations | [ hiber.modem.message.bodyparser.ModemMessageBodyParser.AvailableToChildOrganizations](#hibermodemmessagebodyparsermodemmessagebodyparseravailabletochildorganizations) | If set, this parser is available to your child organizations, as a Provided parser. |

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
| metadata_fields | [repeated string](#string) | Other metadata fields, which will be added to the metadata json for easy processing. |
| location_fields | [ hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields.LocationFields](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafieldslocationfields) | Specify a pair of fields in the message body that contain location data, which will update the modem location and the map. |

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
| add_data_fields | [repeated hiber.value.Field](#hibervaluefield) | Add fields to the data fields list. |
| remove_data_fields | [repeated string](#string) | Remove fields from the data fields list. |
| metadata_fields | [ hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields](#hibermodemmessagebodyparserupdateuploadedmodemmessagebodyparserrequestmetadatafields) | Fields in the parsed result that match special things that can be processed by the system, like a location. |

### hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields



| Field | Type | Description |
| ----- | ---- | ----------- |
| add_metadata_fields | [repeated string](#string) | Add metadata fields to the metadata fields list. |
| remove_metadata_fields | [repeated string](#string) | Remove metadata fields from the metadata fields list. |
| update_location_fields | [ hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields.LocationFields](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafieldslocationfields) | Update the location fields. |

### hiber.modem.message.bodyparser.UploadModemMessageBodyParserRequest

Upload a new body parser from a .ksy file.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| name | [ string](#string) | A descriptive name for this parser. |
| content_ksy | [ string](#string) | The ksy definition for this parser. |
| data_fields | [repeated hiber.value.Field](#hibervaluefield) | Fields in the parsed result that contain data. This can be useful to track which fields could be plotted, etc. |
| metadata_fields | [ hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafields) | Fields in the parsed result that match special things that can be processed by the system, like a location. |


### Enums
#### hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Endian


| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | none | 0 |
| LITTLE_ENDIAN | none | 1 |
| BIG_ENDIAN | none | 2 |



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
| maximum_inactivity_period | [ int32](#int32) | Period in days, if modem inactivity exceeds this period, alerts will be triggered and health will go to error. Deprecated in favor of using an alarm. |
| maximum_inactivity | [ hiber.Duration](#hiberduration) | If modem inactivity exceeds this period, alerts will be triggered and health will go to error. Deprecated in favor of using an alarm. |
| health | [ hiber.Health](#hiberhealth) | Deprecated health based on the number of error and warning events this modem has received in the past 30 days Uses the OK, WARNING, ERROR format. |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | Health level based on the modem alarm and some always-present alarms. |
| health_config | [ hiber.modem.Modem.HealthConfig](#hibermodemmodemhealthconfig) | Health configuration for unresolvable built-in modem alarms, like delayed or skipped messages. |
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

Simple examples selecting a field:
- $.my_field: a field in the root of the parsed object
- $.my_obj.my_field: a field in a deeper structure
- $.my_array[x].my_field: the field my_field of the element at index x is selected

Complex use cases are also possible, but they require a bit more understanding of json path logic:
- $.my_array.length(): the length of my_array is selected. Combine with an equals or threshold check,
to require that an array has a certain length.
- $.my_array[?(@.name == 'D')]: the array of all objects in my_array where name equals 'D' is selected.
- $.my_array[?(@.name == 'D')]..my_field: the array of my_field values from all objects in
my_array where name equals 'D' is selected.
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
| unit | [ hiber.value.Field.Numeric.Unit](#hibervaluefieldnumericunit) | The unit that this alarm check is using. The field's values will automatically be converted into this unit before the check is applied.

Note: unit is not currently available in the alarm_parameters. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.equals | [ hiber.modem.alarm.ModemAlarm.Check.FieldCheck.EqualsCheck](#hibermodemalarmmodemalarmcheckfieldcheckequalscheck) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.oneof | [ hiber.modem.alarm.ModemAlarm.Check.FieldCheck.OneOfCheck](#hibermodemalarmmodemalarmcheckfieldcheckoneofcheck) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.minimum | [ hiber.modem.alarm.ModemAlarm.Check.FieldCheck.MinimumCheck](#hibermodemalarmmodemalarmcheckfieldcheckminimumcheck) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.maximum | [ hiber.modem.alarm.ModemAlarm.Check.FieldCheck.MaximumCheck](#hibermodemalarmmodemalarmcheckfieldcheckmaximumcheck) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.threshold | [ hiber.modem.alarm.ModemAlarm.Check.FieldCheck.ThresholdCheck](#hibermodemalarmmodemalarmcheckfieldcheckthresholdcheck) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.delta | [ hiber.modem.alarm.ModemAlarm.Check.FieldCheck.DeltaCheck](#hibermodemalarmmodemalarmcheckfieldcheckdeltacheck) | none |

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

### hiber.modem.alarm.ModemAlarm.Check.FieldCheck.OneOfCheck

Check that the field is in a set of expected values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| expected | [repeated google.protobuf.Value](#googleprotobufvalue) | The list of allowed values, one of which should match the field value. |

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

| Field | Type | Description |
| ----- | ---- | ----------- |
| timestamp | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | none |
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
| MODEM_STALE | none | 16 |
| MODEM_MESSAGE_RECEIVED | none | 5 |
| MODEM_MESSAGE_BODY_PARSED | none | 39 |
| MODEM_MESSAGE_BODY_RECEIVED | none | 45 |
| MODEM_MESSAGE_DELAYED | none | 14 |
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
| MASS_KILOGRAMS | none | 37 |
| MASS_POUNDS | none | 38 |
| FLOW_CUBIC_METERS_PER_HOUR | none | 39 |

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
