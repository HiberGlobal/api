# role_service.proto



#### This file was generated from [role_service.proto](https://github.com/HiberGlobal/api/blob/master/role_service.proto).

## Table of Contents

- Services
  - [RoleService](#roleservice)

- Messages
  - [ListRoles](#listroles)
  - [ListRoles.Request](#listrolesrequest)
  - [ListRoles.Response](#listrolesresponse)

- Enums

- Referenced messages from [currentuser.proto](#referenced-messages-from-currentuserproto)
  - [hiber.user.AcceptOrganizationInviteRequest](#hiberuseracceptorganizationinviterequest)
  - [hiber.user.AcceptOrganizationInviteRequest.Response](#hiberuseracceptorganizationinviterequestresponse)
  - [hiber.user.AcceptTermsAndConditionsRequest](#hiberuseraccepttermsandconditionsrequest)
  - [hiber.user.AcceptTermsAndConditionsRequest.Response](#hiberuseraccepttermsandconditionsrequestresponse)
  - [hiber.user.AccessibleOrganizationsRequest](#hiberuseraccessibleorganizationsrequest)
  - [hiber.user.AccessibleOrganizationsRequest.AccessibleOrganization](#hiberuseraccessibleorganizationsrequestaccessibleorganization)
  - [hiber.user.AccessibleOrganizationsRequest.Response](#hiberuseraccessibleorganizationsrequestresponse)
  - [hiber.user.CancelAccessRequestRequest](#hiberusercancelaccessrequestrequest)
  - [hiber.user.CancelAccessRequestRequest.Response](#hiberusercancelaccessrequestrequestresponse)
  - [hiber.user.CurrentUser](#hiberusercurrentuser)
  - [hiber.user.CurrentUserRequest](#hiberusercurrentuserrequest)
  - [hiber.user.DeleteCurrentUserRequest](#hiberuserdeletecurrentuserrequest)
  - [hiber.user.DeleteCurrentUserRequest.Response](#hiberuserdeletecurrentuserrequestresponse)
  - [hiber.user.ListOrganizationInvitesRequest](#hiberuserlistorganizationinvitesrequest)
  - [hiber.user.ListOrganizationInvitesRequest.Invite](#hiberuserlistorganizationinvitesrequestinvite)
  - [hiber.user.ListOrganizationInvitesRequest.Response](#hiberuserlistorganizationinvitesrequestresponse)
  - [hiber.user.OverrideRoles](#hiberuseroverrideroles)
  - [hiber.user.OverrideRoles.Request](#hiberuseroverriderolesrequest)
  - [hiber.user.OverrideRoles.Response](#hiberuseroverriderolesresponse)
  - [hiber.user.OverrideRoles.Restore](#hiberuseroverriderolesrestore)
  - [hiber.user.OverrideRoles.Restore.Request](#hiberuseroverriderolesrestorerequest)
  - [hiber.user.OverrideRoles.Restore.Response](#hiberuseroverriderolesrestoreresponse)
  - [hiber.user.RequestAccessRequest](#hiberuserrequestaccessrequest)
  - [hiber.user.RequestAccessRequest.Response](#hiberuserrequestaccessrequestresponse)
  - [hiber.user.UpdateDefaultOrganizationRequest](#hiberuserupdatedefaultorganizationrequest)
  - [hiber.user.UpdateDefaultOrganizationRequest.Response](#hiberuserupdatedefaultorganizationrequestresponse)
  - [hiber.user.UpdateMissionControlSettingsRequest](#hiberuserupdatemissioncontrolsettingsrequest)
  - [hiber.user.UpdateMissionControlSettingsRequest.Response](#hiberuserupdatemissioncontrolsettingsrequestresponse)


- Referenced messages from [role.proto](#referenced-messages-from-roleproto)
  - [hiber.role.Role](#hiberrolerole)
  - [hiber.role.RoleSelection](#hiberroleroleselection)


- [Scalar Value Types](#scalar-value-types)


## RoleService


### List
> **rpc** List([ListRoles.Request](#listrolesrequest))
    [ListRoles.Response](#listrolesresponse)



### Override
> **rpc** Override([.hiber.user.OverrideRoles.Request](#hiberuseroverriderolesrequest))
    [.hiber.user.OverrideRoles.Response](#hiberuseroverriderolesresponse)



### Restore
> **rpc** Restore([.hiber.user.OverrideRoles.Restore.Request](#hiberuseroverriderolesrestorerequest))
    [.hiber.user.OverrideRoles.Restore.Response](#hiberuseroverriderolesrestoreresponse)




## Messages

### ListRoles




### ListRoles.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ RoleSelection](#roleselection) |  |

### ListRoles.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| roles | [repeated Role](#role) |  |
| request | [ ListRoles.Request](#listrolesrequest) |  |


## Enums


## Referenced messages from currentuser.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [currentuser.proto](https://github.com/HiberGlobal/api/blob/master/currentuser.proto).


### hiber.user.AcceptOrganizationInviteRequest

Accept an invitation to an organization.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| default_organization | [ bool](#bool) | Set to true to mark the organization as your default organization. |

### hiber.user.AcceptOrganizationInviteRequest.Response




### hiber.user.AcceptTermsAndConditionsRequest

Accept the Hiber terms and conditions.

| Field | Type | Description |
| ----- | ---- | ----------- |
| accept_tac | [ bool](#bool) |  |

### hiber.user.AcceptTermsAndConditionsRequest.Response




### hiber.user.AccessibleOrganizationsRequest

List all organizations that can be impersonated.

| Field | Type | Description |
| ----- | ---- | ----------- |
| search | [ string](#string) | Search accessible organizations by name. |
| member_only | [ bool](#bool) | Only list organizations of which you are a member (exclude organizations that you can only impersonate). |
| default_only | [ bool](#bool) | Only list your default organization. |
| pagination | [ hiber.Pagination](#hiberpagination) |  |

### hiber.user.AccessibleOrganizationsRequest.AccessibleOrganization



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Organization identifier, i.e. "my-organization" |
| display_name | [ string](#string) | Organization name, i.e. "My Organization" |
| contact | [ hiber.organization.Organization.Contact](#hiberorganizationorganizationcontact) | The contact person for this organization |
| member | [ bool](#bool) | If true, you are a member of this organization (= you are directly linked to this organization) |
| default_organization | [ bool](#bool) | If true, this is the organization that you use by default. |

### hiber.user.AccessibleOrganizationsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| organizations | [repeated hiber.user.AccessibleOrganizationsRequest.AccessibleOrganization](#hiberuseraccessibleorganizationsrequestaccessibleorganization) | Details for the organizations that you can access. |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### hiber.user.CancelAccessRequestRequest

Cancel a previously made access request.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |

### hiber.user.CancelAccessRequestRequest.Response




### hiber.user.CurrentUser

Your personal data.

| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) |  |
| email | [ string](#string) |  |
| name | [ string](#string) |  |
| organizations | [repeated string](#string) | The organizations that this user has access to. |
| default_organization | [ string](#string) | The default organization for this user. |
| requested_organizations | [repeated string](#string) | Open access requests. |
| current_organization | [ string](#string) | The current organization for this user. If this is a user, this equals the default_organization. If this is a token, it's the token's organization. |
| current_organization_permissions | [ hiber.Filter.OrganizationPermissions](#hiberfilterorganizationpermissions) | Permissions for the current organization. |
| user_permissions | [ hiber.Filter.UserPermissions](#hiberfilteruserpermissions) | Permissions for the user. If this is a token, the user permissions may be limited. |
| support_permissions | [ hiber.Filter.SupportPermissions](#hiberfiltersupportpermissions) | Permissions for customer support. Used for features typically reserved for customer support, or that behave differently when used by a customer support operator. |
| roles | [repeated string](#string) | Roles for the current organization. |
| mission_control_settings | [ string](#string) |  |
| accepted_tac | [ bool](#bool) | Whether the user accepted the terms and conditions. |
| user_hash | [ string](#string) |  |

### hiber.user.CurrentUserRequest

Get your personal data.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |

### hiber.user.DeleteCurrentUserRequest

Delete yourself.
Removes all login information and personal data, except for you email address for auditing purposes.


### hiber.user.DeleteCurrentUserRequest.Response




### hiber.user.ListOrganizationInvitesRequest

List all invitations from organizations.

| Field | Type | Description |
| ----- | ---- | ----------- |
| search | [ string](#string) |  |

### hiber.user.ListOrganizationInvitesRequest.Invite



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |
| display_name | [ string](#string) |  |
| invited_at | [ hiber.Timestamp](#hibertimestamp) |  |

### hiber.user.ListOrganizationInvitesRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| organizations | [repeated hiber.user.ListOrganizationInvitesRequest.Invite](#hiberuserlistorganizationinvitesrequestinvite) |  |

### hiber.user.OverrideRoles




### hiber.user.OverrideRoles.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.role.RoleSelection](#hiberroleroleselection) |  |

### hiber.user.OverrideRoles.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| current_user | [ hiber.user.CurrentUser](#hiberusercurrentuser) |  |
| request | [ hiber.user.OverrideRoles.Request](#hiberuseroverriderolesrequest) |  |

### hiber.user.OverrideRoles.Restore




### hiber.user.OverrideRoles.Restore.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [repeated string](#string) | Optionally, specify organization(s) with an active override that you wish to remove. If no organizations are provided, all overrides will be removed. |

### hiber.user.OverrideRoles.Restore.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| current_user | [ hiber.user.CurrentUser](#hiberusercurrentuser) |  |
| request | [ hiber.user.OverrideRoles.Restore.Request](#hiberuseroverriderolesrestorerequest) |  |

### hiber.user.RequestAccessRequest

Request access to an organization by name, if it exists.
You request will be saved and the organization owner notified.
Organization admins can approve or reject your request.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |

### hiber.user.RequestAccessRequest.Response




### hiber.user.UpdateDefaultOrganizationRequest

Set the default organization to use when it is not specified in the call.
Note: this can be a child organization of one of the owned organizations.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) |  |

### hiber.user.UpdateDefaultOrganizationRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| default_organization | [ string](#string) |  |

### hiber.user.UpdateMissionControlSettingsRequest

Update mission control settings, which are in a json format.

| Field | Type | Description |
| ----- | ---- | ----------- |
| update | [ string](#string) |  |

### hiber.user.UpdateMissionControlSettingsRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| mission_control_settings | [ string](#string) |  |


### Enums


## Referenced messages from role.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [role.proto](https://github.com/HiberGlobal/api/blob/master/role.proto).


### hiber.role.Role



| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) | Unique identifier for the role. |
| display_name | [ string](#string) | Display name for the role. |
| description | [ string](#string) | Description for the role. |
| permissions | [repeated hiber.OrganizationPermission](#hiberorganizationpermission) | The organization permissions the role grants. |
| support_permissions | [repeated hiber.SupportPermission](#hibersupportpermission) | The support permissions the role grants. This is not typically available in any organizations other than the Hiber organization. |

### hiber.role.RoleSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| search | [ string](#string) |  |
| roles | [ hiber.Filter.Roles](#hiberfilterroles) |  |


### Enums
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

