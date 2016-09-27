## AutryPublications_Sheet1

### PyTransforms
#### _ObjectURI_
From column: _ObjectID_
>``` python
return "object/"+getValue("ObjectID")
```

#### _CompleteWorldCatURL_
From column: _WorldCatURL_
>``` python
ret = getValue("WorldCatURL")
if ret:
    return ret
else:
    return "https://www.worldcat.org/oclc/" + getValue("OCLC_Number")[3:]
```

#### _OCLC_URI_
From column: _OCLC_Number_
>``` python
return getValue("ObjectURI") + "/oclc_number"
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _AutryMakerURL_ | `uri` | `crm:E42_Identifier2`|
| _AutryMakerURL_ | `uri` | `crm:E39_Actor1`|
| _BirthDate_ | `crm:P82_at_some_time_within` | `crm:E52_Time-Span1`|
| _BirthDateURI_ | `uri` | `crm:E50_Date1`|
| _Caption_ | `crm:P3_has_note` | `crm:E22_Man-Made_Object1`|
| _CaptionURI_MainImage_ | `uri` | `crm:E33_Linguistic_Object1`|
| _CaptionURI_OtherImage_ | `uri` | `crm:E33_Linguistic_Object3`|
| _Caption_OtherImage_ | `crm:P3_has_note` | `crm:E33_Linguistic_Object3`|
| _Classification_ | `rdfs:label` | `crm:E55_Type1`|
| _ClassificationURI_ | `uri` | `crm:E55_Type1`|
| _CompleteWorldCatURL_ | `uri` | `crm:E31_Document1`|
| _CompleteWorldCatURL_ | `uri` | `crm:E75_Conceptual_Object_Appellation1`|
| _CompleteWorldCatURL_ | `uri` | `crm:E75_Conceptual_Object_Appellation1`|
| _CreditLineURI_ | `uri` | `crm:E55_Type4`|
| _CreditLineURI_MainImage_ | `uri` | `crm:E33_Linguistic_Object4`|
| _CreditLineURI_OtherImage_ | `uri` | `crm:E33_Linguistic_Object2`|
| _CreditLine_MainImage_ | `crm:P3_has_note` | `crm:E33_Linguistic_Object4`|
| _CreditLine_OtherImage_ | `crm:P3_has_note` | `crm:E33_Linguistic_Object2`|
| _DateBeginValid_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span1`|
| _DateEndValid_ | `crm:P82b_end_of_the_end` | `crm:E52_Time-Span1`|
| _Dated_ | `rdfs:label` | `crm:E52_Time-Span1`|
| _Dates_ | `crm:P3_has_note` | `crm:E33_Linguistic_Object1`|
| _DeathDate_ | `uri` | `crm:E50_Date2`|
| _DeathDateURI_ | `crm:P82_at_some_time_within` | `crm:E52_Time-Span2`|
| _DimensionURI_ | `uri` | `crm:E54_Dimension1`|
| _Dimensions_ | `crm:P3_has_note` | `crm:E54_Dimension1`|
| _ImageLinkURI_ | `uri` | `crm:E42_Identifier1`|
| _Maker_ | `rdfs:label` | `crm:E82_Actor_Appellation1`|
| _Materials_ | `crm:P2_has_type` | `crm:E55_Type2`|
| _Materials_ | `crm:P3_has_note` | `crm:E55_Type2`|
| _MaterialsURI_ | `uri` | `crm:E55_Type2`|
| _MeasurementsURI_ | `uri` | `crm:E55_Type3`|
| _Medium_ | `crm:P3_has_note` | `crm:E57_Material1`|
| _MediumURI_ | `uri` | `crm:E57_Material1`|
| _Nationality_ | `rdfs:label` | `crm:E74_Group1`|
| _NationalityURI_ | `uri` | `crm:E74_Group1`|
| _OCLC_URI_ | `uri` | `crm:E75_Conceptual_Object_Appellation2`|
| _OCLC_URI_ | `uri` | `crm:E75_Conceptual_Object_Appellation2`|
| _ObjectNumber_ | `rdfs:label` | `crm:E42_Identifier2`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _OtherImageLink_ | `uri` | `crm:E38_Image1`|
| _Owner_ | `rdfs:label` | `crm:E40_Legal_Body1`|
| _Owner_ | `rdfs:label` | `crm:E51_Contact_Point1`|
| _Owner_ | `rdfs:label` | `crm:E41_Appellation1`|
| _OwnerURL_ | `uri` | `crm:E41_Appellation1`|
| _OwnerURL_ | `uri` | `crm:E51_Contact_Point1`|
| _OwnerURL_ | `uri` | `crm:E40_Legal_Body1`|
| _PrimaryImageLink_ | `uri` | `crm:E38_Image2`|
| _ProductionDateURI_ | `uri` | `crm:E52_Time-Span1`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
| _PublicDescription_ | `crm:P3_has_note` | `crm:E22_Man-Made_Object1`|
| _Title_ | `rdfs:label` | `crm:E42_Identifier1`|
| _Title_ | `rdfs:label` | `crm:E35_Title1`|
| _TitleURI_ | `uri` | `crm:E35_Title1`|
| _ULAN_ID_ | `rdfs:label` | `crm:E82_Actor_Appellation2`|
| _ULAN_ID_ | `rdfs:label` | `crm:E42_Identifier1`|
| _imagelink_ | `crm:P3_has_note` | `crm:E42_Identifier1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E22_Man-Made_Object1` | `crm:P148_has_component` | `crm:E73_Information_Object1`|
| `crm:E22_Man-Made_Object1` | `crm:P149_is_identified_by` | `crm:E75_Conceptual_Object_Appellation1`|
| `crm:E22_Man-Made_Object1` | `crm:P149_is_identified_by` | `crm:E75_Conceptual_Object_Appellation2`|
| `crm:E73_Information_Object1` | `crm:P1_is_identified_by` | `crm:E42_Identifier1`|
