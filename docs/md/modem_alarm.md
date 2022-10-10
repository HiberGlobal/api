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
  - [MakeModemAlarmAvailableToChildOrganizationRequest](#makemodemalarmavailabletochildorganizationrequest)
  - [MakeModemAlarmUnavailableToChildOrganizationRequest](#makemodemalarmunavailabletochildorganizationrequest)
  - [ModemAlarm](#modemalarm)
  - [ModemAlarm.Check](#modemalarmcheck)
  - [ModemAlarm.Check.DelayCheck](#modemalarmcheckdelaycheck)
  - [ModemAlarm.Check.FieldCheck](#modemalarmcheckfieldcheck)
  - [ModemAlarm.Check.FieldCheck.AllowedCheck](#modemalarmcheckfieldcheckallowedcheck)
  - [ModemAlarm.Check.FieldCheck.BlockedCheck](#modemalarmcheckfieldcheckblockedcheck)
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
  - [UpdateModemAlarmAvailability](#updatemodemalarmavailability)
  - [UpdateModemAlarmAvailability.Request](#updatemodemalarmavailabilityrequest)
  - [UpdateModemAlarmAvailability.Response](#updatemodemalarmavailabilityresponse)
  - [UpdateModemAlarmRemoveCheck](#updatemodemalarmremovecheck)
  - [UpdateModemAlarmRemoveCheck.Request](#updatemodemalarmremovecheckrequest)
  - [UpdateModemAlarmRemoveCheck.Response](#updatemodemalarmremovecheckresponse)
  - [UpdateModemAlarmUpdateCheck](#updatemodemalarmupdatecheck)
  - [UpdateModemAlarmUpdateCheck.Request](#updatemodemalarmupdatecheckrequest)
  - [UpdateModemAlarmUpdateCheck.Request.UpdateUsingParametersEntry](#updatemodemalarmupdatecheckrequestupdateusingparametersentry)
  - [UpdateModemAlarmUpdateCheck.Response](#updatemodemalarmupdatecheckresponse)

- Enums
  - [ModemAlarm.TriggerCondition](#modemalarmtriggercondition)

- Referenced messages from [modem.proto](#referenced-messages-from-modemproto)
  - [hiber.modem.Modem](#hibermodemmodem)
  - [hiber.modem.ModemSelection](#hibermodemmodemselection)

    - [hiber.modem.ListModemsRequest.Sort](#hibermodemlistmodemsrequestsort)
    - [hiber.modem.Modem.Lifecycle](#hibermodemmodemlifecycle)
    - [hiber.modem.Modem.Peripherals.HiberAntenna](#hibermodemmodemperipheralshiberantenna)
    - [hiber.modem.Modem.Transfer.Status](#hibermodemmodemtransferstatus)
    - [hiber.modem.Modem.Type](#hibermodemmodemtype)
    - [hiber.modem.ModemMessage.Source](#hibermodemmodemmessagesource)

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
  - [hiber.Filter.FieldEnumValues](#hiberfilterfieldenumvalues)
  - [hiber.Filter.Modems](#hiberfiltermodems)
  - [hiber.Filter.Modems.Update](#hiberfiltermodemsupdate)
  - [hiber.Filter.OrganizationPermissions](#hiberfilterorganizationpermissions)
  - [hiber.Filter.Organizations](#hiberfilterorganizations)
  - [hiber.Filter.Publishers](#hiberfilterpublishers)
  - [hiber.Filter.SupportPermissions](#hiberfiltersupportpermissions)
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

### UpdateAvailability
> **rpc** UpdateAvailability([UpdateModemAlarmAvailability.Request](#updatemodemalarmavailabilityrequest))
    [UpdateModemAlarmAvailability.Response](#updatemodemalarmavailabilityresponse)

Make a modem alarm (un)available to (a selection of) child organizations.

### MakeAvailableToChildOrganization
> **rpc** MakeAvailableToChildOrganization([MakeModemAlarmAvailableToChildOrganizationRequest](#makemodemalarmavailabletochildorganizationrequest))
    [ModemAlarm](#modemalarm)

Make a modem alarm available to a child organization.

### MakeUnavailableToChildOrganization
> **rpc** MakeUnavailableToChildOrganization([MakeModemAlarmUnavailableToChildOrganizationRequest](#makemodemalarmunavailabletochildorganizationrequest))
    [ModemAlarm](#modemalarm)

Make a modem alarm unavailable to a child organization.

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
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarms | [ ModemAlarmSelection](#modemalarmselection) | none |
| modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | none |
| parameters | [map AssignModemAlarms.Request.ParametersEntry](#assignmodemalarmsrequestparametersentry) | The alarm parameters, by alarm identifier, if any, overriding any default values in the alarm(s). |

### AssignModemAlarms.Request.ParametersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ google.protobuf.Struct](#googleprotobufstruct) | none |

### AssignModemAlarms.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| created | [repeated AssignedModemAlarm](#assignedmodemalarm) | none |
| request | [ AssignModemAlarms.Request](#assignmodemalarmsrequest) | none |

### AssignedModemAlarm

Directly assigned modem alarm to a modem.

| Field | Type | Description |
| ----- | ---- | ----------- |
| alarm_identifier | [ string](#string) | none |
| modem_number | [ string](#string) | none |

### CreateModemAlarm

Create a new alarm.

The request contains the option to add checks as well.
This is a shortcut for creating an alarm and then adding checks, and as such can result in multiple events:
- a created event on the alarm
- an update event on the alarm checks, iff any checks were added


### CreateModemAlarm.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| name | [ string](#string) | A name for the alarm. |
| description | [ string](#string) | A short description of what the alarm should do. |
| trigger_condition | [ ModemAlarm.TriggerCondition](#modemalarmtriggercondition) | Condition determining when an alarm is triggered if it has multiple checks. |
| checks | [repeated ModemAlarm.Check](#modemalarmcheck) | The checks to add to this alarm. Shortcut for creating an alarm and then adding checks to it. |
| default_health_level | [ string](#string) | The default health level for this alarm. See ModemAlarm.default_health_level for more information. |
| health_level_after_resolved | [ ModemAlarm.HealthLevelAfterResolved](#modemalarmhealthlevelafterresolved) | The health level this alarm should cause after it is resolved. See ModemAlarm.health_level_after_resolved for more information. |

### CreateModemAlarm.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| created | [ ModemAlarm](#modemalarm) | none |

### DeleteModemAlarm




### DeleteModemAlarm.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | none |

### DeleteModemAlarm.Response




### ListModemAlarms




### ListModemAlarms.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ ModemAlarmSelection](#modemalarmselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |
| apply_unit_preferences | [ bool](#bool) | Apply your UnitPreferences to the alarm checks. For example, if a temperature check is configured in kelvin, but your unit preferences specify celsius for temperature, the check value will be converted to celsius instead. |

### ListModemAlarms.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem_alarms | [repeated ModemAlarm](#modemalarm) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |
| request | [ ListModemAlarms.Request](#listmodemalarmsrequest) | none |

### MakeModemAlarmAvailableToChildOrganizationRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the alarm that should be updated. |
| available_to | [repeated string](#string) | The child organization(s) that the alarm should be available to. This will - when the organization is on the exclude list, remove it - when the includeAll flag is false, add it to the include list (if not already present) |

### MakeModemAlarmUnavailableToChildOrganizationRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the alarm that should be updated. |
| unavailable_to | [repeated string](#string) | The child organization(s) that the alarm should be unavailable to. This will - when the organization is on the include list, remove it - when the includeAll flag is true, add it to the exclude list (if not already present) |

### ModemAlarm

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
| trigger_condition | [ ModemAlarm.TriggerCondition](#modemalarmtriggercondition) | Condition determining when an alarm is triggered if it has multiple checks. |
| default_health_level | [ string](#string) | The default health level for checks in this alarm, if they have no health_level configured. |
| health_level_after_resolved | [ ModemAlarm.HealthLevelAfterResolved](#modemalarmhealthlevelafterresolved) | Allow the alarm to cause a health level for the modem even after it has been resolved. By configuring this, you can specify the modem health should be affected for a longer period. For example, when using an inactivity check, this would could be used to configure modem health ERROR while inactive, lowering to INVESTIGATE for a day after a new message comes in. |
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
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.location | [ ModemAlarm.Check.LocationCheck](#modemalarmchecklocationcheck) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.field | [ ModemAlarm.Check.FieldCheck](#modemalarmcheckfieldcheck) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.inactivity | [ ModemAlarm.Check.InactivityCheck](#modemalarmcheckinactivitycheck) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.delay | [ ModemAlarm.Check.DelayCheck](#modemalarmcheckdelaycheck) | none |

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
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.equals | [ ModemAlarm.Check.FieldCheck.EqualsCheck](#modemalarmcheckfieldcheckequalscheck) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.allowed | [ ModemAlarm.Check.FieldCheck.AllowedCheck](#modemalarmcheckfieldcheckallowedcheck) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.blocked | [ ModemAlarm.Check.FieldCheck.BlockedCheck](#modemalarmcheckfieldcheckblockedcheck) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.minimum | [ ModemAlarm.Check.FieldCheck.MinimumCheck](#modemalarmcheckfieldcheckminimumcheck) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.maximum | [ ModemAlarm.Check.FieldCheck.MaximumCheck](#modemalarmcheckfieldcheckmaximumcheck) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.threshold | [ ModemAlarm.Check.FieldCheck.ThresholdCheck](#modemalarmcheckfieldcheckthresholdcheck) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **check**.delta | [ ModemAlarm.Check.FieldCheck.DeltaCheck](#modemalarmcheckfieldcheckdeltacheck) | none |

### ModemAlarm.Check.FieldCheck.AllowedCheck

Check that the field is in a set of expected values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| allowed | [repeated google.protobuf.Value](#googleprotobufvalue) | The list of allowed values, one of which should match the field value. |

### ModemAlarm.Check.FieldCheck.BlockedCheck

Check that the field is not in a set of blocked values.

| Field | Type | Description |
| ----- | ---- | ----------- |
| blocked | [repeated google.protobuf.Value](#googleprotobufvalue) | none |

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
| expected | [ google.protobuf.Value](#googleprotobufvalue) | none |

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

Check that the field is within a given numeric range.

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
| deprecated_maximum | [ hiber.Duration](#hiberduration) | none |

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

For example, when using an inactivity check, this would could be used to configure modem health ERROR while
inactive, lowering to INVESTIGATE for a day after a new message comes in.

| Field | Type | Description |
| ----- | ---- | ----------- |
| health_level | [ string](#string) | The health level that this check would cause for a modem, when the original failure is resolved. |
| period | [ hiber.Duration](#hiberduration) | The amount of time that this health level would be active. |

### ModemAlarmSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| identifiers | [repeated string](#string) | none |
| search | [ string](#string) | Search for the given string in identifier, description, fields and values. |
| owner_organizations | [repeated string](#string) | Only return alarms that were created by the given organizations. |
| only_owned_alarms | [ bool](#bool) | none |

### TestModemAlarmTestParameters




### TestModemAlarmTestParameters.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarm_identifier | [ string](#string) | none |
| parameters | [ google.protobuf.Struct](#googleprotobufstruct) | none |

### TestModemAlarmTestParameters.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| result | [ ModemAlarm](#modemalarm) | none |

### UnassignModemAlarms

Remove a direct assignment.
If an overlapping assignment using a rule exists, it is not affected, except that it is longer shadowed.

Simplified version of assign.UnassignDirectly.


### UnassignModemAlarms.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarms | [ ModemAlarmSelection](#modemalarmselection) | none |
| modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | none |

### UnassignModemAlarms.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| removed_direct_assignments | [repeated AssignedModemAlarm](#assignedmodemalarm) | none |
| request | [ UnassignModemAlarms.Request](#unassignmodemalarmsrequest) | none |

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
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifiers of the alarm to update |
| update_name | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | Update the name, optionally. |
| update_description | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | Update the description, optionally. |
| update_trigger_condition | [ ModemAlarm.TriggerCondition](#modemalarmtriggercondition) | Update the trigger condition, optionally. |
| update_default_health_level | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | Update the default health level, optionally. |
| update_health_level_after_resolved | [ ModemAlarm.HealthLevelAfterResolved](#modemalarmhealthlevelafterresolved) | Update the health after resolved, optionally. |
| remove_health_level_after_resolved | [ bool](#bool) | Remove the health after resolved, optionally. |
| add_checks | [repeated ModemAlarm.Check](#modemalarmcheck) | The checks to add to this alarm. Shortcut for updating an alarm and then adding checks to it. |
| update_checks | [map UpdateModemAlarm.Request.UpdateChecksEntry](#updatemodemalarmrequestupdatechecksentry) | The checks to update in this alarm. Shortcut for updating an alarm and then updating checks. |
| delete_checks | [repeated string](#string) | The checks to remove from this alarm. Shortcut for updating an alarm and then removing checks. |

### UpdateModemAlarm.Request.UpdateChecksEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ ModemAlarm.Check](#modemalarmcheck) | none |

### UpdateModemAlarm.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ ModemAlarm](#modemalarm) | none |

### UpdateModemAlarmAddCheck

Add a check to the alarm, iff you are the owner or can impersonate the owner organization.


### UpdateModemAlarmAddCheck.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarm_identifier | [ string](#string) | none |
| check | [ ModemAlarm.Check](#modemalarmcheck) | The check to add to the Modem Alarm. Identifier must be unique within the alarm. |

### UpdateModemAlarmAddCheck.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ ModemAlarm](#modemalarm) | none |

### UpdateModemAlarmAvailability




### UpdateModemAlarmAvailability.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarm_identifier | [ string](#string) | none |
| replace_apply_to_child_organizations | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | The new set of child organizations that this rule applies to. Replaces the original value! |

### UpdateModemAlarmAvailability.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ ModemAlarm](#modemalarm) | none |

### UpdateModemAlarmRemoveCheck




### UpdateModemAlarmRemoveCheck.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarm_identifier | [ string](#string) | none |
| check_identifier | [ string](#string) | none |

### UpdateModemAlarmRemoveCheck.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ ModemAlarm](#modemalarm) | none |

### UpdateModemAlarmUpdateCheck




### UpdateModemAlarmUpdateCheck.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| alarm_identifier | [ string](#string) | none |
| check_identifier | [ string](#string) | none |
| update_check | [ ModemAlarm.Check](#modemalarmcheck) | none |
| update_using_parameters | [map UpdateModemAlarmUpdateCheck.Request.UpdateUsingParametersEntry](#updatemodemalarmupdatecheckrequestupdateusingparametersentry) | Use parameters to update the check, as it would be when they were added when the alarm was assigned. |
| test_parameters_only | [ bool](#bool) | If set, the update is not actually saved, but only applied and returned. This is a convenience to easily test parameters for a check similar to TestModemAlarmTestParameters. |

### UpdateModemAlarmUpdateCheck.Request.UpdateUsingParametersEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ google.protobuf.Value](#googleprotobufvalue) | none |

### UpdateModemAlarmUpdateCheck.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ ModemAlarm](#modemalarm) | none |


## Enums
### ModemAlarm.TriggerCondition
Condition determining when an alarm is triggered if it has multiple checks.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | Defaults to the current value when updating, or to ANY_CHECK_FAILED when creating. | 0 |
| ANY_CHECK_FAILED | Trigger the alarm when any of the checks fail. This is useful when providing a single device health alarm, that checks, for example, battery, operating temperature, etc. and should trigger when any of those are outside the expected range. | 1 |
| ALL_CHECKS_FAILED | Trigger the alarm only when all checks fail. This is useful when creating a combined alarm, where several data points factor into the decisions to trigger the alarm, for example, combining a check on the current value with a delta check on the historical values, to trigger only if the value is high for a longer period. | 2 |



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
| lifecycle | [ hiber.modem.Modem.Lifecycle](#hibermodemmodemlifecycle) | none |
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
| only_active | [ bool](#bool) | Use lifecycle filter instead. |
| activated_in | [ hiber.TimeRange](#hibertimerange) | none |
| with_last_message_in | [ hiber.TimeRange](#hibertimerange) | none |
| with_service_type | [repeated hiber.organization.subscription.ServiceType](#hiberorganizationsubscriptionservicetype) | none |
| health | [repeated hiber.Health](#hiberhealth) | Deprecated health that uses the OK, WARNING, ERROR format. |
| health_levels | [repeated string](#string) | Filter modems by health level. |
| lifecycles | [repeated hiber.modem.Modem.Lifecycle](#hibermodemmodemlifecycle) | Filter modems by lifecycle(s). Defaults to nominal lifecycles, excluding disabled or decommissioned modems. |
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

#### hiber.modem.Modem.Lifecycle


| Name | Description | Number |
| ---- | ----------- | ------ |
| ACCEPTANCE_TESTING | Modem is deployed, but not active yet. Invisible for customer. | 0 |
| INSTALLED | Modem is active and sending messages. See health for more details on its health, based on the past messages. | 1 |
| PAUSED | none | 6 |
| DISABLED | none | 5 |
| DECOMMISSIONED | none | 4 |
| DAMAGED | Kept for backwards compatibility. Internally mapped to decommissioned | 2 |
| LOST | Kept for backwards compatibility. Internally mapped to decommissioned | 3 |

#### hiber.modem.Modem.Peripherals.HiberAntenna
A Hiber antenna is required for the modem to function.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | none | 0 |
| HIBER_PANDA | none | 1 |
| HIBER_GRIZZLY | none | 2 |
| HIBER_BLACK | none | 3 |
| CUSTOM | none | 4 |

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

### hiber.Filter.FieldEnumValues



| Field | Type | Description |
| ----- | ---- | ----------- |
| field | [ string](#string) | none |
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

### hiber.Filter.Publishers



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated int64](#int64) | none |
| exclude | [repeated int64](#int64) | none |
| only_active | [ bool](#bool) | none |

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

