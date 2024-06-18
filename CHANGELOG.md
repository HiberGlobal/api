# Changelog Hiber API

### 0.197 (2024-06-18)

##### CurrentUserService

- Fixed a bug where `CurrentUser` would return an inaccessible default organization when using a token from a child organization.
- Adjusted `CurrentUser` to allow it to be used with a token with `UserPermission.READ` by limiting the data returned, but still returning permissions and roles.

### 0.196 (2024-06-11)

##### UserService

- Added `UserValidation.allowed_sign_in_providers` to limit the sign in providers for an organization.
  - Added `UserValidation.SignInProvider` list of supported sign in providers.
    - If any new providers would be added, and a limitation is in place, they are excluded by default.

##### ValueService

- Fixed a bug where downsampled values were duplicated is mutiple devices were selected.

### 0.195 (2024-06-04)

##### FieldService

- Added `ForAsset` to list the fields for an asset.

##### ValueService

- Added `assets` to `ValueSelection`, in a `oneof`, so a selection selects either assets or devices.
  - Renamed `modems` to `devices`.
- Added `assets` to `ValueContext` for values for assets.
- Renamed `modem` to `device` in `ValueContext`.
- Marked `AggregatedValues.location` optional instead of deprecated.

##### AssignmentService

- Removed the option for future time values for assignment, since it has unintended consequences.

##### AssetService

- Removed the option for future time values for assignment, since it has unintended consequences.

### 0.192 (2024-05-14)

##### AssignmentService

- Added `override_time` and `schedule_end_time` to `Assign.Request` to customize the assignment time.
- Added `override_time` to `Unassign.Request` to customize the unassignment time.
- Added `include_inactive_assignments` to `ListAssignments.Request` to list inactive assignments.
  - Assignments that no longer have an effect while inactive may be removed automatically.

### 0.191 (2024-04-30)

##### AssetService

- Introducing `Asset`s as the conceptual counterpart of the devices.
  - Assets are abstractions managed by the customer and linked to devices.
  - Assets will own data (values) produced by devices, but when a device is replaced, the asset's values will just
    continue with the data from the new device.
  - Assets have type for common use cases (currently well-related Annulus A/B/C/D and tubing head pressure).
    - Asset are not limited to the predefined types, they can be anything that is required to collect data
      into one place.
  - Assets will get SLA configuration and calculate SLAs.
    - We will phase out SLA configuration on devices slowly.

##### base.proto

- Deprecated the `Update*` types in favor of using `optional` fields.
  - Deprecated `UpdateZeroableInt`.
  - Deprecated `UpdateClearableString`.
  - Deprecated `UpdateOptionalId`.
  - Deprecated `UpdateOptionalDuration`.
  - Deprecated `UpdateBoolean`.
  - Deprecated `Filter.ChildOrganizations.Update`.
  - Deprecated `Filter.Events.Update`.
  - Deprecated `Filter.Modems.Update`.
  - Deprecated `Filter.Tags.Update`.
  - Deprecated `BytesOrHex.Update`.
  - Updated a lot of services to use `optional` instead of `Update*` types.

##### Organization Permissions

- Split the `MODEMS_ALARMS` permission to manage alarms into a view permission `MODEMS_ALARMS` and manage permission `MODEMS_ALARMS_UPDATE`.
  - Roles have been updated to keep effective permissions consistent, but new roles will have more granularity.

### 0.188 (2024-04-09)

##### All proto files

- Added optional flag in many places to explicitly indicate optionality.
- Deleted a large number of deprecated rpc and messages:
  - `MesageService/AvailableBodyFields` - use FieldService/List instead
  - `ModemService/MessageCount` - no longer in use
  - `ModemService/RenameModem` - use DeviceService/Update instead
  - `ModemService/UpdateNotes` - use DeviceService/Update instead
  - `ModemService/UpdateSecureNotes` - use DeviceService/Update instead
  - `ModemService/UpdateLifecycle` - use DeviceService/Update instead
  - `ModemService/UpdatePeripherals` - use DeviceService/Update instead
  - `ModemService/HealthCount` - no longer in use
  - `Testingservice/PushModemMessagesFromDebugPort` - no longer in use

##### EventService

- `DeviceUpdatedEvents` are now also generated for device type changes.

##### ModemService

- When your device sends an info message (typically on startup) we automatically assign the device type.
  - If the device already has a device type, it will not be replaced.

### 0.186 (2024-03-19)

##### ModemService

- `Modem.lifecycle` will now automatically switch to `INSTALLED` on a new message, when the `lifecycle` was:
  - `PAUSED`
  - `READY_TO_INSTALL`

### 0.185 (2024-03-12)

##### AlarmService

- Add `BlockedRangeCheck` as an explicit inverted `ThresholdCheck`.
  - Creating a `ThresholdCheck` where `minimum` > `maximum` automatically creates a `BlockedRangeCheck`.
  - Creating a `BlockedRangeCheck` where `minimum` > `maximum` automatically creates a `ThresholdCheck`.

##### UserService

- Fixed a bug where a user that was invited and removed from an organization could not be invited again.

##### ModemService

- Added a new lifecycle: `READY_TO_INSTALL` to `Modem.Lifecycle`.
- Updated the documentation for `Modem.Lifecycle` to be more clear.

### 0.183 (2024-02-27)

##### ValueService

- Added a number of Flow units and a Speed unit, with conversion
- Fixed a bug in the conversion from bbl/d to m^3/h
- Improved documentation for units
- Fixed a bug where precision could be lost when units were converted
  - This was mostly unnoticable with the rounding in the UI, but still a bug
  - This bug could be seen when using unit conversion in alarms

##### UserService

- Added `child_organizations` to `ListUsersRequest` to list users from child organizations.
  - Added `organization` to `User` to support this feature.

### 0.181 (2024-02-13)

##### Value

- Renamed `Value.Numeric.*.Unit` to specific names, to make it the enum names clearer.

### 0.180 (2024-02-06)

##### EventService

- Updated event titles and descriptions to match the renaming in the previous release.

##### UserService

- Fixed a bug where `UpdateUserRoles` would sometimes incorrectly reject the new roles.

### 0.179 (2024-01-30)

##### Json generated documentation

- Generated documentation for enums into json format, to have easily accessible values and descriptions.

##### EventService

- Renamed and moved a number of events and event fields to better reflect reality (vs when they were defined).

##### EventType

- Documented the event types with a short description.

##### UserService

- Fixed a bug where `Remove` did not remove access requests.

### 0.178 (2024-01-23)

##### TokenService

- Fix a bug where the user id would not be set in the details if the user does not exists in the organization.
  (Other details are still omitted when the user is not in the organization)

### 0.177 (2024-01-16)

##### ModemMessagePayloadParserService

- Fixed a bug in `Retry` where the `parser_selection` was ignored for some modems.
- Fixed a bug in `Retry` where the `require_message_metadata` of parsers was not checked when retrying, leading to parser errors.

##### OrganizationPermissions

- Added `TAGS_MANAGE` permission for creating, updating and deleting tags.

##### SupportPermissions

- Added `MANAGE_DEVICE_TIME_ZONE` to replace `CUSTOMER_SUPPORT` for updating time zone.

### 0.176 (2023-12-19)

##### ModemService

- Fixed a bug in `Grouped` where the total count did not include devices in child organizations.
- Better validation when explicit modems are given, but not found.
  This could previously result in an empty result, or those items missing from the list.
  Now, a proper error is given that you have provided a modem you do not have access to.
  - This fix also applies to other usages for the ModemSelection object.

##### SupportPermissions

- Added `MANAGE_DEVICE_TRANSMISSION_INTERVAL` to replace `CUSTOMER_SUPPORT` for updating transmission interval.
- Added `MANAGE_DEVICE_SLA` to replace `CUSTOMER_SUPPORT` for updating SLA configuration.
- Added `DEVICE_VIEW_ALL_LIFECYCLES` to replace `CUSTOMER_SUPPORT` for seeing all possible lifecycles.
- Added `MANAGE_DEVICE_NOTES` to replace `CUSTOMER_SUPPORT` for updating customer support device notes.

##### TokenService

- Add `user_details`, including name and email address, of the token owner, to `Token`.

##### UserService

- Added `support_permissions` to `User` and `UserSelection`.
- Removed all options to set individual permissions on users
  - Removed deprecated `UpdateUserPermissions`.
  - Removed deprecated option `permissions` in
    - `ApproveUserRequest`
    - `InviteUserRequest`
    - `CreateUserRequest`
    - `CreateUsersRequest`
  - Renamed `override_allow_no_permissions` to `override_allow_no_roles` in
    - `ApproveUserRequest`
    - `InviteUserRequest`
    - `CreateUserRequest`
    - `CreateUsersRequest`

### 0.175 (2023-12-12)

##### ValueService

- Do not omit trailing 0s, but output the digits expects from unit format preferences and field format preferences.

##### ModemService

- List all external identifier variations in `Modem.ConnectedDeviceInfo.external_device_ids`.

### 0.174 (2023-12-05)

##### DeviceTypeService

- Added new device types to parse both pressure and temperature.

##### ModemMessageBodyParserService

- Fixed a bug where the `operational` flag on data fields was not saved correctly, which resulting in operation values like reboot count showing up in the dashboards.

##### TokenService

- Added `CreateTokenRequest.for_user_id` to create a token for another user.
  To do so, you must have the USERS_MANAGE permission and you must both have the permissions granted to the new token.
  As such, user permissions are not allowed when creating a token like this.

##### Publishers

- Fixed a bug where retry would not be triggered for publishers (webhooks, mqtt, shell-ssip)

### 0.173 (2023-11-28)

##### MQTTIntegrationService

- Improved at-rest encryption of MQTT call history

##### SlackService

- Improved at-rest encryption of slack call history

##### WebhookService

- Improved at-rest encryption of webhook history

##### UserService

- Fixed a bug where email subscriptions could remain active after a user was removed from the organization.

##### TokenService

- Fix a bug in the validation for the expiry date for tokens.

### 0.172 (2023-11-21)

##### WebhookService

- Replaced the http client library used for webhook calls with one that is better maintained.

##### ModemService

- Fix a bug where `gateway_info` was set for devices.

##### UnitPreferencesService

- Renamed `unit` and `unit_category` in preference messages to `preference` for simplicity.

##### FieldService

- Introduced `operational` fields. Fields represent operational time-series data and are hidden by default.

### 0.171 (2023-11-14)

##### UserService

- Deprecated all options to set individual permissions on users, in favor of using roles:
  - Deprecated `ApproveUserRequest.permissions`.
  - Deprecated `InviteUserRequest.permissions`.
  - Deprecated `CreateUserRequest.permissions`.
  - Deprecated `CreateUsersRequest.permissions`.
  - Deprecated `UpdateUserPermissionsRequest`.

##### ModemService

- Removed deprecation on `ListModemsRequest.child_organizations`.

### 0.168 (2023-10-24)

##### CurrentUserService

- Added `OverrideRoles` and `RestoreRoles` to temporarily override and restore roles.

##### RoleService

- Moved `RoleService` to `role_service.proto`, split off from `role.proto`, for cleaner imports.
- Added `Override` and `Restore` to temporarily override and restore roles.

##### TokenService

- Added `Token.Type` to indicate the type of token:
  - `SPECIFIC`: has a specified set of permissions. All tokens before this release were specific.
  - `PERSONAL`: uses the user's roles and permissions
- Added `Token.type` and `CreateTokenRequest.type` to use the new type.
- Added `TokenSelection.type` to list specific token types.

### 0.167 (2023-10-17)

##### AlarmService

- Fixed a bug where an out-of-order message could trigger an inactivity check (by scheduling the trigger from its sent time).

##### ModemService

- Added `total` to `ListModemsGrouped.Response` for convenience, since the pagination was not sufficient to get totals.

##### RoleService

- Added `description` to `Role`.
- Added `support_permissions` to `Role` for some Hiber employees.

##### UserService

- Fixed a bug where updating roles would still allow you to reduce a user to have no permissions.
  - Added `override_allow_no_permissions` to `UpdateUserRoles.Request`.

### 0.166 (2023-10-10)

##### RoleService

- Introduced the `RoleService` to list available `Role`s.
  - A `Role` is a named collection of `OrganizationPermission`s.

##### TokenService

- Added `roles` to `Token`
  - Added `roles` to `TokenSelection` to select tokens with specific roles.
  - Added `roles` to `CreateTokenRequest` to create a token with roles.
  - Added `UpdateTokenRoles` to update the roles on a token.

##### UserService

- Introducing the concept of roles to the system.
  Roles group permissions and impersonation limitations in one place.
  - Added `roles` to `User` to see the roles a user has.
  - Added `roles` to `ApproveUserRequest`, `InviteUserRequest`, `CreateUserRequest` and `CreateUsersRequest`, where users are added.
  - Added `UserSelection.roles` to list the users with a given (set of) roles.
  - Added `UserSelection.permissions` to list the users with a given (set of) permissions.
- Fixed an issue where users that let their invite expire could not be invited again.

### 0.164 (2023-09-19)

##### Permissions

- Add a number of new `SupportPermission`s:
  - `MANAGE_ORGANIZATION_FEATURE`: to manage organization features
  - `MANAGE_DEVICE_TYPE` to manage device types
  - `CUSTOM_TAGS` to manage custom tags
  - `INTEGRATION_SHELL_SSIP` to manage the Shell SSIP integration

##### PublisherService

- Add `Data.ShellSsipConfig`, the `SHELL_SSIP` type for Shell SSIP integration.

##### TagService

- Added validation to avoid changing from a default tag type (like well, site or production area) to a custom tag type.

### 0.162 (2023-09-05)

##### ModemService

- Fixed an issue where gateway counts would sometimes count devices that were still in acceptance testing.

##### MessageService

- Fixed an issue where a deprecated call was not updated to use the new device type logic.

##### ValueService

- Added `Value.Numeric.Duration`
  - It is backwards compatible with `Duration` in `base.proto`
  - Replaced `Value.Numeric.DurationUnit` with `Value.Numeric.Duration.Unit` (also backwards compatible, but might require code changes when using the new API version)

##### Technical

- Prepare for database migration (date to be determined), by cleaning up some data and preparing for proper READ-ONLY notifications and banner.

### 0.161 (2023-08-29)

##### ExportService

- Fixed a bug that could break the export list call.

### 0.158 (2023-07-17)

##### ModemService

- Added `Modem.Lifecycle.DEFECTIVE`.

### 0.157 (2023-07-10)

##### AlarmService

- Added support for inverted threshold check, where the value must be outside of the given (inverted) range.

##### DeviceTypeService

- Add `gateway` flag to device type, indicating this is a gateway, and some additional related validation.

##### TagService

- Add `Health` call to list the health for tags.
  - Lists multiple health levels if applicable, the most severe is marked as most severe.

##### ModemService

- Added `TagCount` to count modems per tag.
- Rename some of the values in `Modem.Type` to be more descriptive:
  - `CONNECTED_DEVICE` to `SENSOR`
  - `DEVICE` to `DISCONNECTED_SENSOR`

### 0.156 (2023-06-26)

##### StatusService

- Removed the outdated status service; it was no longer in use and used the old health.

##### ModemService

- Fix a bug where `connected_to_gateway` was not set on modem when showing child organizations.

##### UserService

- Invites now expire after 30 days.
  - This has also been applied to existing invites.

### 0.155 (2023-06-19)

- Refactored encryption logic to allow us to more easily improve encryption (i.e. switching algorithms) in the future

##### DeviceService

- Added the option to sort on tags for some common tag types: 'well', 'site' and 'production_area'.

##### ModemService

- Added the option to sort on tags for some common tag types: 'well', 'site' and 'production_area'.

##### SingleSignOnService

- Removed Dundas option.

### 0.154 (2023-06-12)

##### DeviceService

- Added `DeviceSelection.device_types` to select modems by `device_type`
  and `DeviceSelection.sensor_brand` to select modems by `sensor_brand`.
  - For values, use `DevicTypeService.List`

##### ModemService

- Added `ModemSelection.device_types` to select modems by `device_type`
  and `ModemSelection.sensor_brand` to select modems by `sensor_brand`.
  - For values, use `DevicTypeService.List`

### 0.153 (2023-06-05)

##### ValueService

- Fixed a bug where rotation speed and rate value were not set correctly in the API response.

### 0.152 (2023-05-29)

##### AlarmService

- Removed unused field `UpdateModemAlarmUpdateCheck.Request.update_using_parameters`.

##### EventService

- Added `resolved` and `resolve_identifier` (in a `one-of`, since it cannot have both) to top-level `Event`.
- Fixed a bug where `ModemHealth` would return non-modem events with health.

##### ValueService

- Fixed a bug where rotation speed and rate value were not set correctly in the API response.

### 0.151 (2023-05-22)

##### DeviceService

- Added `Device.type` to indicate the device type.

##### DeviceTypeService

- Added the `DeviceTypeService` to list available device types.

##### FieldService

- Added modem `name` and `identifier` to `ListFieldsForModem.Response.ModemWithFields`.

##### ModemService

- Added `Modem.ConnectedDeviceInfo.device_type` to indicate the device type.
- Added blocking logic for gateways (i.e. when license expires)

##### TokenService

- Added uniqueness check on token name (for active tokens) within organization.

### 0.148 (2023-04-17)

##### EventService

- Fix a bug where events from transferred modems would be fetched, resulting in errors.

##### ModemTransferService

- Removed the deprecated `ModemTransferService` and related fields

##### ModemTransferReturnService

- Removed the deprecated `ModemTransferReturnService`.

##### EventService

- Removed `deprecated_transfer` from `TransferEvent`.

##### EventService

- Added `ModemHealth` call, which returns all events that affect modem health in the organization (without time limit).

### 0.144 (2023-03-20)

##### AlarmService

- Fix a bug where `search` did not search on `name`.

##### HealthService

- Changed the default health levels:
  - "Error" to "Alarm"
  - "Warning" to "Build up"
  - "Ok" to "Healthy"

### 0.143 (2023-03-13)

##### EmailNotificationPreferencesService

- Email notifications for devices that are not installed are no longer sent unless you are a customer support user.

##### ValueService

- Added `downsampled` command (with `DownsampledValues`) to algorithmically downsample the selected values to a number of points.
  - Use `points` or `pagination.size` to specify the amount of points. If not specified, default pagination size is used.
    - Note that when both `points` (i.e. 1000) and `pagination.size` (i.e. 100) are given, the points are paginated.

##### MQTTService

- Enabled retry mechanism for MQTT publishers.

### 0.142 (2023-02-27)

##### ModemService

- Transmission interval can only be changed when you have the CUSTOMER_SUPPORT support permission.

### 0.141 (2023-02-20)

##### ModemService

- Fixed bug where text search would be case sensitive for modem tags.

### 0.140 (2023-02-13)

##### ModemMessageBodyParserService

- Removed deprecated field `data_fields_deprecated`
- Added field `metadata_fields.require_message_metadata` to replace `require_message_metadata`
- Deprecated field `require_message_metadata`

##### EventService

- Changed the title and description for `ModemEvent.MessageEvent.ModemMessageCannotBeParsedEvent`
  to reflect that this is a configuration issue that hiber support should solve.

### 0.139 (2023-02-06)

##### ModemService

- Removed deprecated lifecycle values `LOST` and `DAMAGED` from `Modem.Lifecycle`.

### 0.138 (2023-01-30)

##### ModemAlarmService

- Removed `available_to_child_organizations` from `ModemAlarm`.
  - Inheritance was not really used, so we opted to remove it.
  - Removed `UpdateAvailability`, `MakeAvailableToChildOrganization` and `MakeUnavailableToChildOrganization` calls.
  - Removed `only_owned_alarms` and `owner_organizations` from `ModemAlarmSelection`.

##### Units

- Added new unit *barrels per day* (`bbl/d`) for usage in all calls/responses that use `flow` values.

##### base.proto

- We now always set the `time_zone` in `Timestamp`, typically "UTC".

### 0.137 (2023-01-23)

- Removed all satellite-related leftovers:
  - Removed `satellite.proto` which contained the unused `SatelliteService`.
  - Removed `GroundStation` and `Satellite` from `map.proto`.
    - Removed `include_ground_stations` and `include_satellites` from `TileMapRequest`.
    - Removed `ground_stations` and `satellites` from `TileMapRequest.Response`.
  - Removed `ground_stations` and `satellites` from `StatusRequest.Response`.
