# Changelog Hiber API

### 0.47 (2020-05-07)

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

- Added a `Test` command to test a payload parser on a given byte sequence, or an existing message id.

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

