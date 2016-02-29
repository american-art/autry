## AutryMedia_Sheet1

### PyTransforms
#### _ObjectURI_
From column: _ObjectID_
>``` python
return "object/"+getValue("ObjectID")
```

#### _CaptionURI_MainImage_
From column: _Caption_
>``` python
if getValue("Caption") and getValue("SortOrder")=='1':
    return getValue("ObjectURI")+"/image/"+getValue("SortOrder")+"/caption"
else:
    return ""
```

#### _CreditLineURI_MainImage_
From column: _CreditLine_
>``` python
if getValue("CreditLine_MainImage"):
    return getValue("ObjectURI")+"/image/"+getValue("SortOrder")+"/CreditLine"
else:
    return ""
```

#### _PrimaryImageLink_
From column: _ImageLink_
>``` python
if getValue("SortOrder") == '1':
    return getValue("ImageLink")
else:
    return ""
```

#### _OtherImageLink_
From column: _PrimaryImageLink_
>``` python
if getValue("SortOrder") == '1':
    return ""
else:
    return getValue("ImageLink")
```

#### _Caption_MainImage_
From column: _Caption_
>``` python
if getValue("Caption") and getValue("SortOrder")=='1':
    return getValue("Caption")
else:
    return ""
```

#### _CaptionURI_OtherImage_
From column: _CaptionURI_MainImage_
>``` python
if getValue("Caption") and getValue("SortOrder")!='1':
    return getValue("ObjectURI")+"/image/"+getValue("SortOrder")+"/caption"
else:
    return ""
```

#### _Caption_OtherImage_
From column: _CaptionURI_OtherImage_
>``` python
if getValue("Caption") and getValue("SortOrder")!='1':
    return getValue("Caption")
else:
    return ""
```

#### _CreditLine_MainImage_
From column: _CreditLine_
>``` python
if getValue("CreditLine") and getValue("SortOrder")==1:
    return getValue(CreditLine)
else:
    return ""
```

#### _CreditLineURI_OtherImage_
From column: _CreditLineURI_MainImage_
>``` python
if getValue("CreditLine") and getValue("SortOrder")!='1':
    return getValue("ObjectURI")+"/image/"+getValue("SortOrder")+"/CreditLine"
else:
    return ""
```

#### _CreditLine_OtherImage_
From column: _CreditLineURI_OtherImage_
>``` python
if getValue("CreditLineURI_OtherImage"):
    return getValue("CreditLine")
else:
    return ""
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _CaptionURI_ | `uri` | `E33_Linguistic_Object1`|
| _Caption_MainImage_ | `http://www.cidoc-crm.org/cidoc-crm/P3_has_note` | `E33_Linguistic_Object1`|
| _Caption_OtherImage_ | `http://www.cidoc-crm.org/cidoc-crm/P3_has_note` | `E33_Linguistic_Object3`|
| _Caption_OtherImage_ | `uri` | `E33_Linguistic_Object3`|
| _CreditLineURI_ | `uri` | `E33_Linguistic_Object2`|
| _CreditLineURI_OtherImage_ | `uri` | `E33_Linguistic_Object4`|
| _CreditLine_MainImage_ | `http://www.cidoc-crm.org/cidoc-crm/P3_has_note` | `E33_Linguistic_Object2`|
| _CreditLine_OtherImage_ | `http://www.cidoc-crm.org/cidoc-crm/P3_has_note` | `E33_Linguistic_Object4`|
| _ObjectURI_ | `uri` | `E22_Man-Made_Object1`|
| _OtherImageLink_ | `uri` | `E38_Image2`|
| _PrimaryImageLink_ | `uri` | `E38_Image1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `E22_Man-Made_Object1` | `bmo:PX_has_main_representation` | `E38_Image1`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P138i_has_representation` | `E38_Image2`|
| `E33_Linguistic_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P129_is_about` | `E38_Image1`|
| `E33_Linguistic_Object2` | `http://www.cidoc-crm.org/cidoc-crm/P129_is_about` | `E38_Image1`|
| `E33_Linguistic_Object3` | `http://www.cidoc-crm.org/cidoc-crm/P129_is_about` | `E38_Image2`|
| `E33_Linguistic_Object4` | `http://www.cidoc-crm.org/cidoc-crm/P129_is_about` | `E38_Image2`|
