# Ignition Widget Builder

A project to create reusable Perspective views/widgets for Ignition SCADA systems.

## Project Status

| Widget | Status |
|--------|--------|
| Caploader Widget | Complete |
| Pallet Widget | Complete |
| Filler Widget | Complete |
| Washer Widget | Complete |
| Tank Widget | Complete |
| Vat Widget | Complete |
| Labeler Widget | Complete |
| Packager Widget | Complete |
| Sealer Widget | Complete |
| Workstation Widget | Complete |
| Work Order Widget | Complete |
| Reference Analysis | Complete |
| Documentation | Complete |

## Files

```
Ignition-Widget-Builder/
├── _ref/
│   ├── reference-UDT-view.json          # Styling & structure reference
│   ├── sparkline-reference-udt-view.json # Sparkline implementation reference
│   ├── caploader-data-tag-structure.json # Caploader UDT tag structure
│   ├── full-udt-reference.json          # Complete UDT definitions
│   ├── widget-design.txt                 # Layout/data display inspiration
│   ├── work-order-references.json        # Work Order UDT tag structure
│   └── time-metrics-component.json       # Reusable time breakdown bar component
├── caploader-widget-view.json            # Cap Loader widget
├── pallet-widget-view.json               # Pallet widget
├── filler-widget-view.json               # Filler widget
├── washer-widget-view.json               # Washer widget
├── tank-widget-view.json                 # Tank widget (process-focused)
├── vat-widget-view.json                  # Vat widget (with work order)
├── labeler-widget-view.json              # Labeler widget
├── packager-widget-view.json             # Packager widget
├── sealer-widget-view.json               # Sealer widget
├── workstation-widget-view.json          # Workstation widget
├── workorder-widget-view.json            # Work Order widget
└── README.md                             # This file
```

## Widget Overview

