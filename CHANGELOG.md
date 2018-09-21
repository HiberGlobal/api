# Changelog Hiber API

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

