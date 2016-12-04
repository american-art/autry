## AutryObjects_Sheet1

### PyTransforms
#### _ObjectURI_
From column: _ObjectID_
>``` python
return UM.uri_from_fields("object/", getValue("ObjectID"))
```

#### _PreferredIDURI_
From column: _ObjectNumber_
>``` python
return UM.uri_from_fields("object/preferred_id/", getValue("ObjectNumber"))
```

#### _PreferredTermsURI_
From column: _PreferredIDURI_
>``` python
if getValue("ObjectNumber"):
    return "aat:300404670"
else:
    return ''
```

#### _TitleURI_
From column: _Title_
>``` python
if getValue("Title"):
    return UM.uri_from_fields("object/title/", getValue("Title"))
else:
    return ''
```

#### _TitlePreferredTermsURI_
From column: _TitleURI_
>``` python
if getValue("Title"):
    return "aat:300404670"
else:
    return ''
```

#### _OwnerURI_
From column: _Owner_
>``` python
if getValue("Owner"):
    return UM.uri_from_fields("object/owner/", getValue("Owner"))
else:
    return ''
```

#### _CreditLineURI_
From column: _CreditLine_
>``` python
if getValue("CreditLine"):
    return UM.uri_from_fields("object/credit_line/", getValue("CreditLine"))
else:
    return ''
```

#### _AcknowledgementsURI_
From column: _CreditLineURI_
>``` python
if getValue("CreditLine"):
    return "aat:300026687"
else:
    return ''
```

#### _DimensionsTextURI_
From column: _Measurements_
>``` python
if getValue("Measurements"):
    return getValue("ObjectURI") + "/dimensions_text"
else:
    return ''
```

#### _DimensionsAATURI_
From column: _DimensionsTextURI_
>``` python
if getValue("Measurements"):
    return "aat:300266036"
else:
    return ''
```

#### _MediumTextURI_
From column: _Materials_
>``` python
if getValue("Materials"):
    return getValue("ObjectURI") + "/medium_text"
else:
    return ''
```

#### _MaterialComponentsURI_
From column: _MediumTextURI_
>``` python
if getValue("Materials"):
    return "aat:300264237"
else:
    return ''
```

#### _ClassificationURI_
From column: _ObjectName_
>``` python
if getValue("ObjectName"):
    return UM.uri_from_fields("thesauri/classification/", getValue("ObjectName"))
else:
    return ''
```

#### _ClassificationEventURI_
From column: _ClassificationURI_
>``` python
if getValue("ObjectName"):
    prefix = getValue("ObjectURI") + "/classification_event/"
    return UM.uri_from_fields(prefix, getValue("ObjectName"))
else:
    return ''
```

#### _VisualWorksURI_
From column: _ClassificationEventURI_
>``` python
if getValue("ObjectName"):
    return "aat:300179869"
else:
    return ''
```

#### _ObjectNumberCopy_
From column: _ObjectNumber_
>``` python
return getValue("ObjectNumber")
```

#### _ObjectIDCopy_
From column: _ObjectID_
>``` python
return getValue("ObjectID")
```

#### _ObjectIDURI_
From column: _ObjectID_
>``` python
return UM.uri_from_fields("object/id/", getValue("ObjectID"))
```

#### _RepositoryTermsURI_
From column: _ObjectID_
>``` python
return "aat:300404621"
```

#### _TitleCopy_
From column: _Title_
>``` python
return getValue("Title")
```

#### _OwnerURLCopy_
From column: _OwnerURL_
>``` python
return getValue("OwnerURL")
```

