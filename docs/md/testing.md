# testing.proto



#### This file was generated from [testing.proto](https://github.com/HiberGlobal/api/blob/master/testing.proto).

## Table of Contents

- Services
  - [SimulationService](#simulationservice)
  - [TestingService](#testingservice)

- Messages
  - [PushModemMessagesFromDebugPortRequest](#pushmodemmessagesfromdebugportrequest)
  - [PushModemMessagesFromDebugPortRequest.Response](#pushmodemmessagesfromdebugportrequestresponse)
  - [PushModemMessagesRequest](#pushmodemmessagesrequest)
  - [PushModemMessagesRequest.MessageToPush](#pushmodemmessagesrequestmessagetopush)
  - [PushModemMessagesRequest.Response](#pushmodemmessagesrequestresponse)
  - [Simulation](#simulation)
  - [Simulation.DelayedMessageSimulation](#simulationdelayedmessagesimulation)
  - [Simulation.GetRequest](#simulationgetrequest)
  - [Simulation.ModemInactivitySimulation](#simulationmodeminactivitysimulation)
  - [Simulation.ModemMessageSimulation](#simulationmodemmessagesimulation)
  - [Simulation.ModemMessageSimulation.Defaults](#simulationmodemmessagesimulationdefaults)
  - [Simulation.ModemMessageSimulation.Delete](#simulationmodemmessagesimulationdelete)
  - [Simulation.ModemMessageSimulation.Delete.Request](#simulationmodemmessagesimulationdeleterequest)
  - [Simulation.ModemMessageSimulation.Delete.Response](#simulationmodemmessagesimulationdeleteresponse)
  - [Simulation.ModemMessageSimulation.List](#simulationmodemmessagesimulationlist)
  - [Simulation.ModemMessageSimulation.List.Request](#simulationmodemmessagesimulationlistrequest)
  - [Simulation.ModemMessageSimulation.List.Response](#simulationmodemmessagesimulationlistresponse)
  - [Simulation.ModemMessageSimulation.LocationRotation](#simulationmodemmessagesimulationlocationrotation)
  - [Simulation.ModemMessageSimulation.MessageBodyRotation](#simulationmodemmessagesimulationmessagebodyrotation)
  - [Simulation.ModemMessageSimulation.Summary](#simulationmodemmessagesimulationsummary)
  - [Simulation.ModemMessageSimulation.Update](#simulationmodemmessagesimulationupdate)
  - [Simulation.ModemMessageSimulation.Update.Request](#simulationmodemmessagesimulationupdaterequest)
  - [Simulation.ModemMessageSimulation.Update.Response](#simulationmodemmessagesimulationupdateresponse)
  - [Simulation.UpdateRequest](#simulationupdaterequest)

- Enums

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
  - [hiber.Filter.HealthLevels](#hiberfilterhealthlevels)
  - [hiber.Filter.ModemIdentifiers](#hiberfiltermodemidentifiers)
  - [hiber.Filter.Modems](#hiberfiltermodems)
  - [hiber.Filter.Modems.Update](#hiberfiltermodemsupdate)
  - [hiber.Filter.OrganizationPermissions](#hiberfilterorganizationpermissions)
  - [hiber.Filter.Organizations](#hiberfilterorganizations)
  - [hiber.Filter.Properties](#hiberfilterproperties)
  - [hiber.Filter.Publishers](#hiberfilterpublishers)
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


## SimulationService
Simulation service to manage active simulations.
Simulation can help fill in the gaps until real data is present, by, for example, simulating messages from a device.

### Get
> **rpc** Get([Simulation.GetRequest](#simulationgetrequest))
    [Simulation](#simulation)



### Update
> **rpc** Update([Simulation.UpdateRequest](#simulationupdaterequest))
    [Simulation](#simulation)



### ListModemMessageSimulations
> **rpc** ListModemMessageSimulations([Simulation.ModemMessageSimulation.List.Request](#simulationmodemmessagesimulationlistrequest))
    [Simulation.ModemMessageSimulation.List.Response](#simulationmodemmessagesimulationlistresponse)



### UpdateModemMessageSimulations
> **rpc** UpdateModemMessageSimulations([Simulation.ModemMessageSimulation.Update.Request](#simulationmodemmessagesimulationupdaterequest))
    [Simulation.ModemMessageSimulation.Update.Response](#simulationmodemmessagesimulationupdateresponse)



### DisableModemMessageSimulations
> **rpc** DisableModemMessageSimulations([Simulation.ModemMessageSimulation.Delete.Request](#simulationmodemmessagesimulationdeleterequest))
    [Simulation.ModemMessageSimulation.Delete.Response](#simulationmodemmessagesimulationdeleteresponse)





## TestingService
Method to test the system in different ways, meant for customer access. For example, you can use this to test
whether everything works from message to webhook call, and further in your own system.

### PushModemMessages
> **rpc** PushModemMessages([PushModemMessagesRequest](#pushmodemmessagesrequest))
    [PushModemMessagesRequest.Response](#pushmodemmessagesrequestresponse)



### PushModemMessagesFromDebugPort
> **rpc** PushModemMessagesFromDebugPort([PushModemMessagesFromDebugPortRequest](#pushmodemmessagesfromdebugportrequest))
    [PushModemMessagesFromDebugPortRequest.Response](#pushmodemmessagesfromdebugportrequestresponse)




## Messages

### PushModemMessagesFromDebugPortRequest

Push a message using the data gotten from the modem debug port.
This means the message is an encrypted string, which the server can parse.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| encoded_messages | [repeated string](#string) | none |

### PushModemMessagesFromDebugPortRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ PushModemMessagesFromDebugPortRequest](#pushmodemmessagesfromdebugportrequest) | none |

### PushModemMessagesRequest

Push any number of modem messages. These are marked as test messages, which means they will be treated
differently in a few places (i.e. message sequence, to avoid errors on the next real messages).
The message is handled like a real message, it's encrypted as if sent from a modem, then goes through
the decryption process and all relevant events are triggered (including webhooks calls caused by the events).

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| messages | [repeated PushModemMessagesRequest.MessageToPush](#pushmodemmessagesrequestmessagetopush) | none |

### PushModemMessagesRequest.MessageToPush



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem_number | [ string](#string) | none |
| time | [ hiber.Timestamp](#hibertimestamp) | none |
| location | [ hiber.Location](#hiberlocation) | none |
| content | [ bytes](#bytes) | none |
| metadata | [ google.protobuf.Struct](#googleprotobufstruct) | Metadata for this message. For example: LoRaWAN values like fPort. |

### PushModemMessagesRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| request | [ PushModemMessagesRequest](#pushmodemmessagesrequest) | none |

### Simulation

Simulation settings for this organization.

The simulation settings for an organization can be used to configure some organization-wide setting for
specific simulations, like a default for the number of messages to simulate per enabled modem), or configuring
a percentage of simulated messages to trigger a delayed event.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | none |
| enabled | [ bool](#bool) | Whether or not all simulations for this organization are enabled. |
| modem_inactivity | [ Simulation.ModemInactivitySimulation](#simulationmodeminactivitysimulation) | Configuration for simulating modem inactivity. |
| delayed_messages | [ Simulation.DelayedMessageSimulation](#simulationdelayedmessagesimulation) | Configuration for simulating delayed messages. |
| modem_message_simulation_defaults | [ Simulation.ModemMessageSimulation.Defaults](#simulationmodemmessagesimulationdefaults) | Default configuration for the modem message simulation. |
| modem_message_simulation | [ Simulation.ModemMessageSimulation.Summary](#simulationmodemmessagesimulationsummary) | Summary of modems with message simulation. |

### Simulation.DelayedMessageSimulation

Simulate delayed messages.

Requires modems with message simulation.
Adds a random delay between minimum_message_delay and maximum_message_delay to a percentage of messages
generated by the modem message simulation.
The messages themselves are not actually delayed; this just sets the sent time further into the past.

| Field | Type | Description |
| ----- | ---- | ----------- |
| percentage_of_simulated_messages | [ uint32](#uint32) | none |
| minimum_message_delay | [ hiber.Duration](#hiberduration) | none |
| maximum_message_delay | [ hiber.Duration](#hiberduration) | none |

### Simulation.GetRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |

### Simulation.ModemInactivitySimulation

Simulate modem inactivity randomly.

Requires modems with message simulation.
For all those modems, randomly picks modems up to the configured percentage to be inactive.
Those modems are excluded from the simulation for a period between period_min and period_max.
When a modem is no longer inactive, another modem is randomly picked to be inactive. This allows you to test
inactivity detection, health, etc.

This does not affect messages that are not simulated (like test messages or real messages).

| Field | Type | Description |
| ----- | ---- | ----------- |
| percentage_of_simulating_modems | [ uint32](#uint32) | none |
| period_min | [ hiber.Duration](#hiberduration) | none |
| period_max | [ hiber.Duration](#hiberduration) | none |

### Simulation.ModemMessageSimulation



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem_number | [ string](#string) | none |
| messages_per_interval | [ uint32](#uint32) | The number of simulated messages per day for this modem. This value is either the custom amount per day for this modem or the default value |
| simulation_interval | [ hiber.Duration](#hiberduration) | Interval messages should be simulated at (i.e. once every hour). |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **message_bodies**.message_body | [ hiber.BytesOrHex](#hiberbytesorhex) | A message body to use for the simulated messages. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **message_bodies**.message_body_rotation | [ Simulation.ModemMessageSimulation.MessageBodyRotation](#simulationmodemmessagesimulationmessagebodyrotation) | Rotate through a list of message bodies. |
| message_body_variable_byte_indices | [repeated uint32](#uint32) | The indices of bytes in the message body that should be randomized (to have variable values). |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **location**.random_location_in_area | [ hiber.Area](#hiberarea) | Randomize modem location within the given area. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **location**.location_rotation | [ Simulation.ModemMessageSimulation.LocationRotation](#simulationmodemmessagesimulationlocationrotation) | Rotate through a list of locations. |
| next_simulation_run_after | [ hiber.Timestamp](#hibertimestamp) | Timestamp after which the next simulation run will be triggered (not guaranteed to be exactly at this time). If further in the future, message simulation for this modem is inactive until this time. This may be set to a time in the future manually, or by the ModemInactivitySimulation. |

### Simulation.ModemMessageSimulation.Defaults



| Field | Type | Description |
| ----- | ---- | ----------- |
| messages_per_interval | [ uint32](#uint32) | Default for the amount of messages to simulate per interval for a modem that has simulation enabled. Must be between 1 and 24 (for a maximum of 240 message per day). |
| simulation_interval | [ hiber.Duration](#hiberduration) | Default for interval messages should be simulated at (i.e. once every hour). |

### Simulation.ModemMessageSimulation.Delete




### Simulation.ModemMessageSimulation.Delete.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | none |

### Simulation.ModemMessageSimulation.Delete.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| deleted | [ uint32](#uint32) | none |
| request | [ Simulation.ModemMessageSimulation.Delete.Request](#simulationmodemmessagesimulationdeleterequest) | none |

### Simulation.ModemMessageSimulation.List




### Simulation.ModemMessageSimulation.List.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |
| include_disabled | [ bool](#bool) | Include modems for which message simulation is disabled. |

### Simulation.ModemMessageSimulation.List.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [repeated Simulation.ModemMessageSimulation](#simulationmodemmessagesimulation) | none |
| request | [ Simulation.ModemMessageSimulation.List.Request](#simulationmodemmessagesimulationlistrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### Simulation.ModemMessageSimulation.LocationRotation

Rotate through a list of locations.

| Field | Type | Description |
| ----- | ---- | ----------- |
| locations | [repeated hiber.Location](#hiberlocation) | The rotating list of locations to use when simulating messages. |

### Simulation.ModemMessageSimulation.MessageBodyRotation

Rotate through a list of message bodies.

| Field | Type | Description |
| ----- | ---- | ----------- |
| message_bodies | [repeated hiber.BytesOrHex](#hiberbytesorhex) | The rotating list of message bodies to use when simulating messages. |

### Simulation.ModemMessageSimulation.Summary



| Field | Type | Description |
| ----- | ---- | ----------- |
| enabled_modems | [ uint32](#uint32) | The number of modems for which message simulation has been enabled. |
| active_modems | [ uint32](#uint32) | The number of modems that are actively simulating messages. |
| inactive_modems | [ uint32](#uint32) | The number of modems that have been marked inactive (by ModemInactivitySimulation or a user). |
| total_messages_per_day | [ uint32](#uint32) | The total amount of messages that will be simulated in this organization per day. |
| total_simulations_per_day | [ uint32](#uint32) | The number of modem message simulation runs for this organization per day. |

### Simulation.ModemMessageSimulation.Update

Create or update the modem message simulation for a selection of modems.


### Simulation.ModemMessageSimulation.Update.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | Modems to create or update the message simulation for. |
| messages_per_interval | [ uint32](#uint32) | The number of simulated messages per simulation interval for these modems. This value is either the custom amount per day for these modems or the default value |
| simulation_interval | [ hiber.Duration](#hiberduration) | Interval messages should be simulated at (i.e. once every hour). |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **message_body**.update_message_body | [ hiber.BytesOrHex.Update](#hiberbytesorhexupdate) | A message body to use for the simulated messages. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **message_body**.replace_message_body_rotation | [ Simulation.ModemMessageSimulation.MessageBodyRotation](#simulationmodemmessagesimulationmessagebodyrotation) | Replace the list of message bodies to rotate through. This does not have to match the length of the location rotation, if any. Note that this **replaces** the entire list of values, to ensure the order is maintained. |
| message_body_add_variable_byte_indices | [repeated uint32](#uint32) | Add indices of bytes in the message body that should be randomized (to have variable values). |
| message_body_remove_variable_byte_indices | [repeated uint32](#uint32) | Remove indices of bytes in the message body that should be randomized (to have variable values). |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **location**.random_location_in_area | [ hiber.Area](#hiberarea) | Randomize modem location within the given area. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **location**.replace_location_rotation | [ Simulation.ModemMessageSimulation.LocationRotation](#simulationmodemmessagesimulationlocationrotation) | Replace the list of locations to rotate through. This does not have to match the length of the message body rotation, if any. Note that this **replaces** the entire list of values, to ensure the order is maintained. |
| set_inactive_until | [ hiber.Timestamp](#hibertimestamp) | Disable the message simulation until the given date (UTC). |
| pagination | [ hiber.Pagination](#hiberpagination) | none |

### Simulation.ModemMessageSimulation.Update.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modems | [repeated Simulation.ModemMessageSimulation](#simulationmodemmessagesimulation) | none |
| request | [ Simulation.ModemMessageSimulation.Update.Request](#simulationmodemmessagesimulationupdaterequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### Simulation.UpdateRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| enabled | [ hiber.UpdateBoolean](#hiberupdateboolean) | none |
| simulate_modem_inactivity | [ Simulation.ModemInactivitySimulation](#simulationmodeminactivitysimulation) | none |
| simulate_delayed_messages | [ Simulation.DelayedMessageSimulation](#simulationdelayedmessagesimulation) | none |
| modem_message_simulation_defaults | [ Simulation.ModemMessageSimulation.Defaults](#simulationmodemmessagesimulationdefaults) | none |


## Enums


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
| ACCEPTANCE_TESTING | Device is deployed, but not active yet. Invisible for customer. | 0 |
| INSTALLED | Device is active and sending messages. See health for more details on its health, based on the past messages. | 1 |
| PAUSED | Device is paused and not sending messages. This should be of a temporary nature. (e.g. a change to the installation is being made) | 6 |
| DISABLED | Device is disabled and not sending messages. Invisible for customer. This could be either temporary or become permanent. Used for cases where devices is being serviced and customer should not be burdened with the health of this device. | 5 |
| DECOMMISSIONED | Device is (going to be) removed from installation and will not return to installed status again. | 4 |
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
| MODEM_TRANSFER_STARTED | none | 17 |
| MODEM_TRANSFER_RECEIVED | none | 18 |
| MODEM_TRANSFER_CANCELLED | none | 19 |
| MODEM_TRANSFER_NOT_RECEIVED | none | 20 |
| MODEM_TRANSFER_RETURN_TRANSFER_STARTED | none | 21 |
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

