## AutryObjects_Sheet1

### PyTransforms
#### _ObjectURI_
From column: _ObjectID_
>``` python
return "object/" + getValue("ObjectID").replace('.','_')
```

#### _OwnerURI_
From column: _Owner_
>``` python
if getValue("Owner") != 'NULL':
    return UM.uri_from_fields("thesauri/person-institution/", getValue("Owner"))
else:
    return ''
```

#### _CreditLineType_
From column: _CreditLine_
>``` python
if getValue("CreditLine"):
    return "Credit Line Statement"
else:
    return ""
```

#### _CreditLineTypeURI_
From column: _CreditLine_
>``` python
if getValue("CreditLineType"):
    return "thesauri/credit_line_string_type/credit_line_statement"
else:
    return ''
```

#### _CreditLineURI_
From column: _CreditLine_
>``` python
if getValue("CreditLine"):
    return getValue("ObjectURI") + "/credit_line"
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

#### _MediumURI_
From column: _Materials_
>``` python
if getValue("Materials"):
    return getValue("ObjectURI")+"/medium"
else:
    return ''
```

#### _TitleTranslateType_
From column: _Title_
>``` python
if getValue("Title"):
    return "Not Translatable"
else:
    return ''
```

#### _TitleTranslateTypeURI_
From column: _TitleTranslateType_
>``` python
if getValue("TitleTranslateType"):
    return "thesauri/title_translate_type/not_translatable"
else:
    return ''
```

#### _TitleURI_
From column: _Title_
>``` python
if getValue("Title"):
    return UM.uri_from_fields("thesauri/title/", getValue("Title"))
else:
    return ''
```

#### _DimensionStringType_
From column: _Measurements_
>``` python
if getValue("Measurements"):
    return "Dimension Statement"
else:
    return ''
```

#### _DimensionStringTypeURI_
From column: _DimensionStringType_
>``` python
if getValue("DimensionStringType"):
    return "thesauri/dimension_string_type/dimension_statement"
else:
    return ''
```

#### _DimensionURI_
From column: _Measurements_
>``` python
if getValue("Measurements") != 'NULL':
    return getValue("ObjectURI") + "/dimensions"
