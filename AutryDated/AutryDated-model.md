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

#### _StartDateFormatted_
From column: _EARLIEST_YEAR_
``` python
if getValue("EARLIEST_YEAR"):
    return "01-01-"+getValue("EARLIEST_YEAR")
else:
    return ""
```

#### _EndDateFormatted_
From column: _LATEST_YEAR_
``` python
if getValue("LATEST_YEAR"):
    return "12-31-"+getValue("LATEST_YEAR")
else:
    return ""
```

#### _DateLabel_
From column: _Dated_
``` python
if getValue("StartDateFormatted") or getValue("EndDateFormatted"):
    return getValue("StartDateFormatted") + " to " + getValue("EndDateFormatted")
else:
    return ""
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _DateLabel_ | `rdfs:label` | `crm:E52_Time-Span1`|
| _EndDateFormatted_ | `crm:P82b_end_of_the_end` | `crm:E52_Time-Span1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _ProductionTimespanURI_ | `uri` | `crm:E52_Time-Span1`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
| _StartDateFormatted_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E12_Production1` | `crm:P4_has_time-span` | `crm:E52_Time-Span1`|
| `crm:E22_Man-Made_Object1` | `crm:P108i_was_produced_by` | `crm:E12_Production1`|