- Removed `subscription.proto` and `ModemSelection.with_service_type`.

### 0.136 (2023-01-16)

##### AssignmentService

- Limited (un)assigning parsers to the owners of those parsers.
  - Inherited parsers can now only be (un)assigned by their owners, impersonated into the child organization.

##### ModemTransferService

- Deprecated the ModemTransferService to be replaced by the much simpler TransferService.
  - Reimplemented the ModemTransferService with the TransferService where possible.
    - Some new limitation apply to the ModemTransferService because of this:
      - transfers are always marked as received immediately
      - returns are no longer supported

##### TransferService

- Introduced the TransferService as simple reimplementation of the transfer logic.
  - Instead of marking received / not received, etc, a transfer is now automatic.
    - Transfers are only allowed if you have access to the recipient organization.

#### Events

- Message export ready event will now contain modem tags in the description.

##### OrganizationService

- Removed the confirmation flow for organization delete.

### 0.135 (2023-01-02)

##### ModemMessageBodyParserService

- Added possibility to define a filter on modem message metadata.
  The parser will only be applied to a message if the metadata matches.

##### ValueService

- Fixed a bug where modem data was merged together when requesting data for multiple modems.
- Fixed a bug where the modem field was never set.

##### ModemClaimService

- Removed the modem claim service.
  - The proto is left in place to not break build immediately, but the service itself wil no longer be supported.

##### EasypulseService

- Removed the Easypulse service.

##### OrganizationService

- Removed the Easypulse-related organization features.

### 0.133 (2022-12-12)

##### ValueService

- Cleared up some things in `ValueContext`:
  - Renamed `duration` to `value_durations`.
  - Fixed the documentation inside the `oneof value_type`.

### 0.130 (2022-11-21)

##### EventService

- Renamed the deprecated `ModemEvent.ModemActivatedEvent` to `ModemEvent.ModemInstalledEvent` to reflect the new
  lifecycles.
  - Renamed `Event.modem_activated` to `Event.modem_installed`.
  - Removed deprecation flag from `ModemEvent.ModemActivatedEvent`.
  - Changed when the event is produced:
    - `ModemEvent.ModemActivatedEvent` was produced by the first real message from the modem.
    - Now, `ModemEvent.ModemInstalledEvent` is produced when the lifecycle is changed to `INSTALLED`.
      - Because of this `message_id` and `sent_at`, were removed from `ModemEvent.ModemInstalledEvent`.
#### Unit values
- Added support for rotation speed
  - Currently only one unit, which is revolutions per minute (RPM)
#### UnitPreferences

- Add optional fields to UnitPreferences for each unit
- Deprecate old oneof unit fields (with a separate boolean for each unit indicating whether that unit has a preference set)

### 0.129 (2022-11-14)

##### EasypulseService

- Fix a bug where the Easypulse.Fields call could report incorrect fields, because it assumed all modems were using the
  new parser format.

##### OrganizationService

- Add `database_info` field to prepare for separate databases for organizations.

### 0.128 (2022-11-07)

#### ValueService

- Add `MODEM_VALUES` permission to Permissions.
  - Let ValueServices use this permission instead of the `MODEM_MESSAGES` permission.

### 0.127 (2022-10-31)

### 0.126 (2022-10-24)

##### DeviceService

- Added a new device service to make updates to devices easier.

### 0.125 (2022-10-17)

##### EasypulseService

- Added more options for sorting:
  - `HEALTH_ASC_ALPHABETICAL`: Health sorted alphabetically by health level name.
  - `HEALTH_DESC_ALPHABETICAL`: Health sorted alphabetically by health level name, descending order.
  - `LIFECYCLE_ASC`: Sort modem on its lifecycle.
  - `LIFECYCLE_DESC`: Sort modem on its lifecycle in reverse order.
  - `LIFECYCLE_ASC_ALPHABETICAL`: lifecycle sorted alphabetically by lifecycle name.
  - `LIFECYCLE_DESC_ALPHABETICAL`: lifecycle sorted alphabetically by lifecycle name, descending order.
- Added `lifecycle` to `Asset` to match the one from `ModemService`.

##### EventService

- Deprecate the `ModemActivatedEvent`. It will be removed in the future.
  - Since the modem lifecycle (which will replace status) no longer contains an ACTIVE state, this event is no longer
    relevant.

### 0.124 (2022-10-10)

##### Permissions

- Added `SupportPermission`s:
  - `SupportPermission`s are used for features typically reserved for customer support, or that behave differently
    when used by a customer support operator.
  - Added `Filter.SupportPermissions`.

##### CurrentUserService

- Added `CurrentUser.support_permissions` to show the support permissions for the current user.

##### EasypulseService

- Added `Fields` call to get field configuration for Easypulse.

##### ModemService

- Added a few more options to `ListModemsRequest.Sort`:
  - `STATUS_ASC_ALPHABETICAL` and `STATUS_DESC_ALPHABETICAL`: sort by status, alphabetically (instead of by status enum order).
  - `HEALTH_ASC_ALPHABETICAL` and `HEALTH_DESC_ALPHABETICAL`: sort by health, alphabetically (instead of by severity).
- Renamed Modem.Status to Modem.Lifecycle
  - Updated enum values:
    - DEFAULT = ACCEPTANCE_TESTING
    - ACTIVE = INSTALLED
    - DEAD = DECOMMISSIONED
  - Added enum value:
    - PAUSED
  - Deprecated enum values:
    - DAMAGED
    - LOST

### 0.123 (2022-10-03)

##### EasypulseService

- Deprecated the `Easypulse.History` in favor of the `ValueService`.

##### UserService

- Fixed a bug with leftover invites when a user was invited, but was added to an organization in another way.

### 0.122 (2022-09-26)

##### ValueService

- Implemented the `DELTA` value transformation for numeric values.

### 0.121 (2022-09-19)

##### ModemService

- Fixed a bug where modems created (using the Create command) would get a random location, when location and location_in_area were not set.

##### ValueSimulationService

Created a new simulation service that allows to directly simulate values.

- Create/list/update/delete rotating values for any field
- Create/list/update/delete rotating values for location or pick random location within a square area.

###### SingleSignOnService

- Added `DundasSSO.Request.kill_other_sessions` to kill other sessions when validating or creating the session cookie.

### 0.120 (2022-09-12)

#### ModemMessageBodyParserService

- Added `measured_at_time_field` and `measured_at_offset_field` to `ModemMessageBodyParser.MetadataFields`
  and `UpdateUploadedModemMessageBodyParserRequest.MetadataFields`.
  - `measured_at_time_field`: contains the time (epoch seconds) to use for the values extracted from the message.
  - `measured_at_offset_field`: contains the time offset (second before sent time) to use for the values extracted
    from the message.
  - Only one of these can be set

### 0.119 (2022-09-05)

##### EasypulseService

- Added `MINIMUM` and `MAXIMUM` aggregation to `Easypulse.History.Request.Aggregation`.

##### FieldService

- Added `ForModem` call (with `ListFieldsForModem`) to list the fields for a selection of modems.
  - This is an improved version to `MessageService.AvailableBodyFields`
    - Added `apply_unit_preferences` to choose whether to apply the unit preferences.
    - Added `field_selection` to filter the fields.
- Added `optional` to `Field` to indicate the system should not consider the parser result invalid
  if the field is not in it.
  - Added `optional` to `UpdateFieldRequest`.

##### MessageService

- Added `MINIMUM` and `MAXIMUM` aggregation to `MessageBodyFieldHistory.Request.Aggregation`.
- Deprecated `History` call in favor of the new `ValueService`.
- Deprecated `AvailableBodyFields` call in favor of the new `FieldService.ForModem` call.

##### SingleSignOnService

- Added `current_session_id` to `DundasSSO.Request` to submit your current session id.
  If it is still valid, no new session is created and the given session id is returned.
- Added `session_id_subdomain` to `DundasSSO.Response` with the subdomain to write the session id to, for convenience.

##### ValueService

- Introducing the `ValueService` to fetch time series data from our system.
  - Use `List` to list absolute values for a given period of time.
  - Use `Aggregated` to aggregate values over a given period of time, optionally partitioned (i.e. average per day).

### 0.116 (2022-08-01)

##### FieldService

- When type is not specified for a new field, and no details (numeric or enum) are specified, it will now default to type text, instead of OTHER.

### 0.115 (2022-07-25)

##### AssignmentService

- **[B]** Removed `include_child_organizations` from `ListTagAssignments` and `ListModemAssignments`.

##### AWSIoTService

- **[B]** Removed the AWS IoT Integration. It was not used and outdated, and may be replaced in the future.

##### ModemService

- Deprecated `ListModemsRequest.child_organizations`, it will be removed in the future.
- Added `in_accessible_organizations` to `GetModemRequest`, to find the modem in any organization you have access to.

##### ModemAlarmService

- Removed support for JsonPath filter expressions for now.
- Added validation to check names: spaces and most symbols except for `_` and `-` and no longer allowed.

##### MQTTService

- Improved error handling and messages.
- Fixed an issue where setting a password could result in an internal server error because of
  incorrect encryption parameters.
- Improved MQTT client reliability.
- Added server CA certificate option.

##### base.proto

- Added `time_zone` to `Timestamp`. It will mostly be empty (UTC), but might be used when a modem has a time zone.

### 0.114 (2022-07-18)

##### EasypulseService

- Added tell-tale fields to EasyPulse Assets
- Improved accuracy for history results:
  - Removed `oneof` around `timestamp` and `time_range` in `History.Response.Value`.
    Instead, `timestamp` will be set when we have an exact time:
    - When not grouping, time of the individual point (and `time_range` would not be set, as before)
    - When the aggregation applies to a single data point, time of that point
    - When the aggregation would return an exact data point (i.e. LAST), the time of that point.
    - When the aggregation would not return an exact data point (i.e. AVERAGE), no value is set for timestamp.

##### EventService

- Fixed a bug where some `PublisherEvent.UpdatedEvent` would not be saved.

##### Field

- Extracted field from `value.proto` to `field.proto`
- **[B]** Changed package to `field`, instead of `value`
  - Doesn't break backwards compatibility, but requires code changes when proto files are recompiled
    because the package changed.

##### FieldService

- Introducing the FieldService to manage fields:
  - `List`: list fields for an organization based on all parsers.
  - `Add`: add fields to a parser.
  - `Update`: update a field, changing the `display_name`, `priority`, numeric details or enum values.
  - `UpdateNumericDetails`: just update the numeric details on a field.
  - `UpdateEnumValues`: just update the enum values for a field.
  - `Delete`: delete a field (from a parser).

##### MessageService

- Improved accuracy for history results:
  - Removed `oneof` around `timestamp` and `time_range` in `MessageBodyFieldHistory.Response.TimedValue`.
    Instead, `timestamp` will be set when we have an exact time:
    - When not grouping, time of the individual point (and `time_range` would not be set, as before)
    - When the aggregation applies to a single data point, time of that point
    - When the aggregation would return an exact data point (i.e. LAST), the time of that point.
    - When the aggregation would not return an exact data point (i.e. AVERAGE), no value is set for timestamp.

##### ModemAlarmService

- Renamed `OneOfCheck` to `AllowedCheck` in `ModemAlarm.Check.Field`.
- Added `BlockedCheck` in `ModemAlarm.Check.Field`, which is the opposite of the `AllowedCheck`:
  if the value is in the `blocked` list, the alarm is triggered.

##### UnitPreferencesService

- Extracted UnitPreferencesService from `value.proto` to `unit_preferences_service.proto`

##### Value

- Added `Value.Enum` with the enum `value`, `display_name` and optional `description`, `color` and `priority`.

### 0.112 (2022-06-27)

- Added new fields for EasyPulse Assets
  - rpm: Latest peak rpm measurement
  - fuelUsageIdling: The amount of fuel used while idling.
  - engineIdleTime: The amount of time the engine has been idling
  - powerTakeOfEngagementCount: The amount of times the power-take-off was engaged
  - powerTakeOfEngagementDuration: The duration the power-take-off was engaged for

- Add option to configure post-processing to message parser in API.

##### EventService

- Improved the title and description for alarm events with multiple error messages.

### 0.110 (2022-06-13)

- Added support for textual shortcuts in `Timestamp.textual`:
  - "now": converted to the request time
- Added support for textual shortcuts for `TimeRange`,
  which allows a few more values in `Timestamp.textual` in `TimeRange` only:
  - "now": converted to the request time
  - a duration as an offset of now, i.e. "-10h" or "PT-10h": converted to now + offset, so -10h for start is 10 hours before the end time
    - For example, to fetch messages in the past hour, a request could use the
      TimeRange `{ start.textual = "-1h", end.textual = "now" }` instead of specifying Timestamps explicitly.

##### EventService

- **[B]** Removed deprecated events types:
  - **[B]** Removed `Event.ModemEvent.ModemStaleEvent`. This functionality can be replicated with alarms instead, using the inactivity check type.
  - **[B]** Removed `Event.ModemEvent.MessageEvent.ModemMessageDelayedEvent`. This functionality can be replicated with alarms instead, using the delay check type.
  - **[B]** Remove EventType.MODEM_STALE and EventType.MODEM_MESSAGE_DELAYED.
- When retrieving events that relate to a modem, the modem time zone is used to set the returned `Timestamp.textual` in the right time zone.

##### ModemService

- When retrieving messages, the modem time zone is used to set the returned `Timestamp.textual` in the right time zone.

##### MessageService

- Added `MessageSelection.override_time_range_with_modem_time_zone` to replace whatever time zone was specified
  in the start and end time with the modem time zone.
  - This means you may get values outside of the original time range, but can be useful when requesting
    data for a date, for example.
- When retrieving messages, the modem time zone is used to set the returned `Timestamp.textual` in the right time zone.

##### Backwards incompatible changes

- **[B]** Removed deprecated events types:
  - **[B]** Removed `Event.ModemEvent.ModemStaleEvent`.
  - **[B]** Removed `Event.ModemEvent.MessageEvent.ModemMessageDelayedEvent`.
  - **[B]** Remove EventType.MODEM_STALE and EventType.MODEM_MESSAGE_DELAYED.

### 0.109 (2022-06-07)

##### CurrentUserService

- Fixed search for AccessibleOrganizations, to also search the organization display name.

##### EasypulseService

- Added `Easypulse.TargetValues`, with a call to list them and a call to set them.
  - These values will be used to calculate scores at a later point in time.

##### ExportService

- Fixed an issue where CSV export asked for configuration to be set, while it did work when the configuration was empty.

##### Organization

- Added `SINARMAS_SPECIFIC` to `Organization.Feature` for some specific processing.

##### Units

- Added `WEEKS` to `Value.Numeric.DurationUnit`.
- Added `CUBIC_METER` and `CUBIC_FOOT` to `Value.Numeric.Volume.Unit`.
- (Added equivalent values to the deprecated `UnitOfMeasurement`)

### 0.108 (2022-05-30)

##### ModemService

- Fixed an issue where time zone could not be cleared.

### 0.107 (2022-05-23)

##### EasypulseService

- Added `time_zone` to `Asset`. In the future, this will be used to
  - retrieve data in the correct time zone
  - aggregate on days using the correct time zone
  - etc.

### 0.106 (2022-05-16)

##### EventService

- Improved the event titles and descriptions.

##### ModemService

- Added `time_zone` to `Modem` and `UpdatePeripheralsRequest`, to manage the time zone that a
  modem is in. In the future, this will be used to
  - retrieve data in the correct time zone
  - aggregate on days using the correct time zone
  - etc.

### 0.105 (2022-05-09)

##### PublisherService

- Fixed a bug where updating the health filter would fail.

### 0.104 (2022-05-02)

##### ModemService

- Added `metadata` to `Modem`, a json object of metadata, similar to `ModemMesssage.metadata`.

##### ModemMessageBodyParserService

- Added `ModemMessageBodyParser.MetadataFields.modem_metadata_fields` for fields that should sync to modem metadata.
  - Related changes in `UpdateUploadedModemMessageBodyParserRequest.MetadataFields`:
    - Added `add_modem_metadata_fields`, `remove_modem_metadata_fields` for the new modem metadata fields.
    - Renamed `add_metadata_fields` to `add_message_metadata_fields` for clarity.
    - Renamed `remove_metadata_fields` to `remove_message_metadata_fields` for clarity.
    - Added `replace_message_metadata_fields` and `replace_modem_metadata_fields` for convenience.

### 0.103 (2022-04-25)

##### AlarmService

- Added default error message templates for all checks.
  You can now omit the error message template when creating a check, using the default automatically.

### 0.102.1 (2022-04-21)

##### AlarmService

- Fixed a bug where the alarm would not correctly detect the field unit, and fail with

    Invalid configuration: unit is configured, but field does not have a unit! Invalid configuration: unit is configured, but field does not have a unit!

### 0.102 (2022-04-19)

##### Value and Field

- Added `Unit` (with a single value `PERCENT`) to `Value.Numeric.Percenatage`, for client convenience.
- Added `percentage` to `Field.Numeric.Unit`, for consistency.
- Added `converted_from` to `Field.Numeric`, so you can tell that unit preferences were applied.

### 0.101 (2022-04-07)

##### Units

- Renamed Weight to Mass
- Added Flow to UnitPreferences (mostly for formatting, since there is currrently just one unit)
- Add `ENUM` option to `Value.Type`
- Extracted the values in `Value.Numeric.numeric_unit` to `Value.Numeric.Unit` for simplicity.

##### AssignmentService

- Added `apply_unit_preferences` to apply the unit preferences to the alarm check values
  (i.e. displaying a check defined in kelvin as celsius), in requests for aggregated assignments:
  - `ListModemAssignments.Request`
  - `ListAlarmAssignments.Request`
  - `ListTagAssignments.Request`

##### EasypulseService

- Added 4 new measures
  - odometer: the value of total distance travelled
  - fuel_used: the total volume of fuel used by this vehicle
  - engine_runtime: the total duration of runtime for the engine of this vehicle
  - engine_oil_temperature: the temperature of the engine oil.
- Added conversions for existing measures (deprecating the old versions)
  - speed: the speed of the asset. (Old measure renamed to speed_deprecated)
  - temperature: the temperature of the asset. (Old measure renamed to temperature_deprecated)
  - fuel_level: the percentage of fuel available to the asset. (Old measure renamed to fuel_level_deprecated)
  - battery_level: The percentage of battery charge left (Old renamed to battery_level_deprecated)
  - tire_pressure: The pressure of the tires. (Old renamed to tire_pressure_deprecated)

##### ExportService

- Fixed a bug where an export that is ready could also mark similar exports ready that were running
  at the same time.

##### ModemAlarmService

- Added `unit` to `ModemAlarm.Check`, to set alarms in a different unit than the field you are checking.
  - For example, a sensor returns data in Kelvin, but you want to set an alarm in Celsius. Now, you can make a check in
    Celsius and the Kelvin value is converted to Celsius automatically before the check is applied.
- Added `apply_unit_preferences` to `ListModemAlarms.Request` to apply the unit preferences to the alarm check values
  (i.e. displaying a check defined in kelvin as celsius).

##### ModemMessageBodyParserService

- Replaced `ModemMessageBodyParser.DataField` with `value.Field`
  - Removed `ModemMessageBodyParser.DataField`. The replacement, `value.Field` is backwards compatible, so current
    clients should keep working, but need to update their code when they regenerate from proto files.
  - Removed grouping for fields.
    - **[B]** Removed `modem.message.bodyparser.ModemMessageBodyParser.DataFieldOrGroup`
    - **[B]** Removed `ModemMessageBodyParser.data_fields_with_groups`
- **[B]** Removed the deprecated `data_fields_deprecated` from `UploadModemMessageBodyParserRequest`
- **[B]** Removed the deprecated `add_data_fields_deprecated` from `UpdateUploadedModemMessageBodyParserRequest`

##### ModemMessageService

