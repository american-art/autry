## AutryPublications_Sheet1

### PyTransforms
#### _ObjectURI_
From column: _ObjectID_
>``` python
return "object/" + getValue("ObjectID").replace('.','_')
```

#### _ReferenceURI_
From column: _ObjectURI_
>``` python
return getValue("ObjectURI") + "/reference"
```

#### _TitleURI_
From column: _Title_
>``` python
return UM.uri_from_fields("thesauri/title/", getValue("Title"))
```

#### _TitleTranslateType_
From column: _TitleURI_
>``` python
if getValue("Title") != 'NULL':
    return "Not Translatable"
else:
    return ''
```

#### _TitleTranslateTypeURI_
From column: _TitleTranslateType_
>``` python
if getValue("Title") != 'NULL':
    return "thesauri/title_translate_type/not_translatable"
else:
    return ''
```

#### _PagesURI_
From column: _Pages_
>``` python
if getValue("Pages") != 'NULL':
    prefix = getValue("ReferenceURI") + "/page/"
    return UM.uri_from_fields(prefix, getValue("Pages"))
else:
    return ''
```

#### _OCLC_NumberURI_
From column: _OCLC_Number_
>``` python
if getValue("OCLC_Number") != 'NULL':
    return UM.uri_from_fields("thesauri/oclc_number/", getValue("OCLC_Number"))
else:
    return ''
```

#### _ReferenceTitleURI_
From column: _ReferenceURI_
>``` python
return getValue("ReferenceURI") + "/title"
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _AutryMakerURL_ | `crm:P3_has_note` | `crm:E39_Actor1`|
| _BeginDate_ | `crm:P82_at_some_time_within` | `crm:E52_Time-Span2`|
| _BeginXSDDate_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span2`|
| _BirthDateURI_ | `uri` | `crm:E52_Time-Span2`|
| _BirthURI_ | `uri` | `crm:E67_Birth1`|
| _ConstituentURI_ | `uri` | `crm:E39_Actor1`|
| _CreditLine_ | `rdfs:label` | `crm:E39_Actor1`|
| _Culture_ | `rdfs:label` | `crm:E74_Group1`|
| _CultureURI_ | `uri` | `crm:E74_Group1`|
| _Dated_ | `crm:P3_has_note` | `crm:E52_Time-Span2`|
| _Dated_ | `rdfs:label` | `crm:E52_Time-Span2`|
| _DeathDateURI_ | `uri` | `crm:E52_Time-Span1`|
| _DeathURI_ | `uri` | `crm:E69_Death1`|
| _DimensionURI_ | `uri` | `crm:E54_Dimension1`|
| _Dimensions_ | `rdfs:label` | `crm:E54_Dimension1`|
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
| _Medium_ | `crm:P3_has_note` | `crm:E55_Type4`|
| _MiddleName_ | `rdfs:label` | `crm:E41_Appellation2`|
| _MiddleNameAppellationURI_ | `uri` | `crm:E41_Appellation2`|
| _MiddleNameURI_ | `uri` | `crm:E55_Type2`|
| _NameType_ | `rdfs:label` | `crm:E55_Type3`|
| _OCLC_Number_ | `rdfs:label` | `crm:E42_Identifier1`|
| _OCLC_NumberURI_ | `uri` | `crm:E42_Identifier1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _Pages_ | `rdfs:label` | `crm:E41_Appellation2`|
| _PagesURI_ | `uri` | `crm:E41_Appellation2`|
| _PlacePublished_ | `rdfs:label` | `crm:E44_Place_Appellation1`|
| _PlacePublishedURI_ | `uri` | `crm:E44_Place_Appellation1`|
| _PrimaryTitle_ | `rdfs:label` | `crm:E35_Title2`|
| _PrimaryTitleTranslationType_ | `rdfs:label` | `crm:E55_Type2`|
| _PrimaryTitleURI_ | `uri` | `crm:E35_Title2`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
| _PublicDescription_ | `crm:P3_has_note` | `crm:E22_Man-Made_Object1`|
| _ReferenceTitleURI_ | `uri` | `crm:E41_Appellation1`|
| _ReferenceURI_ | `uri` | `crm:E31_Document1`|
| _ReferenceURI_ | `uri` | `crm:E31_Document1`|
| _SecondaryTitle_ | `rdfs:label` | `crm:E35_Title1`|
| _SecondaryTitleTranslateType_ | `rdfs:label` | `crm:E55_Type4`|
| _SecondaryTitleTranslateTypeURI_ | `uri` | `crm:E55_Type4`|
| _SecondaryTitleType_ | `rdfs:label` | `crm:E55_Type1`|
| _SecondaryTitleURI_ | `uri` | `crm:E35_Title1`|
| _SubTitleTranslateType_ | `rdfs:label` | `crm:E55_Type5`|
| _SubTitleTranslateTypeURI_ | `uri` | `crm:E55_Type5`|
| _Title_ | `rdfs:label` | `crm:E35_Title1`|
| _TitleTranslateType_ | `rdfs:label` | `crm:E55_Type1`|
| _TitleTranslateTypeURI_ | `uri` | `crm:E55_Type1`|
| _TitleURI_ | `uri` | `crm:E35_Title1`|
| _ULAN_ID_ | `rdfs:label` | `crm:E42_Identifier1`|
| _ULAN_ID_Type_ | `uri` | `crm:E42_Identifier1`|
| _WorldCatURL_ | `crm:P3_has_note` | `crm:E31_Document1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E31_Document1` | `crm:P70_documents` | `crm:E22_Man-Made_Object1`|
| `crm:E31_Document1` | `crm:P1_is_identified_by` | `crm:E41_Appellation1`|
| `crm:E31_Document1` | `crm:P106_is_composed_of` | `crm:E41_Appellation2`|
| `crm:E31_Document1` | `crm:P48_has_preferred_identifier` | `crm:E42_Identifier1`|
| `crm:E35_Title1` | `crm:P2_has_type` | `crm:E55_Type1`|
| `crm:E41_Appellation1` | `crm:P106_is_composed_of` | `crm:E35_Title1`|
