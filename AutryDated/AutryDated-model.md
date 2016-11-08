## AutryDated_Sheet1

### PyTransforms
#### _ObjectURI_
From column: _ObjectID_
>``` python
return "object/"+getValue("ObjectID")
```

#### _ProductionURI_
From column: _ObjectURI_
>``` python
return getValue("ObjectURI")+"/production"
```

#### _ProductionDateURI_
From column: _ProductionURI_
>``` python
return getValue("ObjectURI")+"/production/date"
```

#### _BeginISODateXSDFormat_
From column: _EARLIEST_YEAR_
>``` python
return getValue("EARLIEST_YEAR") + "-01-01"
```

#### _EndISODateXSDFormat_
From column: _LATEST_YEAR_
>``` python
return getValue("LATEST_YEAR") + "-12-31"
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _BeginDate_ | `crm:P82_at_some_time_within` | `crm:E52_Time-Span2`|
| _BeginISODateXSDFormat_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span1`|
| _BeginXSDDate_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span2`|
| _BirthDateURI_ | `uri` | `crm:E52_Time-Span2`|
| _BirthURI_ | `uri` | `crm:E67_Birth1`|
| _ConstituentURI_ | `uri` | `crm:E39_Actor1`|
| _Culture_ | `rdfs:label` | `crm:E74_Group1`|
| _CultureURI_ | `uri` | `crm:E74_Group1`|
| _Dated_ | `crm:P3_has_note` | `crm:E52_Time-Span2`|
| _Dated_ | `crm:P3_has_note` | `crm:E52_Time-Span1`|
| _DeathDateURI_ | `uri` | `crm:E52_Time-Span1`|
| _DeathURI_ | `uri` | `crm:E69_Death1`|
| _DisplayName_ | `rdfs:label` | `crm:E41_Appellation5`|
| _DisplayNameURI_ | `uri` | `crm:E41_Appellation5`|
| _DisplayNameURI_ | `uri` | `crm:E41_Appellation4`|
| _DisplayPersonInstitutionName_ | `rdfs:label` | `crm:E41_Appellation4`|
| _EndDate_ | `crm:P82_at_some_time_within` | `crm:E52_Time-Span1`|
| _EndISODateXSDFormat_ | `crm:P82b_end_of_the_end` | `crm:E52_Time-Span1`|
| _EndXSDDate_ | `crm:P82b_end_of_the_end` | `crm:E52_Time-Span2`|
| _FirstName_ | `rdfs:label` | `crm:E41_Appellation3`|
| _FirstNameAppellationURI_ | `uri` | `crm:E41_Appellation3`|
| _FirstNameURI_ | `uri` | `crm:E55_Type3`|
| _LastName_ | `rdfs:label` | `crm:E41_Appellation1`|
| _LastNameAppellationURI_ | `uri` | `crm:E41_Appellation1`|
| _LastNameURI_ | `uri` | `crm:E55_Type1`|
| _MiddleName_ | `rdfs:label` | `crm:E41_Appellation2`|
| _MiddleNameAppellationURI_ | `uri` | `crm:E41_Appellation2`|
| _MiddleNameURI_ | `uri` | `crm:E55_Type2`|
| _NameType_ | `rdfs:label` | `crm:E55_Type3`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _PlacePublished_ | `rdfs:label` | `crm:E44_Place_Appellation1`|
| _PlacePublishedURI_ | `uri` | `crm:E44_Place_Appellation1`|
| _PrimaryTitle_ | `rdfs:label` | `crm:E35_Title2`|
| _PrimaryTitleTranslationType_ | `rdfs:label` | `crm:E55_Type2`|
| _PrimaryTitleURI_ | `uri` | `crm:E35_Title2`|
| _ProductionDateURI_ | `uri` | `crm:E52_Time-Span1`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
| _ReferenceURI_ | `uri` | `crm:E31_Document1`|
| _SecondaryTitle_ | `rdfs:label` | `crm:E35_Title1`|
| _SecondaryTitleTranslateType_ | `rdfs:label` | `crm:E55_Type4`|
| _SecondaryTitleTranslateTypeURI_ | `uri` | `crm:E55_Type4`|
| _SecondaryTitleType_ | `rdfs:label` | `crm:E55_Type1`|
| _SecondaryTitleURI_ | `uri` | `crm:E35_Title1`|
| _SubTitleTranslateType_ | `rdfs:label` | `crm:E55_Type5`|
| _SubTitleTranslateTypeURI_ | `uri` | `crm:E55_Type5`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E12_Production1` | `crm:P4_has_time-span` | `crm:E52_Time-Span1`|
| `crm:E22_Man-Made_Object1` | `crm:P108i_was_produced_by` | `crm:E12_Production1`|
