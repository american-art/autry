## AutryMakers_Sheet1

### PyTransforms
#### _ObjectURI_
From column: _ObjectID_
>``` python
return UM.uri_from_fields("object/", getValue("ObjectID"))
```

#### _MakerCopy_
From column: _Maker_
>``` python
return getValue("Maker")
```

#### _PreferredTermsURI_
From column: _MakerCopy_
>``` python
if getValue("Maker"):
    return "aat:300404670"
else:
    return ''
```

#### _BirthYear_
From column: _Dates_
>``` python
time = getValue("Dates").replace(' ', '').lower()
dash_index = time.find('-')

if (time == 'NULL') or ('founded' in time) or ('circa' in time) or ('active' in time) or ('established' in time):
    return ''

if 'born' in time:
    born_index = time.find('born')
    return time[born_index + 4: born_index + 9]

if dash_index != -1:
    return time[dash_index-4:dash_index]

return ''
```

#### _DeathYear_
From column: _Dates_
>``` python
time = getValue("Dates").replace(' ', '').lower()
dash_index = time.find('-')

if (time == 'NULL') or ('founded' in time) or ('circa' in time) or ('active' in time) or ('established' in time) or ('born' in time):
    return ''

if dash_index != -1:
    return time[dash_index+1:dash_index+5]

return ''
```

#### _MakerURI_
From column: _Maker_
>``` python
if getValue("Maker") != 'NULL':
    return  UM.uri_from_fields("maker/", getValue("Maker"))
else:
    return ''
```

#### _MakerAppellationURI_
From column: _MakerURI_
>``` python
if getValue("MakerURI") != 'NULL':
    return getValue("MakerURI") + "/appellation"
else:
    return ''
```

#### _ProductionURI_
From column: _ObjectURI_
>``` python
return getValue("ObjectURI") + "/production"
```

#### _BirthURI_
From column: _BirthYear_
>``` python
if getValue("BirthYear") != 'NULL':
    return getValue("MakerURI") + "/birth_event"
else:
    return ''
```

#### _BirthTimespanURI_
From column: _BirthYear_
>``` python
if getValue("BirthYear") != 'NULL':
    return getValue("MakerURI") + "/birth_timespan"
else:
    return ''
```

#### _DeathURI_
From column: _DeathYear_
>``` python
if getValue("DeathYear") != 'NULL':
    return getValue("MakerURI") + "/death_event"
else:
    return ''
```

#### _DeathTimespanURI_
From column: _DeathYear_
>``` python
if getValue("DeathYear") != 'NULL':
    return getValue("MakerURI") + "/death_timespan"
else:
    return ''
```

