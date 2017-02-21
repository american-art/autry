# AutryCultureMade.csv

## Add Column

## Add Node/Literal

## PyTransforms
#### _ObjectURI_
From column: _ObjectID_
``` python
return "object/"+getValue("ObjectID")
```

#### _ArtistURI_
From column: _Culture_
``` python
return getValue("Culture").replace(" ","-").split("?")[0]
```

#### _CultureURI_
From column: _ArtistURI_
``` python
return "thesauri/culture/" + getValue("Culture").replace(" ","_").split("?")[0]
```

#### _ProductionURI_
From column: _ObjectURI_
``` python
return getValue("ObjectURI")+"/production"
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _ArtistURI_ | `uri` | `crm:E39_Actor1`|
| _Culture_ | `rdfs:label` | `crm:E74_Group1`|
| _CultureURI_ | `uri` | `crm:E74_Group1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E12_Production1` | `crm:P14_carried_out_by` | `crm:E39_Actor1`|
| `crm:E22_Man-Made_Object1` | `crm:P108i_was_produced_by` | `crm:E12_Production1`|
| `crm:E39_Actor1` | `crm:P107i_is_current_or_former_member_of` | `crm:E74_Group1`|