- Changed the type of `AvailableMessageBodyFields.Response.ModemWithFields.message_body_fields` to `repeated value.Field`.
  This type is backwards compatible, so current clients should keep working, but need to update their code when they
  regenerate from proto files.
  - Also changes the type for `AvailableMessageBodyFields.Response.total` to `repeated value.Field`.
- Added `field_value_details` to `Value` in `MessageBodyFieldHistory.Response`.
  This is a map of field to `value.Value`, which specifies the unit and what it was converted from (based on your
  unit preferences)
  - Renamed `Value` in `MessageBodyFieldHistory.Response` to `TimedValue`, to not conflict with `value.Value`.

##### WebhookService

- Added `hmac_header_name` to `WebhookData`, to customize the hmac signature header name.
  - Added `update_hmac_header_name` to `UpdateWebhook` to update it.
- Added `custom_headers` to `WebhookData`, to add headers to every webhook call.
  - Added `add_custom_headers` and `remove_custom_headers` to `UpdateWebhook` to update them.
- Fixed a bug where blocked calls were included when listing history with the `only_failures` flag.

### 0.100.1 (2022-03-22)

##### ExportService

- Fixed a bug where an export that is ready could also mark similar exports ready that were running
  at the same time.

### 0.100 (2022-03-17)

- Added `flow` measure with `cubic meters per hour` unit.

### 0.99 (2022-03-10)

##### CurrentUserService

- Added `organization` to `CurrentUser`, to get the 'current' organization values for an organization other than the default organization.

##### EventService

- Fixed a bug where a modem filter would exclude assigned and unassign events

##### OrganizationService

- Added `OrganizationFeature.BI_TOOLING_BETA` for integrating BI tooling in the Mission Control interface.

##### SingleSignOnService

- Added `DundasSSO` to sign in to Dundas with your Mission Control session.

##### ModemAlarmService

- Fixed a bug where inactivity alarms without a health level would never trrigger.

##### UnitPreferencesService

- Added option to manage unit preferences in the API.

### 0.98 (2022-02-17)

##### EventService

- Added `MarkEventsResolved` to mark events as manually resolved in bulk.

##### ModemAlarmService

- Added `ModemAlarm.created_at` and `ModemAlarm.updated_at` to track alarm creation and last update, respectively.

##### MessageService

- Fixed a bug that affected message fetch performance when selecting a large time range.

### 0.97 (2022-01-27)

##### EasypulseService

- Fixed a bug where the last chunk was not included when requesting history, if the grouping did not fit exactly.

##### EventService

- Fixed a bug where filtering on modem number would exclude some event types incorrectly.
  Specifically: transfer events, claim events and modem alarm events were excluded incorrectly.
- Imrpoved performance of fetching events.

##### MessageService

- Fixed a bug where the last chunk was not included when requesting history, if the grouping did not fit exactly.

##### ModemMessageBodyParserService

- Added `priority` to `ModemMessageBodyParser.DataFieldGroup` as well, with the maximum value of the group.
- Added `group_identifier` to `ModemMessageBodyParser.DataField`, to group the fields.
  - Fields are grouped iff they have the same `group_identifier` or (if `group_identifier` is not set)
    the same `display_name`.

### 0.96 (2022-01-20)

This release collects a number of small bug fixes, improvements, deprecations
and some experimental features.

- The new MessageService aims to simplify the ModemService and provide a more consistent
  service for handling messages.
- The Easypulse service now supports the experimental Easypulse Scorecard

##### AssignmentService

- Fixed an issue where alarm name was not set.
- Fixed an issue where assigning something that was already assigned would throw an error
  instead of just returning the existing assignment.

##### EasypulseService

- Added some fields related to the new Easypulse Scorecard screen.

##### EventService

- Fixed a bug that blocked retrieving events of type `MODEM_MESSAGE_BODY_PARSED` in specific cases.
- Fixed a bug where filtering on modem number would exclude some event types incorrectly.
  Specifically: transfer events, claim events and modem alarm events were excluded incorrectly.

##### OrganizationService

- Added `Organization.Feature.EASYPULSE_SCORECARD`.

##### MessageService

- Added new service `MessageService`, for message-related functionality.
  - `List` messages for modems (like `ListModemMessagesRequest` in the `ModemService`)
  - `Count` messages for modems (like `MessageCountRequest` in the `ModemService`)
  - `AvailableBodyFields` lists the available message body fields for modems(s), based on the assigned parsers.
    Uses the `ModemMessageBodyParser.DataField` from `ModemMessageBodyParserService` instead of the error-prone
    implementation from `ModemService`.
  - `History` for message body field(s). Port of the `Easypulse.History` for all modems.
    This allows you to fetch individual message fields and apply aggregations to them, for example:
    - the average value per day
    - the sum per week

##### ModemService

- Deprecated `Messages` (`ListModemMessagesRequest`), in favor of the new `MessageService`.
- Deprecated `MessageCount` (`MessageCountRequest`), in favor of the new `MessageService`.
- **[B]** Removed `LicenseKeys` (`LicenseKeysRequest`), which was no longer supported and deprecated for a while.
- **[B]** Removed `AvailableMessageFields` (`AvailableModemMessageFields.Request`),
  in favor of the new `MessageService`.

##### ModemMessageBodyParserService

- Added `ModemMessageBodyParser.DataFieldGroup`, to group fields that represent the same value,
  in different units (used in `ModemMessageBodyParser.data_fields_with_groups`).
- Added `unit_symbol` to `ModemMessageBodyParser.DataField`, the symbol for the `unit_of_measurement`, for convenience.
- Added `priority` to `ModemMessageBodyParser.DataField`, to order the fields.

### 0.95 (2021-12-16)

#### Changes

- Added some additional comments in a few places.

##### AssignmentService

- Add alarm name when an alarm is returned.

##### EasypulseService

- Add `speed` in km/h to `Easypulse.Asset`, `Easypulse.History.Request` and `Easypulse.History.Response.Value`.

##### TransferService

- When excluding data from transfer, the data will now be actually deleted after a set period.
- It is now (temporary) not possible anymore to transfer data with modems.

### 0.94 (2021-12-02)

This release fixes an issue where the health for some events, sthat should resolve over time,
was not resolved.

#### Changes

- Fixed a bug where the health for events (where health expires over time) was not consistently updated.

### 0.93 (2021-11-25)

This release contains a number of bugfixes and some Easypulse improvements.

#### Changes

- Cleaned up the example event json files and added a few that were missing.

##### AlarmService

- Fix a bug where the inactivity check would trigger correctly, but fill an incorrect value in the error message.

##### EasypulseService

- Removed the `oneof` from `Easypulse.History.Request` and `Easypulse.History.Response`.
  All fiels can now be requrested at the same time.
- Added `sort` to `Easypulse.History` to specify if the results should be sorted by time descending or ascending.
- Added new `Easypulse.History.Request.Aggregation` option: `LAST`, which just takes the last value in a time range.
  This is especially useful when grouping the data.
- Added `Easypulse.History.Request.location` and `Easypulse.History.Response.location` to get the location at a
  given time. Since most aggregations don't make sense for the location, it always uss the `LAST` aggregation when
  aggregating.

##### OrganizationService

- Added `pagination` to `GetOrganizationAvatar` to limit the amount of Avatars that can be requested at once.
- Added new `EXPERIMENTAL` and `EARLY_ACCESS` flag.

### 0.92 (2021-11-08)

This release adds some much-needed defaults and fields to the AlarmService,
adds a call to show the location history for a modem and fixes some bugs.

#### Changes

##### AlarmService

- Added optional `name` to `ModemAlarm`.
- Added optional `description` to `ModemAlarm.Check`
- Renamed `ModemAlarm.Check.identifier` to `ModemAlarm.Check.name`, since it is not like other identifiers.
- Added default names for checks, based on the initial config.
- Added default error message templates for all check types:
  - LocationCheck: "Modem {modem} is no longer in {expected}! It is now at {actual}."
  - InactivityCheck: "Modem {modem} is inactive! It has not sent any messages for {actual}!"
  - DelayedCheck: "Message from {modem} was delayed for {actual}!"
  - FieldCheck.EqualsCheck: "{modem}: {field:path} should be {expected}, but was {actual:.3f}!"
  - FieldCheck.OneOfCheck: "{modem}: {field:path} should be in {expected}, but was {actual:.3f}!"
  - FieldCheck.MinimumCheck: "{modem}: {field:path} should be higher than {expected}, but was {actual:.3f}!"
  - FieldCheck.MaximumCheck: "{modem}: {field:path} should be lower than {expected}, but was {actual:.3f}!"
  - FieldCheck.ThresholdCheck: "{modem}: {field:path} should be between {field:threshold:minimum} and
      {field:threshold:maximum}, but was {actual:.3f}!"
  - FieldCheck.DeltaCheck: "{modem}: delta for {field:path} should be between {field:delta:threshold:minimum} and
      {field:delta:threshold:maximum}, but was {actual:.3f} (from {field:delta:previous:.3f} to
      {field:delta:current:.3f})"
- Fixed a number of bugs related to named locations used in alarms.

##### EventService

- **[B]** Removed `ModemMessageDroppedEvent` and its event type.

##### MapService

- Added `LocationHistory` to list the location history for a modem, with path simplification based on the zoom level.

##### ModemTransferService

- Fixed a bug that blocked the transfer of a connected device without its gateway, even though the gateway
  was active in the recipient organization.

##### NamedLocationService

- Fixed a bug where named locations could not be deleted.

### 0.91 (2021-10-28)

This release replaces a number of assignment-related services and reduces it all to a single, simlpe assignment service.
This release also contains a lot of work to improve events, including listing them in a timeline and
adding base information without having to look inside the oneof to determine the details.

Note: this release contains a number of backwards-incompatible changes!

#### Changes

##### AssignmentService

- **[B]** Removed the entire `DirectAssignmentservice`, `AutomaticAssignmentservice`,
  `ModemMessageBodyParserAssignmentService` and `ModemMessageBodyParserAutomaticAssignmentService`.
  - All functionality is now available in the `AssignmentService`.
    Unfortunately, this could not be done in a backwards-compatible way.
  - **[B]** Removed the option to assign an alarm to a parser, for now.
- Added `AssignmentService.assign` to assign things.
  - Added assignments to tags:
    - modem to tag: implements the modem tags.
    - alarm to tag: effectively assigns the alarm to all modems with that tag.
    - parser to tag: effectively assigns the parser to all modems with that tag.
- Added `AssignmentService.unassign` to remove assignments.
- Added `AssignmentService.TagAssignments` to list tags and everything assigned to them.
- Added `AssignmentService.AlarmAssignments` to list alarms with everything they are assigned to.
- Added `AssignmentService.ModemMessageBodyParserAssignments` to list parsers with everything they are assigned to.
- Introduced new assignment events:
  - `AssignedEvent` for a new assignments.
  - `UnassignedEvent` when an assignment is removed.

##### EventService

- Added `EventHistory` to list all `Event`s in single timeline. Does not fill the event details in `Event.event` oneof.
  - Added a lot of common information to `Event`:
    - Added `Event.type`.
    - Added `Event.time`.
    - Added `Event.title` and `Event.description`.
    - Added `Event.modem`, which is a `Event.Modem` ocject with `number`, `name` and `identifier`.
- Added `UpdateEventHealthConfiguration` to configure the effect events have on the health of the system.
  This only allows changing health for events that actually affect health.
- Added `EventSelection.include_resolved_events` to include resolved events.
- Added `ListEventsRequest.unbundled_events` to replace `EventSelection.unbundled_events`.
  - Deprecated `EventSelection.unbundled_events`.
- **[B]** Removed a number of assignment-related events. They have all been replaced with the new assignment events.
  - **[B]** Removed `ModemEvent.MessageBodyParserEvent.AutomaticAssignmentEvent.CreatedEvent` and
    `EventType.MODEM_MESSAGE_BODY_PARSER_AUTOMATIC_ASSIGNMENT_CREATED`.
  - **[B]** Removed `ModemEvent.MessageBodyParserEvent.AutomaticAssignmentEvent.UpdatedEvent` and
    `EventType.MODEM_MESSAGE_BODY_PARSER_AUTOMATIC_ASSIGNMENT_UPDATED`.
  - **[B]** Removed `ModemEvent.MessageBodyParserEvent.AutomaticAssignmentEvent.DeletedEvent` and
    `EventType.MODEM_MESSAGE_BODY_PARSER_AUTOMATIC_ASSIGNMENT_DELETED`.
  - **[B]** Removed `ModemEvent.MessageBodyParserEvent.AssignedEvent` and
    `EventType.MODEM_MESSAGE_BODY_PARSER_ASSIGNED`.
  - **[B]** Removed `ModemEvent.MessageBodyParserEvent.UnassignedEvent` and
    `EventType.MODEM_MESSAGE_BODY_PARSER_UNASSIGNED`.
  - **[B]** Removed `AssignmentEvent.AutomaticModemAssignmentCreatedEvent` and
    `EventType.AUTOMATIC_MODEM_ASSIGNMENT_CREATED`.
  - **[B]** Removed `AssignmentEvent.AutomaticModemAssignmentUpdatedEvent` and
    `EventType.AUTOMATIC_MODEM_ASSIGNMENT_UPDATED`.
  - **[B]** Removed `AssignmentEvent.AutomaticModemAssignmentDeletedEvent` and
    `EventType.AUTOMATIC_MODEM_ASSIGNMENT_DELETED`.
  - **[B]** Removed `AssignmentEvent.DirectAssignmentAddedEvent` and `EventType.DIRECT_ASSIGNMENT_ADDED`.
  - **[B]** Removed `AssignmentEvent.DirectAssignmentRemovedEvent` and `EventType.DIRECT_ASSIGNMENT_REMOVED`.
  - Added `AssignmentEvent.AssignedEvent` and `EventType.ASSIGNED` for a new assignments,
    or when assignments are updated
  - Added `AssignmentEvent.UnassignedEvent` and `EventType.UNASSIGNED` when an assignment is removed.
- Deprecated a few events that will be replaced by alarms:
  - `ModemStaleEvent`: use an inactivity check in an alarm instead.
  - `ModemMessageDroppedEvent`: only worked for some modems.
  - `ModemMessageDelayedEvent`: use a delayed check in an alarm instead.

##### ModemService

- Deprecated `Modem.maximum_inactivity_period` and `Modem.maximum_inactivity`:
  use an inactivity check in an alarm instead.
- Deprecated `Modem.HealthConfig`: use the new health configuration for events instead.
- Deprecated `LicenseKeysRequest`: this is no longer in use and will be removed soon.

##### TagService

- Add `type` to `Tag.Label`, to give tags more flexibility. All current tags have been set to the default type `group`.
  - New tags for which no type is specified will default to group, but this may change in the future.

#### Backwards incompatible changes

- **[B]** Removed the `DirectAssignmentservice`.
- **[B]** Removed the `AutomaticAssignmentservice`.
- **[B]** Removed the `ModemMessageBodyParserAssignmentService`.
- **[B]** Removed the `ModemMessageBodyParserAutomaticAssignmentService`.
- **[B]** Removed the option to assign an alarm to a parser, for now.
- **[B]** Removed `ModemEvent.MessageBodyParserEvent.AutomaticAssignmentEvent.CreatedEvent` and
  `EventType.MODEM_MESSAGE_BODY_PARSER_AUTOMATIC_ASSIGNMENT_CREATED`.
- **[B]** Removed `ModemEvent.MessageBodyParserEvent.AutomaticAssignmentEvent.UpdatedEvent` and
  `EventType.MODEM_MESSAGE_BODY_PARSER_AUTOMATIC_ASSIGNMENT_UPDATED`.
- **[B]** Removed `ModemEvent.MessageBodyParserEvent.AutomaticAssignmentEvent.DeletedEvent` and
  `EventType.MODEM_MESSAGE_BODY_PARSER_AUTOMATIC_ASSIGNMENT_DELETED`.
- **[B]** Removed `ModemEvent.MessageBodyParserEvent.AssignedEvent` and
  `EventType.MODEM_MESSAGE_BODY_PARSER_ASSIGNED`.
- **[B]** Removed `ModemEvent.MessageBodyParserEvent.UnassignedEvent` and
  `EventType.MODEM_MESSAGE_BODY_PARSER_UNASSIGNED`.
- **[B]** Removed `AssignmentEvent.AutomaticModemAssignmentCreatedEvent` and
  `EventType.AUTOMATIC_MODEM_ASSIGNMENT_CREATED`.
- **[B]** Removed `AssignmentEvent.AutomaticModemAssignmentUpdatedEvent` and
  `EventType.AUTOMATIC_MODEM_ASSIGNMENT_UPDATED`.
- **[B]** Removed `AssignmentEvent.AutomaticModemAssignmentDeletedEvent` and
  `EventType.AUTOMATIC_MODEM_ASSIGNMENT_DELETED`.
- **[B]** Removed `AssignmentEvent.DirectAssignmentAddedEvent` and `EventType.DIRECT_ASSIGNMENT_ADDED`.
- **[B]** Removed `AssignmentEvent.DirectAssignmentRemovedEvent` and `EventType.DIRECT_ASSIGNMENT_REMOVED`.

### 0.90 (2021-10-11)

This release contains a number of bugfixes and removes some deprecated options from ModemAlarm.

#### Changes

- Fixed a few performance issues.

##### ModemService

- Fixed a bug where `ModemSelection.filter_by_tags` would return only the modems matching the entire set of given tags
  (ALL) instead of modems with one of the given tags (ANY).

##### ModemAlarmService

- Remove the deprecated options on `LocationCheck`:
  - Custom `area` or `shape` are no longer supported, use a named location instead.

##### NamedLocationService

- Cleaned up the comments which referred to saved location instead of named location.
- Added `NamedLocation.created_at`: the time it was created.
- Added `NamedLocation.updated_at`: the last time the location was updated, if any.
- Added `NamedLocation.referenced_by_alarms`, the list of alarms that reference this named location.
- Using `NamedLocation` for create and updated is no longer practical now that we have added more fields:
  - Introduced `CreateNamedLocation` to be used to in `CreateNamedLocations.Request`.
  - Introduced `UpdateNamedLocation` fields to be used to in `UpdateNamedLocation.Request`.
- Fixed a bug where a named location that is used in an alarm check could still be deleted.

##### SimulationService

- Fixed a bug where, in rare cases, simulated messages might end up with a sent time outside the configured delay range.

### 0.88 (2021-09-09)

This release contains a number of bug fixes and usability improvements.

#### Changes

- Improved comments and generated documentation.

##### ExportService

- When requesting available fields for export, providing a non-empty modem selection is no longer required.
  When an empty (or no) modem selection is provided, the result is the total of all modems in the organization.
  (The columns may differ per modem because of assigned message body parsers.)

##### HealthService

- Fixed a bug where the modem health was not updated when you deleted a custom health level.

##### ModemService

- Removed the option to consider message with source `TEST` as real (when applying processing).
  - Simulated modem messages are now considered real to the system, since that was the real use case for this option.
- Fixed a race condition where modem health would occasionally be "OK", then switch back to its actual health.

##### OrganizationService

- Added `Organization.Feature.MODEM_CREATION` to allow an organization to manually create modems using the ModemService.
- Fixed a bug where an incorrect error message was returned when creating an organization without the correct
  OrganizationPermission.

##### SimulationService

- Added `Simulation.ModemMessageSimulation.message_body_rotation` to rotate through a list of pre-configured
  message bodies when simulating messages. This can be done to simulate a modem looping through different healths
  during the simulation.
- Added `Simulation.ModemMessageSimulation.location_rotation` to rotate through a list of pre-configured
  locations when simulating messages. This can be done to simulate a modem moving on the map during the simulation.

### 0.87 (2021-09-02)

This release add an ease of use improvement for exporting, and contains a number of bugfixes.

#### Changes

##### ModemService

- Added `ModemMessage.tagNames` for convenience, since most of the time the ids are not relevant.

##### ExportService

- Added `AvailableFieldsForExport` (for `ExportService.AvailableFields`) to get the fields that are available to export.
  - Provides a list of json paths for use in custom json field mapping.
  - Provides the default column mapping for CSV export.

### 0.86 (2021-08-30)

This release fixes a few bugs and adds a few missing features.

#### Changes

##### base.proto

- Added `PRESSURE_K_PA` to `UnitOfMeasurement`, for pressure in `kPA`.

