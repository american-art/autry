# AutryDated.csv

## Add Column

## Add Node/Literal

## PyTransforms
#### _ObjectURI_
From column: _ObjectID_
``` python
return UM.uri_from_fields("object/", getValue("ObjectID"))
```

#### _ProductionURI_
From column: _ObjectURI_
``` python
return getValue("ObjectURI") + "/production"
```

#### _ProductionTimespanURI_
From column: _ProductionURI_
``` python
return getValue("ProductionURI") + "/timespan"
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _Dated_ | `rdfs:label` | `crm:E52_Time-Span1`|
| _EARLIEST_YEAR_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span1`|
| _LATEST_YEAR_ | `crm:P82b_end_of_the_end` | `crm:E52_Time-Span1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _ProductionTimespanURI_ | `uri` | `crm:E52_Time-Span1`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E12_Production1` | `crm:P4_has_time-span` | `crm:E52_Time-Span1`|
| `crm:E22_Man-Made_Object1` | `crm:P108i_was_produced_by` | `crm:E12_Production1`|
