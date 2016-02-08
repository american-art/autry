## AutryPubDesc_Sheet1

### PyTransforms
#### _ObjectURI_
From column: _ObjectID_
>``` python
return "object/"+getValue("ObjectID")
```

#### _PublicDescriptionURI_
From column: _PublicDescription_
>``` python
return getValue("ObjectURI")+"/public_description"
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _ObjectURI_ | `uri` | `E22_Man-Made_Object1`|
| _PublicDescription_ | `http://www.cidoc-crm.org/cidoc-crm/P3_has_note` | `E33_Linguistic_Object1`|
| _PublicDescriptionURI_ | `uri` | `E33_Linguistic_Object1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `E33_Linguistic_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P129_is_about` | `E22_Man-Made_Object1`|
