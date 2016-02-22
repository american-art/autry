## AutryMakers_Sheet1

### PyTransforms
#### _ObjectURI_
From column: _ObjectID_
>``` python
return "object/"+getValue("ObjectID")
```

#### _NationalityURI_
From column: _Nationality_
>``` python
if getValue("Nationality"):
    return "thesauri/nationality/"+getValue("Nationality").replace(" ","-")
else:
    return ""
```

#### _ProductionURI_
From column: _ObjectURI_
>``` python
return getValue("ObjectURI")+"/production"
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _Dates_ | `http://www.cidoc-crm.org/cidoc-crm/P3_has_note` | `E33_Linguistic_Object1`|
| _Maker_ | `rdfs:label` | `E82_Actor_Appellation1`|
| _Nationality_ | `rdfs:label` | `E74_Group1`|
| _NationalityURI_ | `uri` | `E74_Group1`|
| _ObjectURI_ | `uri` | `E22_Man-Made_Object1`|
| _ProductionURI_ | `uri` | `E12_Production1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `E12_Production1` | `http://www.cidoc-crm.org/cidoc-crm/P14_carried_out_by` | `E39_Actor1`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P108i_was_produced_by` | `E12_Production1`|
| `E33_Linguistic_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P129_is_about` | `E39_Actor1`|
| `E39_Actor1` | `http://www.cidoc-crm.org/cidoc-crm/P107i_is_current_or_former_member_of` | `E74_Group1`|
| `E39_Actor1` | `http://www.cidoc-crm.org/cidoc-crm/P131_is_identified_by` | `E82_Actor_Appellation1`|
