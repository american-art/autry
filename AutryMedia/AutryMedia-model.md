# AutryMedia.csv

## Add Column

## Add Node/Literal

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


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _AutryObjectURL_ | `uri` | `foaf:Document1`|
| _AutryObjectURLCopy_ | `rdfs:label` | `foaf:Document1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _imagelink_ | `uri` | `crm:E38_Image1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E22_Man-Made_Object1` | `crm:P138i_has_representation` | `crm:E38_Image1`|
| `crm:E22_Man-Made_Object1` | `foaf:homepage` | `foaf:Document1`|
