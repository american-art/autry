## AutryMedia_Sheet1

### PyTransforms
#### _ObjectURI_
From column: _ObjectID_
>``` python
return "object/"+getValue("ObjectID")
```

#### _CaptionURI_
From column: _Caption_
>``` python
return getValue("ObjectURI")+"/image/"+getValue("SortOrder")+"/caption"
```

#### _CreditLineURI_
From column: _CreditLine_
>``` python
return getValue("ObjectURI")+"/image/"+getValue("SortOrder")+"/CreditLine"
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _Caption_ | `http://www.cidoc-crm.org/cidoc-crm/P3_has_note` | `E33_Linguistic_Object1`|
| _CaptionURI_ | `uri` | `E33_Linguistic_Object1`|
| _CreditLine_ | `http://www.cidoc-crm.org/cidoc-crm/P3_has_note` | `E33_Linguistic_Object2`|
| _CreditLineURI_ | `uri` | `E33_Linguistic_Object2`|
| _ImageLink_ | `uri` | `E38_Image1`|
| _ObjectURI_ | `uri` | `E22_Man-Made_Object1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P138i_has_representation` | `E38_Image1`|
| `E33_Linguistic_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P129_is_about` | `E38_Image1`|
| `E33_Linguistic_Object2` | `http://www.cidoc-crm.org/cidoc-crm/P129_is_about` | `E38_Image1`|
