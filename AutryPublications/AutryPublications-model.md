# AutryPublications.csv

## Add Column

## Add Node/Literal

## PyTransforms
#### _ObjectURI_
From column: _ObjectID_
``` python
return UM.uri_from_fields("object/",getValue("ObjectID"))
```

#### _TitleLabel_
From column: _Title_
``` python
return getValue("Title")
```

#### _TitleURI_
From column: _ObjectURI_
``` python
return UM.uri_from_fields("thesauri/title/",getValue("Title"))
```

#### _URLURI_
From column: _WorldCatURL_
``` python
if getValue("WorldCatURL"):
    return getValue("WorldCatURL")
else:
    return ""
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _Title_ | `rdfs:label` | `crm:E35_Title1`|
| _TitleLabel_ | `rdfs:label` | `crm:E22_Man-Made_Object1`|
| _TitleURI_ | `uri` | `crm:E35_Title1`|
| _URLURI_ | `uri` | `foaf:Document1`|
| _WorldCatURL_ | `rdfs:label` | `foaf:Document1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E22_Man-Made_Object1` | `crm:P102_has_title` | `crm:E35_Title1`|
| `crm:E22_Man-Made_Object1` | `foaf:homepage` | `foaf:Document1`|
