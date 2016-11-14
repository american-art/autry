## AutryMakers_Sheet1

### PyTransforms
#### _ObjectURI_
From column: _ObjectID_
>``` python
return "object/" + getValue("ObjectID").replace('.','_')
```

#### _MakerNameURI_
From column: _Maker_
>``` python
if getValue("Maker") != 'NULL':
    return UM.uri_from_fields("thesauri/display_name/", getValue("Maker"))
else:
    return ''
```

#### _NationalityURI_
From column: _Nationality_
>``` python
return getValue("MakerNameURI") + "/nationality_notes"
```

#### _ProductionURI_
From column: _ObjectURI_
>``` python
return getValue("ObjectURI")+"/production"
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

#### _BirthURI_
From column: _BirthYear_
>``` python
if getValue("BirthYear"):
    return getValue("MakerNameURI") + "/birth"
else:
    return ''
```

#### _DeathURI_
From column: _DeathYear_
>``` python
if getValue("DeathYear"):
    return getValue("MakerNameURI") + "/death"
else:
    return ''
```

#### _BirthYearURI_
From column: _BirthYear_
>``` python
if getValue("BirthURI"):
    return getValue("BirthURI")+"/date"
else:
    return ""
```

#### _DeathYearURI_
From column: _DeathYear_
>``` python
if getValue("DeathURI"):
    return getValue("DeathURI")+"/date"
else:
    return ""
```

#### _ULAN_ID_URI_
From column: _ULAN_ID_
>``` python
if getValue("ULAN_ID"):
    return getValue("MakerNameURI") + "/ulan_id"
else:
    return ''
```

#### _MakerURI_
From column: _ProductionURI_
>``` python
return getValue("ObjectURI")+"/maker"
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _AutryMakerURL_ | `crm:P3_has_note` | `crm:E39_Actor1`|
| _BeginDate_ | `crm:P82_at_some_time_within` | `crm:E52_Time-Span2`|
| _BeginXSDDate_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span2`|
| _BirthDateURI_ | `uri` | `crm:E52_Time-Span2`|
| _BirthURI_ | `uri` | `crm:E67_Birth1`|
| _BirthURI_ | `uri` | `crm:E67_Birth1`|
| _BirthYear_ | `crm:P82_at_some_time_within` | `crm:E52_Time-Span1`|
| _BirthYearURI_ | `uri` | `crm:E52_Time-Span1`|
| _ConstituentURI_ | `uri` | `crm:E39_Actor1`|
| _Culture_ | `rdfs:label` | `crm:E74_Group1`|
| _CultureURI_ | `uri` | `crm:E74_Group1`|
| _Dated_ | `crm:P3_has_note` | `crm:E52_Time-Span2`|
| _DeathDateURI_ | `uri` | `crm:E52_Time-Span1`|
| _DeathURI_ | `uri` | `crm:E69_Death1`|
| _DeathURI_ | `uri` | `crm:E69_Death1`|
| _DeathYear_ | `crm:P82_at_some_time_within` | `crm:E52_Time-Span2`|
| _DeathYearURI_ | `uri` | `crm:E52_Time-Span2`|
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
| _Maker_ | `rdfs:label` | `crm:E41_Appellation1`|
| _MakerNameURI_ | `uri` | `crm:E41_Appellation1`|
| _MakerURI_ | `uri` | `crm:E39_Actor1`|
| _MiddleName_ | `rdfs:label` | `crm:E41_Appellation2`|
| _MiddleNameAppellationURI_ | `uri` | `crm:E41_Appellation2`|
| _MiddleNameURI_ | `uri` | `crm:E55_Type2`|
| _NameType_ | `rdfs:label` | `crm:E55_Type3`|
| _Nationality_ | `rdfs:label` | `crm:E74_Group1`|
| _NationalityURI_ | `uri` | `crm:E74_Group1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _PlacePublished_ | `rdfs:label` | `crm:E44_Place_Appellation1`|
| _PlacePublishedURI_ | `uri` | `crm:E44_Place_Appellation1`|
| _PrimaryTitle_ | `rdfs:label` | `crm:E35_Title2`|
| _PrimaryTitleTranslationType_ | `rdfs:label` | `crm:E55_Type2`|
| _PrimaryTitleURI_ | `uri` | `crm:E35_Title2`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
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
| _ULAN_ID_ | `rdfs:label` | `crm:E42_Identifier1`|
| _ULAN_ID_Type_ | `uri` | `crm:E42_Identifier1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E12_Production1` | `crm:P14_carried_out_by` | `crm:E39_Actor1`|
| `crm:E22_Man-Made_Object1` | `crm:P108i_was_produced_by` | `crm:E12_Production1`|
| `crm:E39_Actor1` | `crm:P131_is_identified_by` | `crm:E41_Appellation1`|
| `crm:E39_Actor1` | `crm:P48_has_preferred_identifier` | `crm:E42_Identifier1`|
| `crm:E39_Actor1` | `crm:P98i_was_born` | `crm:E67_Birth1`|
| `crm:E39_Actor1` | `crm:P100i_died_in` | `crm:E69_Death1`|
| `crm:E39_Actor1` | `crm:P107i_is_current_or_former_member_of` | `crm:E74_Group1`|
| `crm:E67_Birth1` | `crm:P4_has_time-span` | `crm:E52_Time-Span1`|
| `crm:E69_Death1` | `crm:P4_has_time-span` | `crm:E52_Time-Span2`|
