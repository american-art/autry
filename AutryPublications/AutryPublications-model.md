# AutryPublications.csv

## Add Column

## Add Node/Literal

## PyTransforms
#### _ObjectURI_
From column: _ObjectID_
``` python
return UM.uri_from_fields("object/", getValue("ObjectID"))
```

#### _ReferenceURI_
From column: _ObjectURI_
``` python
return getValue("ObjectURI") + "/reference"
```

#### _TitleURI_
From column: _Title_
``` python
return UM.uri_from_fields("thesauri/title/", getValue("Title"))
```

#### _TitleTranslateType_
From column: _TitleURI_
``` python
if getValue("Title") != 'NULL':
    return "Not Translatable"
else:
    return ''
```

#### _TitleTranslateTypeURI_
From column: _TitleTranslateType_
``` python
if getValue("Title") != 'NULL':
    return "thesauri/title_translate_type/not_translatable"
else:
    return ''
```

#### _PagesURI_
From column: _Pages_
``` python
if getValue("Pages") != 'NULL':
    prefix = getValue("ReferenceURI") + "/page/"
    return UM.uri_from_fields(prefix, getValue("Pages"))
else:
    return ''
```

#### _OCLC_NumberURI_
From column: _OCLC_Number_
``` python
if getValue("OCLC_Number") != 'NULL':
    return UM.uri_from_fields("thesauri/oclc_number/", getValue("OCLC_Number"))
else:
    return ''
```

#### _ReferenceTitleURI_
From column: _ReferenceURI_
``` python
return getValue("ReferenceURI") + "/title"
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _OCLC_Number_ | `rdfs:label` | `crm:E42_Identifier1`|
| _OCLC_NumberURI_ | `uri` | `crm:E42_Identifier1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _Pages_ | `rdfs:label` | `crm:E41_Appellation2`|
| _PagesURI_ | `uri` | `crm:E41_Appellation2`|
| _ReferenceTitleURI_ | `uri` | `crm:E41_Appellation1`|
| _ReferenceURI_ | `uri` | `crm:E31_Document1`|
| _Title_ | `rdfs:label` | `crm:E35_Title1`|
| _TitleTranslateType_ | `rdfs:label` | `crm:E55_Type1`|
| _TitleTranslateTypeURI_ | `uri` | `crm:E55_Type1`|
| _TitleURI_ | `uri` | `crm:E35_Title1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E31_Document1` | `crm:P70_documents` | `crm:E22_Man-Made_Object1`|
| `crm:E31_Document1` | `crm:P1_is_identified_by` | `crm:E41_Appellation1`|
| `crm:E31_Document1` | `crm:P106_is_composed_of` | `crm:E41_Appellation2`|
| `crm:E31_Document1` | `crm:P48_has_preferred_identifier` | `crm:E42_Identifier1`|
| `crm:E35_Title1` | `crm:P2_has_type` | `crm:E55_Type1`|
| `crm:E41_Appellation1` | `crm:P106_is_composed_of` | `crm:E35_Title1`|
