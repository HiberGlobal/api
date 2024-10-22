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
  - [ListFieldsForAsset](#listfieldsforasset)
  - [ListFieldsForAsset.Request](#listfieldsforassetrequest)
  - [ListFieldsForAsset.Response](#listfieldsforassetresponse)
  - [ListFieldsForAsset.Response.AssetWithFields](#listfieldsforassetresponseassetwithfields)
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

- Referenced messages from [asset.proto](#referenced-messages-from-assetproto)
  - [hiber.asset.Asset](#hiberassetasset)
  - [hiber.asset.Asset.AssignedDevice](#hiberassetassetassigneddevice)
  - [hiber.asset.AssetSelection](#hiberassetassetselection)

    - [hiber.asset.Asset.Type](#hiberassetassettype)

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
  - [hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields.RequireMessageMetadataEntry](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafieldsrequiremessagemetadataentry)
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
  - [hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields](#hibermodemmessagebodyparserupdateuploadedmodemmessagebodyparserrequestmetadatafields)
  - [hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields.AddRequireMessageMetadataEntry](#hibermodemmessagebodyparserupdateuploadedmodemmessagebodyparserrequestmetadatafieldsaddrequiremessagemetadataentry)
  - [hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields.ReplaceRequireMessageMetadataEntry](#hibermodemmessagebodyparserupdateuploadedmodemmessagebodyparserrequestmetadatafieldsreplacerequiremessagemetadataentry)
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
  - [hiber.value.Value.Numeric.Duration](#hibervaluevaluenumericduration)
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
    - [hiber.value.Value.Numeric.BatteryLevel.BatteryLevelUnit](#hibervaluevaluenumericbatterylevelbatterylevelunit)
    - [hiber.value.Value.Numeric.Distance.DistanceUnit](#hibervaluevaluenumericdistancedistanceunit)
    - [hiber.value.Value.Numeric.Duration.DurationUnit](#hibervaluevaluenumericdurationdurationunit)
    - [hiber.value.Value.Numeric.Flow.FlowUnit](#hibervaluevaluenumericflowflowunit)
    - [hiber.value.Value.Numeric.FuelEfficiency.FuelEfficiencyUnit](#hibervaluevaluenumericfuelefficiencyfuelefficiencyunit)
    - [hiber.value.Value.Numeric.Mass.MassUnit](#hibervaluevaluenumericmassmassunit)
    - [hiber.value.Value.Numeric.Percentage.PercentageUnit](#hibervaluevaluenumericpercentagepercentageunit)
    - [hiber.value.Value.Numeric.Pressure.PressureUnit](#hibervaluevaluenumericpressurepressureunit)
    - [hiber.value.Value.Numeric.Rate.RateUnit](#hibervaluevaluenumericraterateunit)
    - [hiber.value.Value.Numeric.RotationSpeed.RotationSpeedUnit](#hibervaluevaluenumericrotationspeedrotationspeedunit)
    - [hiber.value.Value.Numeric.Speed.SpeedUnit](#hibervaluevaluenumericspeedspeedunit)
    - [hiber.value.Value.Numeric.Temperature.TemperatureUnit](#hibervaluevaluenumerictemperaturetemperatureunit)
    - [hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype)
    - [hiber.value.Value.Numeric.Voltage.VoltageUnit](#hibervaluevaluenumericvoltagevoltageunit)
    - [hiber.value.Value.Numeric.Volume.VolumeUnit](#hibervaluevaluenumericvolumevolumeunit)
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
  - [hiber.Filter.DeviceTypes](#hiberfilterdevicetypes)
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
  - [hiber.Filter.Roles](#hiberfilterroles)
  - [hiber.Filter.SensorBrands](#hiberfiltersensorbrands)
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



### ForAsset
> **rpc** ForAsset([ListFieldsForAsset.Request](#listfieldsforassetrequest))
    [ListFieldsForAsset.Response](#listfieldsforassetresponse)



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
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| parser_identifier | [ string](#string) | The identifier for the parser to remove the field from. |
| fields | [repeated Field](#field) | The fields to add to the parser. |

### DeleteFieldsRequest

Delete the given fields from a parser.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| parser_identifier | [ string](#string) | The identifier for the parser to remove the field from. |
| field_identifiers | [repeated string](#string) | The name or JsonPath of the field to remove. |

### FieldSelection



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** search | [optional string](#string) | Search the fields (matches field, display_name and parser identifier). |
|  **optional** only_owned | [optional bool](#bool) | Only return the fields owned by your organization (exclude fields from inherited parsers). |
| types | [repeated hiber.value.Value.Type](#hibervaluevaluetype) | Filter fields by type. |
| numeric_types | [repeated hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype) | Filter fields by numeric type. Limits field types to numeric. |
| field_identifiers | [repeated string](#string) | Filter fields by field identifiers. |
|  **optional** include_operational | [optional bool](#bool) | Include operational fields as well (e.g. battery, device status). |

### ListFields




### ListFields.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional FieldSelection](#fieldselection) | Select which fields to return. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |
|  **optional** sort | [optional ListFields.Sort](#listfieldssort) |  |
|  **optional** apply_unit_preferences | [optional bool](#bool) | Whether to apply the unit preferences to the fields. This will convert any fields into your preferred unit, for convenience. |

### ListFields.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| fields | [repeated Field](#field) |  |
| request | [ ListFields.Request](#listfieldsrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |

### ListFieldsForAsset




### ListFieldsForAsset.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** asset_selection | [optional hiber.asset.AssetSelection](#hiberassetassetselection) | Select the assets to fetch the fields for. Optional, when omitted or empty everything is included. |
|  **optional** field_selection | [optional FieldSelection](#fieldselection) | Select which fields to return. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |
| sort | [ ListFields.Sort](#listfieldssort) |  |
|  **optional** apply_unit_preferences | [optional bool](#bool) | Whether to apply the unit preferences to the fields. This will convert any fields into you preferred unit, for convenience. |
|  **optional** include_total | [optional bool](#bool) | Whether to also calculate the total fields for all selected assets, and return them as a single list in the response. This can be useful to display table columns, for example. |
|  **optional** include_historic_fields | [optional bool](#bool) | Whether to include fields that were only present from previously assigned devices. |

### ListFieldsForAsset.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| asset_fields | [repeated ListFieldsForAsset.Response.AssetWithFields](#listfieldsforassetresponseassetwithfields) |  |
| request | [ ListFieldsForAsset.Request](#listfieldsforassetrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |
| total | [repeated Field](#field) | A merged result of all fields, for all assets. This can be useful to display table columns, for example. |

### ListFieldsForAsset.Response.AssetWithFields



| Field | Type | Description |
| ----- | ---- | ----------- |
| asset_name | [ string](#string) |  |
| asset_identifier | [ string](#string) |  |
| fields | [repeated Field](#field) |  |

### ListFieldsForModem




### ListFieldsForModem.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** modem_selection | [optional hiber.modem.ModemSelection](#hibermodemmodemselection) | Select the modems to fetch the fields for. Optional, when omitted or empty everything is included. |
|  **optional** field_selection | [optional FieldSelection](#fieldselection) | Select which fields to return. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |
| sort | [ ListFields.Sort](#listfieldssort) |  |
|  **optional** apply_unit_preferences | [optional bool](#bool) | Whether to apply the unit preferences to the fields. This will convert any fields into you preferred unit, for convenience. |
|  **optional** include_total | [optional bool](#bool) | Whether to also calculate the total fields for all selected modems, and return them as a single list in the response. This can be useful to display table columns, for example. |

### ListFieldsForModem.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem_fields | [repeated ListFieldsForModem.Response.ModemWithFields](#listfieldsformodemresponsemodemwithfields) |  |
| request | [ ListFieldsForModem.Request](#listfieldsformodemrequest) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |
| total | [repeated Field](#field) | A merged result of all fields, for all modems. This can be useful to display table columns, for example. |

### ListFieldsForModem.Response.ModemWithFields



| Field | Type | Description |
| ----- | ---- | ----------- |
| modem | [ string](#string) |  |
| name | [ string](#string) |  |
| identifier | [ string](#string) |  |
| fields | [repeated Field](#field) |  |

### ReplaceAllFieldsRequest

Replace all fields for a parser with the fields given.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
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
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| field_identifier | [ string](#string) | The identifier for the field. |
| update | [ UpdateFieldEnumValues](#updatefieldenumvalues) |  |

### UpdateFieldEnumValues.UpdateEnumValue



| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [ string](#string) | The enum value. This might be a cryptic value, see the display_name and description for more information. |
|  **optional** display_name | [optional string](#string) | Update the user-facing name for this value. |
| update_display_name | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
|  **optional** description | [optional string](#string) | Update the description for this enum value. |
| update_description | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
|  **optional** color | [optional string](#string) | Update the color for this enum value. |
| update_color | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
|  **optional** priority | [optional uint32](#uint32) | Update the priority, which is used to sort the enum values. |
| update_priority | [ hiber.UpdateZeroableInt](#hiberupdatezeroableint) | <strong>Deprecated.</strong>  |

### UpdateFieldNumericDetails



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** replace_unit | [optional Field.Numeric.Unit](#fieldnumericunit) | Replace the unit for this field. Automatically replaces the type and the symbol based on the unit. |
|  **optional** replace_format | [optional Field.Numeric.Format](#fieldnumericformat) | Replace the formatting for this field. The entire object must be configured. |
|  **optional** replace_unit_of_measurement | [optional hiber.UnitOfMeasurement](#hiberunitofmeasurement) | <strong>Deprecated.</strong> Replace the unit for this field. Automatically replaces the type and the symbol based on the unit. Deprecated: use replace_unit instead |

### UpdateFieldNumericDetails.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| field_identifier | [ string](#string) | The identifier for the field. |
| update | [ UpdateFieldNumericDetails](#updatefieldnumericdetails) |  |

### UpdateFieldRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| field_identifier | [ string](#string) | The identifier for the field. |
|  **optional** display_name | [optional string](#string) | An optional display name for the field. |
|  **optional** deprecated_display_name | [optional hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
|  **optional** priority | [optional uint32](#uint32) | Priority of the field, typically used for ordering. |
|  **optional** deprecated_priority | [optional hiber.UpdateZeroableInt](#hiberupdatezeroableint) | <strong>Deprecated.</strong>  |
|  **optional** encrypted | [optional bool](#bool) | Whether this field should be stored encrypted or not. When set to true at a later point, earlier values are not encrypted retro-actively. |
|  **optional** deprecated_encrypted | [optional hiber.UpdateBoolean](#hiberupdateboolean) | <strong>Deprecated.</strong>  |
|  **optional** optional | [optional bool](#bool) | Whether this field is optional or not. |
|  **optional** deprecated_optional | [optional hiber.UpdateBoolean](#hiberupdateboolean) | <strong>Deprecated.</strong>  |
|  **optional** operational | [optional bool](#bool) | If the field is used by operations and does not produce process values. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **update_details**.numeric | [ UpdateFieldNumericDetails](#updatefieldnumericdetails) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **update_details**.enum | [ UpdateFieldEnumValues](#updatefieldenumvalues) |  |


## Enums
### ListFields.Sort


| Name | Description | Number |
| ---- | ----------- | ------ |
| PARSER_PRIORITY | Sort by parser and priority in the parser. | 0 |
| DISPLAY_NAME | Sort by display_name. | 1 |
| FIELD_PATH | Sort by json path only. | 2 |



## Referenced messages from asset.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [asset.proto](https://github.com/HiberGlobal/api/blob/master/asset.proto).


### hiber.asset.Asset

Assets are things that collect the data produced by devices.
Devices are assigned to assets to handle data ownership.
When a device is replaced, the data flow for the asset continues with the data from the new device.
Multiple devices can be assigned to an asset, though it is advisable to only do so when they send
different type of data (i.e. one sensor for pressure and one for flow).

For example, if you have a Well, you might have assets for Annulus A and the tubing head.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) |  |
| name | [ string](#string) | Name of the asset |
|  **optional** type | [optional hiber.asset.Asset.Type](#hiberassetassettype) | Type of the asset, if any of the predefined types applies. |
|  **optional** description | [optional string](#string) | Longer detailed description of the asset. |
|  **optional** notes | [optional string](#string) | Multiline notes field that can be used to add additional information to an asset. |
|  **optional** time_zone | [optional string](#string) | Optional time zone for the asset. This can, for example, be used to calculate SLAs on a daily basis, adjusted by time zone. |
|  **optional** expected_transmission_rate | [optional hiber.value.Value.Numeric.Rate](#hibervaluevaluenumericrate) | The expected transmission rate for this asset. |
| metadata | [ google.protobuf.Struct](#googleprotobufstruct) | Metadata for the asset. This can be automatically populated from linked devices or manually added. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) | Tags assigned to this asset |
| devices | [repeated hiber.asset.Asset.AssignedDevice](#hiberassetassetassigneddevice) | Devices assigned to this asset |
| inactive_devices | [repeated hiber.asset.Asset.AssignedDevice](#hiberassetassetassigneddevice) | Devices that were assigned to this asset in the past |
| organization | [ string](#string) | The organization that owns this asset. Typically only relevant if child organizations are included. |

### hiber.asset.Asset.AssignedDevice

A device assigned to this asset.
Non-operational values that the device produces will be linked to this asset
(i.e. pressure, but not battery level).

| Field | Type | Description |
| ----- | ---- | ----------- |
| number | [ string](#string) |  |
| identifiers | [repeated string](#string) |  |
|  **optional** name | [optional string](#string) |  |
|  **optional** type | [optional string](#string) |  |
|  **optional** last_message_sent_at | [optional hiber.Timestamp](#hibertimestamp) |  |
|  **optional** last_message_received_at | [optional hiber.Timestamp](#hibertimestamp) |  |
|  **optional** assignment_time_range | [optional hiber.TimeRange](#hibertimerange) |  |
|  **optional** health | [optional hiber.health.HealthLevel](#hiberhealthhealthlevel) |  |
| numeric_value_types | [repeated hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype) |  |

### hiber.asset.AssetSelection

Selection object for assets.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifiers | [repeated string](#string) | Select assets by identifier. |
| search | [repeated string](#string) | Search assets by (partial, case insensitive) identifier, name, description, notes and time zone. |
| types | [repeated hiber.asset.Asset.Type](#hiberassetassettype) | Select assets by type. |
|  **optional** filter_by_tags | [optional hiber.tag.TagSelection](#hibertagtagselection) | Select assets by tags |


### Enums
#### hiber.asset.Asset.Type
Predefined assets types that can be used to say something about the data.
Currently a limited list, but more may be added in the future.

| Name | Description | Number |
| ---- | ----------- | ------ |
| UNKNOWN |  | 0 |
| WELL_ANNULUS_A |  | 1 |
| WELL_ANNULUS_B |  | 2 |
| WELL_ANNULUS_C |  | 3 |
| WELL_ANNULUS_D |  | 4 |
| WELL_HEAD |  | 15 |
| WELL_TUBING_HEAD |  | 5 |
| WELL_TUBING |  | 6 |
| WELL_FLOW_LINE |  | 7 |
| WELL_CASING |  | 8 |
| WELL_PRODUCTION_CASING_PRESSURE |  | 9 |
| WELL_INTERMITTENT_CASING_PRESSURE |  | 10 |
| PIPELINE |  | 11 |
| PRODUCTION_LINE |  | 12 |
| GAS_MANIFOLD |  | 13 |
| PRODUCTION_MANIFOLD |  | 14 |



## Referenced messages from field.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [field.proto](https://github.com/HiberGlobal/api/blob/master/field.proto).


### hiber.field.Field



| Field | Type | Description |
| ----- | ---- | ----------- |
| identifier | [ string](#string) | Unique identifier for this field. |
| field | [ string](#string) | The name of the field (if in the root structure) or a JsonPath to the field. |
|  **optional** display_name | [optional string](#string) | An optional display name for the field. |
| priority | [ int32](#int32) | Priority of the field, typically used for ordering. |
| type | [ hiber.value.Value.Type](#hibervaluevaluetype) | The type of value the field contains. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **details**.numeric | [ hiber.field.Field.Numeric](#hiberfieldfieldnumeric) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **details**.enum | [ hiber.field.Field.Enum](#hiberfieldfieldenum) |  |
| encrypted | [ bool](#bool) | Whether this field should be stored encrypted or not. If it is, some processing options may be unavailable or slower. |
| optional | [ bool](#bool) | Whether this field should be validated from the parser output. |
| operational | [ bool](#bool) | Field contains values relevant for operating the device. |
|  **optional** unit_of_measurement | [optional hiber.UnitOfMeasurement](#hiberunitofmeasurement) | <strong>Deprecated.</strong> If numeric, the unit of the field. Deprecated: use numeric.numeric_unit oneof instead |
|  **optional** unit_symbol | [optional string](#string) | <strong>Deprecated.</strong> The symbol for the unit. Deprecated: use numeric.symbol instead |

### hiber.field.Field.Enum

If the field is an enum, this specifies the enum values for the field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| values | [repeated hiber.value.Value.Enum](#hibervaluevalueenum) |  |

### hiber.field.Field.Numeric

If the field is numeric, this specifies the unit and formatting details for the field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype) | The type of numeric value. |
| symbol | [ string](#string) | The symbol to use for the field's unit. |
| format | [ hiber.field.Field.Numeric.Format](#hiberfieldfieldnumericformat) | How to format the values (number of decimals, rounding, etc.). |
| unit | [ hiber.field.Field.Numeric.Unit](#hiberfieldfieldnumericunit) | The unit for the field, depending on the type. |
|  **optional** converted_from | [optional hiber.field.Field.Numeric.Unit](#hiberfieldfieldnumericunit) | If the unit preferences were applied, and the unit is different, the field will be converted to the preferred unit, from the original unit specified in this field. |

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
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.battery_level | [ hiber.value.Value.Numeric.BatteryLevel.BatteryLevelUnit](#hibervaluevaluenumericbatterylevelbatterylevelunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.distance | [ hiber.value.Value.Numeric.Distance.DistanceUnit](#hibervaluevaluenumericdistancedistanceunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.duration | [ hiber.value.Value.Numeric.Duration.DurationUnit](#hibervaluevaluenumericdurationdurationunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.fuel_efficiency | [ hiber.value.Value.Numeric.FuelEfficiency.FuelEfficiencyUnit](#hibervaluevaluenumericfuelefficiencyfuelefficiencyunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.flow | [ hiber.value.Value.Numeric.Flow.FlowUnit](#hibervaluevaluenumericflowflowunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.percentage | [ hiber.value.Value.Numeric.Percentage.PercentageUnit](#hibervaluevaluenumericpercentagepercentageunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.pressure | [ hiber.value.Value.Numeric.Pressure.PressureUnit](#hibervaluevaluenumericpressurepressureunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.speed | [ hiber.value.Value.Numeric.Speed.SpeedUnit](#hibervaluevaluenumericspeedspeedunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.temperature | [ hiber.value.Value.Numeric.Temperature.TemperatureUnit](#hibervaluevaluenumerictemperaturetemperatureunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.voltage | [ hiber.value.Value.Numeric.Voltage.VoltageUnit](#hibervaluevaluenumericvoltagevoltageunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.volume | [ hiber.value.Value.Numeric.Volume.VolumeUnit](#hibervaluevaluenumericvolumevolumeunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.mass | [ hiber.value.Value.Numeric.Mass.MassUnit](#hibervaluevaluenumericmassmassunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.rotation_speed | [ hiber.value.Value.Numeric.RotationSpeed.RotationSpeedUnit](#hibervaluevaluenumericrotationspeedrotationspeedunit) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **unit**.rate | [ hiber.value.Value.Numeric.Rate.RateUnit](#hibervaluevaluenumericraterateunit) |  |


### Enums
#### hiber.field.Field.Numeric.Format.RoundingMode
How to round the value when scale is applied.
For example, a value of 3.1415 with scale 3 could be
  4.141 (DOWN, HALF_DOWN, FLOOR) or
  4.142 (HALF_UP, UP, CEILING).

| Name | Description | Number |
| ---- | ----------- | ------ |
| HALF_UP | Round towards nearest neighbor unless both neighbors are equidistant, in which case round up Effectively round up when >= .5, otherwise round down. | 0 |
| HALF_DOWN | Round towards nearest neighbor unless both neighbors are equidistant, in which case round down. Effectively round up when > .5, otherwise round down. | 1 |
| UP | Round away from zero: 1.1 -> 2, while -1.1 -> -2. | 3 |
| DOWN | Round towards zero: 1.1 -> 1, while -1.1 -> -1. | 4 |
| CEILING | Round towards positive infinity. | 5 |
| FLOOR | Round towards negative infinity. | 6 |
| HALF_EVEN | Round towards the nearest neighbor unless both neighbors are equidistant, in which case, round towards the even neighbor. Effectively round up when >= .5 and next integer value is even, otherwise round down. | 7 |



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
| organization | [ string](#string) |  |
| name | [ string](#string) | An optional descriptor given to the modem |
| location | [ hiber.Location](#hiberlocation) |  |
| last_message_id | [ uint64](#uint64) |  |
| last_message_received_at | [ hiber.Timestamp](#hibertimestamp) | Time the server has received the last message. |
| last_message_sent_at | [ hiber.Timestamp](#hibertimestamp) | Time the modem has sent the last message. |
| last_message_body | [ hiber.BytesOrHex](#hiberbytesorhex) | The body of the last message. |
| inactivity | [ hiber.Duration](#hiberduration) | The amount of time since the last message from this modem was received on the server. |
| health_level | [ hiber.health.HealthLevel](#hiberhealthhealthlevel) | Health level based on the modem alarm and some always-present alarms. |
| lifecycle | [ hiber.modem.Modem.Lifecycle](#hibermodemmodemlifecycle) |  |
| technical | [ hiber.modem.Modem.TechnicalData](#hibermodemmodemtechnicaldata) | additional information |
| peripherals | [ hiber.modem.Modem.Peripherals](#hibermodemmodemperipherals) |  |
| notes | [ string](#string) | Notes field that can be used to add additional information to a modem. |
| secure_notes | [ string](#string) | Secure notes field that can be used to add additional information to a modem, with limited accessibility. |
| tags | [repeated hiber.tag.Tag](#hibertagtag) |  |
| is_gateway | [ bool](#bool) | <strong>Deprecated.</strong> [DEPRECATED] Whether the modem is a gateway, it has been configured as a gateway and has connected devices. Use `type` instead. |
| is_device_connected_to_gateway | [ bool](#bool) | <strong>Deprecated.</strong> [DEPRECATED] Whether the modem is connected to a modem configured as a gateway. Use `type` instead. |
| connected_to_gateway | [ string](#string) | <strong>Deprecated.</strong> [DEPRECATED] The modem number that this modem is connected to, if any. Use `connected_device_info.connected_to_gateway` instead. |
| external_device_ids | [repeated string](#string) | <strong>Deprecated.</strong> [DEPRECATED] External device ids, if any. Use `connected_device_info.external_device_ids` instead. |
| type | [ hiber.modem.Modem.Type](#hibermodemmodemtype) | The type of modem. Used mainly to differentiate in the UI or to sort on. |
| gateway_info | [ hiber.modem.Modem.GatewayInfo](#hibermodemmodemgatewayinfo) | Additional information when this modem is a gateway. |
| connected_device_info | [ hiber.modem.Modem.ConnectedDeviceInfo](#hibermodemmodemconnecteddeviceinfo) | Additional information when this modem is a connected device. |
| metadata | [ google.protobuf.Struct](#googleprotobufstruct) | Modem metadata, typically extracted from messages. |
| time_zone | [ string](#string) | The timezone configured for the modem. |
| transmission_interval | [ hiber.Duration](#hiberduration) | The transmission interval for this modem, if configured. |
|  **optional** expected_transmission_rate | [optional hiber.value.Value.Numeric.Rate](#hibervaluevaluenumericrate) | The expected transmission rate for this modem. |
| numeric_value_types | [repeated hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype) | The numeric value types that this device produces. The device may produce other values (like battery level), but these are the primary value types. |

### hiber.modem.ModemSelection

Selection object for modems.
Filter modems by modem id, (child)organization, tags, activation status and time, service type and last message time.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** modems | [optional hiber.Filter.Modems](#hiberfiltermodems) |  |
|  **optional** free_text_search | [optional string](#string) |  |
|  **optional** only_active | [optional bool](#bool) | <strong>Deprecated.</strong> Use lifecycle filter instead. |
|  **optional** activated_in | [optional hiber.TimeRange](#hibertimerange) | <strong>Deprecated.</strong>  |
|  **optional** with_last_message_in | [optional hiber.TimeRange](#hibertimerange) |  |
| health_levels | [repeated string](#string) | Filter modems by health level. |
| lifecycles | [repeated hiber.modem.Modem.Lifecycle](#hibermodemmodemlifecycle) | Filter modems by lifecycle(s). Defaults to nominal lifecycles, excluding disabled or decommissioned modems. |
|  **optional** transfers | [optional hiber.modem.ModemSelection.Transfers](#hibermodemmodemselectiontransfers) |  |
| include_types | [repeated hiber.modem.Modem.Type](#hibermodemmodemtype) | Only include modems that have a type listed in types. In other words, when providing multiple types, this is an "OR" relationship. |
| exclude_types | [repeated hiber.modem.Modem.Type](#hibermodemmodemtype) | Exclude modems that have a type listed in types. |
|  **optional** device_types | [optional hiber.Filter.DeviceTypes](#hiberfilterdevicetypes) |  |
|  **optional** sensorBrands | [optional hiber.Filter.SensorBrands](#hiberfiltersensorbrands) |  |
|  **optional** identifiers | [optional hiber.Filter.ModemIdentifiers](#hiberfiltermodemidentifiers) |  |
|  **optional** only_gateways | [optional bool](#bool) | <strong>Deprecated.</strong> [DEPRECATED] Only list devices that are a gateway. Replaced by `types`. If you only want to have gateways in the result, create a selection with only `Modem.Type.GATEWAY` for `types`. |
|  **optional** only_has_external_device_ids | [optional bool](#bool) | <strong>Deprecated.</strong> [DEPRECATED] Only list devices that are a connected devices. Typically these are LoRaWAN sensors. Replaced by `types`. If you only want to have connected devices in the result, create a selection with only `Modem.Type.CONNECTED_DEVICE` for `types`. |
|  **optional** connected_to_gateways | [optional hiber.Filter.Modems](#hiberfiltermodems) |  |
| external_device_ids | [repeated string](#string) | <strong>Deprecated.</strong>  |
|  **optional** filter_by_tags | [optional hiber.tag.TagSelection](#hibertagtagselection) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **peripheral_selection**.peripherals | [ hiber.modem.ModemSelection.Peripherals](#hibermodemmodemselectionperipherals) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **peripheral_selection**.only_without_peripheral | [ bool](#bool) | When set to true, only modems that do not have any peripheral will be included in the result. |
|  **optional** only_connected_to_gateway | [optional bool](#bool) | Only select modems that are connected to a gateway (connected devices). |
|  **optional** not_connected_to_gateway | [optional bool](#bool) | Only select modems that are not connected to a gateway (i.e. gateways). |


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
| SENSOR_BRAND_ASC | Sort alphabetically on the brand of the sensor, in ascending order. | 16 |
| SENSOR_BRAND_DESC | Sort alphabetically on the brand of the sensor, in descending order. | 17 |
| DEVICE_TYPE_ASC | Sort alphabetically on the device type, in ascending order. | 18 |
| DEVICE_TYPE_DESC | Sort alphabetically on the device type, in descending order. | 19 |
| TAG_TYPE_WELL_ASC | Sort alphabetically on any tags of type 'well', in ascending order. | 20 |
| TAG_TYPE_WELL_DESC | Sort alphabetically on any tags of type 'well', in descending order. | 21 |
| TAG_TYPE_SITE_ASC | Sort alphabetically on any tags of type 'site', in ascending order. | 22 |
| TAG_TYPE_SITE_DESC | Sort alphabetically on any tags of type 'site', in descending order. | 23 |
| TAG_TYPE_PRODUCTION_AREA_ASC | Sort alphabetically on any tags of type 'production_area', in ascending order. | 24 |
| TAG_TYPE_PRODUCTION_AREA_DESC | Sort alphabetically on any tags of type 'production_area', in descending order. | 25 |

#### hiber.modem.Modem.Lifecycle


| Name | Description | Number |
| ---- | ----------- | ------ |
| ACCEPTANCE_TESTING | Device is being tested by Hiber. Devices in this state are not visible to customers. | 0 |
| READY_TO_INSTALL | Device has passed Acceptance Testing and is ready be installed. When it sends it first message, it will automatically go to INSTALLED. Devices in this state are not visible to customers. | 8 |
| INSTALLED | Device is active and sending messages. | 1 |
| PAUSED | Device is paused and not sending messages. This should be of a temporary nature (e.g. a change to the installation is being made). On its next message, it will automatically go back to INSTALLED. Offline alarm checks will not be triggered for devices in this lifecycle. | 6 |
| DISABLED | Device is disabled and not sending messages. This is a more permanent version of PAUSED. Devices in this state are not visible to customers. | 5 |
| DECOMMISSIONED | Device is (going to be) removed from installation and will not return to installed status again. Devices in this state are not visible to customers. | 4 |
| DEFECTIVE | Device is defective and should not be used anymore. Devices in this state are typically RMA-ed and (should be) transferred to the RMA organization. Devices in this state are not visible to customers. | 7 |
| SPARE | Spare device sent to customer in case it is needed. | 9 |

#### hiber.modem.Modem.Type
The effective type of this modem.
Type can depend on the hardware itself as well as network topology.

| Name | Description | Number |
| ---- | ----------- | ------ |
| OTHER | A device of which the specific type is not known | 0 |
| DISCONNECTED_SENSOR | A device that is not currently connected to a gateway. | 1 |
| GATEWAY | A device that can receive messages from sensors in the field and relay them (directly) to the satellite. Typically a LoRaWAN hub. Note that gateways also send messages themselves (e.g. a daily heartbeat). | 2 |
| SENSOR | A sensor that can (only) send data to a gateway. Typically using a LoRaWAN connection. | 3 |

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
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| assign_parsers | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) |  |
| to_modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) |  |

### hiber.modem.message.bodyparser.AssignModemMessageBodyParsers.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| created | [repeated hiber.modem.message.bodyparser.AssignedModemMessageBodyParser](#hibermodemmessagebodyparserassignedmodemmessagebodyparser) |  |
| request | [ hiber.modem.message.bodyparser.AssignModemMessageBodyParsers.Request](#hibermodemmessagebodyparserassignmodemmessagebodyparsersrequest) |  |

### hiber.modem.message.bodyparser.AssignedModemMessageBodyParser

Directly assigned modem message parser to a modem.

| Field | Type | Description |
| ----- | ---- | ----------- |
| parser_identifier | [ string](#string) |  |
| modem_number | [ string](#string) |  |

### hiber.modem.message.bodyparser.CreateSimpleModemMessageBodyParserRequest

Create a simple modem message parser, which generates a .ksy specification.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| parser | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser](#hibermodemmessagebodyparsersimplemodemmessagebodyparser) |  |

### hiber.modem.message.bodyparser.DeleteModemMessageBodyParserRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| selection | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) | A selection of parsers to be deleted. |

### hiber.modem.message.bodyparser.DeleteModemMessageBodyParserRequest.Response




### hiber.modem.message.bodyparser.ListModemMessageBodyParsersRequest

List the parser your organizations has access to. This may include inherited parsers.

If include_content is not set, this call may omit parser specifications, like the ksy, since those are
typically larger multi-line strings.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
|  **optional** selection | [optional hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) | Select the parsers to list. Optional, when omitted or empty everything is included. |
|  **optional** pagination | [optional hiber.Pagination](#hiberpagination) |  |
|  **optional** exclude_content | [optional bool](#bool) | Whether to omit the content in the resulting ModemMessageBodyParsers. |

### hiber.modem.message.bodyparser.ListModemMessageBodyParsersRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| parsers | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser](#hibermodemmessagebodyparsermodemmessagebodyparser) |  |
| pagination | [ hiber.Pagination.Result](#hiberpaginationresult) |  |
| request | [ hiber.modem.message.bodyparser.ListModemMessageBodyParsersRequest](#hibermodemmessagebodyparserlistmodemmessagebodyparsersrequest) |  |

### hiber.modem.message.bodyparser.MakeModemMessageBodyParserAvailableToChildOrganizationRequest

Make this parser available to a specific child organizations.

This will
- when the organization is on the exclude list, remove it
- when the includeAll flag is false, add it to the include list (if not already present)

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the parser that should be updated. |
| available_to | [repeated string](#string) | The child organization(s) that the parser should be available to. |

### hiber.modem.message.bodyparser.MakeModemMessageBodyParserUnavailableToChildOrganizationRequest

Make this parser unavailable to a specific child organizations.

This will
- when the organization is on the include list, remove it
- when the includeAll flag is true, add it to the exclude list (if not already present)

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
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
| metadata_fields | [ hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafields) | Fields in the parsed result that contain metadata, and special things like a location. |
| available_to_child_organizations | [ hiber.modem.message.bodyparser.ModemMessageBodyParser.AvailableToChildOrganizations](#hibermodemmessagebodyparsermodemmessagebodyparseravailabletochildorganizations) | If set, this parser is available to your child organizations, as a Provided parser. |
| post_processing | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser.PostProcessing](#hibermodemmessagebodyparsermodemmessagebodyparserpostprocessing) | <strong>Deprecated.</strong> The list of post-processing steps applied to the result of this parser. |
| require_message_metadata | [map hiber.modem.message.bodyparser.ModemMessageBodyParser.RequireMessageMetadataEntry](#hibermodemmessagebodyparsermodemmessagebodyparserrequiremessagemetadataentry) | <strong>Deprecated.</strong> In order to use this parser on a message, the metadata on the message must match the given requirement here. The key of the map is the json-path to look for in the message metadata, the value of the map is the json to expect at that json-path. Deprecated: use metadata_fields.require_message_metadata |

### hiber.modem.message.bodyparser.ModemMessageBodyParser.AvailableToChildOrganizations

A modem message body parser with this object is available to child organizations.
This means the child organization can use it, but not update or delete it.

| Field | Type | Description |
| ----- | ---- | ----------- |
| child_organizations | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) |  |

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
| require_message_metadata | [map hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields.RequireMessageMetadataEntry](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafieldsrequiremessagemetadataentry) | In order to use this parser on a message, the metadata on the message must match the given requirement here. The key of the map is the json-path to look for in the message metadata, the value of the map is the json to expect at that json-path. |

### hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields.LocationFields



| Field | Type | Description |
| ----- | ---- | ----------- |
| latitude | [ string](#string) |  |
| longitude | [ string](#string) |  |

### hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields.RequireMessageMetadataEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ google.protobuf.Value](#googleprotobufvalue) |  |

### hiber.modem.message.bodyparser.ModemMessageBodyParser.RequireMessageMetadataEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ google.protobuf.Value](#googleprotobufvalue) |  |

### hiber.modem.message.bodyparser.ModemMessageBodyParserSelection

Selection object for parsers. Used to select which parser to list, assign, etc.

| Field | Type | Description |
| ----- | ---- | ----------- |
| identifiers | [repeated string](#string) | Filter parsers by their identifiers. |
|  **optional** search | [optional string](#string) | Find parsers by searching for this text in the name, content_ksy, data fields or simple parser definition. |
|  **optional** only_simple | [optional bool](#bool) | Only return simple parsers, created using SimpleModemMessageBodyParser. |
|  **optional** only_ksy_file | [optional bool](#bool) | Only return parsers created from an uploaded .ksy file. |
|  **optional** only_owned_parsers | [optional bool](#bool) | Exclude parsers that are not owned by your organization (those that you did not create yourself). |
| owner_organizations | [repeated string](#string) | Only return parsers that were created by the given parent organizations. |
| has_data_fields | [repeated string](#string) | Only return parsers that have one of the given data fields This only works when the fields are marked explicitly using the data fields option. |

### hiber.modem.message.bodyparser.RenameModemMessageBodyParserRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the parser that should be updated. |
| name | [ string](#string) | The new name for this parser. |

### hiber.modem.message.bodyparser.RetryModemMessageBodyParsing

Retry a message, parsing it with all the currently assigned parsers that are in the given selection.
If the message was previously parsed by any of those parsers, the previous result is replaced.


### hiber.modem.message.bodyparser.RetryModemMessageBodyParsing.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| modem_message_ids | [repeated uint64](#uint64) | The messages to parse. |
| parser_selection | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) | A selection of parsers to apply, if they are assigned. |
| suppress_events | [ bool](#bool) | Re-parsing messages causes new events to be sent out. Set suppress_events to true to prevent that. |

### hiber.modem.message.bodyparser.RetryModemMessageBodyParsing.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| parsed_messages | [repeated hiber.modem.ModemMessage.ParsedBody](#hibermodemmodemmessageparsedbody) |  |

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
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.integer | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Integer](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfieldinteger) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.float | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Float](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfieldfloat) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.bytes | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Bytes](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfieldbytes) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.string | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.String](#hibermodemmessagebodyparsersimplemodemmessagebodyparserfieldstring) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.magic | [ bytes](#bytes) | Specify an expected magic sequence (some bytes that are always the same). |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **type**.custom_type | [ string](#string) | Specify a custom type name. |

### hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Field.Bytes



| Field | Type | Description |
| ----- | ---- | ----------- |
| size | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.DelimitedSize](#hibermodemmessagebodyparsersimplemodemmessagebodyparserdelimitedsize) |  |

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
| size | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.DelimitedSize](#hibermodemmessagebodyparsersimplemodemmessagebodyparserdelimitedsize) |  |
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
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **parser**.identifier | [ string](#string) | The identifier of the parser you want to test. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **parser**.content_ksy | [ string](#string) | A ksy definition you want to test. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **parser**.simple_parser | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser](#hibermodemmessagebodyparsersimplemodemmessagebodyparser) | A simple parser definition you want to test. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.parse_bytes | [ hiber.BytesOrHex](#hiberbytesorhex) | A byte array (message body) to parse. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **data**.modem_message_id | [ uint64](#uint64) | The id of an existing message, testing the parser on its body. |

### hiber.modem.message.bodyparser.TestModemMessageBodyParserRequest.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **result**.parsed | [ google.protobuf.Struct](#googleprotobufstruct) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **result**.error | [ string](#string) |  |

### hiber.modem.message.bodyparser.UnassignModemMessageBodyParsers

Remove a direct assignment.
If an overlapping assignment using a rule exists, it is not affected, except that it is longer shadowed.

Simplified version of assign.UnassignDirectly.


### hiber.modem.message.bodyparser.UnassignModemMessageBodyParsers.Request



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| unassign_parsers | [ hiber.modem.message.bodyparser.ModemMessageBodyParserSelection](#hibermodemmessagebodyparsermodemmessagebodyparserselection) |  |
| from_modems | [ hiber.modem.ModemSelection](#hibermodemmodemselection) |  |

### hiber.modem.message.bodyparser.UnassignModemMessageBodyParsers.Response



| Field | Type | Description |
| ----- | ---- | ----------- |
| removed_direct_assignments | [repeated hiber.modem.message.bodyparser.AssignedModemMessageBodyParser](#hibermodemmessagebodyparserassignedmodemmessagebodyparser) |  |
| request | [ hiber.modem.message.bodyparser.UnassignModemMessageBodyParsers.Request](#hibermodemmessagebodyparserunassignmodemmessagebodyparsersrequest) |  |

### hiber.modem.message.bodyparser.UpdateChildOrganizationAvailabilityRequest

Update the child availability for a parser.
Parsers can be made available to child organizations, which means that they can be viewed in,
and assigned to modems in, child organizations.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the parser that should be updated. |
| available_to_child_organizations | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) | The new child organization availability filter for this parser. |

### hiber.modem.message.bodyparser.UpdateSimpleModemMessageBodyParserRequest

Update a simple modem message parser, updating the generated .ksy specification.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the parser that should be updated. |
| parser | [ hiber.modem.message.bodyparser.SimpleModemMessageBodyParser](#hibermodemmessagebodyparsersimplemodemmessagebodyparser) |  |

### hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest

Upload an updated body parser from a .ksy file, replacing the previous file.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| identifier | [ string](#string) | The identifier of the parser that should be updated. |
|  **optional** name | [optional string](#string) | If set, changes the name of the parser. |
|  **optional** content_ksy | [optional string](#string) | The new ksy definition for this parser. |
| add_data_fields | [repeated hiber.field.Field](#hiberfieldfield) | Add fields to the data fields list. |
| remove_data_fields | [repeated string](#string) | Remove fields from the data fields list. |
|  **optional** metadata_fields | [optional hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields](#hibermodemmessagebodyparserupdateuploadedmodemmessagebodyparserrequestmetadatafields) | Fields in the parsed result that match special things that can be processed by the system, like a location. |
| add_post_processing | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser.PostProcessing](#hibermodemmessagebodyparsermodemmessagebodyparserpostprocessing) | <strong>Deprecated.</strong> Add a post-processing step to the result of this parser. |
| remove_post_processing | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser.PostProcessing](#hibermodemmessagebodyparsermodemmessagebodyparserpostprocessing) | <strong>Deprecated.</strong> Remove a post-processing step to the result of this parser. |

### hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** update_location_fields | [optional hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields.LocationFields](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafieldslocationfields) | Update the location fields. |
| add_message_metadata_fields | [repeated string](#string) | Add fields to the message metadata fields list. |
| remove_message_metadata_fields | [repeated string](#string) | Remove fields from the message metadata fields list. |
| replace_message_metadata_fields | [repeated string](#string) | Replace the message metadata fields list. |
| add_modem_metadata_fields | [repeated string](#string) | Add fields to the modem metadata fields list. |
| remove_modem_metadata_fields | [repeated string](#string) | Remove fields from the modem metadata fields list. |
| replace_modem_metadata_fields | [repeated string](#string) | Replace the modem metadata fields list. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **measured_at_field**.measured_at_time_field | [ string](#string) | Update the custom field to extract to measured_at time. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **measured_at_field**.deprecated_measured_at_time_field | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **measured_at_field**.measured_at_offset_field | [ string](#string) | Update the custom field to extract to measured_at offset from the sent_at time in seconds. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **measured_at_field**.deprecated_measured_at_offset_field | [ hiber.UpdateClearableString](#hiberupdateclearablestring) | <strong>Deprecated.</strong>  |
| add_require_message_metadata | [map hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields.AddRequireMessageMetadataEntry](#hibermodemmessagebodyparserupdateuploadedmodemmessagebodyparserrequestmetadatafieldsaddrequiremessagemetadataentry) | In order to use this parser on a message, the metadata on the message must match the given requirement here. The key of the map is the json-path to look for in the message metadata, the value of the map is the json to expect at that json-path. |
| remove_require_message_metadata | [repeated string](#string) | Remove a requirement for the metadata. Remove by listing the json-path here. |
| replace_require_message_metadata | [map hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields.ReplaceRequireMessageMetadataEntry](#hibermodemmessagebodyparserupdateuploadedmodemmessagebodyparserrequestmetadatafieldsreplacerequiremessagemetadataentry) | Replaces the entire configuration for required message metadata. |

### hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields.AddRequireMessageMetadataEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ google.protobuf.Value](#googleprotobufvalue) |  |

### hiber.modem.message.bodyparser.UpdateUploadedModemMessageBodyParserRequest.MetadataFields.ReplaceRequireMessageMetadataEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ google.protobuf.Value](#googleprotobufvalue) |  |

### hiber.modem.message.bodyparser.UploadModemMessageBodyParserRequest

Upload a new body parser from a .ksy file.

| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** organization | [optional string](#string) | Pick the organization to use (/impersonate). If unset, your default organization is used. |
| name | [ string](#string) | A descriptive name for this parser. |
| content_ksy | [ string](#string) | The ksy definition for this parser. |
| data_fields | [repeated hiber.field.Field](#hiberfieldfield) | Fields in the parsed result that contain data. This can be useful to track which fields could be plotted, etc. |
|  **optional** metadata_fields | [optional hiber.modem.message.bodyparser.ModemMessageBodyParser.MetadataFields](#hibermodemmessagebodyparsermodemmessagebodyparsermetadatafields) | Fields in the parsed result that match special things that can be processed by the system, like a location. |
| post_processing | [repeated hiber.modem.message.bodyparser.ModemMessageBodyParser.PostProcessing](#hibermodemmessagebodyparsermodemmessagebodyparserpostprocessing) |  |
| require_message_metadata | [map hiber.modem.message.bodyparser.UploadModemMessageBodyParserRequest.RequireMessageMetadataEntry](#hibermodemmessagebodyparseruploadmodemmessagebodyparserrequestrequiremessagemetadataentry) | In order to use this parser on a message, the metadata on the message must match the given requirement here. The key of the map is the json-path to look for in the message metadata, the value of the map is the json to expect at that json-path. |

### hiber.modem.message.bodyparser.UploadModemMessageBodyParserRequest.RequireMessageMetadataEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ google.protobuf.Value](#googleprotobufvalue) |  |


### Enums
#### hiber.modem.message.bodyparser.ModemMessageBodyParser.PostProcessing
The type of post-processing to be applied to the result of this parser.

| Name | Description | Number |
| ---- | ----------- | ------ |
| NOTHING |  | 0 |

#### hiber.modem.message.bodyparser.SimpleModemMessageBodyParser.Endian


| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT |  | 0 |
| LITTLE_ENDIAN |  | 1 |
| BIG_ENDIAN |  | 2 |



## Referenced messages from value.proto
(Note that these are included because there is a proto dependency on the file,
so not all messages listed here are referenced.)

#### This section was generated from [value.proto](https://github.com/HiberGlobal/api/blob/master/value.proto).


### hiber.value.Value



| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ hiber.value.Value.Type](#hibervaluevaluetype) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.numeric | [ hiber.value.Value.Numeric](#hibervaluevaluenumeric) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.text | [ string](#string) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **value**.enum | [ hiber.value.Value.Enum](#hibervaluevalueenum) |  |

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
| type | [ hiber.value.Value.Numeric.Type](#hibervaluevaluenumerictype) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.battery_level | [ hiber.value.Value.Numeric.BatteryLevel](#hibervaluevaluenumericbatterylevel) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.distance | [ hiber.value.Value.Numeric.Distance](#hibervaluevaluenumericdistance) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.duration | [ hiber.value.Value.Numeric.Duration](#hibervaluevaluenumericduration) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.fuel_efficiency | [ hiber.value.Value.Numeric.FuelEfficiency](#hibervaluevaluenumericfuelefficiency) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.percentage | [ hiber.value.Value.Numeric.Percentage](#hibervaluevaluenumericpercentage) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.pressure | [ hiber.value.Value.Numeric.Pressure](#hibervaluevaluenumericpressure) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.speed | [ hiber.value.Value.Numeric.Speed](#hibervaluevaluenumericspeed) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.temperature | [ hiber.value.Value.Numeric.Temperature](#hibervaluevaluenumerictemperature) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.voltage | [ hiber.value.Value.Numeric.Voltage](#hibervaluevaluenumericvoltage) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.volume | [ hiber.value.Value.Numeric.Volume](#hibervaluevaluenumericvolume) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.mass | [ hiber.value.Value.Numeric.Mass](#hibervaluevaluenumericmass) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.flow | [ hiber.value.Value.Numeric.Flow](#hibervaluevaluenumericflow) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.rotation_speed | [ hiber.value.Value.Numeric.RotationSpeed](#hibervaluevaluenumericrotationspeed) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.rate | [ hiber.value.Value.Numeric.Rate](#hibervaluevaluenumericrate) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **typed_value**.unknown | [ double](#double) |  |
| value | [ double](#double) |  |
| textual | [ string](#string) | Textual representation including unit symbol, rounded based on the user preferences and field config. |
| unit | [ hiber.UnitOfMeasurement](#hiberunitofmeasurement) | Unit of the value, based on the user preferences. |
| unit_symbol | [ string](#string) | Display string of the unit symbol, based on the unit of the value (which is based on user preferences). |
|  **optional** converted_from | [optional hiber.UnitOfMeasurement](#hiberunitofmeasurement) | The original unit, iff this value was converted from another unit because of user preferences. |

### hiber.value.Value.Numeric.BatteryLevel

Special case for battery level, since it can be provided in many units.
Not included in the UnitPreferences, since it cannot be converted.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.BatteryLevel.BatteryLevelUnit](#hibervaluevaluenumericbatterylevelbatterylevelunit) |  |

### hiber.value.Value.Numeric.Distance

The value is a distance value, converted to your preferred distance unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.Distance.DistanceUnit](#hibervaluevaluenumericdistancedistanceunit) |  |

### hiber.value.Value.Numeric.Duration



| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.Duration.DurationUnit](#hibervaluevaluenumericdurationdurationunit) |  |
| duration | [ google.protobuf.Duration](#googleprotobufduration) |  |

### hiber.value.Value.Numeric.Flow



| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.Flow.FlowUnit](#hibervaluevaluenumericflowflowunit) |  |

### hiber.value.Value.Numeric.FuelEfficiency

The value is a distance value, converted to your preferred distance unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.FuelEfficiency.FuelEfficiencyUnit](#hibervaluevaluenumericfuelefficiencyfuelefficiencyunit) |  |

### hiber.value.Value.Numeric.Mass

The value is a volume value, converted to your preferred volume unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.Mass.MassUnit](#hibervaluevaluenumericmassmassunit) |  |

### hiber.value.Value.Numeric.Percentage

The value is a percentage.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.Percentage.PercentageUnit](#hibervaluevaluenumericpercentagepercentageunit) |  |

### hiber.value.Value.Numeric.Pressure

The value is a pressure value, converted to your preferred pressure unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.Pressure.PressureUnit](#hibervaluevaluenumericpressurepressureunit) |  |

### hiber.value.Value.Numeric.Rate



| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.Rate.RateUnit](#hibervaluevaluenumericraterateunit) |  |
| value | [ uint32](#uint32) |  |

### hiber.value.Value.Numeric.RotationSpeed

The value for rotation speed. The only value is revolutions per minute (RPM), therefore it is not included in
unit preferences.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.RotationSpeed.RotationSpeedUnit](#hibervaluevaluenumericrotationspeedrotationspeedunit) |  |

### hiber.value.Value.Numeric.Speed

The value is a speed value, converted to your preferred speed unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.Speed.SpeedUnit](#hibervaluevaluenumericspeedspeedunit) |  |

### hiber.value.Value.Numeric.Temperature

The value is a temperature, converted to your preferred temperature unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.Temperature.TemperatureUnit](#hibervaluevaluenumerictemperaturetemperatureunit) |  |

### hiber.value.Value.Numeric.Voltage

The value is a voltage, converted to your preferred voltage unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.Voltage.VoltageUnit](#hibervaluevaluenumericvoltagevoltageunit) |  |

### hiber.value.Value.Numeric.Volume

The value is a volume value, converted to your preferred volume unit.

| Field | Type | Description |
| ----- | ---- | ----------- |
| unit | [ hiber.value.Value.Numeric.Volume.VolumeUnit](#hibervaluevaluenumericvolumevolumeunit) |  |


### Enums
#### hiber.value.Value.Numeric.BatteryLevel.BatteryLevelUnit
Convenience type for battery level. Other units may be added here later, like voltage.

| Name | Description | Number |
| ---- | ----------- | ------ |
| PERCENT | Battery level as a percentage (technically not a unit). | 0 |

#### hiber.value.Value.Numeric.Distance.DistanceUnit
Unit of distance

| Name | Description | Number |
| ---- | ----------- | ------ |
| METER | m | 0 |
| MILLIMETER | mm | 1 |
| CENTIMETER | cm | 2 |
| KILOMETER | km | 3 |
| YARD | yd | 5 |
| MILE | mi | 4 |
| FOOT | ' | 6 |
| INCH | ″ | 7 |
| NAUTICAL_MILE | NM. This is a special case unit and may not be auto-converted to your UnitPreference. | 8 |

#### hiber.value.Value.Numeric.Duration.DurationUnit
Unit of duration.

| Name | Description | Number |
| ---- | ----------- | ------ |
| MILLISECONDS | ms | 0 |
| SECONDS | s | 1 |
| MINUTES | min | 2 |
| HOURS | h | 3 |
| DAYS | d | 4 |
| WEEKS | w | 5 |

#### hiber.value.Value.Numeric.Flow.FlowUnit
Unit of volume per time.

| Name | Description | Number |
| ---- | ----------- | ------ |
| CUBIC_METER_PER_HOUR | m³/h | 0 |
| BARRELS_PER_DAY | bbl/d | 1 |
| CUBIC_METER_PER_SECOND | m³/s | 2 |
| CUBIC_FEET_PER_HOUR | ft³/h | 3 |
| CUBIC_FEET_PER_SECOND | ft³/s | 4 |
| LITER_PER_HOUR | l/h | 5 |
| LITER_PER_SECOND | l/s | 6 |

#### hiber.value.Value.Numeric.FuelEfficiency.FuelEfficiencyUnit
Unit of fuel efficiency

| Name | Description | Number |
| ---- | ----------- | ------ |
| LITER_PER_100_KILOMETER | l/100km | 0 |
| KILOMETER_PER_LITER | km/l | 1 |
| KILOMETER_PER_GALLON | km/gal (US) | 2 |
| KILOMETER_PER_IMPERIAL_GALLON | km/gal (imp) | 3 |
| MILES_PER_GALLON | mpg (US) | 4 |
| MILES_PER_IMPERIAL_GALLON | mpg (imp) | 5 |
| MILES_PER_LITER | mpl | 6 |

#### hiber.value.Value.Numeric.Mass.MassUnit
Unit of mass.

| Name | Description | Number |
| ---- | ----------- | ------ |
| KILOGRAMS | kg | 0 |
| POUNDS | lb | 1 |

#### hiber.value.Value.Numeric.Percentage.PercentageUnit
Convenience type for percentage. Technically not a unit, but for consistency, we've added it here.

| Name | Description | Number |
| ---- | ----------- | ------ |
| PERCENT | % | 0 |

#### hiber.value.Value.Numeric.Pressure.PressureUnit
Unit of pressure.

| Name | Description | Number |
| ---- | ----------- | ------ |
| BAR | bar | 0 |
| PSI | psi | 1 |
| K_PA | kPa | 2 |
| KILOGRAM_PER_CENTIMETER_SQUARED | kg/cm² | 3 |

#### hiber.value.Value.Numeric.Rate.RateUnit


| Name | Description | Number |
| ---- | ----------- | ------ |
| ITEMS_PER_24_HOURS | The amount of items counted in a 24 hour window. | 0 |

#### hiber.value.Value.Numeric.RotationSpeed.RotationSpeedUnit


| Name | Description | Number |
| ---- | ----------- | ------ |
| REVOLUTIONS_PER_MINUTE | rpm | 0 |

#### hiber.value.Value.Numeric.Speed.SpeedUnit
Unit of speed.

| Name | Description | Number |
| ---- | ----------- | ------ |
| KILOMETERS_PER_HOUR | km/h | 0 |
| KNOTS | kn. This is a special case unit and may not be auto-converted to your UnitPreference. | 1 |
| METERS_PER_SECOND | m/s | 2 |
| MILES_PER_HOUR | mph | 3 |
| FEET_PER_SECOND | ft/s | 4 |

#### hiber.value.Value.Numeric.Temperature.TemperatureUnit
Unit of temperature.

| Name | Description | Number |
| ---- | ----------- | ------ |
| KELVIN | K | 0 |
| DEGREES_CELSIUS | °C | 1 |
| DEGREES_FAHRENHEIT | °F | 2 |

#### hiber.value.Value.Numeric.Type
The type of numeric value that is represented.
Supported types will automatically convert to the preferred unit (based on the user settings).

| Name | Description | Number |
| ---- | ----------- | ------ |
| TYPE_UNKNOWN |  | 0 |
| PERCENTAGE |  | 1 |
| TEMPERATURE |  | 2 |
| DISTANCE |  | 3 |
| PRESSURE |  | 4 |
| VOLTAGE |  | 5 |
| SPEED |  | 6 |
| VOLUME |  | 7 |
| DURATION |  | 8 |
| FUEL_EFFICIENCY |  | 9 |
| MASS |  | 10 |
| BATTERY_LEVEL |  | 11 |
| FLOW |  | 12 |
| ROTATION_SPEED |  | 13 |
| RATE |  | 14 |

#### hiber.value.Value.Numeric.Voltage.VoltageUnit
Unit of voltage.

| Name | Description | Number |
| ---- | ----------- | ------ |
| MILLIVOLT | mV | 0 |

#### hiber.value.Value.Numeric.Volume.VolumeUnit
Unit of volume.

| Name | Description | Number |
| ---- | ----------- | ------ |
| LITER | l | 0 |
| GALLON_US | gal (US) | 1 |
| GALLON_IMPERIAL | gal (imp) | 2 |
| CUBIC_METER | m³ | 3 |
| CUBIC_FEET | ft³ | 4 |

#### hiber.value.Value.Type
The type of value that is represented.

| Name | Description | Number |
| ---- | ----------- | ------ |
| OTHER |  | 0 |
| NUMERIC | This field contains numeric values, with an optional unit of measurement defined below. | 1 |
| TEXT | This field contains text to be displayed. | 2 |
| ENUM | This field switches between several predefined values. Typically used for status fields. | 3 |

#### hiber.value.ValueAggregation
Get an aggregated value for the selected data (e.g. average).
Text fields can only use the LAST aggregation.
Enum fields support a subset of aggregations:
  - DEFAULT and LAST return the last value;
  - MINIMUM and MAXIMUM return the lowest or highest value (respectively) based on the enum value order;
  - AVERAGE and SUM are not supported.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT |  | 0 |
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
| center | [ hiber.Location](#hiberlocation) |  |
| bottom_left | [ hiber.Location](#hiberlocation) |  |
| top_right | [ hiber.Location](#hiberlocation) |  |
|  **optional** textual | [optional string](#string) | Text representation. Can be used as an alternative input in a request, filled in by the API in responses. |

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
|  **optional** bytes | [optional bytes](#bytes) |  |
|  **optional** hex | [optional string](#string) |  |

### hiber.BytesOrHex.Update

<strong>Deprecated.</strong> 

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.BytesOrHex](#hiberbytesorhex) |  |

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
|  **optional** year | [optional uint32](#uint32) |  |
|  **optional** month | [optional uint32](#uint32) |  |
|  **optional** day | [optional uint32](#uint32) |  |
|  **optional** textual | [optional string](#string) |  |

### hiber.DoubleRange

Decimal range.

| Field | Type | Description |
| ----- | ---- | ----------- |
| start | [ double](#double) |  |
| end | [ double](#double) |  |

### hiber.Duration



| Field | Type | Description |
| ----- | ---- | ----------- |
|  **optional** duration | [optional google.protobuf.Duration](#googleprotobufduration) |  |
|  **optional** textual | [optional string](#string) |  |

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
| include_all | [ bool](#bool) |  |
| include | [repeated string](#string) |  |
| exclude | [repeated string](#string) |  |

### hiber.Filter.ChildOrganizations.Update

<strong>Deprecated.</strong> Update object to update a Filter.ChildOrganizations field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.Filter.ChildOrganizations](#hiberfilterchildorganizations) |  |

### hiber.Filter.DeviceTypes



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) |  |
| exclude | [repeated string](#string) |  |

### hiber.Filter.Events



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated hiber.EventType](#hibereventtype) |  |
| exclude | [repeated hiber.EventType](#hibereventtype) |  |

### hiber.Filter.Events.Update

<strong>Deprecated.</strong> Update object to update a Filter.Events field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.Filter.Events](#hiberfilterevents) |  |

### hiber.Filter.FieldEnumValues



| Field | Type | Description |
| ----- | ---- | ----------- |
| field | [ string](#string) |  |
| include | [repeated string](#string) |  |
| exclude | [repeated string](#string) |  |

### hiber.Filter.HealthLevels



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) |  |
| exclude | [repeated string](#string) |  |

### hiber.Filter.ModemIdentifiers



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) |  |
| exclude | [repeated string](#string) |  |

### hiber.Filter.Modems



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) | Include all modems with these modem numbers (HEX) |
| exclude | [repeated string](#string) | Exclude all modems with these modem numbers (HEX). Exclude takes precedence over include. |

### hiber.Filter.Modems.Update

<strong>Deprecated.</strong> Update object to update a Filter.Modems field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.Filter.Modems](#hiberfiltermodems) |  |

### hiber.Filter.OrganizationPermissions



| Field | Type | Description |
| ----- | ---- | ----------- |
| include_all | [ bool](#bool) |  |
| include | [repeated hiber.OrganizationPermission](#hiberorganizationpermission) |  |
| exclude | [repeated hiber.OrganizationPermission](#hiberorganizationpermission) |  |

### hiber.Filter.Organizations



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) |  |
| exclude | [repeated string](#string) |  |

### hiber.Filter.Properties

Filter result on specific properties encoded in map-value pairs.

| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **selection**.properties | [ hiber.MapFilter](#hibermapfilter) |  |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) **selection**.include_only_empty | [ bool](#bool) | When set to true, match only empty property-sets. |

### hiber.Filter.Publishers



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated int64](#int64) |  |
| exclude | [repeated int64](#int64) |  |
| only_active | [ bool](#bool) |  |

### hiber.Filter.Roles



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) |  |
| exclude | [repeated string](#string) |  |

### hiber.Filter.SensorBrands



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) |  |
| exclude | [repeated string](#string) |  |

### hiber.Filter.SupportPermissions



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated hiber.SupportPermission](#hibersupportpermission) |  |
| exclude | [repeated hiber.SupportPermission](#hibersupportpermission) |  |

### hiber.Filter.Tags



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated int64](#int64) |  |
| exclude | [repeated int64](#int64) |  |

### hiber.Filter.Tags.Update

<strong>Deprecated.</strong> Update object to update a Filter.Tags field.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.Filter.Tags](#hiberfiltertags) |  |

### hiber.Filter.UserPermissions



| Field | Type | Description |
| ----- | ---- | ----------- |
| include_all | [ bool](#bool) |  |
| include | [repeated hiber.UserPermission](#hiberuserpermission) |  |
| exclude | [repeated hiber.UserPermission](#hiberuserpermission) |  |

### hiber.Filter.Users



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated string](#string) |  |
| exclude | [repeated string](#string) |  |

### hiber.Filter.Webhooks



| Field | Type | Description |
| ----- | ---- | ----------- |
| include | [repeated int64](#int64) |  |
| exclude | [repeated int64](#int64) |  |
| only_active | [ bool](#bool) |  |

### hiber.Location

Geographic latitude and longitude coordinates specified in decimal degrees.
For more information, see the WGS-84 coordinate system, which is used for most GPS systems.

| Field | Type | Description |
| ----- | ---- | ----------- |
| latitude | [ double](#double) | Decimal degrees north. |
| longitude | [ double](#double) | Decimal degrees east. |
|  **optional** textual | [optional string](#string) | Text representation. Can be used as an alternative input in a request, filled in by the API in responses. |

### hiber.LocationSelection

Selection object for map data.

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
| key | [ string](#string) |  |
| value | [ hiber.MapFilter.OneOfValues](#hibermapfilteroneofvalues) |  |

### hiber.MapFilter.IncludeAndEntry



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) |  |
| value | [ hiber.MapFilter.OneOfValues](#hibermapfilteroneofvalues) |  |

### hiber.MapFilter.OneOfValues

Technical solution to make map<k, v> into a map<k, repeated v>,
which is not possible in protobuf without trickery.

| Field | Type | Description |
| ----- | ---- | ----------- |
| value | [repeated string](#string) |  |

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
|  **optional** size | [optional int32](#int32) |  |
|  **optional** page | [optional int32](#int32) |  |

### hiber.Pagination.Result



| Field | Type | Description |
| ----- | ---- | ----------- |
| size | [ int32](#int32) |  |
| page | [ int32](#int32) |  |
| total | [ int32](#int32) |  |
| total_pages | [ int32](#int32) |  |
| previous | [ hiber.Pagination](#hiberpagination) |  |
| next | [ hiber.Pagination](#hiberpagination) |  |
| approximated_total | [ bool](#bool) | Indicates that the total is an approximation, and not an exact value. This can be set for data that changes often, or is generally only fetched in an infinite scrolling manner. For example, unbundled events are likely to return an approximated total, but not guaranteed to do so. |

### hiber.Shape

Polygon shape defined by a list of locations, which draw a shape on the map.
The last point is connected to the first to close the shape.

For example, the outline of a city would be defined using a Shape,
while a rectangular region is easier to define using Area.

| Field | Type | Description |
| ----- | ---- | ----------- |
| path | [repeated hiber.Location](#hiberlocation) |  |
|  **optional** textual | [optional string](#string) | Text representation. Can be used as an alternative input in a request, filled in by the API in responses. |

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
| start | [ hiber.Timestamp](#hibertimestamp) |  |
| end | [ hiber.Timestamp](#hibertimestamp) |  |

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
|  **optional** timestamp | [optional google.protobuf.Timestamp](#googleprotobuftimestamp) |  |
|  **optional** time_zone | [optional string](#string) |  |
|  **optional** textual | [optional string](#string) |  |

### hiber.UpdateBoolean

<strong>Deprecated.</strong> Update object for a boolean.

Since false is the default value, we need to distinguish between an omitted value and setting the value to false,
in an update object.

To use this to update, set a value and set updated to true

DEPRECATED: use alternative optional fields in the relevant places instead.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ bool](#bool) |  |

### hiber.UpdateClearableString

<strong>Deprecated.</strong> Update object for a string that can be empty.

Since an empty string is also the default value, we need to distinguish between an omitted value and
setting the value to an empty string, in an update object.

To use this to update, set a value and set updated to true

DEPRECATED: use alternative optional fields in the relevant places instead.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ string](#string) |  |

### hiber.UpdateOptionalDuration

<strong>Deprecated.</strong> Update object for an optional Duration.

To use this to update, set a value and set updated to true.
To clear the duration, set updated to true, but set no value.

DEPRECATED: use alternative optional fields in the relevant places instead.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ hiber.Duration](#hiberduration) |  |

### hiber.UpdateOptionalId

<strong>Deprecated.</strong> Update object for an optional id.

To use this to update, set a value and set updated to true. To clear the id, set updated to true, but set no value.

DEPRECATED: use alternative optional fields in the relevant places instead.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ int64](#int64) |  |

### hiber.UpdateZeroableInt

<strong>Deprecated.</strong> Update object for an int that can be set to 0.

Since 0 is also the default value, we need to distinguish between an omitted value and setting the value to 0,
in an update object.

To use this to update, set a value and set updated to true

DEPRECATED: use alternative optional fields in the relevant places instead.

| Field | Type | Description |
| ----- | ---- | ----------- |
| updated | [ bool](#bool) |  |
| value | [ uint32](#uint32) |  |


### Enums
#### hiber.EventType
Enum of api-accessible events.
The event types in this enum have a protobuf implementation, and can be used, for example, in the
api event stream and publishers.

| Name | Description | Number |
| ---- | ----------- | ------ |
| DEFAULT |  | 0 |
| ORGANIZATION_CREATED | A new organization was created under your organization. | 34 |
| ORGANIZATION_UPDATED | Your organization information was updated. This deals with things like display name and contact information, not users and devices. | 12 |
| ORGANIZATION_DELETED | An organization under your organization was deleted. | 35 |
| ORGANIZATION_EVENT_CONFIGURATION_UPDATED | Your organization's event configuration was updated. This refers to things like message summary configuration. | 43 |
| ASSET_CREATED | A new asset was created in your organization. | 70 |
| ASSET_UPDATED | An asset in your organization was updated (i.e. renamed, tagged). | 71 |
| ASSET_DELETED | An asset in your organization was deleted. | 72 |
| DEVICE_CREATED | A new device was created in your organization, either manually or by a gateway. | 55 |
| DEVICE_UPDATED | A device in your organization was manually updated (i.e. renamed, tagged). | 36 |
| DEVICE_LOCATION_UPDATED | The location of a device in your organization was updated, either manually or by a message. | 4 |
| DEVICE_INSTALLED | A device in your organization was installed and should now be active. | 33 |
| MESSAGE_RECEIVED | A device in your organization sent a message. This event is the final output for the message, after any parsing and post-processing. | 5 |
| MESSAGE_BODY_PARSED | A device in your organization sent a message, and it was parsed by a message body parser. For the final event, with all applied parsers and post processing, use MESSAGE_RECEIVED instead. | 39 |
| MESSAGE_BODY_RECEIVED | A device in your organization sent a message, and it has been scheduled for parsing by message body parsers and post-processing. For the final event, with all applied parsers and post processing, use MESSAGE_RECEIVED instead. | 45 |
| MESSAGE_CANNOT_BE_PARSED | A device in your organization sent a message, and it could not be parsed by any assigned message body parser. This is typically a configuration issue. Please contact customer support if this is not resolved. | 15 |
| MESSAGE_SUMMARY | A summary of messages in your organization was created, based on your event configuration. | 42 |
| MESSAGE_BODY_PARSER_CREATED | A new message body parser was created in your organization. This typically only happens for custom solutions. | 46 |
| MESSAGE_BODY_PARSER_UPDATED | A message body parser in your organization was updated. This typically only happens for custom solutions. | 47 |
| MESSAGE_BODY_PARSER_DELETED | A message body parser in your organization was deleted. This typically only happens for custom solutions. | 48 |
| ALARM_TRIGGERED | An alarm was triggered in your organizations. Depending on the alarm, this may mean that a device sent a message with a value (e.g. pressure) outside of the expected range, or moved out of the expected area. | 56 |
| ALARM_CREATED | A new alarm was created in your organization. | 57 |
| ALARM_UPDATED | An alarm in your organization was updated. | 58 |
| ALARM_DELETED | An alarm in your organization was deleted. | 59 |
| ASSIGNED | An assignment was made in your organization. For example: assigning a tag or alarm to a modem. | 63 |
| UNASSIGNED | An assignment was removed in your organization. For example: removing a tag or alarm from a modem. | 64 |
| TRANSFER | A device was transferred into or out of your organization. Transferred device lose their data and are only used in the new organization if connected to a gateway in that organization. | 18 |
| PUBLISHER_CREATED | A new publisher was created in your organization. Publishers are any system that pushes data out of the system, like webhooks, MQTT integrations and even email preferences. | 1 |
| PUBLISHER_UPDATED | A publisher in your organization was updated. Publishers are any system that pushes data out of the system, like webhooks, MQTT integrations and even email preferences. | 2 |
| PUBLISHER_DELETED | A publisher in your organization was deleted. Publishers are any system that pushes data out of the system, like webhooks, MQTT integrations and even email preferences. | 3 |
| PUBLISHER_FAILED | A publisher in your organization failed to send its data. This can be a temporary issue (perhaps the webhook endpoint is down) or an indication of a configuration issue. Publishers are any system that pushes data out of the system, like webhooks, MQTT integrations and even email preferences. | 11 |
| PUBLISHER_AUTO_DISABLED | A publisher in your organization failed to send its data for a long enough period that is has been disabled. This means the failures were not a temporary issue, but there is something wrong with the configuration. Publishers are any system that pushes data out of the system, like webhooks, MQTT integrations and even email preferences. | 37 |
| USER_ACCESS_REQUEST | A user has requested access to your organization. You can review their request and approve or reject them. | 8 |
| USER_INVITED | A user was invited into your organization. They can review your invite and accept it or ignore it. | 38 |
| USER_ADDED | A user was granted access to your organization, by request, invite, or created by an organization admin. | 9 |
| USER_REMOVED | A user was removed from your organization by an organization admin. | 10 |
| USER_VALIDATION_UPDATED | The user validation (i.e. email domain) for your organization was updated. | 54 |
| TOKEN_CREATED | A new token was created for your organization. | 31 |
| TOKEN_EXPIRY_WARNING | A token in your organization will expire within 2 weeks. | 25 |
| TOKEN_EXPIRED | A token in your organization has expired. | 26 |
| TOKEN_DELETED | A token in your organization was deleted. | 32 |
| EXPORT_CREATED | A new export was started for your organization, exporting data (i.e. messages) to a file. | 65 |
| EXPORT_READY | An export in your organization has completed and the resulting file with data (i.e. messages as CSV) is ready to be downloaded. | 66 |
| EXPORT_FAILED | An export in your organization has failed (typically because of incorrect data selection). | 67 |

#### hiber.Health
Health is an indicator for issues. It is used for publishers to give a quick indication of issues.

| Name | Description | Number |
| ---- | ----------- | ------ |
| OK |  | 0 |
| WARNING |  | 1 |
| ERROR |  | 2 |

#### hiber.UnitOfMeasurement
Unit of measurement for a numeric value.

| Name | Description | Number |
| ---- | ----------- | ------ |
| UNIT_UNKNOWN |  | 0 |
| DURATION_MILLISECONDS |  | 40 |
| DURATION_SECONDS |  | 1 |
| DURATION_MINUTES |  | 2 |
| DURATION_HOURS |  | 3 |
| DURATION_DAYS |  | 4 |
| DURATION_WEEKS |  | 41 |
| FUEL_EFFICIENCY_LITER_PER_100_KILOMETER |  | 30 |
| FUEL_EFFICIENCY_KILOMETER_PER_LITER |  | 31 |
| FUEL_EFFICIENCY_KILOMETER_PER_US_GALLON |  | 32 |
| FUEL_EFFICIENCY_KILOMETER_PER_IMPERIAL_GALLON |  | 33 |
| FUEL_EFFICIENCY_MILE_PER_US_GALLON |  | 34 |
| FUEL_EFFICIENCY_MILE_PER_IMPERIAL_GALLON |  | 35 |
| FUEL_EFFICIENCY_MILE_PER_LITER |  | 36 |
| DISTANCE_METER |  | 8 |
| DISTANCE_MILLIMETER |  | 9 |
| DISTANCE_CENTIMETER |  | 10 |
| DISTANCE_KILOMETER |  | 11 |
| DISTANCE_NAUTICAL_MILE |  | 26 |
| DISTANCE_MILE |  | 21 |
| DISTANCE_YARD |  | 27 |
| DISTANCE_FOOT |  | 28 |
| DISTANCE_INCH |  | 29 |
| PERCENT |  | 16 |
| PRESSURE_BAR |  | 12 |
| PRESSURE_PSI |  | 14 |
| PRESSURE_K_PA |  | 17 |
| PRESSURE_KILOGRAM_PER_CENTIMETER_SQUARED |  | 53 |
| SPEED_KILOMETERS_PER_HOUR |  | 18 |
| SPEED_KNOTS |  | 19 |
| SPEED_METERS_PER_SECOND |  | 20 |
| SPEED_MILES_PER_HOUR |  | 22 |
| SPEED_FEET_PER_SECOND |  | 47 |
| TEMPERATURE_KELVIN |  | 5 |
| TEMPERATURE_DEGREES_CELSIUS |  | 6 |
| TEMPERATURE_DEGREES_FAHRENHEIT |  | 7 |
| VOLTAGE_MILLIVOLT |  | 15 |
| VOLUME_LITER |  | 23 |
| VOLUME_GALLON_US |  | 24 |
| VOLUME_GALLON_IMPERIAL |  | 25 |
| VOLUME_CUBIC_METER |  | 42 |
| VOLUME_CUBIC_FOOT |  | 43 |
| MASS_KILOGRAMS |  | 37 |
| MASS_POUNDS |  | 38 |
| FLOW_BARRELS_PER_DAY |  | 46 |
| FLOW_CUBIC_METER_PER_HOUR |  | 39 |
| FLOW_CUBIC_METER_PER_SECOND |  | 49 |
| FLOW_LITER_PER_HOUR |  | 51 |
| FLOW_LITER_PER_SECOND |  | 52 |
| FLOW_CUBIC_FEET_PER_HOUR |  | 48 |
| FLOW_CUBIC_FEET_PER_SECOND |  | 50 |
| REVOLUTIONS_PER_MINUTE |  | 44 |
| ITEMS_PER_24_HOURS |  | 45 |

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