##### AlarmsService

- Fixed a bug where a location extracted from the message body using
  `ModemMessageBodyParser.MetadataFields.location_fields` was not available to alarms.

##### ModemService

- Fixed a bug where a specific query could negatively affect message list performance.

##### UserService

- `ListInvitationsRequest` not filters out accepted invitations by default.
  - Added `ListInvitationsRequest.include_accepted` to include accepted invitations.

##### StatusService

- Fixed a performance issue for the status call when the list of publishers was included.

### 0.85 (2021-08-23)

This release improves the generated API documentation and fixes a few bugs.

#### Changes

- Improved API documentation and generated documentation files
  - Disabled html file generation for now, since it was prone to breaking.
  - Improved markdown file generation significantly

##### EventService

- `ModemEvent.MessageEvent.ModemMessageCannotBeParsedEvent` will no longer resolve after a new successful message,
  since it indicates an invalid configuration.
  - Added `ModemEvent.MessageEvent.ModemMessageCannotBeParsedEvent.resolved` to indicate resolved state.
  - Added `ModemEvent.MessageEvent.ModemMessageCannotBeParsedEvent.resolve_identifier` to resolve the event manually.
  - Added `EventService.Resolve` and `ResolveEvent` to resolve a `ModemMessageCannotBeParsedEvent` manually
    using the provided `resolve_identifier`.
- Fixed the include_resolved filter for some events types for which is was not working properly.

##### MapService

- Added more Density options to the map:
  - `VERY_SPARSE`: for 2x2 icons in a tile
  - `SINGLE`: a single icon in a tile

##### ModemAlarmService

- Added the option to update checks to `UpdateModemAlarm`: `add_checks`, `update_checks` and `delete_checks`.
- Fixed an issue where alarms would not resolve correctly when a mix of correct and incorrect messages arrived
  at the same time.

##### ModemMessageBodyParserService

- Moved validation on `data_fields` and `metadata_fields` from save to execution, for now.

### 0.84 (2021-08-12)

This release contains a few UX improvements, making the API esier to use.

#### Changes

##### EventService

- Added `ModemEvent.AlarmEvent.ModemAlarmEvent.resolved_at` to mark when the alarm was resolved.
  - Added `health_level_after_resolved` and `health_level_after_resolved_until` to denote any health after it
    was resolved. See the alarm documentatin for more information.

##### MapService

- Added textual format to all map elements:
  - Added `Location.textual`, which represents a point on the map as an array `[latitude, longitude]`.
    For example: `[10.0, 15.0]`.
  - Added `Area.textual`, which represents a square on the map as an array `[bottomLeft, topRight]`,
    where `bottomLeft` and `topRight` are textual representations of locations.
    For example: `[[10.0, 15.0], [20.0, 25.0]]`.
  - Added `Shape.textual`, which represents a shape on the map as an array of points `[p1, p2, p3, ...]`,
    where the points are textual representations of locations.
    For example: `[[10.0, 15.0], [15.0, 15.0], [10.0, 10.0]]` is a triangle.

##### ModemService

- Added `ModemMessage.modem_name` for convenience.
- Added `ModemMessage.modem_identifier` for convenience.
- Added `ModemMessage.tags` for convenience.

##### ModemAlarmService

- Added two new check types: `minimum` and `maximum`. These are simplified versions of the threshold that do
  not need a range, just a single value.
  - Added `ModemAlarm.Check.FieldCheck.MinimumCheck`
  - Added `ModemAlarm.Check.FieldCheck.MaximumCheck`
- Added better child organization availability management:
  - (Before, the child availability could only be replaced.)
  - Added `MakeModemAlarmAvailableToChildOrganizationRequest` to add a child organization to the availability.
  - Added `MakeModemAlarmUnavailableToChildOrganizationRequest` to remove a child organization from the availability.

##### ModemMessageBodyParserService

- Added better child organization availability management:
  - (Before, the child availability could only be replaced.)
  - Added `MakeModemMessageBodyParserAvailableToChildOrganizationRequest`
    to add a child organization to the availability.
  - Added `MakeModemMessageBodyParserUnavailableToChildOrganizationRequest`
    to remove a child organization from the availability.

### 0.83.6 (2021-08-10)

This minor release adds sorting on health for modems.

#### Changes

##### EasypulseService

- Added sorting on health to `Easypulse.ListAssets.Request.Sort`:
  - `HEALTH`: sort by health severity, ascending (Ok, Warning, Error when using default health levels).
  - `HEALTH_DESC`: sort by health severity, descending (Error, Warning, Ok when using default health levels).

##### MapService

- Expanded comment on `TileMapRequest.level` to include which levels are available and what they are based on.

##### ModemService

- Added sorting on health to `ListModemsRequest.Sort`:
  - `HEALTH`: sort by health severity, ascending (Ok, Warning, Error when using default health levels).
  - `HEALTH_DESC`: sort by health severity, descending (Error, Warning, Ok when using default health levels).

### 0.83 (2021-08-05)

This release introduces the Easypulse service and some supporting changes.

#### Changes

- Removed a few unnecessary imports.

##### ModemService

- **[B]** Removed `ListModemMessagesRequest.field`.
  The functionality will be replaced with a call like `Easypulse.History` in the future.

##### EasypulseService

- Introduced the `EasypulseService` for Easypulse-specific implementations.
  - This API requires the `Organization.Feature.EASYPULSE` feature flag.
  - This is mostly a convenience view on the normal modems and messages.
  - `Easypulse.History` allows you to fetch individual message fields and apply aggregations to them, for example
    - the average pressure per day
    - the sum of run time per week
    - This feature will be made available for all organizations soon in the `ModemService`.

##### EventService

- Corrected the text for ModemCreatedEvent, which is now produced any time modems are created, whether it is manually
  or automatically.

##### HealthService

- Cleaned up the documentation for `HealthLevel`.

##### ModemMessageBodyParserService

- Added `ModemMessageBodyParser.DataField` to define more properties for data fields in a parser.
  This is mostly used internally, to power the new Easypulse service.
  - Updated `ModemMessageBodyParser`, `UploadModemMessageBodyParserRequest` and
    `UpdateUploadedModemMessageBodyParserRequest`:
    - Deprecated and renamed the repeated string `data_fields` to `data_fields_deprecated`.
    - Added `data_fields` as the repeated `DataField`s.
  - Introduced `UnitOfMeasurement` in `base.proto` to support defining the type for parser data fields.

##### ModemDownlinkMessageService

- Introduced the experimental `ModemDownlinkMessageService` to store and fetch messages that should be sent to
  your devices.
  For now, this is just a CRUD service to prepare and fetch messages, but expect more features in the future.

##### OrganizationPermissions

- Added `OrganizationPermission.MODEM_DOWNLINK_MESSAGES` for using the new ModemDownlinkMessageService.

#### Generated Documentation

- In this release, we're experimenting with some automatically generated documentation in the `docs` folder.

#### Backwards incompatible changes

- **[B]** Removed `ListModemMessagesRequest.field`.
  The functionality will be replaced with a call like `Easypulse.History` in the future.

### 0.81 (2021-07-05)

This release contains a collection of minor features:
- Adding health to the map
- Allowing modems to be filtered on peripherals
- Extracting metadata (and location) from a parsed message body

#### Changes

##### HealthService

- Added `HealthLevel.severity` to allow sorting of health levels when needed.

##### MapService

- Added `TileMapRequest.include_health` to include the health for each map tile (that contains modems).
  - Added `MapTileItem.Modem.health_level` for tiles with a single modem.
  - Added `MapTileItem.Group.most_severe_health_level`, the most severe health level for the modems in this group.
  - Not compatible with including child organizations, since those health levels may differ.
- Removed deprecated calls `Satellites` and `Map`, leaving only the `TileMap` call.
  - Removed `SatellitesRequest`, `MapRequest`, `MapBlock` and `MapSelection`, which were only used
    in the deprecated calls.

##### ModemService

- Added `ModemSelection.peripherals` to filter modems by peripherals.
- Added `ModemSelection.only_without_peripherals` to filter modems that have no peripherals.

##### ModemMessageBodyParserService

- Added `metadata_fields` to `ModemMessageBodyParser`,
  `UploadModemMessageBodyParserRequest` and `UpdateUploadedModemMessageBodyParserRequest`.
  Metadata fields are extracted from the parsed message body to the message metadata.
  - Added specific metadata fields for extracting location from the message body to the modem.

### 0.80.3 (2021-07-02)

This release contains a few more bug fixes.

#### Changes

##### ModemService

- Fixed a bug where fix device count for gateway was not taking organization into account,
  counting orphaned devices in other organizations.
- Fixed device message order, which was broken in 0.80.

### 0.80.2 (2021-06-22)

This release contains a few bug fixes.

#### Changes

- Fixed a bug where an Area or Shape was not allowed to contain a location of (0.0, 0.0).

##### TagService

- Fixed a bug where deleting a tag could affect the assignment of other tags.
- Fixed a bug where deleting a tag did not produce a ModemUpdatedEvent for the affected modems.

### 0.80 (2021-06-17)

This release introduces the option to create your own modems (with some limitations)
and convenience improvements.

#### Changes

- Added a `OrganizationPermission.MODEMS_CREATE` to create modems.

##### OrganizationService

- Renamed `Organization.Feature.GENERAL_PURPOSE_TRACKING` to `Organization.Feature.EASYPULSE`.

##### ModemService

- Added `CreateModem` to create modems for your organization.
  - This call is not available to all organizations, and is typically used to create modems for testing or
    when you want to connect a device to the API using just the API calls in the TestingService.
- Fixed a bug where `UpdateModemStatus` only returned a single modem, even though all selected modems were affected.
- Added `include_types` and `exclude_types` to `ModemSelection`, replacing the simple `types` list of included types.
- Added `ModemMessageSelection.modem_selection` to allow selecting messages from multiple modems
  without having to list the individual modems (i.e. by tag).

### 0.79 (2021-06-03)

This release contains a selection of bugfixes and API Ux improvements.

#### Changes

- Added a new identifier generator to clean up the different types of identifiers a bit.
  - Identifiers - even without their prefix - are unique system-wide
  - New identifiers are generated using the new logic for the following types:
    - modem transfers
    - modem alarms
    - modem message body parsers
    - automatic assignments

##### ModemAlarmService

- Removed limitation where the `minimum` or `maximum` for threshold and delta check could not be `0.0`.

##### ModemService

- The pagination for messages should now be more accurate, and only estimate total counts if you have a lot of messages.
- Added `AvailableModemMessageFields.Request.include_total` and `AvailableModemMessageFields.Response.total`
  to calculate the total fields for all selected modems. This can be useful to display table columns, for example.

##### OrganizationService

- Added new Organization Feature flag: `GENERAL_PURPOSE_TRACKING`

##### SimulationService

- Added `random_location_in_area` to `Simulation.ModemMessageSimulation.Update.Request` to allow the simulation
  to generate a new location for the modem on every message, but contain it within a given area.

##### TokenService

- Added more options to `UpdateTokenOrganizationPermissionsRequest`
  - Renamed `new_organization_permissions` to `replace_organization_permissions`, to be more explicit.
  - Added `add_organization_permissions` to instead just add permission to the token.
  - Added `remove_organization_permissions` to remove permissions from the token.
- Added more options to `UpdateTokenUserPermissionsRequest`
  - Renamed `new_user_permissions` to `replace_user_permissions`, to be more explicit.
  - Added `add_user_permissions` to instead just add permission to the token.
  - Added `remove_user_permissions` to remove permissions from the token.

### 0.78 (2021-05-31)

This release adds health levels to events, so they can be shown and filtered on.

#### Changes

##### EventService

- Added `health_level` to `Event` and specific events, to reflect the `HealthLevel` the event causes.
  This allows us to use the new customizable health levels for events, and filtering events.
  - Added `health_level` to:
    - `ModemStaleEvent`
    - `ModemMessageDroppedEvent`
    - `ModemMessageDelayedEvent`
    - `ModemMessageCannotBeParsedEvent`
    - `ModemAlarmEvent`
    - `ModemTransferNotReceivedEvent`
    - `ModemTransferReturnTransferStartedEvent`
    - `PublisherEvent.AutoDisabledEvent`
    - `PublisherEvent.FailedEvent`
    - `TokenExpiryWarningEvent`
    - `EventSelection`
- **[B]** Deprecated `is_error` and `is_warning` on `Event`, and `errors_only` and `warnings_only` on `EventSelection`
  to be replaced with the `Event.health_level` and `EventSelection.health_levels` respectively.

##### EmailNotificationPreferences

- Added `EmailNotificationPreferences.filter_health_levels` to filter events on health level when sending them by email.
- Added `UpdateEmailNotificationPreferencesRequest.add_health_levels_to_filter` to add health levels to the filter.
- Added `UpdateEmailNotificationPreferencesRequest.remove_health_levels_from_filter` to remove health levels from
  the filter.

##### SlackIntegrationService

- Added `SlackPublisher.filter_health_levels` to filter events on health level when sending them to slack.
- Added `CreateSlackPublisherRequest.filter_health_levels` to filter events on health level when sending them to slack.
- Added `UpdateSlackPublisherRequest.add_health_levels_to_filter` to add health levels to the filter.
- Added `UpdateSlackPublisherRequest.remove_health_levels_from_filter` to remove health levels from
  the filter.

##### WebhookService

- Added `Webhook.filter_health_levels` to filter events on health level when sending them to a webhook.
- Added `CreateWebhookRequest.filter_health_levels` to filter events on health level when sending them to a webhook.
- Added `UpdateWebhookRequest.add_health_levels_to_filter` and
  `UpdateWebhookFilterRequest.add_health_levels_to_filter` to add health levels to the filter.
- Added `UpdateWebhookRequest.remove_health_levels_from_filter` and
  `UpdateWebhookFilterRequest.remove_health_levels_from_filter` to remove health levels from  the filter.

### 0.77 (2021-05-17)

This release contains:
- marking data fields for message body parsers (for processing, charting, etc)
- easy access to parsed message body in messages, using a merged Struct
- exporting message to JSON or CSV

##### EventService

- Added `ExportCreatedEvent`, `ExportReadyEvent` and `ExportFailedEvent` for the new export functionality.
  - Added `export_created`, `export_ready` and `export_failed` to `Event`.

##### ExportService

- Introduced the ExportService, to list and manage exports.
  - Exports are asynchronous and only available for a limited time when ready,
    which is reflected by the `Export.Status` (with `PROCESSING`, `READY`, `EXPIRED`).
  - Added `Export.Format.Json` for exporting in a JSON format.
  - Added `Export.Format.Csv` for exporting in a CSV format.
  - Added `Export.Configuration.ModemMessages` to export modem messages.
    This is currently the only available export configuration.

##### ModemService

- Added `ModemMessage.body_fields`, which is a flattened Struct of all `ModemMessage.body_parsed[*].result`.
  This is a convenience to access the fields from body_parsed, but if any fields are present in
  multiple body_parsed results, it is not defined which field will be used in this Struct.
  This may change in the future.
- Added `ModemMessageFieldsSelection` to select fields in a `ModemMessage`, both proto fields and message body fields.
  - Added `AvailableMessageFields` to list available fields for messages from a modem.
    This is generally useful to list data fields added by message body parsers
    (and powered by `ModemMessageBodyParser.data_fields`).
    The available fields are returned as a `ModemMessageFieldsSelection`.
  - Added `ListModemMessagesRequest.fields` (a `ModemMessageFieldsSelection`) to limit the fields for the
    returned messages, to conserve data or simplify an operation.
    This applies to both protobuf fields and message body fields.

##### ModemMessageBodyParserService

- Added `data_fields` to `ModemMessageBodyParser`, which are fields that are marked to contain data
  (versus status fields or counters), that can be graphed, for example.
  - Added `has_data_fields` to `ModemMessageBodyParserSelection` to select parsers that have specified data fields.
  - Added `data_fields` to `UploadModemMessageBodyParserRequest` to set the data fields for a newly uploaded parser.
  - Added `add_data_fields` and `remove_data_fields` to `UpdateUploadedModemMessageBodyParserRequest` to update the
    data fields for an uploaded parser.

##### Permissions

- Added `EXPORT` permissions to allow a user to create exports and see download links.

### 0.76 (2021-05-04)

- Added tags to modem update event
- Resolving alarms can now affect health for a given period of time after resolving.

### 0.75 (2021-04-29)

This release adds a few more options to modem alarms.

##### ModemAlarmService

- Fixed the index for `InactivityCheck.maximum`.
- Added formatting option to error message templates:
  - Added the option to round numeric values: `{actual:.3f}`
  - Added the option to always sign numeric values (when rounded): `{actual:+.3f}`
  - This is applied to numeric fields and fields that can be numeric, like `{actual}` and `{expected}`.

### 0.74.4 (2021-04-22)

Small convenience hotfix for the `ModemHealthCount`.

##### ModemService

- **[B]** Changed `ModemHealthCount.Response` to group tag health counts instead of having them all in a big list.

#### Backwards incompatible changes

- **[B]** Changed `ModemHealthCount.Response` to group tag health counts instead of having them all in a big list.

### 0.74 (2021-04-15)

#### Changes

##### NamedLocationService

- Added `NamedLocationService` to save locations with a name. These location can then be used in other
  places, like alarms.
  A named locations can be either a `Location`, `Area` or `Shape`.
  - Added permission `LOCATIONS_MANAGE` to `OrganizationPermission` to manage named locations.

##### ModemAlarmService

- Added `named` to `LocationCheck` to use a named location for the check.

##### EventService

- `ModemAlarmEvent` title is now just the error message, without any additional data.
  The description contains the additional data, as before.

### 0.73 (2021-04-12)

#### Changes

##### ModemService

- Added `ModemHealthCount` to efficiently count how many of your modems per health level.
  Optionally, the counts can also be done per tag, specified by a TagSelection.

##### ModemAlarmService

- Added `DelayCheck` to trigger the alarm when message delay
  (the difference between sentAt and receivedAt) exceeds a given threshold.

### 0.72 (2021-03-25)

#### Changes

- Bugfix in modem listing where in a specific edge-case modems would be un-listable after transfer.
- TLE update status does not affect server health any-more (causing restarts when outdated)

### 0.71 (2021-03-16)

The main focus for this release is tweaking the concepts previously introduced around alarms and health.
It also introduces the notion of _features_ for organizations.
_Features_ can be en- or disabled on a per-organization basis
and have an effect on the set of features that organizations can use.

#### Changes

##### Organization features

This change introduces 2 new feature (sets)

