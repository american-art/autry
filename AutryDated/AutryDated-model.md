## AutryDated_Sheet1

### PyTransforms
#### _ObjectURI_
From column: _ObjectID_
>``` python
return "object/"+getValue("ObjectID")
```

#### _ProductionURI_
From column: _ObjectURI_
>``` python
return getValue("ObjectURI")+"/production"
```

#### _ProductionDateURI_
From column: _ProductionURI_
>``` python
return getValue("ObjectURI")+"/production/date"
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _Dated_ | `http://www.cidoc-crm.org/cidoc-crm/P3_has_note` | `E52_Time-Span1`|
| _EARLIEST_YEAR_ | `http://www.cidoc-crm.org/cidoc-crm/P82a_begin_of_the_begin` | `E52_Time-Span1`|
| _LATEST_YEAR_ | `http://www.cidoc-crm.org/cidoc-crm/P82b_end_of_the_end` | `E52_Time-Span1`|
| _ObjectURI_ | `uri` | `E22_Man-Made_Object1`|
| _ProductionDateURI_ | `uri` | `E52_Time-Span1`|
| _ProductionURI_ | `uri` | `E12_Production1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `E12_Production1` | `http://www.cidoc-crm.org/cidoc-crm/P4_has_time-span` | `E52_Time-Span1`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P108i_was_produced_by` | `E12_Production1`|