#### _AutryMakerURLCopy_
From column: _AutryMakerURL_
>``` python
return getValue("AutryMakerURL")
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _AutryMakerURL_ | `uri` | `foaf:Document1`|
| _AutryMakerURL_ | `crm:P3_has_note` | `crm:E39_Actor1`|
| _AutryMakerURLCopy_ | `rdfs:label` | `foaf:Document1`|
| _AutryObjectURL_ | `uri` | `foaf:Document2`|
| _BeginDate_ | `crm:P82_at_some_time_within` | `crm:E52_Time-Span2`|
| _BeginXSDDate_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span2`|
| _BirthDateURI_ | `uri` | `crm:E52_Time-Span2`|
| _BirthTimespanURI_ | `uri` | `crm:E52_Time-Span1`|
| _BirthURI_ | `uri` | `crm:E63_Beginning_of_Existence1`|
| _BirthURI_ | `uri` | `crm:E67_Birth1`|
| _BirthYear_ | `rdfs:label` | `crm:E52_Time-Span1`|
| _ClassificationEventURI_ | `uri` | `crm:E17_Type_Assignment1`|
| _ClassificationURI_ | `uri` | `crm:E55_Type6`|
| _ConstituentURI_ | `uri` | `crm:E39_Actor1`|
| _CreditLine_ | `rdfs:label` | `crm:E39_Actor1`|
| _CreditLine_ | `rdf:value` | `crm:E33_Linguistic_Object3`|
| _CreditLine_ | `rdfs:label` | `crm:E39_Actor2`|
| _CreditLineURI_ | `uri` | `crm:E39_Actor2`|
| _CreditLineURI_ | `uri` | `crm:E33_Linguistic_Object1`|
| _Culture_ | `rdfs:label` | `crm:E74_Group1`|
| _CultureURI_ | `uri` | `crm:E74_Group1`|
| _Dated_ | `crm:P3_has_note` | `crm:E52_Time-Span2`|
| _Dated_ | `rdfs:label` | `crm:E52_Time-Span2`|
| _DeathDateURI_ | `uri` | `crm:E52_Time-Span1`|
| _DeathTimespanURI_ | `uri` | `crm:E52_Time-Span2`|
| _DeathURI_ | `uri` | `crm:E64_End_of_Existence1`|
| _DeathURI_ | `uri` | `crm:E69_Death1`|
| _DeathYear_ | `rdfs:label` | `crm:E52_Time-Span2`|
| _DimensionURI_ | `uri` | `crm:E54_Dimension1`|
| _Dimensions_ | `rdfs:label` | `crm:E54_Dimension1`|
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
| _Maker_ | `rdfs:label` | `crm:E39_Actor1`|
| _MakerAppellationURI_ | `uri` | `crm:E82_Actor_Appellation1`|
| _MakerCopy_ | `rdf:value` | `crm:E82_Actor_Appellation1`|
| _MakerURI_ | `uri` | `crm:E39_Actor1`|
| _Materials_ | `rdf:value` | `crm:E33_Linguistic_Object1`|
| _Measurements_ | `rdf:value` | `crm:E33_Linguistic_Object2`|
| _Medium_ | `crm:P3_has_note` | `crm:E55_Type4`|
| _MediumTextURI_ | `uri` | `crm:E33_Linguistic_Object3`|
| _MiddleName_ | `rdfs:label` | `crm:E41_Appellation2`|
| _MiddleNameAppellationURI_ | `uri` | `crm:E41_Appellation2`|
| _MiddleNameURI_ | `uri` | `crm:E55_Type2`|
| _NameType_ | `rdfs:label` | `crm:E55_Type3`|
| _ObjectID_ | `rdfs:label` | `crm:E42_Identifier2`|
| _ObjectIDCopy_ | `rdf:value` | `crm:E42_Identifier2`|
| _ObjectIDURI_ | `uri` | `crm:E42_Identifier2`|
| _ObjectName_ | `rdfs:label` | `crm:E55_Type6`|
| _ObjectName_ | `rdfs:label` | `crm:E55_Type7`|
| _ObjectNumberCopy_ | `rdf:value` | `crm:E42_Identifier1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _Owner_ | `rdfs:label` | `crm:E40_Legal_Body1`|
| _OwnerURI_ | `uri` | `crm:E40_Legal_Body1`|
| _OwnerURL_ | `uri` | `foaf:Document1`|
| _PlacePublished_ | `rdfs:label` | `crm:E44_Place_Appellation1`|
| _PlacePublishedURI_ | `uri` | `crm:E44_Place_Appellation1`|
| _PreferredTermsURI_ | `uri` | `crm:E55_Type1`|
| _PrimaryTitle_ | `rdfs:label` | `crm:E35_Title2`|
| _PrimaryTitleTranslationType_ | `rdfs:label` | `crm:E55_Type2`|
| _PrimaryTitleURI_ | `uri` | `crm:E35_Title2`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
| _PublicDescription_ | `crm:P3_has_note` | `crm:E22_Man-Made_Object1`|
| _PublicDescription_ | `dc:description` | `crm:E22_Man-Made_Object1`|
| _ReferenceURI_ | `uri` | `crm:E31_Document1`|
| _RepositoryTermsURI_ | `uri` | `crm:E55_Type7`|
| _SecondaryTitle_ | `rdfs:label` | `crm:E35_Title1`|
| _SecondaryTitleTranslateType_ | `rdfs:label` | `crm:E55_Type4`|
| _SecondaryTitleTranslateTypeURI_ | `uri` | `crm:E55_Type4`|
| _SecondaryTitleType_ | `rdfs:label` | `crm:E55_Type1`|
| _SecondaryTitleURI_ | `uri` | `crm:E35_Title1`|
| _SubTitleTranslateType_ | `rdfs:label` | `crm:E55_Type5`|
| _SubTitleTranslateTypeURI_ | `uri` | `crm:E55_Type5`|
| _Title_ | `rdfs:label` | `crm:E22_Man-Made_Object1`|
| _TitleCopy_ | `rdf:value` | `crm:E35_Title2`|
| _ULAN_ID_ | `rdfs:label` | `crm:E42_Identifier1`|
| _ULAN_ID_Type_ | `uri` | `crm:E42_Identifier1`|
| _VisualWorksURI_ | `crm:P21_had_general_purpose` | `crm:E17_Type_Assignment1`|
| _WorldCatURL_ | `crm:P3_has_note` | `crm:E31_Document1`|
| _imagelink_ | `uri` | `crm:E38_Image1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E12_Production1` | `crm:P14_carried_out_by` | `crm:E39_Actor1`|
| `crm:E22_Man-Made_Object1` | `crm:P108i_was_produced_by` | `crm:E12_Production1`|
| `crm:E39_Actor1` | `crm:P92i_was_brought_into_existence_by` | `crm:E63_Beginning_of_Existence1`|
| `crm:E39_Actor1` | `crm:P93i_was_taken_out_of_existence_by` | `crm:E64_End_of_Existence1`|
| `crm:E39_Actor1` | `crm:P131_is_identified_by` | `crm:E82_Actor_Appellation1`|
| `crm:E39_Actor1` | `foaf:homepage` | `foaf:Document1`|
| `crm:E63_Beginning_of_Existence1` | `crm:P4_has_time-span` | `crm:E52_Time-Span1`|
| `crm:E64_End_of_Existence1` | `crm:P4_has_time-span` | `crm:E52_Time-Span2`|
| `crm:E82_Actor_Appellation1` | `crm:P2_has_type` | `crm:E55_Type1`|