- HIBER: (All) the features as currently available under Mission Control
- HILO: Allows access to a separate dashboard that represents the
  [HiberHilo](https://hiber.global/solutions/well-integrity/) product.

#### Health

- Modem selection (now) possible by custom health level names
- Health can now have multiple (named) colours associated with it.

#### Alarm

- A modem alarm now has a default health, which overrides the standard of "most severe".
- Allow the alarm to cause a health level for the modem even after a new message has come in.

### 0.69 (2021-03-04)

This release builds on the new health levels by implementing them for alarm events, and replacing the deprecated health
implementation with the new health levels in a backwards-compatible way.
Additionally, this release introduces some new options to alarm checks, including a new check type for modem inactivity.

#### Changes

##### ModemService

- Replaced the deprecated health implementation with the new health levels. The default health levels are identical
  to the deprecated levels, so unless you change the health levels for your organization, this change is fully backwards
  compatible.
- Added `Modem.inactivity` with the time since the last message.
- Fixed a bug where stale detection would not be triggered.

##### ModemAlarmService

- Added a new check type: Inactivity.
  This check triggers when a modem is inactive for the configured period.
  This is similar to `Modem.maximum_inactivity`, but uses the alarms to add more flexibility, like the option to add
  multiple checks for multiple levels of inactivity and configuring the resulting health for each of those.
- Added a few options to the delta check:
  - `encrypted`: whether the individual field data should be encrypted (all messages are already encrypted).
    Encrypting the individual field values is (relatively) computationally expensive and may lead to
    a slightly delayed alarm event. In the future, some delta features may only
    be available to unencrypted values due to performance issues.
  - `ignore_previous_value_not_found`: Whether to ignore this check if the previous value is not found
    (i.e. there is no history).
- Added `ModemAlarmEvent.health_level` so the configured health is actually reflected in the event.

##### StatusService

- Deprecated `ModemStatus.health`. The status call will be update with health levels in a later release.

### 0.68.3 (2021-03-02)

#### Changes

##### ModemService

- Fixed a bug where message events were not sent in order.

### 0.68 (2021-02-15)

#### Changes

##### EventService

- Added `ModemStaleEvent.maximum_inactivity` to allow maximum inactivity period of any length.
  - Deprecated `ModemStaleEvent.maximum_inactivity_period`, which allows maximum inactivity period in days only.
  - Updated `modem-stale.json` to reflect this added field.

##### HealthService

- Added `HealthSelection` to filter health levels.
- Added `ListHealthLevels.Response.request` to return the request, in case the selection was corrected.

##### ModemService

- Added `Modem.maximum_inactivity` to allow maximum inactivity period of any length.
  - Deprecated `Modem.maximum_inactivity_period`, which allows maximum inactivity period in days only.

##### ModemAlarmService

- Added a comment related to the processing of health levels from parent organizations.
- Fixes a bug where health level was not saved on modem alarms.
  (Note that health is not yet processed to the alarm event or modem health, this will be added soon.)

### 0.67 (2021-02-04)

This release introduces the concepts of health levels.
Over the next few releases, health levels will replace the static health we have now (for example for modems).

Health levels can be customized to as many as you need for your operations, for example:
- INTERVENTION
- DEFECT
- BATTERY
- HIGH
- LOW

The health level caused / produced by events and alarms can be customized in the next few releases.

#### Changes

- Added a new permission `HEALTH_MANAGE` to manage health levels.

##### HealthService

- Introduced the `HealthService` to manage custom health levels. See the proto file for more details.

##### ModemService

- Deprecated the static health on modem and added the new health levels.
  By default, the health levels are identical to the static health levels: OK, WARNING, ERROR.

  - Deprecated `Modem.health`.
    It will be implemented in terms of health levels in the future, as long as your health levels are identical
    to the static health.

  - Added `Modem.health_level` to show the modem's health as a `HealthLevel`.

  - Renamed `Modem.HealthConfig.health_warning_period` to `health_unresolvable_period`,
    since health is now customizable.

### 0.66 (2021-01-28)

Removed some deprecated code.

#### Changes

##### DashboardService

- **[B]** removed deprecated field `selection` from `DashboardRequest`.
- **[B]** removed deprecated fields `satellites`, `ground_stations` and `map_blocks` from `DashboardRequest.Response`.

### 0.64 (2021-01-21)

This release add support for our next satellite, HIBER-4!

It also introduces organization-scoped simulations, with the first implementations:
- modem message simulation: simulate messages on modems
- modem inactivity simulation: randomly disable message simulation on modems to generate inactivity events
- delayed message simulation: give a percentage of simulated messages a random delay (between sent and received time)
  to generate delayed message events.

#### Changes

- Added `BytesOrHex.Update` to update a binary field.

##### EventService

- Limited event streams to *one* per user due to GRPC limitations.

##### TestingService / SimulationService

- Added the `SimulationService` (in `testing.proto`) to support simulating data for testing.
  - Added `SimulationService.Get` with `Simulation.GetRequest` to return the status of the simulations for the
    organization. This includes organization-wide simulation settings and statistics for modem message simulations.
  - Added `SimulationService.Update` with `Simulation.UpdateRequest` to update organization-wide simulation settings.
  - Simulation can be enabled and disabled on an organization with a single toggle: `Simulation.enabled`.
  - With `Simulation.modem_inactivity` modems that are simulating messages can be randomly disabled for a random period
    to generate inactivity events.
  - With `Simulation.delayed_messages` modems that are simulating messages can simulate a percentage of messages
    with a random delay (between sent and received time) to generate delayed message events.
  - With `Simulation.modem_message_simulation_defaults` default can be set for the message simulation, like the default
    message interval `simulation_interval` and the number of messages per interval `messages_per_interval`.

- Added `Simulation.ModemMessageSimulation` to simulate modem messages.
  This supports both direct messages and message via a gateway. The method used depends on the modem configuration.
  - The number of messages can be configured using the `simulation_interval` and `messages_per_interval`.
  - Custom message bodies with optional random values are configurable using the `message_body` as the body and
    the `message_body_variable_byte_indices` to indicate which bytes can be randomized.
  - If needed, the simulation can be disabled for a period by setting `next_simulation_run_after` to a point in
    the future.
  - Added `SimulationService.ListModemMessageSimulations` with `Simulation.ModemMessageSimulation.List.Request` to
    list all modems with an active message simulation.
  - Added `SimulationService.UpdateModemMessageSimulations` with `Simulation.ModemMessageSimulation.Update.Request` to
    enable or update the message simulation for a selection of modems.
  - Added `SimulationService.DisableModemMessageSimulations` with `Simulation.ModemMessageSimulation.Delete.Request` to
    list all modems with an active message simulation.

### 0.62 (2020-12-07)

This release introduces `ModemAlarm`s and new services to manage assignments.

A `ModemAlarm` is a collection of checks that validate a modem's messages, for example by location or by
a field in the parsed message body. Multiple types of checks are available.

With the introduction of `ModemAlarm`, we've also changed how assignment works.
Previously, only `ModemMessageBodyParser`s were assigned, which was implemented with specific assignment services
for `ModemMessageBodyParser`s. With this release, those services have been deprecated in favor of the new assignment
services:

- `DirectAssignmentService`: to directly link
  - a `ModemMessageBodyParser` to a `Modem`
  - a `ModemAlarm` to a `Modem`, with assignment parameters for the alarm
  - a `ModemAlarm` to a `ModemMessageBodyParser`, to assign them both to a modem by assigning one of them to the modem.

- `AutomaticModemAssignmentService`: to set up rules to assign `ModemMessageBodyParser`s and `ModemAlarm`s to a `Modem`
  with certain properties (like tags, manufacturers, peripherals etc).

- `AssignmentService`: to list everything assigned to modem(s) by both the `DirectAssignmentService`
  and `AutomaticModemAssignmentService`.

In addition to the changes above, this release adds more flexibility to messages by adding `metadata` to messages,
allowing users to effectively add any custom data.

#### Changes

- Added `DoubleRange`, a range between two decimal values (inclusive).

- Added `ModemAlarm`-related `EventType`s:
  - `MODEM_ALARM` when a modem alarm is triggered on a message.
  - `MODEM_ALARM_CREATED` when a modem alarm is created.
  - `MODEM_ALARM_UPDATED` when a modem alarm is updated.
  - `MODEM_ALARM_DELETED` when a modem alarm is deleted.

  See `ModemAlarmService` for more details.

- Added assignment-related `EventType`s:
  - `DIRECT_ASSIGNMENT_ADDED` when a direct assignment is added.
  - `DIRECT_ASSIGNMENT_REMOVED` when a direct assignment is removed.
  - `AUTOAMTIC_ASSIGNMENT_CREATED` when an automatic modem assignment is created.
  - `AUTOAMTIC_ASSIGNMENT_UPDATED` when an automatic modem assignment is updated.
  - `AUTOAMTIC_ASSIGNMENT_DELETED` when an automatic modem assignment is deleted.

  See the `DirectAssignmentService` and `AutomaticModemAssignmentService` for more details.

- Deprecated `EventType`s:
  - `MODEM_MESSAGE_BODY_PARSER_AUTOMATIC_ASSIGNMENT_CREATED` is being replaced with `AUTOAMTIC_ASSIGNMENT_CREATED`.
  - `MODEM_MESSAGE_BODY_PARSER_AUTOMATIC_ASSIGNMENT_UPDATED` is being replaced with `AUTOAMTIC_ASSIGNMENT_UPDATED`.
  - `MODEM_MESSAGE_BODY_PARSER_AUTOMATIC_ASSIGNMENT_DELETED` is being replaced with `AUTOAMTIC_ASSIGNMENT_DELETED`.
  - `MODEM_MESSAGE_BODY_PARSER_ASSIGNED` is being replaced with `DIRECT_ASSIGNMENT_ADDED`.
  - `MODEM_MESSAGE_BODY_PARSER_UNASSIGNED` is being replaced with `DIRECT_ASSIGNMENT_REMOVED`.

- Added `OrganizationPermission`s:
  - `MODEM_ALARMS` to manage the new modem alarms.
  - `ASSIGNMENTS` to manage assignments though the new assignment service.

##### AssignmentService

- Introduced the new `AssignmentService`, in combination with the `DirectAssignmentService` and
  `AutomaticModemAssignmentService`, which are used to assign `ModemAlarm`s and `ModemMessageBodyParser`s
  to each other and to `Modem`s.
- Added `AssignmentService.ModemAssignments` (`ListModemAssignments`) to list everything assigned to modem(s).

##### AutomaticModemAssignmentService

- Introduced the new `AutomaticModemAssignmentService`, which can be used to automatically assign `ModemAlarm`s
  and `ModemMessageBodyParser`s to `Modem`s with certain properties (like tags, manufacturers, peripherals etc).
- Added `AutomaticModemAssignmentService.List` (`ListAutomaticModemAssignments`) to list all the
  available automatic modem assignments (including inherited from your parent organizations).
- Added `AutomaticModemAssignmentService.Create` (`CreateAutomaticModemAssignment`) to create a new automatic
  modem assignment.
- Added `AutomaticModemAssignmentService.Update` (`UpdateAutomaticModemAssignment`) to update an existing
  automatic modem assignment, altering which modems it affect and what it assigns.
- Added `AutomaticModemAssignmentService.Enable` (`EnableAutomaticModemAssignment`) to enable an
  automatic modem assignment.
- Added `AutomaticModemAssignmentService.Disable` (`DisableAutomaticModemAssignment`) to disable an
  automatic modem assignment.
- Added `AutomaticModemAssignmentService.Delete` (`DeleteAutomaticModemAssignment`) to delete an
  automatic modem assignment.
- Added `AutomaticModemAssignmentService.UpdateAvailability` (`UpdateAutomaticModemAssignmentAvailability`) to make
  an automatic modem assignment available to (a selection of) child organizations.

##### DirectAssignmentService

- Introduced the new `DirectAssignmentService` and which is used to assign `ModemAlarm`s and `ModemMessageBodyParser`s
  to each other and to `Modem`s.
- Added `DirectAssignmentService.List` (`ListDirectAssignments`) to list direct assignments.
- Added `DirectAssignmentService.Assign` (`AssignDirectly`) to add a new direct assignment,
  possibly overriding an automatic assignment and adding configuration.
- Added `DirectAssignmentService.Unassign` (`UnassignDirectly`) to remove a direct assignment.

##### EventService

- Added `ModemAlarm`-related `Event`s:
  - `ModemEvent.AlarmEvent.ModemAlarmEvent` when a modem alarm is triggered on a message.
  - `ModemEvent.AlarmEvent.CreatedEvent` when a modem alarm is created.
  - `ModemEvent.AlarmEvent.UpdatedEvent` when a modem alarm is updated.
  - `ModemEvent.AlarmEvent.DeletedEvent` when a modem alarm is deleted.

  See `ModemAlarmService` for more details.

- Added assignment-related `Event`s:
  - Added `AssignmentEvent.AutomaticModemAssignmentCreatedEvent` when a direct assignment is added.
  - Added `AssignmentEvent.AutomaticModemAssignmentUpdatedEvent` when a direct assignment is removed.
  - Added `AssignmentEvent.AutomaticModemAssignmentDeletedEvent` when an automatic modem assignment is created.
  - Added `AssignmentEvent.DirectAssignmentAddedEvent` when an automatic modem assignment is updated.
  - Added `AssignmentEvent.DirectAssignmentRemovedEvent` when an automatic modem assignment is deleted.

  See the `DirectAssignmentService` and `AutomaticModemAssignmentService` for more details.

- Deprecated `EventType`s:
  - `ModemEvent.MessageBodyParserEvent.AutomaticAssignmentEvent.CreatedEvent` is being replaced with `AssignmentEvent.AutomaticModemAssignmentCreatedEvent`.
  - `ModemEvent.MessageBodyParserEvent.AutomaticAssignmentEvent.UpdatedEvent` is being replaced with `AssignmentEvent.AutomaticModemAssignmentUpdatedEvent`.
  - `ModemEvent.MessageBodyParserEvent.AutomaticAssignmentEvent.DeletedEvent` is being replaced with `AssignmentEvent.AutomaticModemAssignmentDeletedEvent`.
  - `ModemEvent.MessageBodyParserEvent.AssignedEvent` is being replaced with `AssignmentEvent.DirectAssignmentAddedEvent`.
  - `ModemEvent.MessageBodyParserEvent.UnassignedEvent` is being replaced with `AssignmentEvent.DirectAssignmentRemovedEvent`.

##### ModemService

- Added `ModemMessage.metadata`, which can be filled with metadata that is sent with messages.

##### ModemAlarmService

- Introducing `ModemAlarm`s, which are customizable alarms triggered by a selection of checks.
  Alarms can be set on a modem, and validate that modem's messages, for example by location or by
  a field in the parsed message body.
- Added `ModemAlarmService.List` (`ListModemAlarms`) to list available modem alarms
  (including inherited from your parent organizations).
- Added `ModemAlarmService.Create` (`CreateModemAlarm`) to create a new modem alarm with any number of checks.
- Added `ModemAlarmService.Update` (`UpdateModemAlarm`) to update a modem alarm and its checks, if you are the owner.
- Added `ModemAlarmService.Delete` (`DeleteModemAlarm`) to delete a modem alarm, if you are the owner.
- Added `ModemAlarmService.AddCheck` (`UpdateModemAlarmAddCheck`) to add a check to a modem alarm, if you are the owner.
- Added `ModemAlarmService.UpdateCheck` (`UpdateModemAlarmUpdateCheck`) to update a check in a modem alarm,
  if you are the owner.
- Added `ModemAlarmService.RemoveCheck` (`UpdateModemAlarmRemoveCheck`) to remove a check from a modem alarm,
  if you are the owner.
- Added `ModemAlarmService.TestParameters` (`TestModemAlarmTestParameters`) to test a set of parameters on a
  modem alarm, to see the result when they are applied during assignment.
- Added `ModemAlarmService.UpdateAvailability` (`UpdateModemAlarmAvailability`) to make a modem alarm (un)available to
  (a selection of) child organizations.
- Added `ModemAlarmService.Assign` (`AssignModemAlarms`) to assign a modem alarm to a modem.
- Added `ModemAlarmService.Unassign` (`UnassignModemAlarms`) to unassign a modem alarm from a modem.

##### ModemMessageBodyParserService

- **[B]** Removed `ModemMessageBodyParserService.ListAssignedParsers`, which was deprecated since 0.51.
- **[B]** Removed `ModemMessageBodyParserService.AssignToModems`, which was deprecated since 0.51.
- **[B]** Removed `ModemMessageBodyParserService.RemoveFromModems`, which was deprecated since 0.51.
- **[B]** Removed `ModemMessageBodyParser.id`, which was deprecated since 0.51.
- **[B]** Removed `ModemMessageBodyParserSelection.ids`, which was deprecated since 0.51.
- **[B]** Removed `UpdateUploadedModemMessageBodyParserRequest.id`, which was deprecated since 0.51.
- **[B]** Removed `UpdateSimpleModemMessageBodyParserRequest.id`, which was deprecated since 0.51.
- **[B]** Removed `RenameModemMessageBodyParserRequest.id`, which was deprecated since 0.51.
- **[B]** Removed `UpdateChildOrganizationAvailabilityRequest.id`, which was deprecated since 0.51.
- Added `ModemMessageBodyParserService.assign` as a shortcut for `DirectAssignmentService.Assign`.
- Added `ModemMessageBodyParserService.unassign` as a shortcut for `DirectAssignmentService.Unassign`.

##### ModemMessageBodyParserAssignmentService

- Deprecated the entire service in favour of the assignment services.
- **[B]** Removed a number of options from `ModemMessageBodyParserAssignmentSelection`, that are no longer available.

##### ModemMessageBodyParserAutomaticAssignmentService

- Deprecated the entire service in favour of the assignment services.
- **[B]** Removed `CreateBodyParserAutomaticAssignment.apply_to_child_organizations`: child organization availability
  can now only be set after creation, to avoid accidentally polluting child organizations.

##### TestingService

- Added `PushModemMessagesRequest.metadata`, which adds metadata to the message.
  The metadata is available in `ModemMessage.metadata`.

### 0.61 (2020-12-03)

#### Changes

##### StatusService

- Added `UnhealthyModems` to paginate through unhealthy modems.
- Added `UnhealthyPublishers` to paginate through unhealthy publishers.
- Changed `OrganizationStatus` to paginate its modems and publishers:
  - Deprecated `relevant_modems` in favour of `relevant_modems_response`, which is paginated.
  - Deprecated `relevant_publishers` in favour of `relevant_publishers_response`, which is paginated.

### 0.60 (2020-10-22)

This release contains a lot of preparatory work for future features:
- Gateway and connected devices spanning over child organizations.
- Advanced simulation of messages for modems.
- Performance optimizations to scale up supported message volume.

#### Changes

##### ModemService

- Prepare for allowing structures where a gateway is in a parent organization of the connected devices,
  allowing for more complex reseller structures.
- For testing environment, improved modem message simulation, which includes:
  - Configurable simulation per organization (which will be added to the API after a testing phase)
  - Simulating gateways and connected devices
  - Simulating delayed messages
  - Simulating modem inactivity

##### EventService

- Renamed event type `MODEM_MESSAGE_PARSED` to `MODEM_MESSAGE_BODY_PARSED` for clarity in `base.proto`.
- Added example json files for each event to the `event-json-example` directory.
- In `BundledEvent`, the difference between an absolute count and an approximated count was made more clear:
  - The `amount` field has been deprecated (and renamed to `deprecated_amount`).
  - The `last_event` field has been deprecated (and renamed to `deprecated_last_event`).
  - The `approximated_amount` field has been deprecated (and renamed to `deprecated_approximated_amount`).
  - To replace the fields above, we've added the `exact_amount` and `approximated_amount`, which contain
    an `amount` field.
  - Only `ExactAmount` has a `last_event` field, since this value is not available when approximating.
    The `deprecated_approximated_amount` is set to the request time when approximating.

#### Bugfixes and improvements

- Fix publishers stats, which included deleted publishers.

### 0.59 (2020-10-08)

This release introduces a new event type, adds a few quality of life improvements and
a selection of bugfixes and improvements.

#### Changes

##### EventService

- Added `Event.ModemEvent.ModemCreatedEvent`, which is generated when a new modem is created automatically.
  This happens, for example, when a new device is connected to a gateway.
- Added `EventConfoguration.include_empty_summaries` to enable the sending of a message summary when it has no data.
  This can be useful to alert for inactivity in a configured period, but its value depends on the configuration,
  so it is disabled by default.

##### StatusService

- Added `PublisherStatus.publisher_type` to distinguish between the different types of publishers.

#### Bugfixes and improvements

- Fixed Avatar upload for organizations, which would fail under certain conditions.
- Improved modem stale detection. It will be improved iteratively in the coming months.
- Improved the message deduplication.
- Improved system monitoring and testing.

### 0.58 (2020-09-24)

This release is mostly a bug fix and performance release.

#### Changes

##### EventService

- Fixed the event bundled counts. They were changed to an approximation in 0.54, which needed some nuance.
  Now, event bundles are only approximated when there are large numbers of events.

#### Bugfixes

- Set up for improved stale detection on modems. In a next release, this will be used for better stale detection.
- Fix a bug where organization avatars could not be retrieved.
- Add more (performance) monitoring and data caching.

### 0.57 (2020-09-10)

This release introduces a number of new event fields and the option to stream events from child organizations.

#### Changes

##### EventService

- Added `modem_external_device_id` to all modem events:
  - `ModemUpdatedEvent`
  - `ModemLocationUpdatedEvent`
  - `ModemStaleEvent`
  - `ModemActivatedEvent`
  - `ModemMessageDelayedEvent`
  - `ModemMessageCannotBeParsedEvent`
  - `ModemClaimedEvent`

  The field was already present on some modem events, so this was mostly a change for consistency.

- Added `updated_at` to `ModemLocationUpdatedEvent` with the time the modem sent the message with the new location.

  The event time it the time the location was updated on the server, which was misleading,
  given the possible delay between the modem sending the message and the server processing it.

- Added `child_organizations` to `EventStreamRequest`, to allow a client to stream events from its child organizations.
  Some limitations apply, for example related to filtering on tags or publishers, which only works for
  the current (parent) organization.

### 0.55 (2020-08-11)

This release introduces the option to transfer modems without their data.

#### Changes

##### ModemTransferService

- Added type `TransferModemsRequest.DataTransferMode` and field `TransferModemsRequest.date_transfer_modem`
  to indicate what should happen with modem data like messages and events when it is transferred.
  The current options are to include or exclude everything, but more granular options will be added later.

### 0.54.2 (2020-08-10)

This is a minor release with a few more performance improvements and some bug fixes.

#### Changes

##### ModemService

- Dead, damaged and lost modems are now filtered out by default.

##### ModemTransferService

- Fixed a bug that would cause some transfer to be stuck in transit, returning an error when trying to receive them.

### 0.54 (2020-08-06)

This release contains a lot of performance improvements.

You may see some calls return a time out error if they would take a long time before.
This allows us to conserve resources and trace which calls need to be optimized.

#### Changes

##### EventService

- Some event bundles now have an approximated count, to avoid them timing out.
  In the next few releases, we will optimize this to provide accurate counts whenever possible within the timeout.

### 0.53 (2020-07-27)

#### Changes

##### DashboardService

- Performance fixes for message counts.

##### EventService

- Added `OrganizationCreatedEvent.avatar` with the avatar for the created organization.
- Limited `ModemMessageDroppedEvent` to messages using Hiberband.

##### OrganizationService

- Added `Organization.avatar` and `CreateOrganizationRequest.avatar`.
- Added `GetOrganizationAvatar` request to fetch avatars for organizations.

##### ModemService

- Added `ListModemsRequest.include_missing_group_parents` which when set adds missing group parents
  to the `ListModemsRequest.Response.group_parents`.
- Added `Grouped` and `ListModemsGrouped` to list modems in a grouped structure.
  Currently, the only grouped structure is the gateway and its connected devices.
- Performance fixes for
  - message counts;
  - listing messages when filtering on source.

##### ModemTransferService

- Added `TransferModemsRequest.Response.mark_received_automatically_failed` to indicate whether the
  transfer was successfully marked received when requested, so we don't have to rollback the transfer.
  If this field is false, the transfer needs to be marked as received manually in the receiver organization.

### 0.52.3 (2020-07-13)

This release contains a collection of performance fixes.

- Performance optimizations in the message processing pipeline.
  - Much of the pipeline is now asynchronous, instead of processing in the context of the API request.
    This means API requests will finish faster, and bucketing can be applied to message processing.
    Backpressure is still available through the processes, so if the message processing would get overloaded,
    requests will get delayed eventually.
  - Where before, the request would not finish until the message event was produced, this is no longer connected.
    Keep this in mind when expecting an event before the end of the request.
    There may be a delay of up to 30 seconds between the request and the event, depending on system load, timing
    and request size.

#### Changes

##### UserService

- Bugfix: `UserSelection.search` now also matches user ids.

#### Bugfixes

- `UserSelection.search` also matches user ids.
- `Pagination.Result` next and previous are now unset instead of assigned an empty object when not available.

### 0.52 (2020-07-06)

This release contains a few minor additions and some bugfixes.

#### Changes

##### AWSIoTService

- Added `created_by`, containing the user id of the user who created this publisher, to `AWSIoTConfiguration`.

##### MQTTService

- Added `created_by`, containing the user id of the user who created this publisher, to `MQTTPublisher`.

##### SlackIntegrationService

- Added `created_by`, containing the user id of the user who created this publisher, to `SlackPublisher`.

##### WebhookService

- Added `created_by`, containing the user id of the user who created this publisher, to `Webhook`.

##### Other

- Added `created_by`, containing the user id of the user who created this publisher, to `Publisher`
  (the generic publisher object used in events).

#### Bugfixes

- Fixed a bug where some message would not generate message events, because of a bug in the changes that introduced
  the new `ModemMessageBodyReceivedEvent` and `ModemMessageBodyParsedEvent` types.
  No data was lost, and the events will be generated by the system after the update.

### 0.51 (2020-06-29)

This release introduces automatic assignment rules for modem message body parsers.
These rules can be used to assign body parsers to modems across organizations, based on criteria like
tags, manufacturers and peripherals.

#### Changes

##### DashboardService

- Fixed a few comments.

##### EventService

- Added two new modem message events:
  - `ModemMessageBodyReceivedEvent` is a simplified version of the `ModemMessageReceivedEvent` that
    doesn't have a `Message` object. Instead, it only has `message_id`, `sent_at` and `body`.
    This is useful for the cases where you need a lighter format and are not using body parsing.
  - `ModemMessageBodyParsedEvent` is an event that is produced for each message, for each body parser.
    If you assign 3 body parsers to modem, they all try to parse the message. Every success produces this event.
    This is useful for the cases where you're only interested in the parsed body.
  - For each of these events, an `EventType` has been added to `base.proto`
  - For all three message events, an example json has been added under `event-json-examples`.
    In the future, more examples for other event types will be placed there.

- Added new body parser events:
  - `MessageBodyParserEvent.CreatedEvent` is produced when a new body parser is created.
  - `MessageBodyParserEvent.UpdatedEvent` is produced when a body parser is updated.
  - `MessageBodyParserEvent.DeletedEvent` is produced when a body parser is deleted.
  - `MessageBodyParserEvent.AssignedEvent` is produced when a body parser is directly assigned to a modem.
  - `MessageBodyParserEvent.UnassignedEvent` is produced when a body parser is removed from to a modem.
  - `MessageBodyParserEvent.AutomaticAssignmentEvent.CreatedEvent` is produced when a new automatic assignment rule
    for body parsers is created.
  - `MessageBodyParserEvent.AutomaticAssignmentEvent.UpdatedEvent` is produced when an automatic assignment rules for
    for body parsers is updated.
  - `MessageBodyParserEvent.AutomaticAssignmentEvent.DeletedEvent` is produced when an automatic assignment rules for
    for body parsers is deleted.
  - For each of these events, an `EventType` has been added to `base.proto`

- Added a new event `UserValidationUpdatedEvent` when user validation has been updated.

- Fixed a few imports and comments.

##### ModemService

- `ModemMessage.ParsedBody` was updated to reflect the changes to body parsers:
  - Added `parser_identifier` to `ParsedBody`. This field contains a globally unique identifier
    for the body parser used to parse the message body.
  - The `parser_id` is now deprecated in favour of the `identifier`.
  - Wrapped `result` and `error` in a `oneof`, since only one can be present.

- Added `UpdateModemStatusRequest.modem_selection` to update the status for multiple modems at the same time.
  - Deprecated the single modem field `UpdateModemStatusRequest.modem_number`, since the selection covers that case.

- Fixed a few imports and comments.

##### ModemMessageBodyParserService

- Deprecated the assignment-related calls in favour of the new `ModemMessageBodyParserAssignmentService`:
  - Deprecated `ListAssignedParsers` and `ListAssignedParsersRequest`
  - Deprecated `AssignToModems` and `AssignModemMessageBodyParserToModemsRequest`
  - Deprecated `RemoveFromModems` and `RemoveModemMessageBodyParserFromModemsRequest`

- Updated `ModemMessageBodyParser` to match the new global body parser usage better:
  - Added `identifier` to `ModemMessageBodyParser`, a globally unique identifier for the body parser.
  - Added `organization` to `ModemMessageBodyParser`, to show who owns the body parsers.
  - Deprecated `id` in `ModemMessageBodyParser` in favour of the `identifier`.
  - **[B]** Dropped `ModemMessageBodyParser.AvailableToChildOrganizations.parser_id_for_child_organizations`
    in favour of the new `identifier`.

- Updated `ModemMessageBodyParserSelection` to match the changes to `ModemMessageBodyParser`:
  - **[B]** Removed `SelectIdentifier` and its related field.
  - Added `identifiers` to search on identifiers.
  - Deprecated `ids` in `ModemMessageBodyParser` in favour of `identifiers`.
  - Renamed `exclude_provided_parsers` to `only_owned_parsers`.
  - Renamed `providers` to `owner_organizations`.

- Added `ListModemMessageBodyParsersRequest.exclude_content` to not fill the content of the returned body parsers
  (either the `content_ksy` or `simple_parser` fields).

- Updated `UploadModemMessageBodyParserRequest`, `UpdateSimpleModemMessageBodyParserRequest`,
  `RenameModemMessageBodyParserRequest` and `UpdateChildOrganizationAvailabilityRequest` to match the changes
  to `ModemMessageBodyParser`:
  - Added `identifier` and deprecated `id`.

- Updated `TestModemMessageBodyParserRequest` to match the changes to `ModemMessageBodyParser`:
  - **[B]** Removed the `SelectIdentifier`-based field.
  - Added `identifier`.

##### ModemMessageBodyParserAutomaticAssignmentService

- Added `ModemMessageBodyParserAutomaticAssignmentService` to manage automatic assignment rules for body parsers.

  These rules can be used to automatically assign body parsers to modem that match specific criteria.
  For example, all modems with tag "parse-this" and a peripheral "sensor": "water-sensor-brand-x" can be
  assigned a parser for the data format for that peripheral.

  Criteria can be used and combined in a multitude of ways, but here are a few notable uses:
   - assign a parser to tag, so assigning it to modems is as easy as adding a tag to that modem
   - assign a parser to peripheral, so each modem with that peripheral gets that parser by default
   - blacklisting a parser from a tag, so you can set that tag to exclude a modem from being assigned that parser
   - blacklisting a parser from a set of modems, so you can exclude a set of modem from being assigned that parser
   - add a parser to devices you manufacture, and apply this to child organizations, so that all of your
     customers' modems are automatically assigned that parser

##### ModemMessageBodyParserAssignmentService

- Added `ModemMessageBodyParserAssignmentService` to assign body parsers directly to modems and
  list assignments based on direct assignments to modems and the result of applying automatic assignment rules.

##### TokenService

- Added the `created` `Token` to `CreateTokenRequest`, so the output is more that just the token string.

#### Backwards incompatible changes

- **[B]** Removed `SelectIdentifier` and its related field from `ModemMessageBodyParserSelection`.
  Use the new `identifier` field instead.
- **[B]** Dropped `parser_id_for_child_organizations` from `ModemMessageBodyParser.AvailableToChildOrganizations`.
  Use the new `identifier` field instead.
- **[B]** Removed the `SelectIdentifier`-based field from `TestModemMessageBodyParserRequest`.
  Use the new `identifiers` field instead.

### 0.50 (2020-06-18)

#### Changes

##### ModemService

- Fixed a bug when listing child organizations that could cause incomplete data.

##### TokenService

- Removed `override_allow_no_permissions` from `CreateTokenRequest` and `UpdateTokenOrganizationPermissionsRequest`.
  The API would check whether a token was created with or updated to an empty set of organization permissions.
  This was confusing to users, and since permissions can easily be updated, we opted to remove it.

##### EmailNotificationPreferencesService

- Fixed a bug where a user without the `PUBLISHERS` permission would not be able to update their email preferences.

### 0.49.1 (2020-06-04)

#### Changes

##### ModemService

- Added `gateway_info` to `Modem`, with gateway-specific information, iff the modem is a gateway.
- Added `connected_device_info` to `Modem`, with specific information, iff the modem is a connected device.
  This replaces the `connected_to_gateway` and `external_device_ids` fields on `Modem`, which are now deprecated.

### 0.49 (2020-05-18)

This release contains a few minor additions to the API.

#### Changes

##### CurrentUserService

- Added `contact` to `AccessibleOrganizationsRequest.AccessibleOrganization`.

##### ModemService

- Added `UpdateModemStatusRequest` and `ModemService.UpdateStatus` to update the status of a modem.
  Modems with the `DEAD` status are hidden from the modem list by default.

#### Bugfixes

- An auto-disabled publisher that was manually re-enabled would no longer be eligible for auto-disable.
  This has now been updated to suspend auto-disable for a week.
  If after a week, the publisher is still failing, it will be auto-disabled again.
- Fixed a few instances where transactions were not used, while they should have been.

### 0.48 (2020-05-14)

This release introduces the concept of an organization event configuration.
It is only used for `Event.OrganizationEvent.ModemMessageSummaryEvent` at the moment,
but more events may be configurable this way in the future.

Another change this release makes is in approximating total count for pagination for a few calls.
The `Pagination.Result.approximated_total` field indicates that its total is an approximation.
This will generally be set for data that changes often, or is generally only fetched in a scrolling manner.

Currently, approximation has been enabled for:
- listing modem messages
- listing webhook history
- listing MQTT integration history
- listing Slack integration history
- listing email history
- listing unbundled events

#### Changes

##### Common types in `base.proto`

- Added extra documentation on to `Date` specifying the accepted format for the `textual` field.
- Added `Pagination.Result.approximated_total`, which indicates that the total is an approximation,
  and not an exact value.
- Added `ORGANIZATION_EVENT_CONFIGURATION_UPDATED` to `EventType`. See the `EventService` changes for more information.
- Added `MODEM_MESSAGE_SUMMARY` to `EventType`. See the `EventService` changes for more information.

##### EventService

- Added `Event.OrganizationEvent.ModemMessageSummaryEvent`, which is an event that can be produced at a
  configured period, and gives a summary of messages over that period.
- Added `EventConfiguration`, which is an organization configuration that allows you to customize some
  events for an organization. It is currently only used for the new `Event.OrganizationEvent.ModemMessageSummaryEvent`.
  - Added `GetEventConfiguration` to get the current `EventConfiguration` for the organization.
  - Added `UpdateEventConfiguration` to update the `EventConfiguration` for the organization.
  - Added `Event.OrganizationEvent.EventConfigurationUpdated` which is produced whenever
    the `EventConfiguration` is updated.

### 0.47 (2020-05-07)

This release clears up most of the confusion around the new health options for modems and publishers, and
improves performance.

#### Changes

##### AWSIoTService

- We've opted to remove the option to configure `health_error_period`,
  since it was unclear and had an unintended performance impact.
  - **[B]** Removed `AWSIoTConfiguration.HealthConfig.health_error_period`
  - **[B]** Removed `UpdateAWSIoTIntegrationConfigurationRequest.health_error_period`

##### ModemService

- We've opted to remove the option to configure `health_error_period`,
  since it was unclear and had an unintended performance impact.
  - **[B]** Removed `Modem.HealthConfig.health_error_period`
  - **[B]** Removed `UpdateModemHealthConfig.Request.health_error_period`
- Changed `ListModemsRequest.sort_by` to accept multiple values to sort on, and added more sort options.
- Added `ModemMessageSelection.filter_by_sources` to filter modem message by source
  (i.e. whether it is a real message, received through satellite or direct connection, etc.)

##### ModemTransferService

- Added `TransferModemsRequest.gateway_transfer_mode` to define what happens with connected devices when transferring
  a gateway, either including all connected devices, orphaning them or deleting them.
  See the documentation in `modem_transfer.proto` for more information.
- Deprecated `TransferModemsRequest.allow_gateways_and_external_devices` in favor of
  `TransferModemsRequest.gateway_transfer_mode`.

##### ModemMessageBodyParserService

- Modem message parsers can now be shared with child organizations.
  - Added `ModemMessageBodyParserService.UpdateChildOrganizationAvailability` with
    `UpdateChildOrganizationAvailabilityRequest` to make parsers available to child organizations.
  - Added `ModemMessageBodyParser.provided_parser_id`, the identifier for parsers provided by a parent organization.
  - Added `ModemMessageBodyParser.available_to_child_organizations`, to show the availability to child organizations.
  - Added `ModemMessageParserSelection.identifiers` to filter on both owned and provided parsers.
  - Added `ModemMessageParserSelection.exclude_provided_parsers` to exclude any provided parsers.
  - Added `ModemMessageParserSelection.providers` to filter provided parser by provider organization.
- Added `ModemMessageBodyParserService.Retry` to retry parsing messages and save the result.

##### MQTTService

- We've opted to remove the option to configure `health_error_period`,
  since it was unclear and had an unintended performance impact.
  - **[B]** Removed `MQTTPublisher.HealthConfig.health_error_period`
  - **[B]** Removed `UpdateMQTTPublisherRequest.health_error_period`
- Added `ListMQTTPublishersRequest.sort` to sort the results.

##### SlackService

- We've opted to remove the option to configure `health_error_period`,
  since it was unclear and had an unintended performance impact.
  - **[B]** Removed `SlackPublisher.HealthConfig.health_error_period`
  - **[B]** Removed `UpdateSlackPublisherRequest.health_error_period`
- Added `ListSlackPublishersRequest.sort` to sort the results.

##### WebhookService

- We've opted to remove the option to configure `health_error_period`,
  since it was unclear and had an unintended performance impact.
  - **[B]** Removed `Webhook.HealthConfig.health_error_period`
  - **[B]** Removed `UpdateWebhookRequest.UpdateWebhook.health_error_period`
- Added `ListWebhooksRequest.sort` to sort the results.

### 0.45 (2020-04-02)

##### Modem health changes

The modem health calculation has changed in a number of ways.

First, events that contribute to the modem health are now split on whether they are resolvable or not.
- Events that cannot be resolved will no longer put the modem in ERROR health, but are limited to influencing the
  WARNING health. An example of such events is `MODEM_MESSAGE_DELAYED`.
- Events that can be resolved now determine the error health, which means that as soon as they are resolved
  the modem becomes healthy again (either OK or WARNING depending on the other events).
  An example of such events is `MODEM_STALE`.

Additionally, you can now configure the period used to determine health per modem.
This can be done in the following way:
- `health_warning_period`: the period to consider when determining health from warning events.
- `health_error_period`: the *optional* period to consider when determining health from error events.
  All unresolved error events are included, regardless of age, since they have not been resolved.
  When a period is set (default not set), all error events in that period are included, even if they were
  resolved.

##### Publisher health changes

The health calculation for publisher like webhook, MQTT or AWSIoT integrations has changed in a number of ways.

Publishers are different from modems in that they only have resolvable events.
For example, a `PUBLISHER_FAILED` event is resolved by the next successful call.

You can now configure the period used to determine health per publisher.
This can be done in the following way:
- `health_warning_period`: the period to consider when determining health from percentage of failed calls.
- `health_error_period`: the *optional* period to consider when determining health from error events.
  All unresolved error events are included, regardless of age, since they have not been resolved.
  When a period is set (default not set), all error events in that period are included, even if they were
  resolved.

#### Changes

##### Common types in `base.proto`

- Added `Duration`, which is a duration specified either by `google.protobuf.Duration` or a textual field.
  - Supported textual formats range from the ISO-8601 duration format (`PnDTnHnMn.nS`), to
    formats like `1 day`, `3d4h5m` or even `3 hours -10 minutes`.
  - Added the related `UpdateOptionalDuration` to update the duration when it can be unset.

- Renamed `EventType.MODEM_MESSAGE_SEQUENCE_SKIP` to `EventType.MODEM_MESSAGE_DROPPED`
  - This change is backwards compatible with older versions, since it only changes the name of the field.
    When building with the latest API version, you will need to update your usages.

##### Events

- Added `health_error_period` and `health_warning_period` to `ModemUpdatedEvent` and `PublisherEvent.UpdatedEvent`.

##### AWSIoTService

- Added `health` and `health_config` to `AWSIoTConfiguration`.
- Added `health_error_period`, `health_warning_period` and
  `health_warning_failure_percentage` to `UpdateAWSIoTIntegrationConfiguration`.

##### ModemService

- Added `health_config` to `Modem`.
- Added `UpdateModemHealthConfig` call to update the modem health configuration.
- Added `is_gateway_message` and `via_gateway_message` to `ModemMessage`:
  - `is_gateway_message` indicates that this message was received through a gateway, i.e. Hiberband Via
  - `via_gateway_message` gives the message id of the gateway message it was received through.

##### MQTTService

- Added `health_config` to `MQTTPublisher`.
- Added `health_error_period`, `health_warning_period` and
  `health_warning_failure_percentage` to `UpdateMQTTPublisherRequest`.

##### SlackIntegrationService

- Added `health_config` to `SlackPublisher`.
- Added `health_error_period`, `health_warning_period` and
  `health_warning_failure_percentage` to `UpdateSlackPublisherRequest`.

##### WebhookService

- Added `health_config` to `Webhook`.
- Added `health_error_period`, `health_warning_period` and
  `health_warning_failure_percentage` to `UpdateWebhookRequest`.

### 0.43 (2020-03-10)

This release contains a few minor api tweaks and one semi-breaking change.

#### Changes

##### ModemService

- **[B]** Changed `ModemMessage.ParsedBody.result` to a `google.protobuf.Struct`,
  which is the accurate representation of variable json data in protobuf.
  This change is mostly backwards compatible:
  - For any API client, the previous result field will be empty until their generated api code is updated.
  - For any json client (i.e. webhooks), the output will not change, except that the json will be improved.

##### ModemMessageBodyParserService

- Added a `Test` command to test a body parser on a given byte sequence, or an existing message id.

##### UserService

- Added `search` to `UserSelection`, which searches on all available text fields.
- Added `remove_all_tokens` to `RemoveUserRequest`, to delete all tokens created by that user when
  removing the user from your organization.

##### SlackIntegrationService

- Added `search` in `SlackPublisherSelection` to search on all available text fields.

##### WebhookService

- Added `search` to `WebhookSelection`, which searches on all available text fields.
- Added `UpdateWebhooks` command to update multiple webhooks in one request.

#### Backwards incompatible changes

- **[B]** Changed `ModemMessage.ParsedBody.result` to a `google.protobuf.Struct`,
  which is the accurate representation of variable json data in protobuf.
  This change is mostly backwards compatible:
  - For any API client, the previous result field will be empty until their generated api code is updated.
  - For any json client (i.e. webhooks), the output will not change, except that the json will be improved.


### 0.39 (2020-01-24)

This release introduces a number of smaller fixes, plus a few big new features:

- User Invite system:

  This system allows you to invite a user to your organization.
  The user receives an email and can see a list of invites in mission control, and accept them (implemented in the `CurrentUserService`).

- Modem message body parsing system:

  There is now a sytem in place to parse the body of your messages using a binary specification. This can be done in two ways:

  - This system allows you to upload [Kaitai struct file](https://kaitai.io/) to parse the body of your modem messages.
  - You can also specify a simple parser using the simple parser calls in the `ModemMessageBodyParserService`.

  Soon, you can build a simple parser in Mission Control as well.

  The resulting parsed modem message is added to your message, so you can easily see the parsed version of a message.
  In the message, lok for the `body_parsed_successfully` and `body_parsed` fields.
  The parsed body is represented as a `map<string, string>` in protobuf, and integrated into the json in,
  for example, the `ModemMessageReceivedEvent`.

- User validation system

  This system allows you to set rules to validate new users added to your organization.
  For now, it's limited to a regular expression applied to the email address.
  This is enough for most use cases, like limiting the organization to users with an `@your-domain.com` email address.

#### Changes

- Added a new permission `MODEMS_MESSAGE_BODY_PARSERS` to `OrganizationPermission`, for the new message body parsing system.

##### CertificateService

- Added `include_certificate_content_in_response` to any calls returning a certificate.
  Set this to true to include the certificate in the response.
- **[B]** any calls that return a certificate object no longer return the certificate content by default.
  Use the `include_certificate_content_in_response` to include it.

##### CurrentUserService

- Added `ListOrganizationInvites` and `AcceptOrganizationInvite` for the new invite system.
  You will see this soon in Mission Control.
- Added `member_only` and `default_only` in `AccessibleOrganizationsRequest` to filter the returned organizations.
- **[B]** Added the `AccessibleOrganization` message in the `AccessibleOrganizationsRequest.Response`,
  replacing the original `organizations` field, and adds a lot more information.

##### EventService

- Added `UserEvent.UserInvitedEvent` related to the new invite system.
- Added `notes` and `secure_notes_updated` to `ModemUpdateEvent`.
- Added `sent_at` to `ModemActivatedEvent`.
- Added `modem_external_device_id` to `ModemMessageReceivedEvent`, to easily map the modem message to an external device.

##### ModemService

- Added `body_parsed_successfully` and `body_parsed` to `ModemMessage` for the new message body parsing system.

##### ModemMessageBodyParserService

- Added the `ModemMessageBodyParserService`, which is the main interface for the new message body parser system.

##### TokenService

- Added `override_allow_no_permissions` to a few calls to allow creation of tokens without any organization permissions.

##### UserService

- Added `override_allow_no_permissions` to a few calls to allow users without any organization permissions.
- Added `Invite` and `ListInvitations` for the new invite system.
- Added `GetUserValidation`, `UpdateUserValidation` and `TestUserValidation` for the new user validation system.
- Added `Activity` to see user activity per date.

##### WebhookService

- In `WebhookCall`, the `body` field was renamed to `body_proto` and `body_json` was added for convenience.

#### Backwards incompatible changes

- **[B]** any calls that return a certificate object no longer return the certificate content by default.
  Use the `include_certificate_content_in_response` to include it.
- **[B]** Added the `AccessibleOrganization` message in the `AccessibleOrganizationsRequest.Response`,
  replacing the original `organizations` field, and adds a lot more information.


### 0.33 (2019-11-07)

This release contains a lot of API functionality:

- The publishers have been expanded significantly:
  - The deprecated generic publisher API `PublisherService` has been removed,
    in favor of specific APIs for different publisher types.
  - Added specific publisher APIs:
    - `AWSIoTService` for AWS IoT integration;
    - `MQTTService` for MQTT integration;
    - `SlackIntegrationService` for Slack integration;
    - `EmailNotificationPreferencesService` for email preferences (which is implemented as a publisher).
  - Most publisher types now support **retrying failed calls**.
    This works by retrying a failed publisher with a single failed call
    (when it hasn't already failed on a live call that day). When this call succeeds,
    all other calls are scheduled to be retried.
    - To handle cases where a single call fails, the daily retries are done in a round robin fashion, which means
      that every day a different call is tried.
    - Calls that have failed more than 10 times are reduced in priority and will eventually no longer be retried.
    - A publisher that fails consistently will eventually be disabled,
      generating an `Event.PublisherEvent.AutoDisabledEvent`.

#### Changes

- **[B]** `UpdateWebhookFilterRequest.Update*` and `UpdatePublisherRequest.Update*` have been extracted to
  the `base.proto` as `Filter.*.Update`:
  - `UpdateWebhookFilterRequest.UpdateEvents` is replaced by `Filter.Events.Update`.
  - `UpdateWebhookFilterRequest.UpdateModems` is replaced by `Filter.Modems.Update`.
  - `UpdateWebhookFilterRequest.UpdateTags` is replaced by `Filter.Tags.Update`.
  - `UpdatePublisherRequest.UpdateEvents` is replaced by `Filter.Events.Update`.
  - `UpdatePublisherRequest.UpdateModems` is replaced by `Filter.Modems.Update`.
  - `UpdatePublisherRequest.UpdateTags` is replaced by `Filter.Tags.Update`.
- Added the `MODEMS_SECURE_NOTES` permission. See the `ModemService` changes for more information.

##### AWSIoTService

- Added `mqtt_client_identifier` to `AWSIoTConfiguration`, to customize the MQTT client identifier.
- Replaced `modems` field of `UpdatePublisherRequest.UpdateModems` with `modems` field of `Filter.Modems.Update`.
  The index is different, so this is backwards compatible.

##### CurrentUserService

- Added `user_hash` to `CurrentUser`, for Mission Control.
- Added `search` and `pagination` to `AccessibleOrganizationsRequest` and its `Response`.

##### EmailNotificationPreferencesService

- Added the `EmailNotificationPreferencesService`, which is used to manage your email preferences.
  - You can now receive emails for events, which you can configure here.
  - By default, it uses your user, but you can also set up email preferences for a custom email address.

##### EventService

- Added `Event.ModemEvent.ModemUpdatedEvent`, which is generated whenever modem data is updated by a user.
- Refactored the `Event.PublisherEvent.UpdatedEvent` to use the new data structures.
- Added `Event.PublisherEvent.AutoDisabledEvent` which is generated when a publisher is disabled
  because of consistent failures.

##### MapService

- Added some comments to make the `TileMapRequest` more clear.

##### ModemService

- Added `Modem.notes` and `UpdateModemNotesRequest` to update the notes for a modem.
  - Notes are a free text multi-line notes field which can be used to store any information for a modem.
- Added `Modem.secure_notes` and `UpdateModemSecureNotesRequest` to update the secure notes for a modem.
  - The secure notes field is similar to the normal notes field, but it is encrypted in the database, and only
    visible and editable if you have the `MODEMS_SECURE_NOTES` permission.
- **[B]** Removed `Modem.version`, since it did not contain any useful information for the user.
- Added `Modem.sources` to show where a message has come from:
  - `HIBERBAND`:  A real message from a modem or gateway, sent over Hiberband to the server.
  - `DIRECT_TO_API`: A real message from a modem or gateway, sent directly to the API using a persistent connection.
  - `TEST`: A test message sent to the testing API.
  - `SIMULATION`: A simulated message, generated by the server.

##### MQTTService

- Added `MQTTService` for MQTT integration. This was previously configurable through the deprecated `PublisherService`.

##### OrganizationService

- Added `OrganizationSelection.search` to search organizations.
- Added `ListChildOrganizationsRequest.include_details` to toggle between returning just the names or all the details.

##### PublishersService

- **[B]** This service was deprecated and has now been removed.

##### SlackIntegrationService

- Added `SlackIntegrationService` for Slack integration.
  - This works similarly to a webhook, but send messages directly to Slack using a Slack webhook.

##### WebhookService

- Added `certificate_name`, `ca_certificate_id`, `ca_certificate_name` to `Webhook`.
- Replaced `event_filter`, `modem_filter` and `tag_filter` fields
  in `UpdateWebhookFilterRequest` and `UpdateWebhookRequest` with the new `Filter.*.Update` types.
  The old fields are still available as deprecated fields:
  `deprecated_event_filter`, `deprecated_modem_filter` and `deprecated_tag_filter`.

#### Backwards incompatible changes

- **[B]** Removed `Modem.version`, since it did not contain any useful information for the user.
- **[B]** The `PublishersService` has been removed completely. Use the new specific APIs.
- **[B]** `UpdateWebhookFilterRequest.Update*` and `UpdatePublisherRequest.Update*` have been extracted to
  the `base.proto` as `Filter.*.Update`.
  This is backwards compatible in the `WebhookService`, but the deprecated fields will be removed in time.

### 0.27 (2019-08-14)

#### Changes

##### ModemService

- **[B]** Changed the type of `Modem.external_device_ids` to a list of hex string, instead of `int64`s.
- **[B]** Changed the type of `ModemSelection.external_device_ids` to a list of hex string, instead of `int64`s.

##### SSOService

- removed unused import

#### Backwards incompatible changes

- **[B]** Changed the type of `Modem.external_device_ids` and `ModemSelection.external_device_ids`.

### 0.26 (2019-07-15)

This version introduces a selection of smaller fixes and features.

#### Changes

##### CurrentUserService

- Added `AcceptTermsAndConditions` to accept the terms and conditions.
  This will be an added step in the UI in the future.
- Added `accepted_tac` to `CurrentUser` to show whether a user has accepted the terms and conditions.

##### EventService

- Added `Event.OrganizationEvent.OrganizationCreatedEvent` when an organization is created
  as a child of your organization.
- Added `Event.OrganizationEvent.OrganizationDeletedEvent` when an organization is deleted
  as a child of your organization.

##### ModemService

- Added `last_message_id` to `Modem`, with the id of the last received `ModemMessage` for this modem.
- Added `last_message_sent_at` to `Modem`, with the *sent* time of the last received `ModemMessage` for this modem.
- Added `last_message_payload` to `Modem`, with the payload of the last received `ModemMessage` for this modem.
- Added `ModemMessage.is_test` if the message was sent using the `TestingService`.

##### OrganizationPermission

- Added `MODEM_MESSAGES_SEND_REAL_MESSAGES`, for sending real messages from real modems over the internet.
  The main use for this, at the moment, is for gateways with an internet connection,
  providing a second method to send messages: directly to API over an internet connection.

  The API endpoint for this is not in the public API, though a similar endpoint may be added in the future.

##### PublisherService

- Deprecated the `PublisherService`. It will be replaced with specific APIs, like the WebhookService,
  a specific MQTT publisher API, and more publisher implementations.

  The `PublisherService` was not actually in use in the UI, nor has is been used by any other API clients,
  so its removal is considered to be without consequences.

- Added `in_cooldown_until` to `Publisher`

##### WebhookService

- Added `in_cooldown_until` to `Webhook`, which denotes the cooldown, if any.

- The cooldown times have also been updated to be more lenient, using the following semi-exponential scale:

  `1m, 2m, 5m, 10m, 15m, 30m, 1h, 3h, 6h, 12h, 24h`

#### Backwards incompatible changes

Everything is backwards compatible.

### 0.23 (2019-06-03)

This version introduces the ability to predict satellite passes for your modems, and the ability to look up users by id.

#### Changes

##### SatelliteService

- Added `Passes` method, which calculates the satellites passes for given locations.
  - In `ListSatellitesPassesRequest`, you can specify a time range, and a list of location and/or modems.

##### UserService

- Added `user_ids` to `UserSelection`, to find users by id.
  - You can only find users if you would be able to see them in your organization(s).

#### Backwards incompatible changes

Everything is backwards compatible.

### 0.22 (2019-05-10)

This version introduces the `SatelliteService`, a new service dedicated to
providing an easy way to display our satellites, along with some bug fixes.

#### Changes

##### SatelliteService

- Added the new `SatelliteService`, which provides information about our satellites.
  - `List` list the current satellites, their names and TLEs.
  - `Path` lists the path (in lat/lon pairs) the satellite takes over the surface of the earth.
    - The `MapService` contained a similar call called `Satellites`, which has been deprecated.

##### MapService

- Deprecated the `Satellites` call and it's objects (`Satellite` and `SatellitesRequest`)
  in favor of the new `SatelliteService`.

#### Backwards incompatible changes

Everything is backwards compatible.

### 0.21 (2019-05-02)

This release introduces some minor support fields for the gateway solution we're devloping.
It also includes a few convenience fixes.

#### Changes

##### MapService
- Added `density` to `TileMapRequest` to determine how modems are grouped on the map:
  - Default: uses the standard 8x8 configuration, which ensures there are no more than 8 modems/groups per tile,
    both horizontally and vertically.
  - Dense: allows 4 times as many modems/groups in a tile. Any icons used may overlap significantly.
  - Sparse: limits the amount of icons to only 4 horizontally and vertically, which means groups will be bigger
    but any outliers will probably not be visible separately.

##### ModemService

- Added a few gateway-related fields
- Re-ordered and grouped the available field, since they were getting cluttered.
  Related fields are now together, hopefully making them clearer.

  This does not affect the order in messages, which is defined by the numeric value assigned to the fields,
  and, as such, is fully backwards compatible.

##### ModemTransferService

- Added a *warning and ignore* boolean to `TransferModemsRequest`.

  When this value is not set to true, transferring gateways, or modems with an external device id is not allowed.

  Gateways and external devices are connected to the current organization.
  Moving either a gateway or connected external device to another organization without moving the other can
  cause a number of issues, so they should be moved together.

#### Backwards incompatible changes

Everything is backwards compatible.

### 0.19 (2019-04-15)

Release 0.19 introduces the new `TileMap`, which will replace the map in Mission Control.

Additionally, A lot of smaller functionality was added, improved and/or clarified.

#### Changes

##### DashboardService

- **[D]** We've deprecated the map functionality in the dashboard service.
  The identical `Map` call in the `MapService` has also been deprecated in favour of the new `TileMap` in `MapService`.
- Added string `time_zone` support for messages per day grouping, as an alternative to the numeric `time_zone_offset`.

##### EventService

- Added `ModemActivatedEvent` when a modem receives its first real message.
- Added `TokenDeletedEvent` when a token is deleted.

##### MapService

- Added `TileMap`, which is a map based on Google Maps' 256x256 tile system.
- **[D]** The `Map` call has been deprecated in favour of the new `TileMap`.
  The old map has been re-implemented in the new tile-based map for backwards compatibility,
  and may group slightly different per level. The old map calls may be removed in a future version, though.

##### ModemService

- Added `LocationSelection` to `ListModemsRequest`
- Added string `time_zone` support for messages per day grouping, as an alternative to the numeric `time_zone_offset`.

##### OrganizationService

- **[B]** `DeleteOrganizationRequest` has been changed slightly to make the limitations more explicit.
  Your own organization cannot be deleted; you can only delete child organizations.
- `DeleteOrganizationRequest.Response` now lists the affected modems.
- Added `ValidateCreationToken` to validate an organization creation token.

##### UserService

- Added `CreateUsersRequest` to create multiple users in a single request.
- Added `send_password_reset_mail` and `send_password_reset_mail` to `CreateUserRequest` (and `CreateUsersRequest`)
  to indicate whether the newly created user should receive those emails.
- Added `ResetUserPasswordRequest` to reset a users's password.

#### Backwards incompatible changes

- **[B]** `DeleteOrganizationRequest` has been changed slightly to make the limitations more explicit.
  Your own organization cannot be deleted; you can only delete child organizations.


### 0.17 (2019-02-01)

This update is a collection of quality of life improvements to our systems.
- The Mission Control settings have been replaced with more flexible JSon-based settings.
- A single sign-on service is introduced to consolidate authentication on
  [hiber.cloud](https://hiber.cloud),
  [dev.hiber.global](https://dev.hiber.global) and
  [support.hiber.global](https://support.hiber.global).
- Users without organization can now create an organization (with a token provided by customer support, for now)
  instead of only being able to request access to an organization.

#### Changes

##### CurrentUserService

- **[B]** Removed `CurrentUser.Settings` and `CurrentUser.settings`, which were only used by Mission Control.
- **[B]** Removed `UpdateSettingsRequest`, which updated `CurrentUser.settings`.
- Added `mission_control_settings`, a JSon string with the Mission Control settings.
  This allows greater storage flexibility without requiring changes in the API for everything
  Mission Control needs to store.
- Added `UpdateMissionControlSettingsRequest` to update the mission control settings JSon.

##### OrganizationService

- Added `organization_creation_token` to `CreateOrganizationRequest`.
  Using a token provided by Hiber customer support, a user without an organization can create their first organization.
  This will be implemented in Mission Control in the near future.

##### StatusService

- Added the `server` field to `StatusRequest.Response` for information on anything affecting the server status
  (assuming the server is running and responding to the API).

##### SSOService

- Added the `SingleSignOnService` to support single sign-on for other application, using your Hiber login.
- Using this, [support.hiber.global](https://support.hiber.global) will gain Mission Control sign-on in the near future,
  consolidating the different logins used to access our platform.

#### Backwards incompatible changes

- **[B]** Removed `CurrentUser.Settings` and `CurrentUser.settings`, which were only used by Mission Control.
- **[B]** Removed `UpdateSettingsRequest`, which updated `CurrentUser.settings`.


### 0.16.1 (2019-02-01)

This is mostly an intermediate release, preparing for future features.
We've added more information to the `CurrentUser`, some map improvements and some ease of use improvements.

#### Changes

##### DashboardService

- Add `satellites` to `DashboardRequest.Response`, which is a list of `Satellite` objects.

##### MapService

- Add `Satellite` object, which describes a satellite and it's path for the next minutes.
- Add `Satellites` request to `MapService`, which returns a list of `Satellite` objects.
- Add `satellites` to `MapRequest.Response`, which is a list of `Satellite` objects.

#### Backwards incompatible changes

Everything is backwards compatible.

### 0.16 (2019-02-01)

This is mostly an intermediate release, preparing for future features.
We've added more information to the `CurrentUser`, some map improvements and some ease of use improvements.

#### Changes

##### CurrentUserService

- Add `AccessibleOrganizationsRequest` to list accessible organizations, to make impersonation easier.
- Add `current_organization`, `current_organization_permissions` and `user_permissions` to `CurrentUser`.

##### MapService

- Added more map levels:
  - 0: blocks of 15 degrees (latitude), by 20 degrees (longitude)
  - 1: blocks of 10 degrees (latitude), by 15 degrees (longitude)
  - 2: blocks of 7.5 degrees (latitude), by 10 degrees (longitude)
  - 3: blocks of 5 degrees (latitude), by 7.5 degrees (longitude)
  - 4: blocks of 3 degrees (latitude), by 5 degrees (longitude)

  (The map levels are currently only used for the modem density map in Mission Control.)

- Add `ShapeRestriction` to filter map areas on a shape.
  Currently, the API determines the overlapping blocks (for the specified level) to use.
  This will change when we introduce a more flexible modem filtering by location.

- `GroundStation` can now have a name. We've also added our second ground station.
- **[B]** Removed `child_organizations` from `MapSelection`,
  since `MapSelection` is used in other places, while `child_organizations` was only applicable in `MapRequest`.
  - Added `child_organizations` to `MapRequest`.

##### ModemService

- **[B]** Removed `child_organizations` from `ModemSelection`,
  since `ModemSelection` is used in many places, while `child_organizations` was only applicable in a few places.
- **[B]** Similarly, removed `include_inbound_modems` and `include_outbound_modems` from `ModemSelection`,
  since this really only applies to `ListModemsRequest`.
- Added `child_organizations` to `ListModemsRequest` and `GetModemRequest`.
- Added `include_inbound_modems` and `include_outbound_modems` to `ListModemsRequest`.

##### PublisherService

- `EnablePublisherRequest` can now re-enable a publisher that is in cooldown after a failed call.

#### Backwards incompatible changes

- **[B]** Requests with a `ModemSelection` or `MapSelection` that included `child_organizations` need to be updated.
  They will not break, they will just ignore the `child_organizations` in the selection objects.


### 0.15 (2019-01-14)

This version introduces API Permissions.
API permissions are the main way of handling scoped access for users and tokens.

There are two types of permissions:
  - User permissions (i.e. read, request access, delete)
    - Automatically available when you log in through mission control.
    - Configurable on any tokens you create.
  - Organization permissions (i.e. send test messages, manage tokens, access modem license keys)
    - Configurable for every user on your organization.
    - Configurable on any tokens you create.

Permissions are defined in [permission.proto](permission.proto)

Permissions are meant to be discrete sets of tasks, though some may include other permissions
(i.e. MODEMS_UPDATE includes MODEMS). Creating a user without specifying organization permissions results in an empty set of permissions, which results in very limited functionality.

Because all users and tokens effectively had all permissions, we've given every user and token to give them all permissions.

Mission control currently sets all permissions when creating a user or token, and will be updated in the future.
Similarly, roles (groups of permissions) will be introduced in the future to make permission management easier.

#### Changes

##### Common types

- Added `Filter.OrganizationPermissions` which is used to select and return organization permissions.
- Added `Filter.UserPermissions` which is used to select and return user permissions.

##### Permissions

- Added organization permissions
  - `ORGANIZATION_CREATE`: Create a new child organization.
  - `ORGANIZATION_UPDATE`: Update the organizations data, such as billing information, address, and contact.
  - `ORGANIZATION_DELETE`: Delete child organizations. You cannot delete your own organization. To delete your organization, contact support.
  - `MODEMS`: List modems, see their details and health
  - `MODEMS_UPDATE`: Update modems, such as their peripherals, display name and tags. Includes `MODEMS` permission.
  - `MODEMS_LICENSE_KEYS`: Show and regenerate license keys. Includes `MODEMS` permission.
  - `MODEM_MESSAGES`: Read modem messages.
  - `MODEM_MESSAGES_SEND_TEST_MESSAGES`: Send modem messages using the TestingService. Does not include `MODEMS` or `MESSAGES` permission.
  - `MODEM_TRANSFERS`: See modem transfers, inbound and outbound modems. Includes `MODEMS` permission.
  - `MODEM_TRANSFERS_SEND`: Transfer modems to another organization, cancel open transfers and send return transfers. Includes `MODEMS_TRANSFERS` permission.
  - `MODEM_TRANSFERS_PROCESS`: Mark transfers as received, prepare modems for return. This does not include actually sending the return transfer. Includes `MODEMS_TRANSFERS` permission.
  - `MODEM_CLAIM`: Claiming modems.
  - `USERS`: List all users, see their names and email addresses.
  - `USERS_MANAGE`: Approve or create new users, remove users from the organization. Includes `USERS` permission.
  - `PUBLISHERS`: Manage publishers.
  - `TOKENS`: Manage tokens.
  - `CERTIFICATES`: Read and use uploaded certificates (i.e. for publishers).
  - `CERTIFICATES_MANAGE`: Upload certificates, and update or delete uploaded certificates. Includes the `CERTIFICATES` permission.

- Added user permissions
  - `READ`: Read your name, email, linked organizations and mission-control settings.
  - `UPDATE`: Update your personal information, mission-control settings and default organization. Includes `READ` permission.
  - `REQUEST_ACCESS`: Request access to an organization and cancel open requests. Does not include `READ` permission.
  - `DELETE`: Delete your user account permanently. Includes `READ` permission.

##### ModemService

- Added a `BytesOrHex` message body to support more clients.

##### StatusService

- Added `StatusService.Status`, which gives the status of the Hiber network and your organization.
  - The Hiber network:
    - Satellites: A status for the satellite network.
    - Ground Stations: A status for the ground station network.
    - Areas: Areas of the globe that have a non-OK status, i.e. regions where coverage is hindered by external forces.
  - Your organization:
    - Organization health: a value derived from the status of your modems, publishers, etc.
    - Modem health: a single value derived from the status of all your modems.
    - Publisher health: a single value derived from the status of all your publishers.

##### TokenService

- Added `Token.user_permissions`, the user permissions the token was granted.
- Added `Token.organization_permissions`, the organization permissions the token was granted.
- Added `CreateTokenRequest.user_permissions` to set the user permissions for a new token.
- Added `CreateTokenRequest.organization_permissions` to set the user permissions for a new token.
- Added `UpdateTokenOrganizationPermissionsRequest` to update the organization permissions for a token.
- Added `UpdateTokenUserPermissionsRequest` to update the user permissions for a token.

##### UserService

- Added `User.permissions`, the user's organization permissions for your organization.
- Added `ApproveUserRequest.permissions` to set the permissions for a user when giving them access to your organization.
- Added `CreateUserRequest.permissions` to set the organization permissions for a new user created for your organization.
- Added `UserService.UpdateUserPermissions` to change a user's permissions for a given organization.

#### Backwards incompatible changes

Everything is backwards compatible.


### 0.14 (2018-12-18)

This version contains a lot of performance improvements and bugfixes that have no effect on the API.
The API only has one minor change.

#### Changes

##### ModemService

- `ModemMessageSelection` no longer has the option to include child organizations.
  This change is backwards compatible.

#### Backwards incompatible changes

Everything is backwards compatible.


### 0.13 (2018-12-04)

This version makes a big backwards-incompatible change to modem claiming.
We've determined that the double verification for claiming modems (both the verifier and the accept step)
was unnecessary. We've simplified the flow of claims so that claims are now automatically accepted.

#### Changes

##### Event types

- **[B]** Removed `MODEM_CLAIM_ACCEPTED` and `MODEM_CLAIM_REFUSED` from `EventType`.
- Ordered the remaining event types to be more readable. Indexes have not changed, so this is backwards compatible.

##### EventService

- **[B]** Removed `ModemClaimAcceptedEvent` and `ModemClaimRejectedEvent`.

##### ModemClaimService

- Removed all fields related to acceptance and rejection from `ModemClaim`.
  This change is actually backwards compatible, since the defaults for these fields will be used.
  The removed fields are:
  - `status`
  - `reject_reason`
  - `reject_comment`
  - `closed_at`

- Removed all fields related to acceptance and rejection from `ModemClaimSelection`.
    This change is actually backwards compatible, since the defaults for these fields will be used.
    The removed fields are:
    - `statuses`
    - `closed_time_range`
    - `owned_only`
    - `claimed_only`

    Also, `created_time_range` was renamed to `time_range` (which is backwards compatible).

- Removed or changed most of the calls in this service:
  - `ClaimModemRequest` is unchanged, but the Response contains a `ModemClaim`, which was changed (see above).
  - **[B]** `AcceptModemClaimsRequest` was removed, since claims are approved automatically.
  - **[B]** `RejectModemClaimsRequest` was removed, since claims are approved automatically.
  - `ListModemClaimsRequest` was altered to only list the modems that you owned, that were claimed by another organization.

##### UserService

- Made `password` optional in `CreateUserRequest`.

#### Backwards incompatible changes

Backwards incompatible changes are marked with the **[B]** marker.

- **[B]** Everything related to modem claiming:
  - Claiming modems is backwards compatible, but the resulting `ModemClaim` will have default values for the removed fields.
  - Listing claims is backwards compatible, but the resulting `ModemClaim` will have default values for the removed fields.
  - Accepting and Rejecting claims is no longer possible, and will produce an error on older clients.
  - The default `ModemClaim.status` was `OPEN`, so claims will appear as `OPEN` on older clients, while they have actually already been accepted.


### 0.12 (2018-11-27)

This release introduces publishers and an integration with AWS IoT.
Publishers are a larger scope than the previous webhooks that could be configured,
and support both HTTP (webhook) and MQTT.
The existing WebhookService is maintained for backwards compatibility.

The AWS IoT integration is a special implementation of a MQTT publisher pre-configured to
create things for each selected modem.

#### Changes

##### Common types

- Added `UpdateOptionalId` type to update ids that can be unset.
  This is used in the new publishers service.
- Added the `BytesOrHex` type for more convenient interaction with the API using a different preferred binary formats.
- Added Publisher filter.

##### Event types

- Renamed `WEBHOOK_*` to `PUBLISHER_*`. The indices are the same, and so is the behaviour,
  so this change is fully backwards compatible.
- Added `TOKEN_CREATED` event type.

##### AWSIoTService

- Added `AWSIoTService` to set up the AWS IoT Integration.
  - This configures a publisher with the right configuration
  - In AWS IoT, it will send updates to things with the modem number (without spaces) as thing name.
  - Any thing created after the integration has been set up should still have the previously sent state.
  - Since the integration is a publisher, it will be visible in the `PublisherService`.

##### CertificateService

- Added the `CertificateService` to manage client certificates that publishers might use.

##### CurrentUserService

- Added more configuration options for Mission Control.

##### EventService

- Added `TokenCreatedEvent`.
- Added `OrganizationUpdatedEvent`. The EventType already existed, but it was missing from the API spec.
- **[B]** Removed webhook events. Older clients may receive events that have no value in the `oneof`. This is unavoidable.
- **[B]** Added publisher events. Older clients may receive events that have no value in the `oneof`. This is unavoidable.
- **[B]** In `ModemMessageCannotBeParsedEvent`, the type for `modem_message_id` was changed to uint64.
- Renamed the values `ListEventsRequest.Sort` to be more descriptive.

##### ModemService

- Added `message_id` to `ModemMessage`.

##### PublisherService

- Added the `PublisherService`, which allows users to set up HTTP and MQTT publishers.
  This is similar to the `WebhookService` in many ways, but allows for different publisher types.

##### WebhookService

- This service is maintained for backwards compatibility.
  It is not deprecated in any way.
  Any webhook created through this service is also visible in the `PublisherService`.
- Added the option to use a client certificate for webhook calls.

#### Backwards incompatible changes

Backwards incompatible changes are marked with the **[B]** marker.

- **[B]** Removed webhook events. Older clients may receive events that have no value in the `oneof`.
  This is unavoidable when removing a value from a `oneof`.
- **[B]** Added publisher events. Older clients may receive events that have no value in the `oneof`.
  This is unavoidable when adding a value from a `oneof`.
- **[B]** In `ModemMessageCannotBeParsedEvent`, the type for `modem_message_id` was changed to uint64.
  Depending on your client language, this may or may not be backwards compatible.


### 0.11 (2018-10-22)

We've added a few convenience options for modem claims and transfers.

#### Changes

##### ModemClaimService

- Added convenience options to ModemClaimSelection to easily filter incoming and outgoing claims.

##### ModemTransferService

- Added convenience options to ModemTransferSelection to easily filter incoming and outgoing transfers.
- Added convenience option to mark a transfer as received automatically, as a shortcut
  for impersonating the organization and marking it as received manually.
- The `transfer_id` is no longer required to prepare modems for return.
  The return message has been changed to allow multiple return lines.
  For older clients, field 2 is still set with a single return line when `transfer_id` is given.

### 0.10.5 (2018-09-27)

This is a small maintenance release with some minor bugfixes and a few features added to the API for convenience.

#### Changes

##### EventService

- Added flag to display resolved events. Many event types are resolved automatically,
  but might still be relevant for the history of a modem, for example.

##### ModemTransferService

- Added `MISSING` return reason for modems that were supposed to be in a package, but are missing.
  This would not set the modem status to lost, since it's likely the modem was just not packaged.


### 0.10 (2018-09-21)

#### Changes

##### EventService

- **[B]** We've introduced bundled events, which is the new default for event listing.
  Webhooks and the events in the event stream are unaffected.
- **[B]** An event bundle is a small object with event type, count, last event time and title and description.
  If you've previously just displayed title and description, you can use the new title and description.
- **[B]** The frequency of events can vary greatly per type, resulting in unclear pagination and some event types overshadowing
others. For this reason, events are bundled by default, reducing them to a count per event type.
If unbundled events for certain types are required, this can be toggled in the selection object.
Pagination is only applied to unbundled events, and is applied per event type. This may result in a non-lineair
timeline from page to page when selecting two types with a large difference in frequency, but makes sure you
see the most recent events of each type on the first page.
- **[B]** Removed the option to pre-load events for the event stream. Please use the list call for this instead.

##### DashboardService

- **[B]** Related to event bundling, the dashboard now returns bundled error events, instead of individual errors.

##### ModemService

- Added support for custom antennas.
  To set a custom antenna, set the antenna type to custom and fill in the custom_antenna text field.

##### TestingService

- Added call to send a message from a modems debug port directly to the api.
  The server will then parse it as if received from the modem.
  On the production environment, it will be flagged as a test message,
  which means some validation is disabled and consequences are ignored.

##### WebhookService

- Updated the UpdateWebhookRequest to be able to update relevant webhook data in one request.


### 0.8.6 (2018-08-23)

#### Changes

##### CurrentUserService

- **[B]** Added default values for the Settings enums, to fix updating issues. Note that this has changed the indexing of the values, which means it is not a backwards compatible change. In both cases, the value that was previously at index 0 has been moved to the next available index at the end. Since no settings defaults to these values anyway, the only problem is sending an empty update request, which is no longer allowed.
- Renamed `updated_settings` to `update_settings` to reflect the changes above. Fully backwards compatible, but updating your generated code to 0.8.6 will rename this field.

##### EventService

- Added events related to token expiration.

##### Tagservice

- Added option to List call to count the amount of modems or webhooks for each tag.

##### WebhookService

- **[B]** Renamed `active` field in WebhookData to `disabled`, so a webhook defaults to enabled on creation. If you want it to start disabled, you can do that by setting the field to true.
- Changed the naming for a few fields in WebhookFilters to be clearer (`events` -> `event_types`, `modems` -> `modem_numbers`). The nnumbers have not changed, so this change is fully backwards compatible. Updating your generated code will use the new names, of course, which will require some renaming in clients upon updating to version 0.8.6 of the API.

#### Backwards incompatible changes

Backwards incompatible changes are marked with the **[B]** marker.

- **[B]** Renamed `active` field in WebhookData to `disabled`. See WebhookService change for details
- **[B]** Added default values for the Settings enums in CurrentUserService, which changed indexes for the values that were previously default values.

### 0.8 (2018-07-26)

#### Changes

- Renamed `Account` to `Organization`, since it was causing confusion with `User`
  <br/>(This change is backwards compatible, since the field numbers did not change).
- Consistently using `snake_case` for naming.

##### AccountService

- Renamed to `OrganizationService`.

##### CurrentUserService

- Added `CurrentUser.Settings` and an update rpc under `CurrentUserService`, used by the web application.
- Added an rpc under `CurrentUserService` to cancel an access request.
- Added an rpc under `CurrentUserService` to update your default organization, to be used by the web application.

##### DashboardService

- Added `time_zone_offset` to customize the timezone used for date grouping.
- **[B]** Changed the return field `message_count_per_day` to be a `MessageCount` instead of a `map<string, in32>`, which was unclear.
  See the ModemService changes for more details.

##### EventService

- Added events related to modem transferring and claiming.

##### ModemService

- **[B]** Removed a few fields from the `Modem` object:

    - `chip_id`, `message_format_version`, `payload_template` from `Modem.TechnicalData`: this data was determined to be either too sensitive or irrelevant.
    - `payload_template` from `Modem.TechnicalData`: this feature is not available yet; the field may be restored when it is.
    - `license_key` from `Modem.ActiveSubscription`: this was moved to separate request in `ModemService`.

- Renamed `guard_period` to `maximum_inactivity_period` after customer feedback.
- Added `peripherals` on `Modem` with peripheral information, and the `UpdatePeripherals` rpc on `ModemService` to update this data.
- Added `status` on `Modem` with statuses such as `active` or `dead`.
  Added filtering on status to `ModemSelection` as well.
- Added `transfer` on `Modem` with transfer information if the modem is in a transfer.
  Added filtering by transfer on `ModemSelection` as well.
  See `ModemTransferService` for more information on transfers.
- Added `LicenseKeys` rpc on `ModemService` to get the license key for modems.
- Renamed `time` to `sent_at` and added `received_at` on ModemMessage.
- **[B]** Changed `MessageCountRequest.Response.message_count_per_day` to be a `MessageCount` instead of a `map<string, in32>`, which was unclear.
  <br>The result is effectively the same data, since `MessageCount` is simple a pair of `Date` to `int32`, but the types are a lot clearer.
- Added `time_zone_offset` to `MessageCountRequest` to customize the timezone used for date grouping.
- **[B]** Removed the `UpdatePayloadTemplate` rpc, since it was related to the removed field.
- - Removed `TagSelection` that was used to filter displayed tags in many requests, since it would likely never be used.

##### ModemClaimService

- Added the `ModemClaimService`, which handles the claiming of a modem by number and verification number.

##### ModemTransferService & ModemTransferReturnService

- Added the `ModemTranferService`, which handles the transferring of modems to different organizations.
- Added the `ModemTranferReturnService`, which handles the returning of modems that were transferred to your organization.

##### OrganizationService

- Added `Create` rpc call to create child organizations.
- Added `Delete` and `DeleteConfirmation` for organization deletion.
- Added `ListChildOrganizations` and `Tree` rcps to display child organizations.
- `Update` also works on child organization.

##### TagService

- **[B]** Removed color from tags.

##### TestingService

- **[B]** Removed `PushModemMessagesRequest.Response.messages_sent`, since it did not contain any useful information.

##### UserService

- Added sorting to `List` and `ListAccessRequests` rpcs, using the new `UserSort` enum.
- **[B]** Altered `ApproveUserRequest` and `RemoveUserRequest` to accept multiple user ids.

##### WebhookService

- Removed `TagSelection` that was used to filter displayed tags in many requests, since it would likely never be used.

#### Backwards incompatible changes

Backwards incompatible changes are marked with the **[B]** marker.
This way, you can easily see which, if any, changes could require some work.

Since these changes have been made during the pilot period,
backwards compatibility has not been as strictly enforced as we would normally.

From the list above, these changes are not (fully) backwards compatible:

- The `message_count_per_day` field type has changed, in `ModemService` and `DashboardService`.
- Removed `chip_id`, `message_format_version`, `payload_template`, `payload_template` and `license_key` from `Modem`, and the `UpdatePayloadTemplate` rpc related to `payload_template`.
- Removed color from tags.
- Removed `messages_sent` from `PushModemMessagesRequest.Response` in `TestingService`.
- Altered `user_id` in `ApproveUserRequest` and `RemoveUserRequest` to be an array.

