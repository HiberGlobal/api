# field_service.proto



#### This file was generated from [field_service.proto](https://github.com/HiberGlobal/api/blob/master/field_service.proto).

## Table of Contents

- Services
  - [FieldService](#fieldservice)

- Messages
  - [AddFieldsRequest](#addfieldsrequest)
  - [DeleteFieldsRequest](#deletefieldsrequest)
  - [FieldSelection](#fieldselection)
  - [ListFields](#listfields)
  - [ListFields.Request](#listfieldsrequest)
  - [ListFields.Response](#listfieldsresponse)
  - [ListFieldsForModem](#listfieldsformodem)
  - [ListFieldsForModem.Request](#listfieldsformodemrequest)
  - [ListFieldsForModem.Response](#listfieldsformodemresponse)
  - [ListFieldsForModem.Response.ModemWithFields](#listfieldsformodemresponsemodemwithfields)
  - [ReplaceAllFieldsRequest](#replaceallfieldsrequest)
  - [UpdateFieldEnumValues](#updatefieldenumvalues)
  - [UpdateFieldEnumValues.Request](#updatefieldenumvaluesrequest)
  - [UpdateFieldEnumValues.UpdateEnumValue](#updatefieldenumvaluesupdateenumvalue)
  - [UpdateFieldNumericDetails](#updatefieldnumericdetails)
  - [UpdateFieldNumericDetails.Request](#updatefieldnumericdetailsrequest)
  - [UpdateFieldRequest](#updatefieldrequest)

- Enums
  - [ListFields.Sort](#listfieldssort)

- Referenced messages from [field.proto](#referenced-messages-from-fieldproto)
  - [hiber.field.Field](#hiberfieldfield)
  - [hiber.field.Field.Enum](#hiberfieldfieldenum)
  - [hiber.field.Field.Numeric](#hiberfieldfieldnumeric)
  - [hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat)
  - [hiber.field.Field.Numeric.Unit](#hiberfieldfieldnumericunit)

    - [hiber.field.Field.Numeric.Format.RoundingMode](#hiberfieldfieldnumericformatroundingmode)

- Referenced messages from [modem.proto](#referenced-messages-from-modemproto)
  - [hiber.modem.Modem](#hibermodemmodem)
  - [hiber.modem.ModemSelection](#hibermodemmodemselection)

    - [hiber.modem.ListModemsRequest.Sort](#hibermodemlistmodemsrequestsort)
    - [hiber.modem.Modem.Lifecycle](#hibermodemmodemlifecycle)
    - [hiber.modem.Modem.Type](#hibermodemmodemtype)
    - [hiber.modem.ModemMessage.Source](#hibermodemmodemmessagesource)

- Referenced messages from [modem_message_body_parser.proto](#referenced-messages-from-modem_message_body_parserproto)
  - [hiber.modem.message.bodyparser.AssignModemMessageBodyParsers](#hibermodemmessagebodyparserassignmodemmessagebodyparsers)
  - [hiber.modem.message.bodyparser.AssignModemMessageBodyParsers.Request](#hibermodemmessagebodyparserassignmodemmessagebodyparsersrequest)
  - [hiber.modem.message.bodyparser.AssignModemMessageBodyParsers.Response](#hibermodemmessagebodyparserassignmodemmessagebodyparsersresponse)
  - [hiber.modem.message.bodyparser.AssignedModemMessageBodyParser](#hibermodemmessagebodyparserassignedmodemmessagebodyparser)
  - [hiber.modem.message.bodyparser.CreateSimpleModemMessageBodyParserRequest](#hibermodemmessagebodyparsercreatesimplemodemmessagebodyparserrequest)
  - [hiber.modem.message.bodyparser.DeleteModemMessageBodyParserRequest](#hibermodemmessagebodyparserdeletemodemmessagebodyparserrequest)
  - [hiber.modem.message.bodyparser.DeleteModemMessageBodyParserRequest.Response](#hibermodemmessagebodyparserdeletemodemmessagebodyparserrequestresponse)
  - [hiber.modem.message.bodyparser.ListModemMessageBodyParsersRequest](#hibermodemmessagebodyparserlistmodemmessagebodyparsersrequest)
  - [hiber.modem.message.bodyparser.ListModemMessageBodyParsersRequest.Response](#hibermodemmessagebodyparserlistmodemmessagebodyparsersrequestresponse)
  - [hiber.modem.message.bodyparser.MakeModemMessageBodyParserAvailableToChildOrganizationRequest](#hibermodemmessagebodyparsermakemodemmessagebodyparseravailabletochildorganizationrequest)
  - [hiber.modem.message.bodyparser.MakeModemMessageBodyParserUnavailableToChildOrganizationRequest](#hibermodemmessagebodyparsermakemodemmessagebodyparserunavailabletochildorganizationrequest)
  - [hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser)
  - [hiber.modem.message.bodyparser.ModemMessageBodyParser.AvailableToChildOrganizations](#hibermodemmessagebodyparsermodemmessagebodyparseravailabletochildorganizations)
  - [hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafields)
  - [hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields.LocationFields](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafieldslocationfields)
  - [hiber.modem.message.bodyparser.ModemMessageBodyParser.RequireMessageMetadataEntry](#hibermodemmessagebodyparsermodemmessagebodyparserrequiremessagemetadataentry)
  - [hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection)
  - [hiber.modem.message.bodyparser.RenameModemMessageBodyParserRequest](#hibermodemmessagebodyparserrenamemodemmessagebodyparserrequest)
  - [hiber.modem.message.bodyparser.RetryModemMessageBodyParsing](#hibermodemmessagebodyparserretrymodemmessagebodyparsing)
  - [hiber.modem.message.bodyparser.RetryModemMessageBodyParsing.Request](#hibermodemmessagebodyparserretrymodemmessagebodyparsingrequest)
  - [hiber.modem.message.bodyparser.RetryModemMessageBodyParsing.Response](#hibermodemmessagebodyparserretrymodemmessagebodyparsingresponse)
  - [hiber.modem.message.bodyparser.SimpleModemMessageBodyParser](#hibermodemmessagebodyparsersimplemodemmessagebodyparser)
  - [hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.DelimitedSize](#hibermodemmessagebodyparsersimplemodemmessagebodyparserdelimitedsize)
  - [hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfield)
  - [hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Bytes](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfieldbytes)
  - [hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Float](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfieldfloat)
  - [hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Integer](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfieldinteger)
  - [hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.String](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfieldstring)
  - [hiber.modem.message.bodyparser.TestModemMessageBodyParserRequest](#hibermodemmessagebodyparsertestmodemmessagebodyparserrequest)
  - [hiber.modem.message.bodyparser.TestModemMessageBodyParserRequest.Response](#hibermodemmessagebodyparsertestmodemmessagebodyparserrequestresponse)
  - [hiber.modem.message.bodyparser.UnassignModemMessageBodyParsers](#hibermodemmessagebodyparserunassignmodemmessagebodyparsers)
  - [hiber.modem.message.bodyparser.UnassignModemMessageBodyParsers.Request](#hibermodemmessagebodyparserunassignmodemmessagebodyparsersrequest)
  - [hiber.modem.message.bodyparser.UnassignModemMessageBodyParsers.Response](#hibermodemmessagebodyparserunassignmodemmessagebodyparsersresponse)
  - [hiber.modem.message.bodyparser.UpdateChildOrganizationAvailabilityRequest](#hibermodemmessagebodyparserupdatechildorganizationavailabilityrequest)
  - [hiber.modem.message.bodyparser.UpdateSimpleModemMessageBodyParserRequest](#hibermodemmessagebodyparserupdatesimplemodemmessagebodyparserrequest)
  - [hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest](#hibermodemmessagebodyparserupdateuploadedmodemmessagebodyparserrequest)
  - [hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.AddRequireMessageMetadataEntry](#hibermodemmessagebodyparserupdateuploadedmodemmessagebodyparserrequestaddrequiremessagemetadataentry)
  - [hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields](#hibermodemmessagebodyparserupdateuploadedmodemmessagebodyparserrequestmetadatafields)
  - [hiber.modem.message.bodyparser.UploadModemMessageBodyParserRequest](#hibermodemmessagebodyparseruploadmodemmessagebodyparserrequest)
  - [hiber.modem.message.bodyparser.UploadModemMessageBodyParserRequest.RequireMessageMetadataEntry](#hibermodemmessagebodyparseruploadmodemmessagebodyparserrequestrequiremessagemetadataentry)

    - [hiber.modem.message.bodyparser.ModemMessageBodyParser.PostProcessing](#hibermodemmessagebodyparsermodemmessagebodyparserpostprocessing)
    - [hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Endian](#hibermodemmessagebodyparsersimplemodemmessagebodyparserendian)

- Referenced messages from [value.proto](#referenced-messages-from-valueproto)
  - [hiber.value.Value](#hibervaluevalue)
  - [hiber.value.Value.Enum](#hibervaluevalueenum)
  - [hiber.value.Value.Numeric](#hibervaluevaluenumeric)
  - [hiber.value.Value.Numeric.BatteryLevel](#hibervaluevaluenumericbatterylevel)
  - [hiber.value.Value.Numeric.Distance](#hibervaluevaluenumericdistance)
  - [hiber.value.Value.Numeric.Flow](#hibervaluevaluenumericflow)
  - [hiber.value.Value.Numeric.FuelEfficiency](#hibervaluevaluenumericfuelefficiency)
  - [hiber.value.Value.Numeric.Mass](#hibervaluevaluenumericmass)
  - [hiber.value.Value.Numeric.Percentage](#hibervaluevaluenumericpercentage)
  - [hiber.value.Value.Numeric.Pressure](#hibervaluevaluenumericpressure)
  - [hiber.value.Value.Numeric.Rate](#hibervaluevaluenumericrate)
  - [hiber.value.Value.Numeric.RotationSpeed](#hibervaluevaluenumericrotationspeed)
  - [hiber.value.Value.Numeric.Speed](#hibervaluevaluenumericspeed)
  - [hiber.value.Value.Numeric.Temperature](#hibervaluevaluenumerictemperature)
  - [hiber.value.Value.Numeric.Voltage](#hibervaluevaluenumericvoltage)
  - [hiber.value.Value.Numeric.Volume](#hibervaluevaluenumericvolume)
  - Enums
    - [hiber.value.Value.Numeric.BatteryLevel.Unit](#hibervaluevaluenumericbatterylevelunit)
    - [hiber.value.Value.Numeric.Distance.Unit](#hibervaluevaluenumericdistanceunit)
    - [hiber.value.Value.Numeric.DurationUnit](#hibervaluevaluenumericdurationunit)
    - [hiber.value.Value.Numeric.Flow.Unit](#hibervaluevaluenumericflowunit)
    - [hiber.value.Value.Numeric.FuelEfficiency.Unit](#hibervaluevaluenumericfuelefficiencyunit)
    - [hiber.value.Value.Numeric.Mass.Unit](#hibervaluevaluenumericmassunit)
    - [hiber.value.Value.Numeric.Percentage.Unit](#hibervaluevaluenumericpercentageunit)
    - [hiber.value.Value.Numeric.Pressure.Unit](#hibervaluevaluenumericpressureunit)
    - [hiber.value.Value.Numeric.Rate.Unit](#hibervaluevaluenumericrateunit)
    - [hiber.value.Value.Numeric.RotationSpeed.Unit](#hibervaluevaluenumericrotationspeedunit)
    - [hiber.value.Value.Numeric.Speed.Unit](#hibervaluevaluenumericspeedunit)
    - [hiber.value.Value.Numeric.Temperature.Unit](#hibervaluevaluenumerictemperatureunit)
    - [hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype)
    - [hiber.value.Value.Numeric.Voltage.Unit](#hibervaluevaluenumericvoltageunit)
    - [hiber.value.Value.Numeric.Volume.Unit](#hibervaluevaluenumericvolumeunit)
    - [hiber.value.Value.Type](#hibervaluevaluetype)
    - [hiber.value.ValueAggregation](#hibervaluevalueaggregation)
    - [hiber.value.ValueTransformation](#hibervaluevaluetransformation)

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


## FieldService


### List
> **rpc** List([ListFields.Request](#listfieldsrequest))
    [ListFields.Response](#listfieldsresponse)



### ForModem
> **rpc** ForModem([ListFieldsForModem.Request](#listfieldsformodemrequest))
    [ListFieldsForModem.Response](#listfieldsformodemresponse)



### Add
> **rpc** Add([AddFieldsRequest](#addfieldsrequest))
    [.hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser)



### ReplaceAll
> **rpc** ReplaceAll([ReplaceAllFieldsRequest](#replaceallfieldsrequest))
    [.hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser)



### Delete
> **rpc** Delete([DeleteFieldsRequest](#deletefieldsrequest))
    [.hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser)



### Update
> **rpc** Update([UpdateFieldRequest](#updatefieldrequest))
    [Field](#field)



### UpdateNumericDetails
> **rpc** UpdateNumericDetails([UpdateFieldNumericDetails.Request](#updatefieldnumericdetailsrequest))
    [Field](#field)



### UpdateEnumValues
> **rpc** UpdateEnumValues([UpdateFieldEnumValues.Request](#updatefieldenumvaluesrequest))
    [Field](#field)




## Messages

### AddFieldsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| parser_identifier | [ string](#string) | The identifier for the parser to remove the field from. |
| fields | [repeated Field](#field) | The fields to add to the parser. |

### DeleteFieldsRequest

Delete the given fields from a parser.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| parser_identifier | [ string](#string) | The identifier for the parser to remove the field from. |
| field_identifiers | [repeated string](#string) | The name or JsonPath of the field to remove. |

### FieldSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
| search | [ string](#string) | Search the fields (matches field, display_name and parser identifier). |
| only_owned | [ bool](#bool) | Only return the fields owned by your organization (exclude fields from inherited parsers). |
| types | [repeated hiber.value.Value.Type](#hibervaluevaluetype) | Filter fields by type. |
| numeric_types | [repeated hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype) | Filter fields by numeric type. Limits field types to numeric. |
| field_identifiers | [repeated string](#string) | Filter fields by field identifiers. |

### ListFields




### ListFields.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ FieldSelection](#fieldselection) | Select which fields to return. |
| pagination | [ hiber.Pagination](#hiberpagination) | none |
| sort | [ ListFields.Sort](#listfieldssort) | none |
| apply_unit_preferences | [ bool](#bool) | Whether to apply the unit preferences to the fields. This will convert any fields into your preferred unit, for convenience. |

### ListFields.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| fields | [repeated Field](#field) | none |
| request | [ ListFields.Request](#listfieldsrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |

### ListFieldsForModem




### ListFieldsForModem.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| modem_selection | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | Select the modems to fetch the fields for. |
| field_selection | [ FieldSelection](#fieldselection) | Select which fields to return. |
| pagination | [ hiber.Pagination](#hiberpagination) | none |
| sort | [ ListFields.Sort](#listfieldssort) | none |
| apply_unit_preferences | [ bool](#bool) | Whether to apply the unit preferences to the fields. This will convert any fields into you preferred unit, for convenience. |
| include_total | [ bool](#bool) | Whether to also calculate the total fields for all selected modems, and return them as a single list in the response. This can be useful to display table columns, for example. |

### ListFieldsForModem.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem_fields | [repeated ListFieldsForModem.Response.ModemWithFields](#listfieldsformodemresponsemodemwithfields) | none |
| request | [ ListFieldsForModem.Request](#listfieldsformodemrequest) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |
| total | [repeated Field](#field) | A merged result of all fields, for all modems. This can be useful to display table columns, for example. |

### ListFieldsForModem.Response.ModemWithFields



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem | [ string](#string) | none |
| fields | [repeated Field](#field) | none |

### ReplaceAllFieldsRequest

Replace all fields for a parser with the fields given.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| parser_identifier | [ string](#string) | The identifier for the parser to remove the field from. |
| replace_with_fields | [repeated Field](#field) | The fields to add to the parser, replacing all previous fields. |

### UpdateFieldEnumValues



| Field | Type | Description |
| ----- | ---- | ----------- |
| add_values | [repeated hiber.value.Value.Enum](#hibervaluevalueenum) | Add new enum values to this field. Fails when any already exist. |
| remove_values | [repeated string](#string) | Remove enum values from this field. |
| update_values | [repeated UpdateFieldEnumValues.UpdateEnumValue](#updatefieldenumvaluesupdateenumvalue) | Update enum value details for this field. |
| replace_all_values | [repeated hiber.value.Value.Enum](#hibervaluevalueenum) | Delete all enum values for this field and replace them with this set of enum values. Cannot be combined with update_values, for obvious reasons. |

### UpdateFieldEnumValues.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| field_identifier | [ string](#string) | The identifier for the field. |
| update | [ UpdateFieldEnumValues](#updatefieldenumvalues) | none |

### UpdateFieldEnumValues.UpdateEnumValue



| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ string](#string) | The enum value. This might be a cryptic value, see the display_name and description for more information. |
| update_display_name | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | Update the user-facing name for this value. |
| update_description | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | Update the description for this enum value. |
| update_color | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | Update the color for this enum value. |
| update_priority | [ hiber.UpdateZeroableInt](#hiberupdatezeroableint) | Update the priority, which is used to sort the enum values. |

### UpdateFieldNumericDetails



| Field | Type | Description |
| ----- | ---- | ----------- |
| replace_unit | [ Field.Numeric.Unit](#fieldnumericunit) | Replace the unit for this field. Automatically replaces the type and the symbol based on the unit. |
| replace_format | [ Field.Numeric.Format](#fieldnumericformat) | Replace the formatting for this field. The entire object must be configured. |
| replace_unit_of_measurement | [ hiber.UnitOfMeasurement](#hiberunitofmeasurement) | Replace the unit for this field. Automatically replaces the type and the symbol based on the unit. Deprecated: use replace_unit instead |

### UpdateFieldNumericDetails.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| field_identifier | [ string](#string) | The identifier for the field. |
| update | [ UpdateFieldNumericDetails](#updatefieldnumericdetails) | none |

### UpdateFieldRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| field_identifier | [ string](#string) | The identifier for the field. |
| display_name | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | An optional display name for the field. |
| priority | [ hiber.UpdateZeroableInt](#hiberupdatezeroableint) | Priority of the field, typically used for ordering. |
| encrypted | [ hiber.UpdateBoolean](#hiberupdateboolean) | Whether this field should be stored encrypted or not. When set to true at a later point, earlier values are not encrypted retro-actively. |
| optional | [ hiber.UpdateBoolean](#hiberupdateboolean) | Whether this field is optional or not. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **update_details**.numeric | [ UpdateFieldNumericDetails](#updatefieldnumericdetails) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **update_details**.enum | [ UpdateFieldEnumValues](#updatefieldenumvalues) | none |


## Enums
### ListFields.Sort


| Name | Description | Number |
| ---- | ----------- | ------ |
| PARSER_PRIORITY | Sort by parser and priority in the parser. | 0 |
| DISPLAY_NAME | Sort by display_name. | 1 |
| FIELD_PATH | Sort by json path only. | 2 |



## Referenced messages from field.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [field.proto](https://github.com/HiberGlobal/api/blob/master/field.proto).


### hiber.field.Field



| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) | Unique identifier for this field. |
| field | [ string](#string) | The name of the field (if in the root structure) or a JsonPath to the field. |
| display_name | [ string](#string) | An optional display name for the field. |
| priority | [ int32](#int32) | Priority of the field, typically used for ordering. |
| type | [ hiber.value.Value.Type](#hibervaluevaluetype) | The type of value the field contains. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **details**.numeric | [ hiber.field.Field.Numeric](#hiberfieldfieldnumeric) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **details**.enum | [ hiber.field.Field.Enum](#hiberfieldfieldenum) | none |
| encrypted | [ bool](#bool) | Whether this field should be stored encrypted or not. If it is, some processing options may be unavailable or slower. |
| optional | [ bool](#bool) | Whether this field should be validated from the parser output. |
| unit_of_measurement | [ hiber.UnitOfMeasurement](#hiberunitofmeasurement) | If numeric, the unit of the field. Deprecated: use numeric.numeric_unit oneof instead |
| unit_symbol | [ string](#string) | The symbol for the unit. Deprecated: use numeric.symbol instead |

### hiber.field.Field.Enum

If the field is an enum, this specifies the enum values for the field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| values | [repeated hiber.value.Value.Enum](#hibervaluevalueenum) | none |

### hiber.field.Field.Numeric

If the field is numeric, this specifies the unit and formatting details for the field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype) | The type of numeric value. |
| symbol | [ string](#string) | The symbol to use for the field's unit. |
| format | [ hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat) | How to format the values (number of decimals, rounding, etc.). |
| unit | [ hiber.field.Field.Numeric.Unit](#hiberfieldfieldnumericunit) | The unit for the field, depending on the type. |
| converted_from | [ hiber.field.Field.Numeric.Unit](#hiberfieldfieldnumericunit) | If the unit preferences were applied, and the unit is different, the field will be converted to the preferred unit, from the original unit specified in this field. |

### hiber.field.Field.Numeric.Format

Formatting options for the field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **round**.round_to_integer | [ bool](#bool) | Round to an integer. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **round**.round_to_scale | [ uint32](#uint32) | Round to a number of decimals (at least 1). |
| rounding_mode | [ hiber.field.Field.Numeric.Format.RoundingMode](#hiberfieldfieldnumericformatroundingmode) | How to round the value when scale is applied. |

### hiber.field.Field.Numeric.Unit



| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.battery_level | [ hiber.value.Value.Numeric.BatteryLevel.Unit](#hibervaluevaluenumericbatterylevelunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.distance | [ hiber.value.Value.Numeric.Distance.Unit](#hibervaluevaluenumericdistanceunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.duration | [ hiber.value.Value.Numeric.DurationUnit](#hibervaluevaluenumericdurationunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.fuel_efficiency | [ hiber.value.Value.Numeric.FuelEfficiency.Unit](#hibervaluevaluenumericfuelefficiencyunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.flow | [ hiber.value.Value.Numeric.Flow.Unit](#hibervaluevaluenumericflowunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.percentage | [ hiber.value.Value.Numeric.Percentage.Unit](#hibervaluevaluenumericpercentageunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.pressure | [ hiber.value.Value.Numeric.Pressure.Unit](#hibervaluevaluenumericpressureunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.speed | [ hiber.value.Value.Numeric.Speed.Unit](#hibervaluevaluenumericspeedunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.temperature | [ hiber.value.Value.Numeric.Temperature.Unit](#hibervaluevaluenumerictemperatureunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.voltage | [ hiber.value.Value.Numeric.Voltage.Unit](#hibervaluevaluenumericvoltageunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.volume | [ hiber.value.Value.Numeric.Volume.Unit](#hibervaluevaluenumericvolumeunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.mass | [ hiber.value.Value.Numeric.Mass.Unit](#hibervaluevaluenumericmassunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.rotation_speed | [ hiber.value.Value.Numeric.RotationSpeed.Unit](#hibervaluevaluenumericrotationspeedunit) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.rate | [ hiber.value.Value.Numeric.Rate.Unit](#hibervaluevaluenumericrateunit) | none |


### Enums
#### hiber.field.Field.Numeric.Format.RoundingMode
How to round the value when scale is applied.
For example, a value of 3.1415 with scale 3 could be
  4.141 (DOWN, HALF_DOWN, FLOOR) or
  4.142 (HALF_UP, UP, CEILING).

| Name | Description | Number |
| ---- | ----------- | ------ |
| HALF_UP | Round towards "nearest neighbor" unless both neighbors are equidistant, in which case round up Effectively round up when >= .5, otherwise round down. | 0 |
| HALF_DOWN | Round towards "nearest neighbor" unless both neighbors are equidistant, in which case round down. Effectively round up when > .5, otherwise round down. | 1 |
| UP | Round away from zero: 1.1 -> 2, while -1.1 -> -2. | 3 |
| DOWN | Round towards zero: 1.1 -> 1, while -1.1 -> -1. | 4 |
| CEILING | Round towards positive infinity. | 5 |
| FLOOR | Round towards negative infinity. | 6 |
| HALF_EVEN | Round towards the "nearest neighbor" unless both neighbors are equidistant, in which case, round towards the even neighbor. Effectively round up when >= .5 and next integer value is even, otherwise round down. | 7 |



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
| technical | [ hiber.modem.Modem.TechnicalData](#hibermodemmodemtechnicaldata) | additional information |
| peripherals | [ hiber.modem.Modem.Peripherals](#hibermodemmodemperipherals) | none |
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

#### hiber.modem.Modem.Type
The effective type of this modem.
Type can depend on the hardware itself as well as network topology.

| Name | Description | Number |
| ---- | ----------- | ------ |
| OTHER | A device of which the specific type is not known | 0 |
| DEVICE | A device that is not currently connected to a gateway. | 1 |
| GATEWAY | A device that can receive messages from sensors in the field and relay them (directly) to the satellite. Typically a LoRaWAN hub. Note that gateways also send messages themselves (e.g. a daily heartbeat). | 2 |
| CONNECTED_DEVICE | A sensor that can (only) send data to a gateway. Typically using a LoRaWAN connection. | 3 |

#### hiber.modem.ModemMessage.Source


| Name | Description | Number |
| ---- | ----------- | ------ |
| HIBERBAND | A real message from a modem or gateway, sent over Hiberband to the server. | 0 |
| DIRECT_TO_API | A real message from a modem or gateway, sent directly to the API using a persistent connection. | 1 |
| TEST | A test message sent to the testing API. | 2 |
| SIMULATION | A simulated message, generated by the server. | 3 |



## Referenced messages from modem_message_body_parser.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [modem_message_body_parser.proto](https://github.com/HiberGlobal/api/blob/master/modem_message_body_parser.proto).


### hiber.modem.message.bodyparser.AssignModemMessageBodyParsers

Add direct assignments.
If an overlapping assignment using a rule exists, it is shadowed by the direct assignment.

Simplified version of assign.AssignDirectly.


### hiber.modem.message.bodyparser.AssignModemMessageBodyParsers.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| assign_parsers | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) | none |
| to_modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | none |

### hiber.modem.message.bodyparser.AssignModemMessageBodyParsers.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| created | [repeated hiber.modem.message.bodyparser.AssignedModemMessageBodyParser](#hibermodemmessagebodyparserassignedmodemmessagebodyparser) | none |
| request | [ hiber.modem.message.bodyparser.AssignModemMessageBodyParsers.Request](#hibermodemmessagebodyparserassignmodemmessagebodyparsersrequest) | none |

### hiber.modem.message.bodyparser.AssignedModemMessageBodyParser

Directly assigned modem message parser to a modem.

| Field | Type | Description |
| ----- | ---- | ----------- |
| parser_identifier | [ string](#string) | none |
| modem_number | [ string](#string) | none |

### hiber.modem.message.bodyparser.CreateSimpleModemMessageBodyParserRequest

Create a simple modem message parser, which generates a .ksy specification.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| parser | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser](#hibermodemmessagebodyparsersimplemodemmessagebodyparser) | none |

### hiber.modem.message.bodyparser.DeleteModemMessageBodyParserRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) | A selection of parsers to be deleted. |

### hiber.modem.message.bodyparser.DeleteModemMessageBodyParserRequest.Response




### hiber.modem.message.bodyparser.ListModemMessageBodyParsersRequest

List the parser your organizations has access to. This may include inherited parsers.

If include_content is not set, this call may omit parser specifications, like the ksy, since those are
typically larger multi-line strings.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) | none |
| pagination | [ hiber.Pagination](#hiberpagination) | none |
| exclude_content | [ bool](#bool) | Whether to omit the content in the resulting ModemMessageBodyParsers. |

### hiber.modem.message.bodyparser.ListModemMessageBodyParsersRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| parsers | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser) | none |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) | none |
| request | [ hiber.modem.message.bodyparser.ListModemMessageBodyParsersRequest](#hibermodemmessagebodyparserlistmodemmessagebodyparsersrequest) | none |

### hiber.modem.message.bodyparser.MakeModemMessageBodyParserAvailableToChildOrganizationRequest

Make this parser available to a specific child organizations.

This will
- when the organization is on the exclude list, remove it
- when the includeAll flag is false, add it to the include list (if not already present)

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the parser that should be updated. |
| available_to | [repeated string](#string) | The child organization(s) that the parser should be available to. |

### hiber.modem.message.bodyparser.MakeModemMessageBodyParserUnavailableToChildOrganizationRequest

Make this parser unavailable to a specific child organizations.

This will
- when the organization is on the include list, remove it
- when the includeAll flag is true, add it to the exclude list (if not already present)

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the parser that should be updated. |
| unavailable_to | [repeated string](#string) | The child organization(s) that the parser should be unavailable to. |

### hiber.modem.message.bodyparser.ModemMessageBodyParser

Modem message body parser. This defines a parsing strategy for the body of a message.
A parser can be defined in two ways: using a .ksy (Kaitai struct https://kaitai.io/) file or using the simple parser.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) | The globally (across organizations) unique identifier for this parser. |
| organization | [ string](#string) | The organization that created the parser. |
| name | [ string](#string) | The name for this parser. |
| content_ksy | [ string](#string) | The content of this parsers script. If simple_parser is set, this content is generated from that definition. This field may be omitted by the list call to save data. |
| simple_parser | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser](#hibermodemmessagebodyparsersimplemodemmessagebodyparser) | The simple parser this .ksy was generated from, if it was generated from a simple parser. This field may be omitted on demand to save data in the list call. |
| data_fields | [repeated hiber.field.Field](#hiberfieldfield) | Fields in the parsed result that contain data. Data fields are cached for efficient retrieval and allow all kinds of processing. |
| data_fields_deprecated | [repeated string](#string) | none |
| metadata_fields | [ hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafields) | Fields in the parsed result that contain metadata, and special things like a location. |
| available_to_child_organizations | [ hiber.modem.message.bodyparser.ModemMessageBodyParser.AvailableToChildOrganizations](#hibermodemmessagebodyparsermodemmessagebodyparseravailabletochildorganizations) | If set, this parser is available to your child organizations, as a Provided parser. |
| post_processing | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser.PostProcessing](#hibermodemmessagebodyparsermodemmessagebodyparserpostprocessing) | The list of post-processing steps applied to the result of this parser. |
| require_message_metadata | [map hiber.modem.message.bodyparser.ModemMessageBodyParser.RequireMessageMetadataEntry](#hibermodemmessagebodyparsermodemmessagebodyparserrequiremessagemetadataentry) | In order to use this parser on a message, the metadata on the message must match the given requirement here. The key of the map is the json-path to look for in the message metadata, the value of the map is the json to expect at that json-path. |

### hiber.modem.message.bodyparser.ModemMessageBodyParser.AvailableToChildOrganizations

A modem message body parser with this object is available to child organizations.
This means the child organization can use it, but not update or delete it.

| Field | Type | Description |
| ----- | ---- | ----------- |
| child_organizations | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | none |

### hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields

Fields in the parsed result that match common things that can be processed by the system,
like a location or battery percentage.

| Field | Type | Description |
| ----- | ---- | ----------- |
| location_fields | [ hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields.LocationFields](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafieldslocationfields) | Specify a pair of fields in the message body that contain location data, which will update the modem location and the map. |
| message_metadata_fields | [repeated string](#string) | Custom metadata fields, which will be added to the message metadata json. |
| modem_metadata_fields | [repeated string](#string) | Custom metadata fields, which will be added to the modem metadata json. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **measured_at_field**.measured_at_time_field | [ string](#string) | Field that contains the time (epoch seconds) to use for the values extracted from the message. If not set, sent time is used. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **measured_at_field**.measured_at_offset_field | [ string](#string) | Field that contains the time offset (second before sent time) to use for the values extracted from the message. If not set, sent time is used. |

### hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields.LocationFields



| Field | Type | Description |
| ----- | ---- | ----------- |
| latitude | [ string](#string) | none |
| longitude | [ string](#string) | none |

### hiber.modem.message.bodyparser.ModemMessageBodyParser.RequireMessageMetadataEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ google.protobuf.Value](#googleprotobufvalue) | none |

### hiber.modem.message.bodyparser.ModemMessageBodyParserSelection

Selection object for parsers. Used to select which parser to list, assign, etc.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifiers | [repeated string](#string) | Filter parsers by their identifiers. |
| search | [ string](#string) | Find parsers by searching for this text in the name, content_ksy, data fields or simple parser definition. |
| only_simple | [ bool](#bool) | Only return simple parsers, created using SimpleModemMessageBodyParser. |
| only_ksy_file | [ bool](#bool) | Only return parsers created from an uploaded .ksy file. |
| only_owned_parsers | [ bool](#bool) | Exclude parsers that are not owned by your organization (those that you did not create yourself). |
| owner_organizations | [repeated string](#string) | Only return parsers that were created by the given parent organizations. |
| has_data_fields | [repeated string](#string) | Only return parsers that have one of the given data fields This only works when the fields are marked explicitly using the data fields option. |

### hiber.modem.message.bodyparser.RenameModemMessageBodyParserRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the parser that should be updated. |
| name | [ string](#string) | The new name for this parser. |

### hiber.modem.message.bodyparser.RetryModemMessageBodyParsing

Retry a message, parsing it with all the currently assigned parsers that are in the given selection.
If the message was previously parsed by any of those parsers, the previous result is replaced.


### hiber.modem.message.bodyparser.RetryModemMessageBodyParsing.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| modem_message_ids | [repeated uint64](#uint64) | The messages to parse. |
| parser_selection | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) | A selection of parsers to apply, if they are assigned. |

### hiber.modem.message.bodyparser.RetryModemMessageBodyParsing.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| parsed_messages | [repeated hiber.modem.ModemMessage.ParsedBody](#hibermodemmodemmessageparsedbody) | none |

### hiber.modem.message.bodyparser.SimpleModemMessageBodyParser

Simple modem message body parser. This can be used a convenient way to create a .ksy parser.

| Field | Type | Description |
| ----- | ---- | ----------- |
| name | [ string](#string) | Parser name. When this structure is used as a custom type inside a parser, this name is a reduced to a value containing only lowercase letters, numbers and underscores, like field names. |
| documentation | [ string](#string) | A short, single line description of the field. |
| fields | [repeated hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfield) | The fields in this object. |
| default_endian | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Endian](#hibermodemmessagebodyparsersimplemodemmessagebodyparserendian) | Sets a default endianness for this parser's fields and any fields in custom types. |
| default_text_encoding | [ string](#string) | Sets a default string encoding for this parser's fields and any fields in custom types. |
| custom_types | [repeated hiber.modem.message.bodyparser.SimpleModemMessageBodyParser](#hibermodemmessagebodyparsersimplemodemmessagebodyparser) | A list of custom types used for custom types fields. Each is effectively a simple parser, and can have its own custom types again, which can only be used within that parser structure. The parser name is used for custom type fields. |

### hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.DelimitedSize

Delimited size definition, used for Bytes and Text.

| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **size**.size_bytes | [ int32](#int32) | Specifies the number of bytes in this field. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **size**.end_of_stream | [ bool](#bool) | Specifies that this field parses all bytes until the end of the stream. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **size**.field_name | [ string](#string) | Specifies the number of bytes in this field using the value of an Integer field. This integer field must be parsed before this field is parsed. |
| terminator | [ bytes](#bytes) | Specify a terminator that marks the point the field terminates, optionally, and we should continue to the next field. This is typically a single byte (i.e. 0x00). This can be combined with a size to limit the amounts of bytes that are parsed. |

### hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field



| Field | Type | Description |
| ----- | ---- | ----------- |
| name | [ string](#string) | Field name. This is a reduced to a value containing only lowercase letters, numbers and underscores. |
| documentation | [ string](#string) | A short, single line description of the field. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.integer | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Integer](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfieldinteger) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.float | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Float](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfieldfloat) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.bytes | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Bytes](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfieldbytes) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.string | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.String](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfieldstring) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.magic | [ bytes](#bytes) | Specify an expected magic sequence (some bytes that are always the same). |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.custom_type | [ string](#string) | Specify a custom type name. |

### hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Bytes



| Field | Type | Description |
| ----- | ---- | ----------- |
| size | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.DelimitedSize](#hibermodemmessagebodyparsersimplemodemmessagebodyparserdelimitedsize) | none |

### hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Float



| Field | Type | Description |
| ----- | ---- | ----------- |
| size_bytes | [ int32](#int32) | Specifies the size of this floating point number in bytes. |
| endian | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Endian](#hibermodemmessagebodyparsersimplemodemmessagebodyparserendian) | Specifies endian encoding for this field. This can be omitted if default endianness specified. |

### hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Integer



| Field | Type | Description |
| ----- | ---- | ----------- |
| size_bytes | [ int32](#int32) | Specifies the size of this integer in bytes. |
| signed | [ bool](#bool) | Specifies whether this integer is signed or unsigned. |
| endian | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Endian](#hibermodemmessagebodyparsersimplemodemmessagebodyparserendian) | Specifies endian encoding for this field. This can be omitted if default endianness specified. |

### hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.String



| Field | Type | Description |
| ----- | ---- | ----------- |
| size | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.DelimitedSize](#hibermodemmessagebodyparsersimplemodemmessagebodyparserdelimitedsize) | none |
| encoding | [ string](#string) | Specifies encoding for the string. This can be omitted if default encoding specified. |

### hiber.modem.message.bodyparser.TestModemMessageBodyParserRequest

Test a parsers on a message.

This method provides a number of options and can be used in multiple ways:
- Test a real message or an uploaded message body.
- Test using an existing parser, an ksy definition or a simple parser definition.

This can be used to test a parser with a modem's past messages, before assigning it,
or while developing a parser to validate it with an expected body.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **parser**.identifier | [ string](#string) | The identifier of the parser you want to test. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **parser**.content_ksy | [ string](#string) | A ksy definition you want to test. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **parser**.simple_parser | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser](#hibermodemmessagebodyparsersimplemodemmessagebodyparser) | A simple parser definition you want to test. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.parse_bytes | [ hiber.BytesOrHex](#hiberbytesorhex) | A byte array (message body) to parse. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.modem_message_id | [ uint64](#uint64) | The id of an existing message, testing the parser on its body. |

### hiber.modem.message.bodyparser.TestModemMessageBodyParserRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **result**.parsed | [ google.protobuf.Struct](#googleprotobufstruct) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **result**.error | [ string](#string) | none |

### hiber.modem.message.bodyparser.UnassignModemMessageBodyParsers

Remove a direct assignment.
If an overlapping assignment using a rule exists, it is not affected, except that it is longer shadowed.

Simplified version of assign.UnassignDirectly.


### hiber.modem.message.bodyparser.UnassignModemMessageBodyParsers.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| unassign_parsers | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) | none |
| from_modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) | none |

### hiber.modem.message.bodyparser.UnassignModemMessageBodyParsers.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| removed_direct_assignments | [repeated hiber.modem.message.bodyparser.AssignedModemMessageBodyParser](#hibermodemmessagebodyparserassignedmodemmessagebodyparser) | none |
| request | [ hiber.modem.message.bodyparser.UnassignModemMessageBodyParsers.Request](#hibermodemmessagebodyparserunassignmodemmessagebodyparsersrequest) | none |

### hiber.modem.message.bodyparser.UpdateChildOrganizationAvailabilityRequest

Update the child availability for a parser.
Parsers can be made available to child organizations, which means that they can be viewed in,
and assigned to modems in, child organizations.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the parser that should be updated. |
| available_to_child_organizations | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | The new child organization availability filter for this parser. |

### hiber.modem.message.bodyparser.UpdateSimpleModemMessageBodyParserRequest

Update a simple modem message parser, updating the generated .ksy specification.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the parser that should be updated. |
| parser | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser](#hibermodemmessagebodyparsersimplemodemmessagebodyparser) | none |

### hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest

Upload an updated body parser from a .ksy file, replacing the previous file.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the parser that should be updated. |
| content_ksy | [ string](#string) | The new ksy definition for this parser. |
| add_data_fields | [repeated hiber.field.Field](#hiberfieldfield) | Add fields to the data fields list. |
| remove_data_fields | [repeated string](#string) | Remove fields from the data fields list. |
| metadata_fields | [ hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields](#hibermodemmessagebodyparserupdateuploadedmodemmessagebodyparserrequestmetadatafields) | Fields in the parsed result that match special things that can be processed by the system, like a location. |
| add_post_processing | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser.PostProcessing](#hibermodemmessagebodyparsermodemmessagebodyparserpostprocessing) | Add a post-processing step to the result of this parser. |
| remove_post_processing | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser.PostProcessing](#hibermodemmessagebodyparsermodemmessagebodyparserpostprocessing) | Remove a post-processing step to the result of this parser. |
| add_require_message_metadata | [map hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.AddRequireMessageMetadataEntry](#hibermodemmessagebodyparserupdateuploadedmodemmessagebodyparserrequestaddrequiremessagemetadataentry) | In order to use this parser on a message, the metadata on the message must match the given requirement here. The key of the map is the json-path to look for in the message metadata, the value of the map is the json to expect at that json-path. |
| remove_require_message_metadata | [repeated string](#string) | Remove a requirement for the metadata. Remove by listing the json-path here. |

### hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.AddRequireMessageMetadataEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ google.protobuf.Value](#googleprotobufvalue) | none |

### hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields



| Field | Type | Description |
| ----- | ---- | ----------- |
| update_location_fields | [ hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields.LocationFields](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafieldslocationfields) | Update the location fields. |
| add_message_metadata_fields | [repeated string](#string) | Add fields to the message metadata fields list. |
| remove_message_metadata_fields | [repeated string](#string) | Remove fields from the message metadata fields list. |
| replace_message_metadata_fields | [repeated string](#string) | Replace the message metadata fields list. |
| add_modem_metadata_fields | [repeated string](#string) | Add fields to the modem metadata fields list. |
| remove_modem_metadata_fields | [repeated string](#string) | Remove fields from the modem metadata fields list. |
| replace_modem_metadata_fields | [repeated string](#string) | Replace the modem metadata fields list. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **measured_at_field**.measured_at_time_field | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | Update the custom field to extract to measured_at time. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **measured_at_field**.measured_at_offset_field | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | Update the custom field to extract to measured_at offset from the sent_at time in seconds. |

### hiber.modem.message.bodyparser.UploadModemMessageBodyParserRequest

Upload a new body parser from a .ksy file.

| Field | Type | Description |
| ----- | ---- | ----------- |
| organization | [ string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| name | [ string](#string) | A descriptive name for this parser. |
| content_ksy | [ string](#string) | The ksy definition for this parser. |
| data_fields | [repeated hiber.field.Field](#hiberfieldfield) | Fields in the parsed result that contain data. This can be useful to track which fields could be plotted, etc. |
| metadata_fields | [ hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafields) | Fields in the parsed result that match special things that can be processed by the system, like a location. |
| post_processing | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser.PostProcessing](#hibermodemmessagebodyparsermodemmessagebodyparserpostprocessing) | none |
| require_message_metadata | [map hiber.modem.message.bodyparser.UploadModemMessageBodyParserRequest.RequireMessageMetadataEntry](#hibermodemmessagebodyparseruploadmodemmessagebodyparserrequestrequiremessagemetadataentry) | In order to use this parser on a message, the metadata on the message must match the given requirement here. The key of the map is the json-path to look for in the message metadata, the value of the map is the json to expect at that json-path. |

### hiber.modem.message.bodyparser.UploadModemMessageBodyParserRequest.RequireMessageMetadataEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ google.protobuf.Value](#googleprotobufvalue) | none |


### Enums
#### hiber.modem.message.bodyparser.ModemMessageBodyParser.PostProcessing
The type of post-processing to be applied to the result of this parser.

| Name | Description | Number |
| ---- | ----------- | ------ |
| NOTHING | none | 0 |

#### hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Endian


| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | none | 0 |
| LITTLE_ENDIAN | none | 1 |
| BIG_ENDIAN | none | 2 |



## Referenced messages from value.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [value.proto](https://github.com/HiberGlobal/api/blob/master/value.proto).


### hiber.value.Value



| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.value.Value.Type](#hibervaluevaluetype) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.numeric | [ hiber.value.Value.Numeric](#hibervaluevaluenumeric) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.text | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.enum | [ hiber.value.Value.Enum](#hibervaluevalueenum) | none |

### hiber.value.Value.Enum

If this value is an enum, this specifies the value, display name and color for this enum value.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ string](#string) | The enum value. This might be a cryptic value, see the display_name and description for more information. |
| display_name | [ string](#string) | User-facing name for this value. |
| description | [ string](#string) | More details for this enum value. |
| color | [ string](#string) | (Optional) color for this enum value. |
| priority | [ int32](#int32) | Priority of the value, typically used for ordering. |

### hiber.value.Value.Numeric

If the value is numeric, this specifies the unit, value, etc.

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.battery_level | [ hiber.value.Value.Numeric.BatteryLevel](#hibervaluevaluenumericbatterylevel) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.distance | [ hiber.value.Value.Numeric.Distance](#hibervaluevaluenumericdistance) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.duration | [ hiber.Duration](#hiberduration) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.fuel_efficiency | [ hiber.value.Value.Numeric.FuelEfficiency](#hibervaluevaluenumericfuelefficiency) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.percentage | [ hiber.value.Value.Numeric.Percentage](#hibervaluevaluenumericpercentage) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.pressure | [ hiber.value.Value.Numeric.Pressure](#hibervaluevaluenumericpressure) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.speed | [ hiber.value.Value.Numeric.Speed](#hibervaluevaluenumericspeed) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.temperature | [ hiber.value.Value.Numeric.Temperature](#hibervaluevaluenumerictemperature) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.voltage | [ hiber.value.Value.Numeric.Voltage](#hibervaluevaluenumericvoltage) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.volume | [ hiber.value.Value.Numeric.Volume](#hibervaluevaluenumericvolume) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.mass | [ hiber.value.Value.Numeric.Mass](#hibervaluevaluenumericmass) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.flow | [ hiber.value.Value.Numeric.Flow](#hibervaluevaluenumericflow) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.rotation_speed | [ hiber.value.Value.Numeric.RotationSpeed](#hibervaluevaluenumericrotationspeed) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.rate | [ hiber.value.Value.Numeric.Rate](#hibervaluevaluenumericrate) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.unknown | [ double](#double) | none |

### hiber.value.Value.Numeric.BatteryLevel

Special case for battery level, since it can be provided in many units.
Not included in the UnitPreferences, since it cannot be converted.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ hiber.value.Value.Numeric.BatteryLevel.Unit](#hibervaluevaluenumericbatterylevelunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.BatteryLevel.Unit](#hibervaluevaluenumericbatterylevelunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Distance

The value is a distance value, converted to your preferred distance unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ hiber.value.Value.Numeric.Distance.Unit](#hibervaluevaluenumericdistanceunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Distance.Unit](#hibervaluevaluenumericdistanceunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Flow



| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ hiber.value.Value.Numeric.Flow.Unit](#hibervaluevaluenumericflowunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Flow.Unit](#hibervaluevaluenumericflowunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.FuelEfficiency

The value is a distance value, converted to your preferred distance unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ hiber.value.Value.Numeric.FuelEfficiency.Unit](#hibervaluevaluenumericfuelefficiencyunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.FuelEfficiency.Unit](#hibervaluevaluenumericfuelefficiencyunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Mass

The value is a volume value, converted to your preferred volume unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ hiber.value.Value.Numeric.Mass.Unit](#hibervaluevaluenumericmassunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Mass.Unit](#hibervaluevaluenumericmassunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Percentage

The value is a percentage.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ float](#float) | none |
| unit | [ hiber.value.Value.Numeric.Percentage.Unit](#hibervaluevaluenumericpercentageunit) | none |
| textual | [ string](#string) | Textual representation with % symbol, rounded based on the user preferences and field config. |

### hiber.value.Value.Numeric.Pressure

The value is a pressure value, converted to your preferred pressure unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ hiber.value.Value.Numeric.Pressure.Unit](#hibervaluevaluenumericpressureunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Pressure.Unit](#hibervaluevaluenumericpressureunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Rate



| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ uint32](#uint32) | none |
| unit | [ hiber.value.Value.Numeric.Rate.Unit](#hibervaluevaluenumericrateunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Rate.Unit](#hibervaluevaluenumericrateunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.RotationSpeed

The value for rotation speed. The only value is revolutions per minute (RPM), therefore it is not included in
unit preferences.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ hiber.value.Value.Numeric.RotationSpeed.Unit](#hibervaluevaluenumericrotationspeedunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.RotationSpeed.Unit](#hibervaluevaluenumericrotationspeedunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Speed

The value is a speed value, converted to your preferred speed unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ hiber.value.Value.Numeric.Speed.Unit](#hibervaluevaluenumericspeedunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Speed.Unit](#hibervaluevaluenumericspeedunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Temperature

The value is a temperature, converted to your preferred temperature unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ hiber.value.Value.Numeric.Temperature.Unit](#hibervaluevaluenumerictemperatureunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Temperature.Unit](#hibervaluevaluenumerictemperatureunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Voltage

The value is a voltage, converted to your preferred voltage unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ hiber.value.Value.Numeric.Voltage.Unit](#hibervaluevaluenumericvoltageunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Voltage.Unit](#hibervaluevaluenumericvoltageunit) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.Volume

The value is a volume value, converted to your preferred volume unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ double](#double) | none |
| unit | [ hiber.value.Value.Numeric.Volume.Unit](#hibervaluevaluenumericvolumeunit) | none |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| converted_from | [ hiber.value.Value.Numeric.Volume.Unit](#hibervaluevaluenumericvolumeunit) | The original unit, iff this value was converted from another unit because of user preferences. |


### Enums
#### hiber.value.Value.Numeric.BatteryLevel.Unit
other units will be added here later, like voltage

| Name | Description | Number |
| ---- | ----------- | ------ |
| PERCENT | Battery level as a percentage (technically not a unit). | 0 |

#### hiber.value.Value.Numeric.Distance.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| METER | none | 0 |
| MILLIMETER | none | 1 |
| CENTIMETER | none | 2 |
| KILOMETER | none | 3 |
| YARD | none | 5 |
| MILE | none | 4 |
| FOOT | none | 6 |
| INCH | none | 7 |
| NAUTICAL_MILE | This is a special case unit and may not be auto-converted to your UnitPreference. | 8 |

#### hiber.value.Value.Numeric.DurationUnit
The duration enum is not wrapped in Duration, since duration is always returned as a normalize Duration.
This unit is still used for fields, however.

| Name | Description | Number |
| ---- | ----------- | ------ |
| MILLISECONDS | none | 0 |
| SECONDS | none | 1 |
| MINUTES | none | 2 |
| HOURS | none | 3 |
| DAYS | none | 4 |
| WEEKS | none | 5 |

#### hiber.value.Value.Numeric.Flow.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| CUBIC_METER_PER_HOUR | none | 0 |
| BARRELS_PER_DAY | none | 1 |

#### hiber.value.Value.Numeric.FuelEfficiency.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| LITER_PER_100_KILOMETER | none | 0 |
| KILOMETER_PER_LITER | none | 1 |
| KILOMETER_PER_GALLON | none | 2 |
| KILOMETER_PER_IMPERIAL_GALLON | none | 3 |
| MILE_PER_GALLON | none | 4 |
| MILE_PER_IMPERIAL_GALLON | none | 5 |
| MILE_PER_LITER | none | 6 |

#### hiber.value.Value.Numeric.Mass.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| KILOGRAMS | none | 0 |
| POUNDS | none | 1 |

#### hiber.value.Value.Numeric.Percentage.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| PERCENT | Technically not a unit, but for consistency, we've added it here. | 0 |

#### hiber.value.Value.Numeric.Pressure.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| BAR | none | 0 |
| PSI | none | 1 |
| K_PA | none | 2 |

#### hiber.value.Value.Numeric.Rate.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| ITEMS_PER_24_HOURS | The amount of items counted in a 24 hour window. | 0 |

#### hiber.value.Value.Numeric.RotationSpeed.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| REVOLUTIONS_PER_MINUTE | none | 0 |

#### hiber.value.Value.Numeric.Speed.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| KILOMETERS_PER_HOUR | none | 0 |
| KNOTS | This is a special case unit and may not be auto-converted to your UnitPreference. | 1 |
| METERS_PER_SECOND | none | 2 |
| MILES_PER_HOUR | none | 3 |

#### hiber.value.Value.Numeric.Temperature.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| KELVIN | none | 0 |
| DEGREES_CELSIUS | none | 1 |
| DEGREES_FAHRENHEIT | none | 2 |

#### hiber.value.Value.Numeric.Type
The type of numeric value that is represented.
Supported types will automatically convert to the preferred unit (based on the user settings).

| Name | Description | Number |
| ---- | ----------- | ------ |
| TYPE_UNKNOWN | none | 0 |
| PERCENTAGE | none | 1 |
| TEMPERATURE | none | 2 |
| DISTANCE | none | 3 |
| PRESSURE | none | 4 |
| VOLTAGE | none | 5 |
| SPEED | none | 6 |
| VOLUME | none | 7 |
| DURATION | none | 8 |
| FUEL_EFFICIENCY | none | 9 |
| MASS | none | 10 |
| BATTERY_LEVEL | none | 11 |
| FLOW | none | 12 |
| ROTATION_SPEED | none | 13 |
| RATE | none | 14 |

#### hiber.value.Value.Numeric.Voltage.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| MILLIVOLT | none | 0 |

#### hiber.value.Value.Numeric.Volume.Unit


| Name | Description | Number |
| ---- | ----------- | ------ |
| LITER | none | 0 |
| GALLON_US | none | 1 |
| GALLON_IMPERIAL | none | 2 |
| CUBIC_METER | none | 3 |
| CUBIC_FEET | none | 4 |

#### hiber.value.Value.Type
The type of value that is represented.

| Name | Description | Number |
| ---- | ----------- | ------ |
| OTHER | none | 0 |
| NUMERIC | This field contains numeric values, with an optional unit of measurement defined below. | 1 |
| TEXT | This field contains text to be displayed. | 2 |
| ENUM | This field switches between several predefined values. Typically used for status fields. | 3 |

#### hiber.value.ValueAggregation
Get the values for the selected field.

There are a few limitations here:
- text fields can only use the LAST aggregation.
- enum fields support a subset of aggregations:
  - DEFAULT and LAST return the last value.
  - MINIMUM and MAXIMUM return the lowest or highest value (respectively) based on the enum value order.
  - AVERAGE and SUM are not supported.

- enum duration

An enum example:
Field "status" with this timeline: 00:00 OK, 00:10 FAILED, 00:20 OK, 00:25 FAILED, 00:40 OK
- aggregation DEFAULT or LAST: OK, since it's OK at the end of the time range.
- aggregation SUM: OK: 35m, FAILED: 25m

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT | none | 0 |
| AVERAGE | Return the average value. Not supported for textual and enum fields. When used with these fields, LAST is used instead. | 1 |
| SUM | Return the sum all values. Not supported for textual and enum fields. When used with these fields, LAST is used instead. | 2 |
| LAST | Just take the last value. | 3 |
| MINIMUM | Return the lowest value. For enum fields, the order of values is used to determine the MINIMUM. Not supported for textual fields. When used with these fields, LAST is used instead. | 4 |
| MAXIMUM | Return the highest value. For enum fields, the order of values is used to determine the MAXIMUM. Not supported for textual fields. When used with these fields, LAST is used instead. | 5 |

#### hiber.value.ValueTransformation
Transform the values into a derived value.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DURATION | Instead of returning the value, return the amount of time a value was active. Aggregation (if applicable) is applied afterwards on the duration value. | 0 |
| DELTA | Instead of returning the value, return the difference between the value and the previous value. Aggregation (if applicable) is applied before the delta is calculated. | 1 |



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
| TRANSFER | none | 18 |
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
| FLOW_BARRELS_PER_DAY | none | 46 |
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

