# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [permission.proto](#permission.proto)
    - [OrganizationPermission](#hiber.OrganizationPermission)
    - [UserPermission](#hiber.UserPermission)
  
- [Scalar Value Types](#scalar-value-types)



<a name="permission.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## permission.proto
Permissions limit what a user can do through the API.

 


<a name="hiber.OrganizationPermission"></a>

### OrganizationPermission
OrganizationPermissions limit what a user can do in an Organization.
By default, everyone who has access to an organization, can access:
- organization data
- dashboard (including the map, and message count for the past days, and any events they have access to)
- tags
- deleting tags, but only if they are allowed to update the modems and webhooks the tag is assigned to

Events are filtered by permission, i.e. if you cannot access the users, you would not see user-related events.
Requesting user-related events explicitly if you cannot access the users will return an error.

| Name | Number | Description |
| ---- | ------ | ----------- |
| PERMISSION_DEFAULT | 0 |  |
| ORGANIZATION_CREATE | 1 | Create a new child organization. |
| ORGANIZATION_UPDATE | 2 | Update the organizations data, such as billing information, address, and contact. |
| ORGANIZATION_DELETE | 3 | Delete child organizations. You cannot delete your own organization. To delete your organization, contact support. |
| MODEMS | 10 | List modems, see their details and health |
| MODEMS_CREATE | 50 | Create new modems. Includes MODEMS permission. |
| MODEMS_UPDATE | 11 | Update modems, such as their peripherals, display name and tags. Includes MODEMS permission. |
| MODEMS_LICENSE_KEYS | 12 | Show and regenerate license keys. Includes MODEMS permission. |
| MODEMS_MESSAGE_BODY_PARSERS | 43 | Manage and assign message body parsers. Includes MODEMS permission. |
| MODEMS_SECURE_NOTES | 42 | Show and update secure notes. Includes MODEMS permission. |
| MODEMS_ALARMS | 44 | Manage and assign message alerts. Includes MODEMS permission. |
| MODEM_MESSAGES | 15 | Read modem messages. |
| MODEM_MESSAGES_SEND_TEST_MESSAGES | 16 | Send modem messages using the TestingService. Does not include MODEMS or MESSAGES permission. |
| MODEM_MESSAGES_SEND_REAL_MESSAGES | 41 | Send modem messages using real message sources (i.e. gateway). Does not include MODEMS or MESSAGES permission. |
| MODEM_DOWNLINK_MESSAGES | 51 | Send modem downlink messages. |
| MODEM_TRANSFERS | 20 | See modem transfers, inbound and outbound modems. Includes modems permission. |
| MODEM_TRANSFERS_SEND | 21 | Transfer modems to another organization, cancel open transfers and send return transfers. Includes modems_transfers permission. |
| MODEM_TRANSFERS_PROCESS | 22 | Mark transfers as received, prepare modems for return. This does not include actually sending the return transfer. Includes modems_transfers permission. |
| MODEM_CLAIM | 25 | Claiming modems. |
| USERS | 30 | List all users, see their names and email addresses. |
| USERS_MANAGE | 31 | Approve or create new users, remove users from the organization. Includes users permission. |
| PUBLISHERS | 35 | Manage publishers: webhooks, MQTT integration, AWS IoT integration and custom email publishers. |
| TOKENS | 36 | Manage tokens. |
| CERTIFICATES | 38 | Read and use uploaded certificates (i.e. for publishers). |
| CERTIFICATES_MANAGE | 39 | Upload certificates, and update or delete uploaded certificates. |
| ASSIGNMENTS | 45 | Manage assignments using the assignment services and individual calls on, for example, ModemService. |
| SIMULATION_MANAGE | 46 | Manage simulations, like modem message simulation. |
| HEALTH_MANAGE | 47 | Manage custom health levels. |
| LOCATIONS_MANAGE | 48 | Manage saved locations using the OrganizationLocationService. |
| EXPORT | 49 | Create, access and download exports. |



<a name="hiber.UserPermission"></a>

### UserPermission
UserPermissions are generally used to limit what a token can do to its user.
By default, a user has all UserPermissions, which apply only to himself.
When creating a token, however, the token typically does not need permission to affect the user at all.

| Name | Number | Description |
| ---- | ------ | ----------- |
| READ | 0 | Read your name, email, linked organizations and mission-control settings. |
| UPDATE | 1 | Update your personal information, mission-control settings and default organization. Includes read permission. |
| REQUEST_ACCESS | 2 | Request access to an organization and cancel open requests. Does not include read permission. |
| DELETE | 3 | Delete your user account permanently. Includes read permission. |


 

 

 



## Scalar Value Types

| .proto Type | Notes | C++ | Java | Python | Go | C# | PHP | Ruby |
| ----------- | ----- | --- | ---- | ------ | -- | -- | --- | ---- |
| <a name="double" /> double |  | double | double | float | float64 | double | float | Float |
| <a name="float" /> float |  | float | float | float | float32 | float | float | Float |
| <a name="int32" /> int32 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint32 instead. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="int64" /> int64 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint64 instead. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="uint32" /> uint32 | Uses variable-length encoding. | uint32 | int | int/long | uint32 | uint | integer | Bignum or Fixnum (as required) |
| <a name="uint64" /> uint64 | Uses variable-length encoding. | uint64 | long | int/long | uint64 | ulong | integer/string | Bignum or Fixnum (as required) |
| <a name="sint32" /> sint32 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int32s. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="sint64" /> sint64 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int64s. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="fixed32" /> fixed32 | Always four bytes. More efficient than uint32 if values are often greater than 2^28. | uint32 | int | int | uint32 | uint | integer | Bignum or Fixnum (as required) |
| <a name="fixed64" /> fixed64 | Always eight bytes. More efficient than uint64 if values are often greater than 2^56. | uint64 | long | int/long | uint64 | ulong | integer/string | Bignum |
| <a name="sfixed32" /> sfixed32 | Always four bytes. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="sfixed64" /> sfixed64 | Always eight bytes. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="bool" /> bool |  | bool | boolean | boolean | bool | bool | boolean | TrueClass/FalseClass |
| <a name="string" /> string | A string must always contain UTF-8 encoded or 7-bit ASCII text. | string | String | str/unicode | string | string | string | String (UTF-8) |
| <a name="bytes" /> bytes | May contain any arbitrary sequence of bytes. | string | ByteString | str | []byte | ByteString | string | String (ASCII-8BIT) |

