## AutryCultureMade_Sheet1

### PyTransforms
#### _ObjectURI_
From column: _ObjectID_
>``` python
return "object/"+getValue("ObjectID")
```

#### _Culture_clean_
From column: _Culture_
>``` python
return getValue("Culture").replace(" ","-").split("?")[0]
```

#### _CultureURI_
From column: _Culture_clean_
>``` python
return "thesauri/culture/"+getValue("Culture_clean")
```

#### _ProductionURI_
From column: _ObjectURI_
>``` python
return getValue("ObjectURI")+"/production"
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _Culture_ | `rdfs:label` | `E4_Period1`|
| _CultureURI_ | `uri` | `E4_Period1`|
| _ObjectURI_ | `uri` | `E22_Man-Made_Object1`|
| _ProductionURI_ | `uri` | `E12_Production1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `E12_Production1` | `http://www.cidoc-crm.org/cidoc-crm/P108_has_produced` | `E22_Man-Made_Object1`|
| `E12_Production1` | `http://www.cidoc-crm.org/cidoc-crm/P10_falls_within` | `E4_Period1`|
