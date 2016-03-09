## AutryObjects_Sheet1

### PyTransforms

#### _ObjectURI_
From column: _ObjectID_
>``` python
return "object/"+getValue("ObjectID")
```

#### _TypeURI_
From column: _ObjectName_
>``` python
if getValue("ObjectName"):
    return "thesauri/type/"+getValue("ObjectName").replace(" ","-").replace("(","").replace(")","")
else:
    return ""
```

#### _TitleURI_
From column: _Title_
>``` python
return getValue("ObjectURI")+"/title"
```

#### _DimensionURI_
From column: _Measurements_
>``` python
return getValue("ObjectURI")+"/dimensions"
```

#### _MaterialsURI_
From column: _Materials_
>``` python
return getValue("ObjectURI")+"/materials"
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _Dated_ | `http://www.cidoc-crm.org/cidoc-crm/P3_has_note` | `E52_Time-Span1`|
| _DimensionURI_ | `uri` | `E54_Dimension1`|
| _Materials_ | `http://www.cidoc-crm.org/cidoc-crm/P3_has_note` | `E57_Material1`|
| _MaterialsURI_ | `uri` | `E57_Material1`|
| _Measurements_ | `http://www.cidoc-crm.org/cidoc-crm/P3_has_note` | `E54_Dimension1`|
| _ObjectName_ | `rdfs:label` | `E55_Type1`|
| _ObjectURI_ | `uri` | `E22_Man-Made_Object1`|
| _ProductionDateURI_ | `uri` | `E52_Time-Span1`|
| _ProductionURI_ | `uri` | `E12_Production1`|
| _Title_ | `rdfs:label` | `E35_Title1`|
| _TitleURI_ | `uri` | `E35_Title1`|
| _TypeURI_ | `uri` | `E55_Type1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `E12_Production1` | `http://www.cidoc-crm.org/cidoc-crm/P4_has_time-span` | `E52_Time-Span1`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P102_has_title` | `E35_Title1`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P108i_was_produced_by` | `E12_Production1`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P2_has_type` | `E55_Type1`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P43_has_dimension` | `E54_Dimension1`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P46_is_composed_of` | `E57_Material1`|