#### _AutryObjectURLCopy_
From column: _AutryObjectURL_
>``` python
return getValue("AutryObjectURL")
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _AcknowledgementsURI_ | `uri` | `crm:E55_Type3`|
| _AutryMakerURL_ | `crm:P3_has_note` | `crm:E39_Actor1`|
| _AutryMakerURLCopy_ | `rdfs:label` | `foaf:Document1`|
| _AutryObjectURL_ | `uri` | `foaf:Document2`|
| _AutryObjectURL_ | `uri` | `foaf:Document2`|
| _AutryObjectURLCopy_ | `rdfs:label` | `foaf:Document2`|
| _BeginDate_ | `crm:P82_at_some_time_within` | `crm:E52_Time-Span2`|
| _BeginXSDDate_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span2`|
| _BirthDateURI_ | `uri` | `crm:E52_Time-Span2`|
| _BirthURI_ | `uri` | `crm:E67_Birth1`|
| _BirthURI_ | `uri` | `crm:E63_Beginning_of_Existence1`|
| _ClassificationEventURI_ | `uri` | `crm:E17_Type_Assignment1`|
| _ClassificationEventURI_ | `uri` | `crm:E17_Type_Assignment1`|
| _ClassificationURI_ | `uri` | `crm:E55_Type6`|
| _ClassificationURI_ | `uri` | `crm:E55_Type6`|
| _ConstituentURI_ | `uri` | `crm:E39_Actor1`|
| _CreditLine_ | `rdfs:label` | `crm:E39_Actor1`|
| _CreditLine_ | `rdf:value` | `crm:E33_Linguistic_Object3`|
| _CreditLine_ | `rdfs:label` | `crm:E39_Actor2`|
| _CreditLine_ | `rdf:value` | `crm:E33_Linguistic_Object1`|
| _CreditLineURI_ | `uri` | `crm:E33_Linguistic_Object1`|
| _CreditLineURI_ | `uri` | `crm:E39_Actor2`|
| _CreditLineURI_ | `uri` | `crm:E33_Linguistic_Object1`|
| _Culture_ | `rdfs:label` | `crm:E74_Group1`|
| _CultureURI_ | `uri` | `crm:E74_Group1`|
| _Dated_ | `crm:P3_has_note` | `crm:E52_Time-Span2`|
| _Dated_ | `rdfs:label` | `crm:E52_Time-Span2`|
| _DeathDateURI_ | `uri` | `crm:E52_Time-Span1`|
| _DeathURI_ | `uri` | `crm:E64_End_of_Existence1`|
| _DeathURI_ | `uri` | `crm:E69_Death1`|
| _DeathYear_ | `rdfs:label` | `crm:E52_Time-Span1`|
| _DimensionURI_ | `uri` | `crm:E54_Dimension1`|
| _Dimensions_ | `rdfs:label` | `crm:E54_Dimension1`|
| _DimensionsAATURI_ | `uri` | `crm:E55_Type4`|
| _DimensionsTextURI_ | `uri` | `crm:E33_Linguistic_Object2`|
| _DimensionsTextURI_ | `uri` | `crm:E33_Linguistic_Object2`|
| _DisplayName_ | `rdfs:label` | `crm:E41_Appellation5`|
| _DisplayNameURI_ | `uri` | `crm:E41_Appellation5`|
| _DisplayNameURI_ | `uri` | `crm:E41_Appellation4`|
| _DisplayPersonInstitutionName_ | `rdfs:label` | `crm:E41_Appellation4`|
| _EndDate_ | `crm:P82_at_some_time_within` | `crm:E52_Time-Span1`|
| _EndXSDDate_ | `crm:P82b_end_of_the_end` | `crm:E52_Time-Span2`|
| _FirstName_ | `rdfs:label` | `crm:E41_Appellation3`|
| _FirstNameAppellationURI_ | `uri` | `crm:E41_Appellation3`|
| _FirstNameURI_ | `uri` | `crm:E55_Type3`|
| _LastName_ | `rdfs:label` | `crm:E41_Appellation1`|
| _LastNameAppellationURI_ | `uri` | `crm:E41_Appellation1`|
| _LastNameURI_ | `uri` | `crm:E55_Type1`|
| _MakerAppellationURI_ | `uri` | `crm:E82_Actor_Appellation1`|
| _MakerCopy_ | `rdf:value` | `crm:E82_Actor_Appellation1`|
| _MaterialComponentsURI_ | `uri` | `crm:E55_Type5`|
| _Materials_ | `rdf:value` | `crm:E33_Linguistic_Object3`|
| _Materials_ | `rdf:value` | `crm:E33_Linguistic_Object1`|
| _Measurements_ | `rdf:value` | `crm:E33_Linguistic_Object2`|
| _Measurements_ | `rdf:value` | `crm:E33_Linguistic_Object2`|
| _Medium_ | `crm:P3_has_note` | `crm:E55_Type4`|
| _MediumTextURI_ | `uri` | `crm:E33_Linguistic_Object3`|
| _MediumTextURI_ | `uri` | `crm:E33_Linguistic_Object3`|
| _MiddleName_ | `rdfs:label` | `crm:E41_Appellation2`|
| _MiddleNameAppellationURI_ | `uri` | `crm:E41_Appellation2`|
| _MiddleNameURI_ | `uri` | `crm:E55_Type2`|
| _NameType_ | `rdfs:label` | `crm:E55_Type3`|
| _ObjectID_ | `rdfs:label` | `crm:E42_Identifier2`|
| _ObjectID_ | `rdfs:label` | `crm:E42_Identifier2`|
| _ObjectIDCopy_ | `rdf:value` | `crm:E42_Identifier2`|
| _ObjectIDCopy_ | `rdf:value` | `crm:E42_Identifier2`|
| _ObjectIDURI_ | `uri` | `crm:E42_Identifier2`|
| _ObjectIDURI_ | `uri` | `crm:E42_Identifier2`|
| _ObjectName_ | `rdfs:label` | `crm:E55_Type6`|
| _ObjectName_ | `rdfs:label` | `crm:E55_Type7`|
| _ObjectName_ | `rdfs:label` | `crm:E55_Type6`|
| _ObjectNumber_ | `rdfs:label` | `crm:E42_Identifier1`|
| _ObjectNumberCopy_ | `rdf:value` | `crm:E42_Identifier1`|
| _ObjectNumberCopy_ | `rdf:value` | `crm:E42_Identifier1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _Owner_ | `rdfs:label` | `crm:E40_Legal_Body1`|
| _Owner_ | `rdfs:label` | `crm:E40_Legal_Body1`|
| _OwnerURI_ | `uri` | `crm:E40_Legal_Body1`|
| _OwnerURI_ | `uri` | `crm:E40_Legal_Body1`|
| _OwnerURL_ | `uri` | `foaf:Document1`|
| _OwnerURL_ | `uri` | `foaf:Document1`|
| _OwnerURLCopy_ | `rdfs:label` | `foaf:Document1`|
| _PlacePublished_ | `rdfs:label` | `crm:E44_Place_Appellation1`|
| _PlacePublishedURI_ | `uri` | `crm:E44_Place_Appellation1`|
| _PreferredIDURI_ | `uri` | `crm:E42_Identifier1`|
| _PreferredTermsURI_ | `uri` | `crm:E55_Type1`|
| _PrimaryTitle_ | `rdfs:label` | `crm:E35_Title2`|
| _PrimaryTitleTranslationType_ | `rdfs:label` | `crm:E55_Type2`|
| _PrimaryTitleURI_ | `uri` | `crm:E35_Title2`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
| _PublicDescription_ | `dc:description` | `crm:E22_Man-Made_Object1`|
| _PublicDescription_ | `crm:P3_has_note` | `crm:E22_Man-Made_Object1`|
| _ReferenceURI_ | `uri` | `crm:E31_Document1`|
| _RepositoryTermsURI_ | `uri` | `crm:E55_Type7`|
| _RepositoryTermsURI_ | `uri` | `crm:E55_Type7`|
| _SecondaryTitle_ | `rdfs:label` | `crm:E35_Title1`|
| _SecondaryTitleTranslateType_ | `rdfs:label` | `crm:E55_Type4`|
| _SecondaryTitleTranslateTypeURI_ | `uri` | `crm:E55_Type4`|
| _SecondaryTitleType_ | `rdfs:label` | `crm:E55_Type1`|
| _SecondaryTitleURI_ | `uri` | `crm:E35_Title1`|
| _SubTitleTranslateType_ | `rdfs:label` | `crm:E55_Type5`|
| _SubTitleTranslateTypeURI_ | `uri` | `crm:E55_Type5`|
| _Title_ | `rdfs:label` | `crm:E22_Man-Made_Object1`|
| _Title_ | `rdfs:label` | `crm:E22_Man-Made_Object1`|
| _TitleCopy_ | `rdf:value` | `crm:E35_Title1`|
| _TitleCopy_ | `rdf:value` | `crm:E35_Title2`|
| _TitlePreferredTermsURI_ | `uri` | `crm:E55_Type2`|
| _TitleURI_ | `uri` | `crm:E35_Title1`|
| _ULAN_ID_ | `rdfs:label` | `crm:E42_Identifier1`|
| _ULAN_ID_Type_ | `uri` | `crm:E42_Identifier1`|
| _VisualWorksURI_ | `crm:P21_had_general_purpose` | `crm:E17_Type_Assignment1`|
| _VisualWorksURI_ | `crm:P21_had_general_purpose` | `crm:E17_Type_Assignment1`|
| _WorldCatURL_ | `crm:P3_has_note` | `crm:E31_Document1`|
| _imagelink_ | `uri` | `crm:E38_Image1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E17_Type_Assignment1` | `crm:P42_assigned` | `crm:E55_Type6`|
| `crm:E22_Man-Made_Object1` | `crm:P41i_was_classified_by` | `crm:E17_Type_Assignment1`|
| `crm:E22_Man-Made_Object1` | `crm:P67i_is_referred_to_by` | `crm:E33_Linguistic_Object1`|
| `crm:E22_Man-Made_Object1` | `crm:P67i_is_referred_to_by` | `crm:E33_Linguistic_Object2`|
| `crm:E22_Man-Made_Object1` | `crm:P67i_is_referred_to_by` | `crm:E33_Linguistic_Object3`|
| `crm:E22_Man-Made_Object1` | `crm:P102_has_title` | `crm:E35_Title1`|
| `crm:E22_Man-Made_Object1` | `crm:P52_has_current_owner` | `crm:E40_Legal_Body1`|
| `crm:E22_Man-Made_Object1` | `crm:P1_is_identified_by` | `crm:E42_Identifier1`|
| `crm:E22_Man-Made_Object1` | `crm:P1_is_identified_by` | `crm:E42_Identifier2`|
| `crm:E22_Man-Made_Object1` | `foaf:homepage` | `foaf:Document2`|
| `crm:E22_Man-Made_Object1` | `crm:P2_has_type` | `crm:E55_Type6`|
| `crm:E33_Linguistic_Object1` | `crm:P2_has_type` | `crm:E55_Type3`|
| `crm:E33_Linguistic_Object2` | `crm:P2_has_type` | `crm:E55_Type4`|
| `crm:E33_Linguistic_Object3` | `crm:P2_has_type` | `crm:E55_Type5`|
| `crm:E35_Title1` | `crm:P2_has_type` | `crm:E55_Type2`|
| `crm:E40_Legal_Body1` | `foaf:homepage` | `foaf:Document1`|
| `crm:E42_Identifier1` | `crm:P2_has_type` | `crm:E55_Type1`|
| `crm:E42_Identifier2` | `crm:P2_has_type` | `crm:E55_Type7`|