else:
    return ''
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _AutryMakerURL_ | `crm:P3_has_note` | `crm:E39_Actor1`|
| _AutryObjectURL_ | `crm:P3_has_note` | `crm:E22_Man-Made_Object1`|
| _BeginDate_ | `crm:P82_at_some_time_within` | `crm:E52_Time-Span2`|
| _BeginXSDDate_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span2`|
| _BirthDateURI_ | `uri` | `crm:E52_Time-Span2`|
| _BirthURI_ | `uri` | `crm:E67_Birth1`|
| _ClassificationURI_ | `uri` | `crm:E55_Type2`|
| _ConstituentURI_ | `uri` | `crm:E39_Actor1`|
| _CreditLine_ | `rdfs:label` | `crm:E39_Actor2`|
| _CreditLine_ | `rdfs:label` | `crm:E39_Actor1`|
| _CreditLineType_ | `rdfs:label` | `crm:E55_Type1`|
| _CreditLineTypeURI_ | `uri` | `crm:E55_Type1`|
| _CreditLineURI_ | `uri` | `crm:E39_Actor2`|
| _Culture_ | `rdfs:label` | `crm:E74_Group1`|
| _CultureURI_ | `uri` | `crm:E74_Group1`|
| _Dated_ | `crm:P3_has_note` | `crm:E52_Time-Span2`|
| _Dated_ | `rdfs:label` | `crm:E52_Time-Span2`|
| _DeathDateURI_ | `uri` | `crm:E52_Time-Span1`|
| _DeathURI_ | `uri` | `crm:E69_Death1`|
| _DimensionStringType_ | `rdfs:label` | `crm:E55_Type5`|
| _DimensionStringTypeURI_ | `uri` | `crm:E55_Type5`|
| _DimensionURI_ | `uri` | `crm:E54_Dimension1`|
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
| _Materials_ | `rdfs:label` | `crm:E55_Type4`|
| _Measurements_ | `rdfs:label` | `crm:E54_Dimension1`|
| _Medium_ | `crm:P3_has_note` | `crm:E55_Type4`|
| _MediumURI_ | `uri` | `crm:E55_Type4`|
| _MiddleName_ | `rdfs:label` | `crm:E41_Appellation2`|
| _MiddleNameAppellationURI_ | `uri` | `crm:E41_Appellation2`|
| _MiddleNameURI_ | `uri` | `crm:E55_Type2`|
| _NameType_ | `rdfs:label` | `crm:E55_Type3`|
| _ObjectName_ | `rdfs:label` | `crm:E55_Type2`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _Owner_ | `rdfs:label` | `crm:E39_Actor1`|
| _OwnerURI_ | `uri` | `crm:E39_Actor1`|
| _OwnerURL_ | `crm:P3_has_note` | `crm:E39_Actor1`|
| _PlacePublished_ | `rdfs:label` | `crm:E44_Place_Appellation1`|
| _PlacePublishedURI_ | `uri` | `crm:E44_Place_Appellation1`|
| _PrimaryTitle_ | `rdfs:label` | `crm:E35_Title2`|
| _PrimaryTitleTranslationType_ | `rdfs:label` | `crm:E55_Type2`|
| _PrimaryTitleURI_ | `uri` | `crm:E35_Title2`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
| _PublicDescription_ | `crm:P3_has_note` | `crm:E22_Man-Made_Object1`|
| _ReferenceURI_ | `uri` | `crm:E31_Document1`|
| _SecondaryTitle_ | `rdfs:label` | `crm:E35_Title1`|
| _SecondaryTitleTranslateType_ | `rdfs:label` | `crm:E55_Type4`|
| _SecondaryTitleTranslateTypeURI_ | `uri` | `crm:E55_Type4`|
| _SecondaryTitleType_ | `rdfs:label` | `crm:E55_Type1`|
| _SecondaryTitleURI_ | `uri` | `crm:E35_Title1`|
| _SubTitleTranslateType_ | `rdfs:label` | `crm:E55_Type5`|
| _SubTitleTranslateTypeURI_ | `uri` | `crm:E55_Type5`|
| _Title_ | `rdfs:label` | `crm:E35_Title1`|
| _TitleTranslateType_ | `rdfs:label` | `crm:E55_Type3`|
| _TitleTranslateTypeURI_ | `uri` | `crm:E55_Type3`|
| _TitleURI_ | `uri` | `crm:E35_Title1`|
| _ULAN_ID_ | `rdfs:label` | `crm:E42_Identifier1`|
| _ULAN_ID_Type_ | `uri` | `crm:E42_Identifier1`|
| _WorldCatURL_ | `crm:P3_has_note` | `crm:E31_Document1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E22_Man-Made_Object1` | `crm:P102_has_title` | `crm:E35_Title1`|
| `crm:E22_Man-Made_Object1` | `crm:P49_has_former_or_current_keeper` | `crm:E39_Actor1`|
| `crm:E22_Man-Made_Object1` | `crm:P51_has_former_or_current_owner` | `crm:E39_Actor2`|
| `crm:E22_Man-Made_Object1` | `crm:P43_has_dimension` | `crm:E54_Dimension1`|
| `crm:E22_Man-Made_Object1` | `crm:P2_has_type` | `crm:E55_Type2`|
| `crm:E22_Man-Made_Object1` | `crm:P2_has_type` | `crm:E55_Type4`|
| `crm:E35_Title1` | `crm:P2_has_type` | `crm:E55_Type3`|
| `crm:E39_Actor2` | `crm:P2_has_type` | `crm:E55_Type1`|
| `crm:E54_Dimension1` | `crm:P2_has_type` | `crm:E55_Type5`|
