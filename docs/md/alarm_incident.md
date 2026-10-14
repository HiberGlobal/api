# alarm_incident.proto

Incident for an alarm assigned to a device.

An incident is a series of messages that trigger the alarm, e.g. a period of time that pressure is above a threshold.

#### This file was generated from [alarm_incident.proto](https://github.com/HiberGlobal/api/blob/master/alarm_incident.proto).

## Table of Contents



- Messages
  - [AlarmIncident](#alarmincident)
  - [AlarmIncident.Alarm](#alarmincidentalarm)
  - [AlarmIncident.Device](#alarmincidentdevice)
  - [AlarmIncident.ErrorMessagesEntry](#alarmincidenterrormessagesentry)
  - [AlarmIncident.Update](#alarmincidentupdate)
  - [AlarmIncident.Update.ErrorMessagesEntry](#alarmincidentupdateerrormessagesentry)
  - [AlarmIncident.Update.PreviousErrorMessagesEntry](#alarmincidentupdatepreviouserrormessagesentry)
  - [AlarmIncidentSelection](#alarmincidentselection)

- Enums
  - [AlarmIncident.Status](#alarmincidentstatus)

- Referenced messages from [health.proto](#referenced-messages-from-healthproto)
  - [hiber.health.HealthLevel](#hiberhealthhealthlevel)
  - [hiber.health.HealthLevelSelection](#hiberhealthhealthlevelselection)


- Referenced messages from [modem.proto](#referenced-messages-from-modemproto)
  - [hiber.modem.Modem](#hibermodemmodem)
  - [hiber.modem.ModemSelection](#hibermodemmodemselection)

    - [hiber.modem.ListModemsRequest.Sort](#hibermodemlistmodemsrequestsort)
    - [hiber.modem.Modem.ConnectedDeviceInfo.Frequency](#hibermodemmodemconnecteddeviceinfofrequency)
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

## Messages

### AlarmIncident

Incident for an alarm assigned to a device.

An incident is a series of messages that trigger the alarm, e.g. a period of time that pressure is above a threshold.

The incident goes through a set of statuses, from started to resolved,
and tracks the health and error messages during that period.

When the status changes, an alarm incident event is produced.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) | Unique identifier for this incident. |
| alarm | [ AlarmIncident.Alarm](#alarmincidentalarm) | The alarm that produced the incident. |
| device | [ AlarmIncident.Device](#alarmincidentdevice) | The device that caused the incident. |
| status | [ AlarmIncident.Status](#alarmincidentstatus) | The status of the incident. |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | The health caused by this incident. If this is RESOLVED, the last health caused by this incident before it was resolved. |
| error_messages | [map AlarmIncident.ErrorMessagesEntry](#alarmincidenterrormessagesentry) | The error messages for this incident. If this is RESOLVED, the error messages for this incident before it was resolved. |
| timeline | [repeated AlarmIncident.Update](#alarmincidentupdate) | History of events for this incident, tracking, for example, when it started and when it was resolved. |

### AlarmIncident.Alarm

The alarm that produced the incident.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) |  |
| name | [ string](#string) |  |
| description | [ string](#string) |  |

### AlarmIncident.Device

The device that caused the incident.

| Field | Type | Description |
| ----- | ---- | ----------- |
| number | [ string](#string) |  |
| identifier | [ string](#string) |  |
| name | [ string](#string) |  |
| device_type | [ string](#string) |  |
| lifecycle | [ hiber.modem.Modem.Lifecycle](#hibermodemmodemlifecycle) |  |

### AlarmIncident.ErrorMessagesEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ string](#string) |  |

### AlarmIncident.Update

The history for this incident.

| Field | Type | Description |
| ----- | ---- | ----------- |
| time | [ hiber.Timestamp](#hibertimestamp) |  |
|  **optional** previous_status | [optional AlarmIncident.Status](#alarmincidentstatus) |  |
| status | [ AlarmIncident.Status](#alarmincidentstatus) |  |
|  **optional** previous_health_level | [optional hiber.health.HealthLevel](#hiberhealthhealthlevel) |  |
|  **optional** health_level | [optional hiber.health.HealthLevel](#hiberhealthhealthlevel) |  |
| previous_error_messages | [map AlarmIncident.Update.PreviousErrorMessagesEntry](#alarmincidentupdatepreviouserrormessagesentry) |  |
| error_messages | [map AlarmIncident.Update.ErrorMessagesEntry](#alarmincidentupdateerrormessagesentry) |  |

### AlarmIncident.Update.ErrorMessagesEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ string](#string) |  |

### AlarmIncident.Update.PreviousErrorMessagesEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ string](#string) |  |

### AlarmIncidentSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** search | [optional string](#string) | Search incident text, including identifier, alarm, device, error messages and status. |
| incident_identifier | [repeated string](#string) | Select incidents by identifier. |
|  **optional** alarms | [optional hiber.modem.alarm.ModemAlarmSelection](#hibermodemalarmmodemalarmselection) | Select incidents by alarm. |
|  **optional** devices | [optional hiber.modem.ModemSelection](#hibermodemmodemselection) | Select incidents by device. |
| current_status | [repeated AlarmIncident.Status](#alarmincidentstatus) | Select incidents that currently have one of the given statuses. |
| health_levels | [repeated string](#string) | Select incidents with a given health level. |
|  **optional** include_resolved | [optional bool](#bool) | By default, incidents that have been resolved are not listed. Set this to include them. |


## Enums
### AlarmIncident.Status
The status of the incident.

| Name | Description | Number |
| ---- | ----------- | ------ |
| STARTED | The incident has started, no changes since that moment. | 0 |
| UPDATED | Since the incident started, some of the error messages changed significantly. | 1 |
| ESCALATED | Since the incident started, the health changed. | 2 |
| RESOLVED | The incident has resolved. | 3 |



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
| color | [ string](#string) | <span class="deprecated deprecated-field">Deprecated</span> Default color for the health level, as a string that represents a valid CSS3 color. DEPRECATED: Maps to the color named "text" in color_data. |
| color_data | [map hiber.health.HealthLevel.ColorDataEntry](#hiberhealthhealthlevelcolordataentry) | Map of named colors, where key is the name and the value is a valid CSS3 color definition. |
| severity | [ int64](#int64) | A unique numeric value equal to the index of this health level in the list of health levels sorted by ascending severity (starting at 1). This means higher numbers denote a more severe health. This value cannot be used when creating or updating. To change the severity for a health level, reorder all health levels. |
| catch_all | [ bool](#bool) | Precisely one health level can be assigned as a catch-all for any unknown health levels from alarms (or Hiber systems), which can happen when a device manufacturer has provided alarms for your device (e.g. a low battery alarm). By default, unknown health levels map to the level of the highest severity, unless another level is marked as catch-all. |

### hiber.health.HealthLevelSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** search | [optional string](#string) | Search for the given string in the levels and colors. |
| levels | [repeated string](#string) | Filter by exact levels. |


### Enums


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
| is_gateway | [ bool](#bool) | <span class="deprecated deprecated-field">Deprecated</span> Whether the modem is a gateway, it has been configured as a gateway and has connected devices. Use `type` instead. |
| is_device_connected_to_gateway | [ bool](#bool) | <span class="deprecated deprecated-field">Deprecated</span> Whether the modem is connected to a modem configured as a gateway. Use `type` instead. |
| connected_to_gateway | [ string](#string) | <span class="deprecated deprecated-field">Deprecated</span> The modem number that this modem is connected to, if any. Use `connected_device_info.connected_to_gateway` instead. |
| external_device_ids | [repeated string](#string) | External device ids for this sensor, gateway or valve. |
|  **optional** lora_dev_eui | [optional string](#string) | LoRa DevEUI for this sensor, gateway or valve. |
| device_type | [ string](#string) | Device type for this modem. |
| type | [ hiber.modem.Modem.Type](#hibermodemmodemtype) | The type of modem. Used mainly to differentiate in the UI or to sort on. |
|  **optional** gateway_info | [optional hiber.modem.Modem.GatewayInfo](#hibermodemmodemgatewayinfo) | Additional information when this modem is a gateway. |
|  **optional** connected_device_info | [optional hiber.modem.Modem.ConnectedDeviceInfo](#hibermodemmodemconnecteddeviceinfo) | Additional information when this modem is a connected device. |
|  **optional** valve_info | [optional hiber.modem.Modem.ValveInfo](#hibermodemmodemvalveinfo) | Additional information when this modem is a connected device. |
| metadata | [ google.protobuf.Struct](#googleprotobufstruct) | Modem metadata, typically extracted from messages. |
| time_zone | [ string](#string) | The timezone configured for the modem. |
| transmission_interval | [ hiber.Duration](#hiberduration) | The transmission interval for this modem, if configured. |
|  **optional** expected_transmission_rate | [optional hiber.value.Value.Numeric.Rate](#hibervaluevaluenumericrate) | The expected transmission rate for this modem. |
| numeric_value_types | [repeated hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype) | The numeric value types that this device produces. The device may produce other values (like battery level), but these are the primary value types. |
| files | [repeated hiber.file.File](#hiberfilefile) | Files for this tag. Typically an image of the device installation. See the File.media_type for more information. |
|  **optional** required_device_firmware_identifier | [optional string](#string) |  |
| process_points | [repeated hiber.processpoint.ProcessPoint](#hiberprocesspointprocesspoint) | List of process points that this device is connected to (if you have permission to access them). Some fields might be omitted in this inline view for compactness (like connected devices). |

### hiber.modem.ModemSelection

Selection object for modems.
Filter modems by modem id, (child)organization, tags, activation status and time, service type and last message time.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** modems | [optional hiber.Filter.Modems](#hiberfiltermodems) |  |
|  **optional** free_text_search | [optional string](#string) |  |
|  **optional** only_active | [optional bool](#bool) | <span class="deprecated deprecated-field">Deprecated</span> Use lifecycle filter instead. |
|  **optional** activated_in | [optional hiber.TimeRange](#hibertimerange) | <span class="deprecated deprecated-field">Deprecated</span>  |
|  **optional** with_last_message_in | [optional hiber.TimeRange](#hibertimerange) |  |
| health_levels | [repeated string](#string) | Filter modems by health level. |
| lifecycles | [repeated hiber.modem.Modem.Lifecycle](#hibermodemmodemlifecycle) | Filter modems by lifecycle(s). Defaults to nominal lifecycles, excluding disabled or decommissioned modems. |
|  **optional** transfers | [optional hiber.modem.ModemSelection.Transfers](#hibermodemmodemselectiontransfers) |  |
| include_types | [repeated hiber.modem.Modem.Type](#hibermodemmodemtype) | Only include modems that have a type listed in types. In other words, when providing multiple types, this is an "OR" relationship. |
| exclude_types | [repeated hiber.modem.Modem.Type](#hibermodemmodemtype) | Exclude modems that have a type listed in types. |
|  **optional** device_types | [optional hiber.Filter.DeviceTypes](#hiberfilterdevicetypes) |  |
|  **optional** sensorBrands | [optional hiber.Filter.SensorBrands](#hiberfiltersensorbrands) |  |
|  **optional** identifiers | [optional hiber.Filter.ModemIdentifiers](#hiberfiltermodemidentifiers) |  |
|  **optional** only_gateways | [optional bool](#bool) | <span class="deprecated deprecated-field">Deprecated</span> Only list devices that are a gateway. Replaced by `types`. If you only want to have gateways in the result, create a selection with only `Modem.Type.GATEWAY` for `types`. |
|  **optional** only_has_external_device_ids | [optional bool](#bool) | <span class="deprecated deprecated-field">Deprecated</span> Only list devices that are a connected devices. Typically these are LoRaWAN sensors. Replaced by `types`. If you only want to have connected devices in the result, create a selection with only `Modem.Type.CONNECTED_DEVICE` for `types`. |
|  **optional** connected_to_gateways | [optional hiber.Filter.Modems](#hiberfiltermodems) |  |
| external_device_ids | [repeated string](#string) | <span class="deprecated deprecated-field">Deprecated</span>  |
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
| PROCESS_POINT_ASC | Sort alphabetically on the name of the process point(s) assigned to the modem, in ascending order. | 26 |
| PROCESS_POINT_DESC | Sort alphabetically on the name of the process point(s) assigned to the modem, in descending order. | 27 |
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

#### hiber.modem.Modem.ConnectedDeviceInfo.Frequency
Frequency specified by LoRaWAN regional parameters.

| Name | Description | Number |
| ---- | ----------- | ------ |
| AS923 | AS923 | 0 |
| AS923_2 | AS923-2 | 10 |
| AU915 | AU915 | 1 |
| EU868 | EU868 | 5 |
| IN865 | IN865 | 6 |
| KR920 | KR920 | 7 |
| US915 | US915 | 8 |
| US915_HYBRID | US915-Hybrid | 9 |

#### hiber.modem.Modem.Lifecycle


| Name | Description | Number |
| ---- | ----------- | ------ |
| ACCEPTANCE_TESTING | Device is being tested by Hiber. Devices in this state are not visible to customers. | 0 |
| READY_TO_INSTALL | Device has passed Acceptance Testing and is ready be installed. When it sends it first message, it will automatically go to INSTALLED. | 8 |
| INSTALLED | Device is active and sending messages. | 1 |
| PAUSED | Device is paused and not sending messages. This should be of a temporary nature (e.g. a change to the installation is being made). On its next message, it will automatically go back to INSTALLED. Offline alarm checks will not be triggered for devices in this lifecycle. | 6 |
| DISABLED | Device is disabled and not sending messages. This is a more permanent version of PAUSED. Devices in this state are not visible to customers. | 5 |
| DECOMMISSIONED | Device is (going to be) removed from installation and will not return to installed status again. Devices in this state are not visible to customers. | 4 |
| DEFECTIVE | Device is defective and should not be used anymore. Devices in this state are typically RMA-ed and (should be) transferred to the RMA organization. Devices in this state are not visible to customers. | 7 |
| PENDING_MAINTENANCE | Device is defective in some way and needs maintenance to operate optimally. Devices in this state should be highlighted as they need to be acted upon. | 11 |
| PENDING_REPLACEMENT | Device is defective and needs to be replaced. Devices in this state should be highlighted as they need to be acted upon. | 12 |
| SPARE | Spare device sent to customer in case it is needed. | 9 |

#### hiber.modem.Modem.Type
The effective type of this modem.
Type can depend on the hardware itself as well as network topology.

| Name | Description | Number |
| ---- | ----------- | ------ |
| OTHER | A device of which the specific type is not known | 0 |
| GATEWAY | A device that can receive messages from sensors in the field and relay them (directly) to the satellite. Typically a LoRaWAN hub. Note that gateways also send messages themselves (e.g. a daily heartbeat). | 2 |
| SENSOR | A sensor that can (only) send data to a gateway. Typically using a LoRaWAN connection. | 3 |
| VALVE |  | 4 |

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
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **assign_to**.process_points | [ hiber.processpoint.ProcessPointSelection](#hiberprocesspointprocesspointselection) |  |
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
| alarm_incident_identifiers | [repeated string](#string) | Select alarm from the incident identifier(s). |

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
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unassign_from**.process_points | [ hiber.processpoint.ProcessPointSelection](#hiberprocesspointprocesspointselection) |  |

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
|  **optional** update_name | [optional hiber.UpdateClearableString](#hiberupdateclearablestring) | <span class="deprecated deprecated-field">Deprecated</span> Update the name, optionally. |
|  **optional** name | [optional string](#string) |  |
|  **optional** update_description | [optional hiber.UpdateClearableString](#hiberupdateclearablestring) | <span class="deprecated deprecated-field">Deprecated</span> Update the description, optionally. |
|  **optional** description | [optional string](#string) |  |
|  **optional** update_trigger_condition | [optional hiber.modem.alarm.ModemAlarm.TriggerCondition](#hibermodemalarmmodemalarmtriggercondition) | Update the trigger condition, optionally. |
|  **optional** update_default_health_level | [optional hiber.UpdateClearableString](#hiberupdateclearablestring) | <span class="deprecated deprecated-field">Deprecated</span> Update the default health level, optionally. |
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

