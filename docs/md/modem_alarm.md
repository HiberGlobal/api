# modem_alarm.proto

Service to specify alarm for a modem, monitoring message data, location or activity.

An alarm is a collection of checks that validate the correctness of a modem. For example, an alarm might
check that the modem is in a given location, or that a field in its messages is between certain values.

Alarms are created in isolation, and need to be assigned to a modem before they do anything.
This can be done using the Assign and Unassign methods in the service, or using the AssignmentService for more
advanced use cases, like assigning to a tag.

#### This file was generated from [modem_alarm.proto](https://github.com/HiberGlobal/api/blob/master/modem_alarm.proto).

## Table of Contents

- Services
  - [ModemAlarmService](#modemalarmservice)

- Messages
  - [AssignModemAlarms](#assignmodemalarms)
  - [AssignModemAlarms.Request](#assignmodemalarmsrequest)
  - [AssignModemAlarms.Request.ParametersEntry](#assignmodemalarmsrequestparametersentry)
  - [AssignModemAlarms.Response](#assignmodemalarmsresponse)
  - [AssignedModemAlarm](#assignedmodemalarm)
  - [CreateModemAlarm](#createmodemalarm)
  - [CreateModemAlarm.Request](#createmodemalarmrequest)
  - [CreateModemAlarm.Response](#createmodemalarmresponse)
  - [DeleteModemAlarm](#deletemodemalarm)
  - [DeleteModemAlarm.Request](#deletemodemalarmrequest)
  - [DeleteModemAlarm.Response](#deletemodemalarmresponse)
  - [ListModemAlarms](#listmodemalarms)
  - [ListModemAlarms.Request](#listmodemalarmsrequest)
  - [ListModemAlarms.Response](#listmodemalarmsresponse)
  - [ModemAlarm](#modemalarm)
  - [ModemAlarm.Check](#modemalarmcheck)
  - [ModemAlarm.Check.DelayCheck](#modemalarmcheckdelaycheck)
  - [ModemAlarm.Check.FieldCheck](#modemalarmcheckfieldcheck)
  - [ModemAlarm.Check.FieldCheck.AllowedCheck](#modemalarmcheckfieldcheckallowedcheck)
  - [ModemAlarm.Check.FieldCheck.BlockedCheck](#modemalarmcheckfieldcheckblockedcheck)
  - [ModemAlarm.Check.FieldCheck.BlockedRangeCheck](#modemalarmcheckfieldcheckblockedrangecheck)
  - [ModemAlarm.Check.FieldCheck.DeltaCheck](#modemalarmcheckfieldcheckdeltacheck)
  - [ModemAlarm.Check.FieldCheck.EqualsCheck](#modemalarmcheckfieldcheckequalscheck)
  - [ModemAlarm.Check.FieldCheck.MaximumCheck](#modemalarmcheckfieldcheckmaximumcheck)
  - [ModemAlarm.Check.FieldCheck.MinimumCheck](#modemalarmcheckfieldcheckminimumcheck)
  - [ModemAlarm.Check.FieldCheck.ThresholdCheck](#modemalarmcheckfieldcheckthresholdcheck)
  - [ModemAlarm.Check.InactivityCheck](#modemalarmcheckinactivitycheck)
  - [ModemAlarm.Check.LocationCheck](#modemalarmchecklocationcheck)
  - [ModemAlarm.HealthLevelAfterResolved](#modemalarmhealthlevelafterresolved)
  - [ModemAlarmSelection](#modemalarmselection)
  - [TestModemAlarmTestParameters](#testmodemalarmtestparameters)
  - [TestModemAlarmTestParameters.Request](#testmodemalarmtestparametersrequest)
  - [TestModemAlarmTestParameters.Response](#testmodemalarmtestparametersresponse)
  - [UnassignModemAlarms](#unassignmodemalarms)
  - [UnassignModemAlarms.Request](#unassignmodemalarmsrequest)
  - [UnassignModemAlarms.Response](#unassignmodemalarmsresponse)
  - [UpdateModemAlarm](#updatemodemalarm)
  - [UpdateModemAlarm.Request](#updatemodemalarmrequest)
  - [UpdateModemAlarm.Request.UpdateChecksEntry](#updatemodemalarmrequestupdatechecksentry)
  - [UpdateModemAlarm.Response](#updatemodemalarmresponse)
  - [UpdateModemAlarmAddCheck](#updatemodemalarmaddcheck)
  - [UpdateModemAlarmAddCheck.Request](#updatemodemalarmaddcheckrequest)
  - [UpdateModemAlarmAddCheck.Response](#updatemodemalarmaddcheckresponse)
  - [UpdateModemAlarmRemoveCheck](#updatemodemalarmremovecheck)
  - [UpdateModemAlarmRemoveCheck.Request](#updatemodemalarmremovecheckrequest)
  - [UpdateModemAlarmRemoveCheck.Response](#updatemodemalarmremovecheckresponse)
  - [UpdateModemAlarmUpdateCheck](#updatemodemalarmupdatecheck)
  - [UpdateModemAlarmUpdateCheck.Request](#updatemodemalarmupdatecheckrequest)
  - [UpdateModemAlarmUpdateCheck.Response](#updatemodemalarmupdatecheckresponse)

- Enums
  - [ModemAlarm.TriggerCondition](#modemalarmtriggercondition)

- Referenced messages from [asset.proto](#referenced-messages-from-assetproto)
  - [hiber.asset.Asset](#hiberassetasset)
  - [hiber.asset.Asset.AssignedDevice](#hiberassetassetassigneddevice)
  - [hiber.asset.AssetSelection](#hiberassetassetselection)

    - [hiber.asset.Asset.Type](#hiberassetassettype)

- Referenced messages from [field.proto](#referenced-messages-from-fieldproto)
  - [hiber.field.Field](#hiberfieldfield)
  - [hiber.field.Field.Enum](#hiberfieldfieldenum)
  - [hiber.field.Field.Numeric](#hiberfieldfieldnumeric)
  - [hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat)
  - [hiber.field.Field.Numeric.Unit](#hiberfieldfieldnumericunit)

    - [hiber.field.Field.Numeric.Format.RoundingMode](#hiberfieldfieldnumericformatroundingmode)

- Referenced messages from [modem.proto](#referenced-messages-from-modemproto)
  - [hiber.modem.Modem](#hibermodemmodem)
  - [hiber.modem.ModemSelection](#hibermodemmodemselection)

    - [hiber.modem.ListModemsRequest.Sort](#hibermodemlistmodemsrequestsort)
    - [hiber.modem.Modem.Lifecycle](#hibermodemmodemlifecycle)
    - [hiber.modem.Modem.Type](#hibermodemmodemtype)
    - [hiber.modem.ModemMessage.Source](#hibermodemmodemmessagesource)

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


## ModemAlarmService


### List
> **rpc** List([ListModemAlarms.Request](#listmodemalarmsrequest))
    [ListModemAlarms.Response](#listmodemalarmsresponse)

List available modem alarms (including inherited from your parent organizations).

### Create
> **rpc** Create([CreateModemAlarm.Request](#createmodemalarmrequest))
    [CreateModemAlarm.Response](#createmodemalarmresponse)

Create a new modem alarm with any number of checks.

### Update
> **rpc** Update([UpdateModemAlarm.Request](#updatemodemalarmrequest))
    [UpdateModemAlarm.Response](#updatemodemalarmresponse)

Update a modem alarm and its checks, if you are the owner.

### Delete
> **rpc** Delete([DeleteModemAlarm.Request](#deletemodemalarmrequest))
    [DeleteModemAlarm.Response](#deletemodemalarmresponse)

Delete a modem alarm, if you are the owner.

### AddCheck
> **rpc** AddCheck([UpdateModemAlarmAddCheck.Request](#updatemodemalarmaddcheckrequest))
    [UpdateModemAlarmAddCheck.Response](#updatemodemalarmaddcheckresponse)

Add a check to a modem alarm, if you are the owner.

### UpdateCheck
> **rpc** UpdateCheck([UpdateModemAlarmUpdateCheck.Request](#updatemodemalarmupdatecheckrequest))
    [UpdateModemAlarmUpdateCheck.Response](#updatemodemalarmupdatecheckresponse)

Update a check in a modem alarm, if you are the owner.

### RemoveCheck
> **rpc** RemoveCheck([UpdateModemAlarmRemoveCheck.Request](#updatemodemalarmremovecheckrequest))
    [UpdateModemAlarmRemoveCheck.Response](#updatemodemalarmremovecheckresponse)

Remove a check from a modem alarm, if you are the owner.

### TestParameters
> **rpc** TestParameters([TestModemAlarmTestParameters.Request](#testmodemalarmtestparametersrequest))
    [TestModemAlarmTestParameters.Response](#testmodemalarmtestparametersresponse)

Test a set of parameters on a modem alarm, to see the result when they are applied during assignment.

### Assign
> **rpc** Assign([AssignModemAlarms.Request](#assignmodemalarmsrequest))
    [AssignModemAlarms.Response](#assignmodemalarmsresponse)

Assign a modem alarm to a modem.

### Unassign
> **rpc** Unassign([UnassignModemAlarms.Request](#unassignmodemalarmsrequest))
    [UnassignModemAlarms.Response](#unassignmodemalarmsresponse)

Unassign a modem alarm from a modem.


## Messages

### AssignModemAlarms

Add direct assignments.
If an overlapping assignment using a rule exists, it is shadowed by the direct assignment.

Simplified version of assign.AssignDirectly.


### AssignModemAlarms.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarms | [ ModemAlarmSelection](#modemalarmselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign_to**.modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign_to**.assets | [ hiber.asset.AssetSelection](#hiberassetassetselection) |  |
| parameters | [map AssignModemAlarms.Request.ParametersEntry](#assignmodemalarmsrequestparametersentry) | The alarm parameters, by alarm identifier, if any, overriding any default values in the alarm(s). |

### AssignModemAlarms.Request.ParametersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ google.protobuf.Struct](#googleprotobufstruct) |  |

### AssignModemAlarms.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| created | [repeated AssignedModemAlarm](#assignedmodemalarm) |  |
| request | [ AssignModemAlarms.Request](#assignmodemalarmsrequest) |  |

### AssignedModemAlarm

Directly assigned modem alarm to a modem.

| Field | Type | Description |
| ----- | ---- | ----------- |
| alarm_identifier | [ string](#string) |  |
| modem_number | [ string](#string) |  |

### CreateModemAlarm

Create a new alarm.

The request contains the option to add checks as well.
This is a shortcut for creating an alarm and then adding checks, and as such can result in multiple events:
- a created event on the alarm
- an update event on the alarm checks, iff any checks were added


### CreateModemAlarm.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| name | [ string](#string) | A name for the alarm. |
|  **optional** description | [optional string](#string) | A short description of what the alarm should do. |
| trigger_condition | [ ModemAlarm.TriggerCondition](#modemalarmtriggercondition) | Condition determining when an alarm is triggered if it has multiple checks. |
| checks | [repeated ModemAlarm.Check](#modemalarmcheck) | The checks to add to this alarm. Shortcut for creating an alarm and then adding checks to it. |
|  **optional** default_health_level | [optional string](#string) | The default health level for this alarm. See ModemAlarm.default_health_level for more information. |
|  **optional** health_level_after_resolved | [optional ModemAlarm.HealthLevelAfterResolved](#modemalarmhealthlevelafterresolved) | The health level this alarm should cause after it is resolved. See ModemAlarm.health_level_after_resolved for more information. |

### CreateModemAlarm.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| created | [ ModemAlarm](#modemalarm) | The created modem alarm. |

### DeleteModemAlarm

Delete an alarm.


### DeleteModemAlarm.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | Identifier of the modem alarm to delete. |

### DeleteModemAlarm.Response




### ListModemAlarms

List modem alarms in an organization.


### ListModemAlarms.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional ModemAlarmSelection](#modemalarmselection) | Selection criteria for listing modem alarms. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) | Pagination for the returned alarms. |
|  **optional** apply_unit_preferences | [optional bool](#bool) | Apply your UnitPreferences to the alarm checks. For example, if a temperature check is configured in kelvin, but your unit preferences specify celsius for temperature, the check value will be converted to celsius instead. |

### ListModemAlarms.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem_alarms | [repeated ModemAlarm](#modemalarm) | A list of modem alarms. |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | A pagination object, which can be used to go through the alarms. |
| request | [ ListModemAlarms.Request](#listmodemalarmsrequest) | The request made to list the given alarms. |

### ModemAlarm

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
| trigger_condition | [ ModemAlarm.TriggerCondition](#modemalarmtriggercondition) | Condition determining when an alarm is triggered if it has multiple checks. |
| default_health_level | [ string](#string) | The default health level for checks in this alarm, if they have no health_level configured. |
| health_level_after_resolved | [ ModemAlarm.HealthLevelAfterResolved](#modemalarmhealthlevelafterresolved) | Allow the alarm to cause a health level for the modem even after it has been resolved. By configuring this, you can specify the modem health should be affected for a longer period. For example, when using an inactivity check, this could be used to configure modem health ERROR while inactive, lowering to INVESTIGATE for a day after a new message comes in. |
| checks | [repeated ModemAlarm.Check](#modemalarmcheck) | The checks in this alarm, that validate the state of the modem. |
| alarm_parameters | [ google.protobuf.Struct](#googleprotobufstruct) | Parameters for this alarm. This field displays all the parameters that can be set for the alarm on assignment, with their current value. |

### ModemAlarm.Check

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
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.location | [ ModemAlarm.Check.LocationCheck](#modemalarmchecklocationcheck) | Check whether the device is in a given location. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.field | [ ModemAlarm.Check.FieldCheck](#modemalarmcheckfieldcheck) | Check that a message body field has a specified value. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.inactivity | [ ModemAlarm.Check.InactivityCheck](#modemalarmcheckinactivitycheck) | Check whether the device exceeds inactivity limits. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.delay | [ ModemAlarm.Check.DelayCheck](#modemalarmcheckdelaycheck) | Check whether a message delay exceeds delay limits. |

### ModemAlarm.Check.DelayCheck

Check whether the message was delayed more than a configured limit.
The delay is the time between the message was sent (ModemMessage.sent_at) and the time it was
received on the server (ModemMessage.received_at).

Has the following parameters:
- delay.maximum: the maximum allowed delay

| Field | Type | Description |
| ----- | ---- | ----------- |
| maximum | [ hiber.Duration](#hiberduration) | The maximum value for the message delay (duration between sent and received time). |

### ModemAlarm.Check.FieldCheck

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
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.equals | [ ModemAlarm.Check.FieldCheck.EqualsCheck](#modemalarmcheckfieldcheckequalscheck) | Check that a field equals a value. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.allowed | [ ModemAlarm.Check.FieldCheck.AllowedCheck](#modemalarmcheckfieldcheckallowedcheck) | Check that a field equals one of a set of values. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.blocked | [ ModemAlarm.Check.FieldCheck.BlockedCheck](#modemalarmcheckfieldcheckblockedcheck) | Check that a field does not equal one of a set of values. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.minimum | [ ModemAlarm.Check.FieldCheck.MinimumCheck](#modemalarmcheckfieldcheckminimumcheck) | Chech that a field is higher than the given value. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.maximum | [ ModemAlarm.Check.FieldCheck.MaximumCheck](#modemalarmcheckfieldcheckmaximumcheck) | Check that a field is lower than the given value. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.threshold | [ ModemAlarm.Check.FieldCheck.ThresholdCheck](#modemalarmcheckfieldcheckthresholdcheck) | Check that a field is within a given numeric range. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.blocked_range | [ ModemAlarm.Check.FieldCheck.BlockedRangeCheck](#modemalarmcheckfieldcheckblockedrangecheck) | Check that a field is not in a given numeric range. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.delta | [ ModemAlarm.Check.FieldCheck.DeltaCheck](#modemalarmcheckfieldcheckdeltacheck) | Check that a field's difference in value over a given period is within a specified numeric range. |

### ModemAlarm.Check.FieldCheck.AllowedCheck

Check that the field is in a set of expected values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| allowed | [repeated google.protobuf.Value](#googleprotobufvalue) | The list of allowed values, one of which should match the field value. |

### ModemAlarm.Check.FieldCheck.BlockedCheck

Check that the field is not in a set of blocked values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| blocked | [repeated google.protobuf.Value](#googleprotobufvalue) | The list of blocked values; the field should not match any of them. |

### ModemAlarm.Check.FieldCheck.BlockedRangeCheck

Check that the field is outside of a range.
If the minimum is higher than the maximum (i.e. 30..10), this is automatically converted into a
ThresholdCheck.

| Field | Type | Description |
| ----- | ---- | ----------- |
| blocked | [ hiber.DoubleRange](#hiberdoublerange) | The range the value must not be in. |

### ModemAlarm.Check.FieldCheck.DeltaCheck

A check that evaluates the differences in values over time, for the selected field(s) in the parsed body.

| Field | Type | Description |
| ----- | ---- | ----------- |
| period | [ hiber.Duration](#hiberduration) | The period to evaluate when determining the value difference. |
| threshold | [ ModemAlarm.Check.FieldCheck.ThresholdCheck](#modemalarmcheckfieldcheckthresholdcheck) | Check that the delta is within a given numeric range. |
| encrypted | [ bool](#bool) | Whether the field data should be encrypted in cache storage. Delta checks use a cache for field from messages that are affected by a delta check. Encrypting the individual field values is (relatively) computationally expensive and may lead to a slightly delayed alarm event. In the future, some delta features may only be available to unencrypted values due to performance issues. |
| ignore_previous_value_not_found | [ bool](#bool) | Whether to ignore this check if the previous value is not found (i.e. there is no history). |

### ModemAlarm.Check.FieldCheck.EqualsCheck

Check that the field is equal to the given value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| expected | [ google.protobuf.Value](#googleprotobufvalue) | The expected value a field should have. |

### ModemAlarm.Check.FieldCheck.MaximumCheck

Check that the field is lower than the given value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| maximum | [ double](#double) | The maximum numeric value the field should have. |

### ModemAlarm.Check.FieldCheck.MinimumCheck

Check that the field is higher than the given value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| minimum | [ double](#double) | The minimum numeric value the field should have. |

### ModemAlarm.Check.FieldCheck.ThresholdCheck

Check that the field is above a minimum threshold and under a maximum threshold.
If the minimum is higher than the maximum (i.e. 30..10), this is automatically converted into a
BlockedRangeCheck.

| Field | Type | Description |
| ----- | ---- | ----------- |
| expected | [ hiber.DoubleRange](#hiberdoublerange) | The range the value must be in. |
| minimum | [ double](#double) | The minimum expected value, available separately for convenience and check parameters. |
| maximum | [ double](#double) | The maximum expected value, available separately for convenience and check parameters. |

### ModemAlarm.Check.InactivityCheck

Check whether the device exceeds inactivity limits.

Has the following parameters:
- inactivity.maximum: the maximum allowed inactivity

| Field | Type | Description |
| ----- | ---- | ----------- |
| maximum | [ hiber.Duration](#hiberduration) | The maximum value for the modem's inactivity (time since last message was received on the server). |

### ModemAlarm.Check.LocationCheck

Check that the device location is within a given area.

Has the following parameters:
- location.expected: replace the referenced named location
- location.named: replace the referenced named location

| Field | Type | Description |
| ----- | ---- | ----------- |
| named | [ string](#string) | Specify the name of a named location (NamedLocation) that the device must be in. |

### ModemAlarm.HealthLevelAfterResolved

Allow the alarm to cause a health level for the modem even after a new message has come in.

Typically, an alarm event only affects the modem health while it is from the last message from that modem.
By configuring this, you can specify the modem health should be affected for a longer period.

For example, when using an inactivity check, this could be used to configure modem health ERROR while
inactive, lowering to INVESTIGATE for a day after a new message comes in.

| Field | Type | Description |
| ----- | ---- | ----------- |
| health_level | [ string](#string) | The health level that this check would cause for a modem, when the original failure is resolved. |
| period | [ hiber.Duration](#hiberduration) | The amount of time that this health level would be active. |

### ModemAlarmSelection

Selection criteria for listing modem alarms in an organization. If no options are provided, all modem alarms
are valid.

If values are provided both for identifiers and search, then only alarms are selected that match both criteria.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifiers | [repeated string](#string) | Selects alarms by the given list of alarm identifiers. |
|  **optional** search | [optional string](#string) | Search for the given string in identifier, description, fields and values. |

### TestModemAlarmTestParameters

Test a set of parameters on a modem alarm, to see the result when they are applied during assignment.


### TestModemAlarmTestParameters.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarm_identifier | [ string](#string) | The identifier of the alarm on which to test parameters. |
| parameters | [ google.protobuf.Struct](#googleprotobufstruct) | The parameters of the alarm that are changed. |

### TestModemAlarmTestParameters.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| result | [ ModemAlarm](#modemalarm) |  |

### UnassignModemAlarms

Remove a direct assignment.
If an overlapping assignment using a rule exists, it is not affected, except that it is longer shadowed.

Simplified version of assign.UnassignDirectly.


### UnassignModemAlarms.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarms | [ ModemAlarmSelection](#modemalarmselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unassign_from**.modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unassign_from**.assets | [ hiber.asset.AssetSelection](#hiberassetassetselection) |  |

### UnassignModemAlarms.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| removed_direct_assignments | [repeated AssignedModemAlarm](#assignedmodemalarm) |  |
| request | [ UnassignModemAlarms.Request](#unassignmodemalarmsrequest) |  |

### UpdateModemAlarm

Update the alarm, iff you are the owner or can impersonate the owner organization.

The request contains the option to add, remove or update checks as well.
This is a shortcut for updating an alarm and then adding, removing and/or updating checks,
and as such can result in multiple events:
- an update event on the alarm, iff there were any non-check changes to the alarm.
- an update event on the alarm checks, iff there were any check addition, updates or deletions


### UpdateModemAlarm.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifiers of the alarm to update |
|  **optional** update_name | [optional hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong> Update the name, optionally. |
|  **optional** name | [optional string](#string) |  |
|  **optional** update_description | [optional hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong> Update the description, optionally. |
|  **optional** description | [optional string](#string) |  |
|  **optional** update_trigger_condition | [optional ModemAlarm.TriggerCondition](#modemalarmtriggercondition) | Update the trigger condition, optionally. |
|  **optional** update_default_health_level | [optional hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong> Update the default health level, optionally. |
|  **optional** default_health_level | [optional string](#string) |  |
|  **optional** update_health_level_after_resolved | [optional ModemAlarm.HealthLevelAfterResolved](#modemalarmhealthlevelafterresolved) | Update the health after resolved, optionally. |
|  **optional** remove_health_level_after_resolved | [optional bool](#bool) | Remove the health after resolved, optionally. |
| add_checks | [repeated ModemAlarm.Check](#modemalarmcheck) | The checks to add to this alarm. Shortcut for updating an alarm and then adding checks to it. |
| update_checks | [map UpdateModemAlarm.Request.UpdateChecksEntry](#updatemodemalarmrequestupdatechecksentry) | The checks to update in this alarm. Shortcut for updating an alarm and then updating checks. |
| delete_checks | [repeated string](#string) | The checks to remove from this alarm. Shortcut for updating an alarm and then removing checks. |

### UpdateModemAlarm.Request.UpdateChecksEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ ModemAlarm.Check](#modemalarmcheck) |  |

### UpdateModemAlarm.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ ModemAlarm](#modemalarm) |  |

### UpdateModemAlarmAddCheck

Add a check to the alarm, iff you are the owner or can impersonate the owner organization.


### UpdateModemAlarmAddCheck.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarm_identifier | [ string](#string) | The identifier of the alarm to which the check is added. |
| check | [ ModemAlarm.Check](#modemalarmcheck) | The check to add to the Modem Alarm. Identifier of the check must be unique within the alarm. |

### UpdateModemAlarmAddCheck.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ ModemAlarm](#modemalarm) |  |

### UpdateModemAlarmRemoveCheck

Remove a check from an alarm.


### UpdateModemAlarmRemoveCheck.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarm_identifier | [ string](#string) | The identifier of the alarm from which to remove the check. |
| check_identifier | [ string](#string) | The identifier of the check to remove. |

### UpdateModemAlarmRemoveCheck.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ ModemAlarm](#modemalarm) |  |

### UpdateModemAlarmUpdateCheck

Update a check of an alarm.

Only the values of a check can be updated, e.g., it is not possible to change an inactivity check to a location
check.


### UpdateModemAlarmUpdateCheck.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarm_identifier | [ string](#string) | The identifier of the alarm of which to update the check. |
| check_identifier | [ string](#string) | The identifier of the check to update. |
| update_check | [ ModemAlarm.Check](#modemalarmcheck) | The new values for the check of this alarm. |
| test_parameters_only | [ bool](#bool) | If set, the update is not actually saved, but only applied and returned. This is a convenience to easily test parameters for a check similar to TestModemAlarmTestParameters. |

### UpdateModemAlarmUpdateCheck.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ ModemAlarm](#modemalarm) |  |


## Enums
### ModemAlarm.TriggerCondition
Condition determining when an alarm is triggered if it has multiple checks.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | Defaults to the current value when updating, or to ANY_CHECK_FAILED when creating. | 0 |
| ANY_CHECK_FAILED | Trigger the alarm when any of the checks fail. This is useful when providing a single device health alarm, that checks, for example, battery, operating temperature, etc. and should trigger when any of those are outside the expected range. | 1 |
| ALL_CHECKS_FAILED | Trigger the alarm only when all checks fail. This is useful when creating a combined alarm, where several data points factor into the decisions to trigger the alarm, for example, combining a check on the current value with a delta check on the historical values, to trigger only if the value is high for a longer period. | 2 |



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
| location | [ hiber.Location](#hiberlocation) | Location for the asset. |
| files | [repeated hiber.file.File](#hiberfilefile) | Files for this asset. Typically an image of a place. See the File.media_type for more information. |

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



## Referenced messages from field.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [field.proto](https://github.com/HiberGlobal/api/blob/master/field.proto).


### hiber.field.Field



| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) | Unique identifier for this field. |
| field | [ string](#string) | The name of the field (if in the root structure) or a JsonPath to the field. |
|  **optional** display_name | [optional string](#string) | An optional display name for the field. |
| priority | [ int32](#int32) | Priority of the field, typically used for ordering. |
| type | [ hiber.value.Value.Type](#hibervaluevaluetype) | The type of value the field contains. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **details**.numeric | [ hiber.field.Field.Numeric](#hiberfieldfieldnumeric) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **details**.enum | [ hiber.field.Field.Enum](#hiberfieldfieldenum) |  |
| encrypted | [ bool](#bool) | Whether this field should be stored encrypted or not. If it is, some processing options may be unavailable or slower. |
| optional | [ bool](#bool) | Whether this field should be validated from the parser output. |
| operational | [ bool](#bool) | Field contains values relevant for operating the device. |
|  **optional** unit_of_measurement | [optional hiber.UnitOfMeasurement](#hiberunitofmeasurement) | <strong>Deprecated.</strong> If numeric, the unit of the field. Deprecated: use numeric.numeric_unit oneof instead |
|  **optional** unit_symbol | [optional string](#string) | <strong>Deprecated.</strong> The symbol for the unit. Deprecated: use numeric.symbol instead |

### hiber.field.Field.Enum

If the field is an enum, this specifies the enum values for the field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| values | [repeated hiber.value.Value.Enum](#hibervaluevalueenum) |  |

### hiber.field.Field.Numeric

If the field is numeric, this specifies the unit and formatting details for the field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype) | The type of numeric value. |
| symbol | [ string](#string) | The symbol to use for the field's unit. |
| format | [ hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat) | How to format the values (number of decimals, rounding, etc.). |
| unit | [ hiber.field.Field.Numeric.Unit](#hiberfieldfieldnumericunit) | The unit for the field, depending on the type. |
|  **optional** converted_from | [optional hiber.field.Field.Numeric.Unit](#hiberfieldfieldnumericunit) | If the unit preferences were applied, and the unit is different, the field will be converted to the preferred unit, from the original unit specified in this field. |

### hiber.field.Field.Numeric.Format

Formatting options for the field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **round**.round_to_integer | [ bool](#bool) | Round to an integer. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **round**.round_to_scale | [ uint32](#uint32) | Round to a number of decimals (at least 1). |
| rounding_mode | [ hiber.field.Field.Numeric.Format.RoundingMode](#hiberfieldfieldnumericformatroundingmode) | How to round the value when scale is applied. |

### hiber.field.Field.Numeric.Unit



| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.battery_level | [ hiber.value.Value.Numeric.BatteryLevel.BatteryLevelUnit](#hibervaluevaluenumericbatterylevelbatterylevelunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.distance | [ hiber.value.Value.Numeric.Distance.DistanceUnit](#hibervaluevaluenumericdistancedistanceunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.duration | [ hiber.value.Value.Numeric.Duration.DurationUnit](#hibervaluevaluenumericdurationdurationunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.fuel_efficiency | [ hiber.value.Value.Numeric.FuelEfficiency.FuelEfficiencyUnit](#hibervaluevaluenumericfuelefficiencyfuelefficiencyunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.flow | [ hiber.value.Value.Numeric.Flow.FlowUnit](#hibervaluevaluenumericflowflowunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.percentage | [ hiber.value.Value.Numeric.Percentage.PercentageUnit](#hibervaluevaluenumericpercentagepercentageunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.pressure | [ hiber.value.Value.Numeric.Pressure.PressureUnit](#hibervaluevaluenumericpressurepressureunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.speed | [ hiber.value.Value.Numeric.Speed.SpeedUnit](#hibervaluevaluenumericspeedspeedunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.temperature | [ hiber.value.Value.Numeric.Temperature.TemperatureUnit](#hibervaluevaluenumerictemperaturetemperatureunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.voltage | [ hiber.value.Value.Numeric.Voltage.VoltageUnit](#hibervaluevaluenumericvoltagevoltageunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.volume | [ hiber.value.Value.Numeric.Volume.VolumeUnit](#hibervaluevaluenumericvolumevolumeunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.mass | [ hiber.value.Value.Numeric.Mass.MassUnit](#hibervaluevaluenumericmassmassunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.rotation_speed | [ hiber.value.Value.Numeric.RotationSpeed.RotationSpeedUnit](#hibervaluevaluenumericrotationspeedrotationspeedunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.rate | [ hiber.value.Value.Numeric.Rate.RateUnit](#hibervaluevaluenumericraterateunit) |  |


### Enums
#### hiber.field.Field.Numeric.Format.RoundingMode
How to round the value when scale is applied.
For example, a value of 3.1415 with scale 3 could be
  4.141 (DOWN, HALF_DOWN, FLOOR) or
  4.142 (HALF_UP, UP, CEILING).

| Name | Description | Number |
| ---- | ----------- | ------ |
| HALF_UP | Round towards nearest neighbor unless both neighbors are equidistant, in which case round up Effectively round up when >= .5, otherwise round down. | 0 |
| HALF_DOWN | Round towards nearest neighbor unless both neighbors are equidistant, in which case round down. Effectively round up when > .5, otherwise round down. | 1 |
| UP | Round away from zero: 1.1 -> 2, while -1.1 -> -2. | 3 |
| DOWN | Round towards zero: 1.1 -> 1, while -1.1 -> -1. | 4 |
| CEILING | Round towards positive infinity. | 5 |
| FLOOR | Round towards negative infinity. | 6 |
| HALF_EVEN | Round towards the nearest neighbor unless both neighbors are equidistant, in which case, round towards the even neighbor. Effectively round up when >= .5 and next integer value is even, otherwise round down. | 7 |



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

