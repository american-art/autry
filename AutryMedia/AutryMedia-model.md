# AutryMedia.csv

## Add Column

## Add Node/Literal
#### Literal Node: `http://vocab.getty.edu/aat/300026687`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`


## PyTransforms
#### _ObjectURI_
From column: _ObjectID_
``` python
return UM.uri_from_fields("object/", getValue("ObjectID"))
```

#### _ObjectIDURI_
From column: _ObjectID_
``` python
return UM.uri_from_fields("object/id/", getValue("ObjectID"))
```

#### _ObjectIDCopy_
From column: _ObjectID_
``` python
return getValue("ObjectID")
```

#### _RepositoryTermsURI_
From column: _ObjectIDURI_
``` python
return "http://vocab.getty.edu/aat/300404621"
```

#### _AutryObjectURLCopy_
From column: _AutryObjectURL_
``` python
return getValue("AutryObjectURL")
```

#### _CreditURI_
From column: _CreditLine_
``` python
return getValue("ImageURI") + "/CreditLine"
```

#### _ImageURI_
From column: _imagelink_
``` python
if getValue("imagelink"):
    return getValue("imagelink")
else:
    return ""
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _AutryObjectURL_ | `uri` | `foaf:Document1`|
| _AutryObjectURLCopy_ | `rdfs:label` | `foaf:Document1`|
| _CreditLine_ | `rdf:value` | `crm:E33_Linguistic_Object1`|
| _CreditURI_ | `uri` | `crm:E33_Linguistic_Object1`|
| _ImageURI_ | `uri` | `crm:E38_Image1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E22_Man-Made_Object1` | `crm:P138i_has_representation` | `crm:E38_Image1`|
| `crm:E22_Man-Made_Object1` | `foaf:homepage` | `foaf:Document1`|
| `crm:E33_Linguistic_Object1` | `crm:P2_has_type` | `http://vocab.getty.edu/aat/300026687`|
| `crm:E38_Image1` | `crm:P67i_is_referred_to_by` | `crm:E33_Linguistic_Object1`|
