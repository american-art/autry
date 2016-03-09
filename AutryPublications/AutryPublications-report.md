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


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _CompleteWorldCatURL_ | `uri` | `E31_Document1`|
| _ObjectURI_ | `uri` | `E22_Man-Made_Object1`|
| _Title_ | `rdfs:label` | `E35_Title1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P70i_is_documented_in` | `E31_Document1`|
| `E31_Document1` | `http://www.cidoc-crm.org/cidoc-crm/P102_has_title` | `E35_Title1`|
