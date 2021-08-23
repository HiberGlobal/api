# permission.proto

Permissions limit what a user can do through the API.

#### This file was generated from [permission.proto](https://github.com/HiberGlobal/api/blob/master/permission.proto).## Table of Contents





- Enums
  - [OrganizationPermission](#organizationpermission)
  - [UserPermission](#userpermission)





## Enums
### OrganizationPermission
OrganizationPermissions limit what a user can do in an Organization.
By default, everyone who has access to an organization, can access:
- organization data
- dashboard (including the map, and message count for the past days, and any events they have access to)
- tags
- deleting tags, but only if they are allowed to update the modems and webhooks the tag is assigned to

Events are filtered by permission, i.e. if you cannot access the users, you would not see user-related events.
Requesting user-related events explicitly if you cannot access the users will return an error.

| Name | Description | Number |
| ---- | ----------- | ------ |
| PERMISSION_DEFAULT | none | 0 |
| ORGANIZATION_CREATE | Create a new child organization. | 1 |
| ORGANIZATION_UPDATE | Update the organizations data, such as billing information, address, and contact. | 2 |
| ORGANIZATION_DELETE | Delete child organizations. You cannot delete your own organization. To delete your organization, contact support. | 3 |
| MODEMS | List modems, see their details and health | 10 |
| MODEMS_CREATE | Create new modems. Includes MODEMS permission. | 50 |
| MODEMS_UPDATE | Update modems, such as their peripherals, display name and tags. Includes MODEMS permission. | 11 |
| MODEMS_LICENSE_KEYS | Show and regenerate license keys. Includes MODEMS permission. | 12 |
| MODEMS_MESSAGE_BODY_PARSERS | Manage and assign message body parsers. Includes MODEMS permission. | 43 |
| MODEMS_SECURE_NOTES | Show and update secure notes. Includes MODEMS permission. | 42 |
| MODEMS_ALARMS | Manage and assign message alerts. Includes MODEMS permission. | 44 |
| MODEM_MESSAGES | Read modem messages. | 15 |
| MODEM_MESSAGES_SEND_TEST_MESSAGES | Send modem messages using the TestingService. Does not include MODEMS or MESSAGES permission. | 16 |
| MODEM_MESSAGES_SEND_REAL_MESSAGES | Send modem messages using real message sources (i.e. gateway). Does not include MODEMS or MESSAGES permission. | 41 |
| MODEM_DOWNLINK_MESSAGES | Send modem downlink messages. | 51 |
| MODEM_TRANSFERS | See modem transfers, inbound and outbound modems. Includes modems permission. | 20 |
| MODEM_TRANSFERS_SEND | Transfer modems to another organization, cancel open transfers and send return transfers. Includes modems_transfers permission. | 21 |
| MODEM_TRANSFERS_PROCESS | Mark transfers as received, prepare modems for return. This does not include actually sending the return transfer. Includes modems_transfers permission. | 22 |
| MODEM_CLAIM | Claiming modems. | 25 |
| USERS | List all users, see their names and email addresses. | 30 |
| USERS_MANAGE | Approve or create new users, remove users from the organization. Includes users permission. | 31 |
| PUBLISHERS | Manage publishers: webhooks, MQTT integration, AWS IoT integration and custom email publishers. | 35 |
| TOKENS | Manage tokens. | 36 |
| CERTIFICATES | Read and use uploaded certificates (i.e. for publishers). | 38 |
| CERTIFICATES_MANAGE | Upload certificates, and update or delete uploaded certificates. | 39 |
| ASSIGNMENTS | Manage assignments using the assignment services and individual calls on, for example, ModemService. | 45 |
| SIMULATION_MANAGE | Manage simulations, like modem message simulation. | 46 |
| HEALTH_MANAGE | Manage custom health levels. | 47 |
| LOCATIONS_MANAGE | Manage saved locations using the OrganizationLocationService. | 48 |
| EXPORT | Create, access and download exports. | 49 |

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

