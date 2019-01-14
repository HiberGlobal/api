# Changelog Hiber API

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