All widgets share a common structure and styling using Framework/Card/* classes.

### Common Features

- **Header Row**: Asset name + current state
- **OEE Gauges**: 4 gauges (OEE, Availability, Performance, Quality)
- **Rate Progress Bar**: Thin bar showing actual vs standard rate
- **Time Breakdown Bar**: Stacked bar showing Run/Idle/Planned/Unplanned time distribution
- **Count Rows**: Infeed, Outfeed, Defect counts
- **OEE Sparkline**: 8-hour trend history

### Styling Classes

All widgets use these Framework classes from reference-UDT-view.json:
- `Framework/Card/Label` - Label text styling
- `Framework/Card/Value` - Value display styling
- `Framework/Card/Row` - Row container styling
- `Framework/Card/ContainerWBorder` - Bordered container for gauges/progress

---

## Caploader Widget

**File:** `caploader-widget-view.json`

OEE monitoring widget for cap loader equipment.

| Feature | Tag Path |
|---------|----------|
| Display Name | `_metadata/assetidentifier/displayname` |
| State | `State/name` |
| OEE Metrics | `_metric/oee`, `availability`, `performance`, `quality` |
| Rate | `_metric/input/rateactual` / `ratestandard` |
| Time Metrics | `_metric/input/timerunning`, `timeidle`, `timedownplanned`, `timedownunplanned` |
| Counts | `_metric/input/countinfeed`, `countoutfeed`, `countdefect` |

**Size:** 320 x 500 px

---

## Pallet Widget

**File:** `pallet-widget-view.json`

OEE monitoring widget for pallet handling equipment.

| Feature | Tag Path |
|---------|----------|
| Display Name | `_metadata/assetidentifier/displayname` |
| State | `State/name`, `State/duration` |
| OEE Metrics | `_metric/oee`, `availability`, `performance`, `quality` |
| Rate | `_metric/input/rateactual` / `ratestandard` |
| Time Metrics | `_metric/input/timerunning`, `timeidle`, `timedownplanned`, `timedownunplanned` |
| Counts | `_metric/input/countinfeed`, `countoutfeed`, `countdefect` |
| Counters | `Counters/infeed`, `Counters/outfeed` |

**Size:** 320 x 500 px

---

## Filler Widget

**File:** `filler-widget-view.json`

OEE monitoring widget for filler equipment.

| Feature | Tag Path |
|---------|----------|
| Display Name | `_metadata/assetidentifier/displayname` |
| State | `State/name`, `State/duration` |
| OEE Metrics | `_metric/oee`, `availability`, `performance`, `quality` |
| Rate | `_metric/input/rateactual` / `ratestandard` |
| Time Metrics | `_metric/input/timerunning`, `timeidle`, `timedownplanned`, `timedownunplanned` |
| Counts | `_metric/input/countinfeed`, `countoutfeed`, `countdefect` |

**Size:** 320 x 500 px

---

## Washer Widget

**File:** `washer-widget-view.json`

OEE monitoring widget for washer equipment.

| Feature | Tag Path |
|---------|----------|
| Asset Name | `_metadata/assetidentifier/assetname` (no displayname) |
| State | `State/name`, `State/type` |
| OEE Metrics | `_metric/oee`, `availability`, `performance`, `quality` |
| Rate | `_metric/input/rateactual` / `ratestandard` |
| Time Metrics | `_metric/input/timerunning`, `timeidle`, `timedownplanned`, `timedownunplanned` |
| Counts | `_metric/input/countinfeed`, `countoutfeed`, `countdefect` |

**Size:** 320 x 500 px

---

## Tank Widget

**File:** `tank-widget-view.json`

Process-focused widget for tank equipment with lot tracking.

| Feature | Tag Path |
|---------|----------|
| Display Name | `_metadata/assetidentifier/displayname` |
| State | `State/name`, `State/duration` |
| OEE | `_metric/oee` |
| Process Data | `Process Data/temperature`, `flowrate`, `weight` |
| Lot Info | `lotnumber/lotnumber`, `lotnumber/item/itemname` |
| Rate | `_metric/input/rateactual` / `ratestandard` |
| Time Metrics | `_metric/input/timerunning`, `timeidle`, `timedownplanned`, `timedownunplanned` |
| Counts | `_metric/input/countinfeed`, `countoutfeed`, `countdefect` |

**Sparkline:** Flow rate trend (instead of OEE)

**Size:** 320 x 560 px

---

## Vat Widget

**File:** `vat-widget-view.json`

Process widget for vat equipment with work order tracking.

| Feature | Tag Path |
|---------|----------|
| Asset Name | `_metadata/assetidentifier/assetname` |
| State | `State/name`, `State/duration` |
| OEE Metrics | `_metric/oee`, `availability`, `performance`, `quality` |
| Process Data | `Process Data/temperature`, `flowrate`, `weight` |
| Work Order | `Work Order/workordernumber`, `quantityactual`, `quantitytarget` |
| Rate | `_metric/input/rateactual` / `ratestandard` |
| Time Metrics | `_metric/input/timerunning`, `timeidle`, `timedownplanned`, `timedownunplanned` |

**Size:** 320 x 560 px

---

## Labeler Widget

**File:** `labeler-widget-view.json`

OEE monitoring widget for labeling equipment.

| Feature | Tag Path |
|---------|----------|
| Display Name | `_metadata/assetidentifier/displayname` |
| State | `State/name` |
| OEE Metrics | `_metric/oee`, `availability`, `performance`, `quality` |
| Rate | `_metric/input/rateactual` / `ratestandard` |
| Time Metrics | `_metric/input/timerunning`, `timeidle`, `timedownplanned`, `timedownunplanned` |
| Counts | `_metric/input/countinfeed`, `countoutfeed`, `countdefect` |

**Size:** 320 x 500 px

---

## Packager Widget

**File:** `packager-widget-view.json`

OEE monitoring widget for packaging equipment.

| Feature | Tag Path |
|---------|----------|
| Display Name | `_metadata/assetidentifier/displayname` |
| State | `State/name` |
| OEE Metrics | `_metric/oee`, `availability`, `performance`, `quality` |
| Rate | `_metric/input/rateactual` / `ratestandard` |
| Time Metrics | `_metric/input/timerunning`, `timeidle`, `timedownplanned`, `timedownunplanned` |
| Counts | `_metric/input/countinfeed`, `countoutfeed`, `countdefect` |

**Size:** 320 x 500 px

---

## Sealer Widget

**File:** `sealer-widget-view.json`

OEE monitoring widget for sealing equipment.

| Feature | Tag Path |
|---------|----------|
| Display Name | `_metadata/assetidentifier/displayname` |
| State | `State/name` |
| OEE Metrics | `_metric/oee`, `availability`, `performance`, `quality` |
| Rate | `_metric/input/rateactual` / `ratestandard` |
| Time Metrics | `_metric/input/timerunning`, `timeidle`, `timedownplanned`, `timedownunplanned` |
| Counts | `_metric/input/countinfeed`, `countoutfeed`, `countdefect` |

**Size:** 320 x 500 px

---

## Workstation Widget

**File:** `workstation-widget-view.json`

OEE monitoring widget for general workstation equipment.

| Feature | Tag Path |
|---------|----------|
| Display Name | `_metadata/assetidentifier/displayname` |
| State | `State/name` |
| OEE Metrics | `_metric/oee`, `availability`, `performance`, `quality` |
| Rate | `_metric/input/rateactual` / `ratestandard` |
| Time Metrics | `_metric/input/timerunning`, `timeidle`, `timedownplanned`, `timedownunplanned` |
| Counts | `_metric/input/countinfeed`, `countoutfeed`, `countdefect` |

**Size:** 320 x 500 px

---

## Work Order Widget

**File:** `workorder-widget-view.json`

Production tracking widget for work order monitoring.

| Feature | Tag Path |
|---------|----------|
| Work Order Number | `workordernumber` |
| Target Quantity | `quantitytarget` |
| Actual Quantity | `quantityactual` |
| Defect Quantity | `quantitydefect` |
| Unit of Measure | `uom` |

**Calculated Values:**
- **Completion %**: `quantityactual / quantitytarget × 100`
- **Yield %**: `(quantityactual - quantitydefect) / quantityactual × 100`
- **Good Quantity**: `quantityactual - quantitydefect`
- **Remaining**: `quantitytarget - quantityactual`

**Placeholders** (for future data):
- Status (header, currently shows "--")
- Started time
- Duration

**Size:** 320 x 420 px

---

## Usage

1. Import the desired `*-widget-view.json` into Perspective
2. Set the `basePath` parameter to your UDT instance path:
   ```
   [default]Path/To/Your/equipment
   ```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `basePath` | String | Root path to the UDT instance |

---

## Reference Analysis

### From `reference-UDT-view.json` (Styling & Structure)

This file provides the authoritative patterns for styling and component structure.

#### CSS Framework Classes

| Class | Usage |
|-------|-------|
| `Framework/Card/Label` | Label text (left side of rows, gauge labels) |
| `Framework/Card/Value` | Value display (right side of rows) |
| `Framework/Card/Row` | Horizontal row container with label/value pairs |
| `Framework/Card/ContainerWBorder` | Bordered container for gauges and progress bars |

#### Component Patterns

**Simple Gauge** (`ia.chart.simple-gauge`):
```json
{
  "position": { "basis": "91.8px" },
  "props": {
    "arc": { "width": 10 },
    "label": { "maxDecimal": 1, "size": 15 },
    "maxValue": 100,
    "minValue": 0,
    "style": { "marginBottom": 0 }
  }
}
```

**Progress Bar** (`ia.display.progress`):
```json
{
  "position": { "basis": "72px" },
  "props": {
    "max": 100,
    "style": { "paddingBottom": 15, "paddingTop": 15 },
    "valueDisplay": { "enabled": true, "format": "0" }
  }
}
```

**Label/Value Row**:
```json
{
  "props": {
    "style": { "classes": "Framework/Card/Row" },
    "wrap": "wrap"
  },
  "children": [
    { "props": { "style": { "classes": "Framework/Card/Label" } }, "position": { "grow": 1 } },
    { "props": { "style": { "classes": "Framework/Card/Value" } }, "position": { "shrink": 0 } }
  ]
}
```

**Gauge Container with Label Row**:
```json
{
  "props": {
    "direction": "column",
    "justify": "center",
    "style": { "classes": "Framework/Card/ContainerWBorder" }
  },
  "children": [
    { "type": "ia.chart.simple-gauge", "position": { "basis": "91.8px" } },
    {
      "type": "ia.container.flex",
      "props": { "style": { "overflow": "visible" } },
      "children": [
        { "props": { "style": { "classes": "Framework/Card/Label", "textAlign": "left" } } },
        { "props": { "style": { "classes": "Framework/Card/Label", "textAlign": "right" } } }
      ]
    }
  ]
}
```

#### Flex Layout Patterns

| Property | Value | Purpose |
|----------|-------|---------|
| `position.basis` | `"91.8px"` | Fixed height for gauges |
| `position.basis` | `"72px"` | Fixed height for progress bars |
| `position.basis` | `"100px"` | Fixed height for gauge rows |
| `position.basis` | `"150px"` | Fixed height for progress containers |
| `position.grow` | `1` | Expand to fill available space |
| `position.shrink` | `0` | Prevent element from shrinking |
| `props.direction` | `"column"` | Vertical stacking |
| `props.justify` | `"center"` | Center content vertically |
| `props.style.overflow` | `"visible"` | Allow gauge overflow |

#### Binding Patterns

**Indirect Tag Binding** (for direct tag values):
```json
{
  "binding": {
    "config": {
      "fallbackDelay": 2.5,
      "mode": "indirect",
      "references": {
        "basePath": "{view.params.basePath}"
      },
      "tagPath": "{basePath}/Folder/tagName"
    },
    "type": "tag"
  }
}
```

**Expression Binding** (for formatted/calculated values):
```json
{
  "binding": {
    "config": {
      "expression": "numberformat(tag({view.params.basePath} + \"/path/to/tag\"), '0.00')"
    },
    "type": "expr"
  }
}
```

**Map Transform** (for value-to-text conversion):
```json
{
  "transforms": [{
    "fallback": "Error",
    "inputType": "scalar",
    "mappings": [
      { "input": 0, "output": "Stopped" },
      { "input": 1, "output": "Running" }
    ],
    "outputType": "scalar",
    "type": "map"
  }]
}
```

---

### From `sparkline-reference-udt-view.json` (Sparkline Pattern)

This file provides the pattern for implementing sparklines with tag history.

#### Custom Property for History Tags

```json
{
  "custom": {
    "history": [
      {
        "aggregate": "MinMax",
        "alias": "OEE"
      }
    ]
  },
  "propConfig": {
    "custom.history[0].path": {
      "binding": {
        "config": {
          "expression": "{view.params.basePath}+'/_metric/oee'"
        },
        "type": "expr"
      }
    }
  }
}
```

#### Sparkline Component (`ia.display.sparkline`)

```json
{
  "type": "ia.display.sparkline",
  "position": { "basis": "80px" },
  "props": {
    "marker": {
      "first": { "size": 0 },
      "high": { "size": 0 },
      "last": { "size": 0 },
      "low": { "size": 0 }
    },
    "style": { "classes": "Framework/Card/ContainerWBorder" }
  }
}
```

#### Tag-History Binding for Points

```json
{
  "binding": {
    "config": {
      "aggregate": "MinMax",
      "avoidScanClassValidation": true,
      "dateRange": {
        "mostRecent": "8",
        "mostRecentUnits": "HOUR"
      },
      "enableValueCache": true,
      "returnFormat": "Wide",
      "returnSize": { "numRows": "100", "type": "FIXED" },
      "tags": "{view.custom.history}",
      "valueFormat": "DATASET"
    },
    "type": "tag-history"
  }
}
```

#### Dynamic Range with Script Transform

The range.high and range.low properties use tag-history bindings with script transforms to find min/max values from the dataset, then add padding:

```python
# Find max value from dataset
if value is not None and len(value) > 0:
    maxValue = None
    for row in value:
        val = row[1]  # value column is index 1
        if maxValue is None or val > maxValue:
            maxValue = val
    return maxValue
else:
    return 1  # default for OEE
```

Then an expression transform adds 12.5% padding:
```
min(1, {value}+({value}/8))  # for high
max(0, {value}-({value}/8))  # for low
```

---

### From `caploader-data-tag-structure.json` (Data Structure)

Defines the UDT tag hierarchy for caploader equipment.

#### Tag Structure

```
caploader/
├── _metadata/
│   └── assetidentifier/
│       ├── displayname        # Asset display name
│       ├── assetid
│       ├── assetname
│       ├── assetpath
│       ├── assettypename
│       ├── parentassetid
│       └── sortorder
├── _metric/
│   ├── availability           # 0-1 decimal
│   ├── performance            # 0-1 decimal
│   ├── quality                # 0-1 decimal
│   ├── oee                    # 0-1 decimal
│   └── input/
│       ├── countinfeed        # Parts in
│       ├── countoutfeed       # Parts out
│       ├── countdefect        # Defective parts
│       ├── rateactual         # Current rate (ppm)
│       ├── ratestandard       # Target rate (ppm)
│       ├── timerunning
│       ├── timeidle
│       ├── timedownplanned
│       └── timedownunplanned
├── State/
│   ├── code
│   ├── type                   # State category
│   └── name                   # Display name
├── Input/
│   └── infeedtooutfeed
└── Widget/
    └── (navigation/config metadata)
```

#### Key Data Points Used

| Tag Path | Display | Format |
|----------|---------|--------|
| `_metadata/assetidentifier/displayname` | Header label | Text |
| `State/name` | Header value | Text |
| `_metric/oee` | OEE gauge | × 100 for % |
| `_metric/availability` | Availability gauge | × 100 for % |
| `_metric/performance` | Performance gauge | × 100 for % |
| `_metric/quality` | Quality gauge | × 100 for % |
| `_metric/input/rateactual` | Rate progress value | Integer |
| `_metric/input/ratestandard` | Rate progress max | Integer |
| `_metric/input/countinfeed` | Count row | #,##0 |
| `_metric/input/countoutfeed` | Count row | #,##0 |
| `_metric/input/countdefect` | Count row | #,##0 |

---

### From `work-order-references.json` (Work Order Structure)

Defines the UDT tag hierarchy for work order tracking.

#### Tag Structure

```
Work Order/
├── workordernumber      # Display identifier (primary)
├── workorderid          # Internal unique ID
├── assetid              # Associated asset
├── quantitytarget       # Target production quantity
├── quantityactual       # Current actual quantity
├── quantitydefect       # Defect count
├── uom                  # Unit of measure
└── Widget/              # Navigation metadata (standard)
    ├── sizeX, sizeY
    ├── path, pathDetail, pathTrend, pathConfig
    ├── params, title
    ├── hide, priority
```

#### Key Data Points Used

| Tag Path | Display | Format |
|----------|---------|--------|
| `workordernumber` | Header label | Text |
| `quantitytarget` | Target row | #,##0 |
| `quantityactual` | Actual row, progress bar | #,##0 |
| `quantitydefect` | Defect row | #,##0 |
| `uom` | Progress bar label | Text |

#### Future Data Points (Placeholders)

| Desired Tag | Purpose | Current Display |
|-------------|---------|-----------------|
| `status` | Work order state (Active, Complete, etc.) | "--" |
| `starttime` | When work order began | "--" |
| `duration` | Elapsed time | "--" |

---

### From `time-metrics-component.json` (Time Breakdown Bar)

A reusable stacked bar component showing time distribution across run states.

#### Visual Layout

```
┌─────────────────────────────────────┐
│ TIME BREAKDOWN                      │
│ ██████████████░░░▒▒░░               │  ← Proportional stacked bar
│ RUN    IDLE   PLAN   DOWN           │  ← Color-coded legend
└─────────────────────────────────────┘
```

#### Color Coding

| Segment | Color | Tag Path | Meaning |
|---------|-------|----------|---------|
| Running | Green (#4CAF50) | `_metric/input/timerunning` | Productive time |
| Idle | Yellow (#FFC107) | `_metric/input/timeidle` | Waiting/starved |
| Planned | Orange (#FF9800) | `_metric/input/timedownplanned` | Scheduled downtime |
| Unplanned | Red (#F44336) | `_metric/input/timedownunplanned` | Breakdowns/faults |

#### Implementation Pattern

Uses `position.grow` bindings on flex children to create proportional widths:

```json
{
  "position": { "grow": 1 },
  "propConfig": {
    "position.grow": {
      "binding": {
        "type": "expr",
        "config": {
          "expression": "max(0.001, tag({view.params.basePath} + '/_metric/input/timerunning'))"
        }
      }
    }
  },
  "props": {
    "style": { "backgroundColor": "#4CAF50" }
  }
}
```

The `max(0.001, ...)` prevents zero-width segments from collapsing.

#### Component Size

- **Height:** 70px basis (label + 16px bar + legend)
- **Position:** Between Rate row and Count rows

---

### From `widget-design.txt` (Layout Inspiration)

A React component mockup showing the desired data presentation and layout concepts.

#### Data to Display

| Section | Data Points |
|---------|-------------|
| Header | Asset name, current state |
| Primary Metrics | OEE (prominent), Availability, Performance, Quality |
| Rate | Actual vs standard rate as progress bar |
| Counts | Infeed, Outfeed, Defects |

#### Display Types

| Data | Component Type |
|------|---------------|
| OEE, Availability, Performance, Quality | Gauges |
| Rate (actual vs standard) | Progress bar |
| Counts | Label/value rows |
| State | Text value |

#### Layout Concept

- Compact card-style widget
- Gauges arranged in 2×2 grid
- Rate shown as visual progress bar
- Counts as simple label/value pairs

---

## Lessons Learned

### Styling Approach

1. **Use Framework classes** - Don't apply custom inline styles; rely on the existing `Framework/Card/*` classes for consistent appearance across the application

2. **Reference file is authoritative** - The reference-UDT-view.json defines the correct component configurations, sizes, and class usage

3. **Design mockups are conceptual** - Widget-design.txt provides layout inspiration and data selection guidance, not literal styling

### Perspective Patterns

1. **Indirect bindings** - Best for parameterized views; allows the base path to be swapped at runtime

2. **Expression bindings** - Use for calculations (multiply OEE by 100) or formatting (numberformat)

3. **Fixed basis values** - Gauges work best with `basis: "91.8px"`, progress bars with `basis: "72px"`

4. **Overflow visible** - Required on label containers below gauges to prevent clipping

### Data Considerations

1. **OEE as decimal** - Stored as 0-1, multiply by 100 for percentage display in gauges; sparklines use raw 0-1 values

2. **Rate binding** - Both value and max can be bound; max comes from ratestandard tag

3. **Number formatting** - Use `#,##0` for counts with thousands separators

4. **Sparkline history** - Uses custom.history array with dynamically bound path; requires tag history to be enabled on the tag

---

## Future Enhancements

- [ ] Add click actions to navigate to detail views
- [x] Add trend sparklines for OEE history
- [x] Create variants for different equipment types (pallet, filler, washer, tank, vat)
- [x] Create Work Order widget for production tracking
- [ ] Add alarm indicator integration
- [x] Add time-based metrics stacked bar (running, idle, downtime planned/unplanned)
- [ ] Add process data trending for tank/vat widgets
- [ ] Work Order: Add status tag binding when available
- [ ] Work Order: Add start time / duration bindings when available
- [ ] Work Order: Add item/product info when available
