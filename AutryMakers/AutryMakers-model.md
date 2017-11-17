# AutryMakers.csv

## Add Column

## Add Node/Literal
#### Literal Node: `http://vocab.getty.edu/aat/300404670`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`

#### Literal Node: `http://vocab.getty.edu/aat/300379842`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`


## PyTransforms
#### _ObjectURI_
From column: _ObjectID_
``` python
return UM.uri_from_fields("object/", getValue("ObjectID"))
```

#### _MakerURI_
From column: _MakerID_
``` python
if getValue("MakerID") != 'NULL':
    return  UM.uri_from_fields("maker/", getValue("MakerID"))
else:
    return ''
```

#### _ProductionURI_
From column: _ObjectURI_
``` python
return getValue("ObjectURI") + "/production"
```

#### _PrefIdURI_
From column: _MakerID_
``` python
if getValue("MakerID"):
    return getValue("MakerURI")+"/pref_id"
else:
    return ""
```

#### _Id_Label_
From column: _MakerID_
``` python
return getValue("MakerID")
```

#### _MakerNameURI_
From column: _Maker_
``` python
if getValue("MakerURI") != 'NULL':
    return getValue("MakerURI") + "/name"
else:
    return ''
```

#### _NameCopy_
From column: _Maker_
``` python
return getValue("Maker")
```

#### _NameLabel_
From column: _Maker_
``` python
return getValue("Maker")
```

#### _UlanURI_
From column: _ULAN_ID_
``` python
if getValue("ULAN_ID"):
    return "http://vocab.getty.edu/ulan/"+getValue("ULAN_ID")
else:
    return ""
```

#### _DeathURI_
From column: _Dates_
``` python
time = getValue("Dates").replace(' ', '').lower()
dash_index = time.find('-')

if (time == 'NULL') or ('founded' in time) or ('circa' in time) or ('active' in time) or ('established' in time) or ('born' in time):
    return ''

if dash_index != -1:
    return getValue("MakerURI") + "/death"

return ''
```

#### _DeathTimespanURI_
From column: _DeathURI_
``` python
time = getValue("Dates").replace(' ', '').lower()
dash_index = time.find('-')

if (time == 'NULL') or ('founded' in time) or ('circa' in time) or ('active' in time) or ('established' in time) or ('born' in time):
    return ''

if dash_index != -1:
    return getValue("MakerURI") + "/death_timespan"

return ''
```

#### _DeathYear_
From column: _Dates_
``` python
time = getValue("Dates").replace(' ', '').lower()
dash_index = time.find('-')

if (time == 'NULL') or ('founded' in time) or ('circa' in time) or ('active' in time) or ('established' in time) or ('born' in time):
    return ''

if dash_index != -1:
    return time[dash_index+1:dash_index+5]

return ''
```

#### _DeathDateBegin_
From column: _DeathYear_
``` python
if getValue("DeathYear") != '':
    return getValue("DeathYear") + "-01-01"
else:
    return ''
```

#### _deathDateEnd_
From column: _DeathDateBegin_
``` python
if getValue("DeathYear") != '':
    return getValue("DeathYear") + "-12-31"
else:
    return ''
```

#### _BirthURI_
From column: _Dates_
``` python
time = getValue("Dates").replace(' ', '').lower()
dash_index = time.find('-')

if (time == 'NULL') or ('founded' in time) or ('circa' in time) or ('active' in time) or ('established' in time):
    return ''

if 'born' in time:
    born_index = time.find('born')
    return getValue("MakerURI") + "/birth"

if dash_index != -1:
    return getValue("MakerURI") + "/birth"

return ''
```

#### _BirthTimespanURI_
From column: _BirthURI_
``` python
time = getValue("Dates").replace(' ', '').lower()
dash_index = time.find('-')

if (time == 'NULL') or ('founded' in time) or ('circa' in time) or ('active' in time) or ('established' in time):
    return ''

if 'born' in time:
    born_index = time.find('born')
    return getValue("MakerURI") + "/birth_timespan"

if dash_index != -1:
    return getValue("MakerURI") + "/birth_timespan"

return ''
```

#### _BirthYear_
From column: _Dates_
``` python
time = getValue("Dates").replace(' ', '').lower()
dash_index = time.find('-')

if (time == 'NULL') or ('founded' in time) or ('circa' in time) or ('active' in time) or ('established' in time):
    return ''

if 'born' in time:
    born_index = time.find('born')
    return time[born_index + 4: born_index + 9]

if dash_index != -1:
    return time[dash_index-4:dash_index]

return ''
```

