# permission.proto

Permissions limit what a user can do through the API.

#### This file was generated from [permission.proto](https://github.com/HiberGlobal/api/blob/master/permission.proto).

## Table of Contents





- Enums
  - [OrganizationPermission](#organizationpermission)
  - [SupportPermission](#supportpermission)
  - [UserPermission](#userpermission)

- [Scalar Value Types](#scalar-value-types)




## Enums
### OrganizationPermission
OrganizationPermissions limit what a user can do in an Organization.
By default, everyone who has access to an organization, can access basic organization data.

| Name | Description | Number |
| ---- | ----------- | ------ |
| PERMISSION_DEFAULT |  | 0 |
| ORGANIZATION_CREATE | Create a new child organization. | 1 |
| ORGANIZATION_UPDATE | Update the organizations data, such as billing information, address, and contact. | 2 |
| ORGANIZATION_DELETE | Delete child organizations. You cannot delete your own organization. To delete your organization, contact support. | 3 |
| ASSETS | List assets, see their details | 53 |
| ASSETS_UPDATE | Create and update assets, such as their display name and tags. Includes ASSETS permission. | 54 |
| ASSETS_VALUES | Read asset values, i.e. pressure measurements. | 55 |
| MODEMS | List modems, see their details and health | 10 |
| MODEMS_CREATE | Create new modems. Includes MODEMS permission. | 50 |
| MODEMS_UPDATE | Update modems, such as their peripherals, display name and tags. Includes MODEMS permission. | 11 |
| MODEMS_LICENSE_KEYS | Show and regenerate license keys. Includes MODEMS permission. | 12 |
| MODEMS_MESSAGE_BODY_PARSERS | Manage and assign message body parsers. Includes MODEMS permission. | 43 |
| MODEMS_SECURE_NOTES | Show and update secure notes. Includes MODEMS permission. | 42 |
| MODEMS_ALARMS | View and assign (with the ASSIGNMENTS permission) alarms. Includes MODEMS permission. | 44 |
| MODEMS_ALARMS_UPDATE | Manage alarms. Includes MODEMS permission. | 56 |
| MODEM_VALUES | Read modem values. | 17 |
| MODEM_MESSAGES | Read modem messages. | 15 |
| MODEM_MESSAGES_SEND_TEST_MESSAGES | Send modem messages using the TestingService. Does not include MODEMS or MESSAGES permission. | 16 |
| MODEM_MESSAGES_SEND_REAL_MESSAGES | Send modem messages using real message sources (i.e. gateway). Does not include MODEMS or MESSAGES permission. | 41 |
| MODEM_DOWNLINK_MESSAGES | Send modem downlink messages. | 51 |
| TRANSFERS | See the transfers to/from other organizations. | 20 |
| TRANSFERS_SEND | Transfer devices to another organization. | 21 |
| USERS | List all users, see their names and email addresses. | 30 |
| USERS_MANAGE | Approve or create new users, remove users from the organization. Includes users permission. | 31 |
| PUBLISHERS | Manage publishers: webhooks, MQTT integration and custom email publishers. | 35 |
| TOKENS | Manage tokens. | 36 |
| CERTIFICATES | Read and use uploaded certificates (i.e. for publishers). | 38 |
| CERTIFICATES_MANAGE | Upload certificates, and update or delete uploaded certificates. | 39 |
| ASSIGNMENTS | Manage assignments using the assignment services and individual calls on, for example, ModemService. | 45 |
| SIMULATION_MANAGE | Manage simulations, like modem message simulation. | 46 |
| HEALTH_MANAGE | Manage custom health levels. | 47 |
| LOCATIONS_MANAGE | Manage saved locations using the OrganizationLocationService. | 48 |
| EXPORT | Create, access and download exports. | 49 |
| TAGS_MANAGE | Create, edit and delete tags. Viewing tags is always allowed. | 52 |

### SupportPermission
SupportPermissions are used for features typically reserved for customer support, or that behave differently
when used by a customer support operator.

| Name | Description | Number |
| ---- | ----------- | ------ |
| CUSTOMER_SUPPORT | Allow Customer Support functions. | 0 |
| MANAGE_ORGANIZATION_FEATURE | Manage organization feature flags. | 1 |
| MANAGE_DEVICE_TYPE | Change the device type for devices. | 2 |
| CUSTOM_TAGS | Create and assign custom tags. | 3 |
| INTEGRATION_SHELL_SSIP | Manage Shell SSIP integration. | 4 |
| MANAGE_DEVICE_TRANSMISSION_INTERVAL | Manage device transmission interval (actual interval). | 5 |
| MANAGE_DEVICE_SLA | Manage device SLA values (minimum messages per day). | 6 |
| DEVICE_VIEW_ALL_LIFECYCLES | View all lifecycles. Without this permission, you can only see INSTALLED and PAUSED. | 7 |
| MANAGE_DEVICE_NOTES | Assign device notes. | 8 |
| MANAGE_DEVICE_TIME_ZONE | Assign device time zones. | 9 |

### UserPermission
UserPermissions are generally used to limit what a token can do to its user.
By default, a user has all UserPermissions, which apply only to himself.
When creating a token, however, the token typically does not need permission to affect the user at all.

| Name | Description | Number |
| ---- | ----------- | ------ |
| READ | Read your name, email, linked organizations and mission-control settings. | 0 |
| UPDATE | Update your personal information, mission-control settings and default organization. Includes read permission. | 1 |
| REQUEST_ACCESS | Request access to an organization and cancel open requests. Does not include read permission. | 2 |
| DELETE | Delete your user account permanently. Includes read permission. | 3 |

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

