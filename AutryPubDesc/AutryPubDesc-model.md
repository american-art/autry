# AutryPubDesc_Sheet1

## Add Column

## Add Node/Literal

## PyTransforms
#### _ObjectURI_
From column: _ObjectID_
``` python
return UM.uri_from_fields("object/", getValue("ObjectID"))

```

#### _PreferredTermsURI_
From column: _PublicDescription_
``` python
return "http://vocab.getty.edu/aat/300404670"
```

#### _DescriptionAATURI_
From column: _PublicDescription_
``` python
return "http://vocab.getty.edu/aat/300080091"
```

#### _DescriptionURI_
From column: _PublicDescription_
``` python
return getValue("ObjectURI") + "/description"
```

#### _PublicDescriptionCopy_
From column: _PublicDescription_
``` python
return getValue("PublicDescription")
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _DescriptionAATURI_ | `uri` | `crm:E55_Type1`|
| _DescriptionURI_ | `uri` | `crm:E33_Linguistic_Object1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _PreferredTermsURI_ | `uri` | `crm:E55_Type2`|
| _PublicDescription_ | `dc:description` | `crm:E22_Man-Made_Object1`|
| _PublicDescriptionCopy_ | `rdf:value` | `crm:E33_Linguistic_Object1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E22_Man-Made_Object1` | `crm:P129i_is_subject_of` | `crm:E33_Linguistic_Object1`|
| `crm:E33_Linguistic_Object1` | `crm:P2_has_type` | `crm:E55_Type1`|
| `crm:E33_Linguistic_Object1` | `crm:P2_has_type` | `crm:E55_Type2`|