#### _BirthDateBegin_
From column: _BirthYear_
``` python
if getValue("BirthYear") != '':
    return getValue("BirthYear") + "-01-01"
else:
    return ''
```

#### _BirthDateEnd_
From column: _BirthDateBegin_
``` python
if getValue("BirthYear") != '':
    return getValue("BirthYear") + "-12-31"
else:
    return ''
```

#### _NationalityURI_
From column: _Nationality_
``` python
if (getValue("Nationality") != "NULL") and (getValue("Nationality") != ''):
    return UM.uri_from_fields("thesauri/nationality/", getValue("Nationality"))
else:
    return ''
```

#### _UrlURI_
From column: _AutryMakerURL_
``` python
if getValue("AutryMakerURL"):
    return getValue("AutryMakerURL")
else:
    return ""
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _AutryMakerURL_ | `rdfs:label` | `foaf:Document1`|
| _BirthDateBegin_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span2`|
| _BirthDateEnd_ | `crm:P82b_end_of_the_end` | `crm:E52_Time-Span2`|
| _BirthTimespanURI_ | `uri` | `crm:E52_Time-Span2`|
| _BirthURI_ | `uri` | `crm:E63_Beginning_of_Existence1`|
| _BirthYear_ | `rdfs:label` | `crm:E52_Time-Span2`|
| _DeathDateBegin_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span1`|
| _DeathTimespanURI_ | `uri` | `crm:E52_Time-Span1`|
| _DeathURI_ | `uri` | `crm:E64_End_of_Existence1`|
| _DeathYear_ | `rdfs:label` | `crm:E52_Time-Span1`|
| _Id_Label_ | `rdfs:label` | `crm:E42_Identifier1`|
| _Maker_ | `rdfs:label` | `crm:E39_Actor1`|
| _MakerID_ | `rdf:value` | `crm:E42_Identifier1`|
| _MakerNameURI_ | `uri` | `crm:E82_Actor_Appellation1`|
| _MakerURI_ | `uri` | `crm:E39_Actor1`|
| _NameCopy_ | `rdf:value` | `crm:E82_Actor_Appellation1`|
| _NameLabel_ | `rdfs:label` | `crm:E82_Actor_Appellation1`|
| _Nationality_ | `rdfs:label` | `crm:E74_Group1`|
| _NationalityURI_ | `uri` | `crm:E74_Group1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _PrefIdURI_ | `uri` | `crm:E42_Identifier1`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
| _ULAN_ID_ | `rdfs:label` | `skos:Concept1`|
| _UlanURI_ | `uri` | `skos:Concept1`|
| _UrlURI_ | `uri` | `foaf:Document1`|
| _deathDateEnd_ | `crm:P82b_end_of_the_end` | `crm:E52_Time-Span1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E12_Production1` | `crm:P14_carried_out_by` | `crm:E39_Actor1`|
| `crm:E22_Man-Made_Object1` | `crm:P108i_was_produced_by` | `crm:E12_Production1`|
| `crm:E39_Actor1` | `crm:P1_is_identified_by` | `crm:E42_Identifier1`|
| `crm:E39_Actor1` | `crm:P92i_was_brought_into_existence_by` | `crm:E63_Beginning_of_Existence1`|
| `crm:E39_Actor1` | `crm:P93i_was_taken_out_of_existence_by` | `crm:E64_End_of_Existence1`|
| `crm:E39_Actor1` | `crm:P107i_is_current_or_former_member_of` | `crm:E74_Group1`|
| `crm:E39_Actor1` | `crm:P131_is_identified_by` | `crm:E82_Actor_Appellation1`|
| `crm:E39_Actor1` | `skos:exactMatch` | `skos:Concept1`|
| `crm:E39_Actor1` | `foaf:homepage` | `foaf:Document1`|
| `crm:E42_Identifier1` | `crm:P2_has_type` | `http://vocab.getty.edu/aat/300404670`|
| `crm:E63_Beginning_of_Existence1` | `crm:P4_has_time-span` | `crm:E52_Time-Span2`|
| `crm:E64_End_of_Existence1` | `crm:P4_has_time-span` | `crm:E52_Time-Span1`|
| `crm:E74_Group1` | `crm:P2_has_type` | `http://vocab.getty.edu/aat/300379842`|
| `crm:E82_Actor_Appellation1` | `crm:P2_has_type` | `http://vocab.getty.edu/aat/300404670`|
