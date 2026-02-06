# Ignition Widget Builder

A project to create reusable Perspective views/widgets for Ignition SCADA systems.

## Project Status

### Enterprise B Widgets (OEE-focused)

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

### Enterprise C Widgets (Process-focused)

| Category | Count | Status |
|----------|-------|--------|
| Complex Equipment | 9 | Complete |
| Batch Controllers | 2 | Complete |
| Controller Instruments (PV/SP) | 15 | Complete |
| Simple Indicators | 19 | Complete |
| **Total Enterprise C** | **45** | **Complete** |

### Vendor UDT Widgets (OPC-UA Companion Spec)

| Widget | Status |
|--------|--------|
| Compressor Widget | Complete |
| Compressor Config View | Complete |

## Files

```
Ignition-Widget-Builder/
├── _ref/
│   ├── reference-UDT-view.json          # Styling & structure reference
│   ├── sparkline-reference-udt-view.json # Sparkline implementation reference
│   ├── caploader-data-tag-structure.json # Caploader UDT tag structure
│   ├── full-udt-reference.json          # Complete UDT definitions (Enterprise B)
│   ├── entc-udt-reference.json          # Enterprise C UDT definitions
│   ├── widget-design.txt                 # Layout/data display inspiration
│   ├── work-order-references.json        # Work Order UDT tag structure
│   ├── time-metrics-component.json       # Reusable time breakdown bar component
│   └── vendorUDT/
│       └── compressor-UDT.json          # Vendor compressor UDT definition (OPC-UA)
│
├── # Enterprise B Widgets (OEE-focused)
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
│
├── # Enterprise C Widgets (Process-focused)
├── ## Equipment (9)
├── forehearth-widget-view.json           # Glass forehearth
├── inspector-widget-view.json            # Product inspector
├── batchmixer-widget-view.json           # Batch mixer
├── silo-widget-view.json                 # Storage silo
├── lehr-widget-view.json                 # Annealing lehr
├── furnace-widget-view.json              # Glass furnace
├── ismachine-widget-view.json            # IS machine
├── palletizer-widget-view.json           # Palletizer
├── batchcharger-widget-view.json         # Batch charger
├── ## Batch Controllers (2)
├── tff300-widget-view.json               # TFF300 batch controller
├── chr01-widget-view.json                # CHR01 batch controller
├── ## Controller Instruments (15)
├── tic-widget-view.json                  # Temperature controller
├── tic501-widget-view.json               # Temperature controller 501
├── sic-widget-view.json                  # Speed controller
├── sic501-widget-view.json               # Speed controller 501
├── sic-250-002-widget-view.json          # Speed controller (LPM)
├── sic-250-005-widget-view.json          # Speed controller (mL/min)
├── sic-250-006-widget-view.json          # Speed controller (L/min)
├── sic-250-008-widget-view.json          # Speed controller (LPM)
├── sic-7c8a8608-widget-view.json         # Speed controller (SLPM)
├── aic-250-001-widget-view.json          # Analyzer controller (%)
├── aic-250-003-widget-view.json          # Analyzer controller (pH)
├── fic-widget-view.json                  # Flow controller
├── fic-250-002-widget-view.json          # Flow controller (SLPM)
├── fcv-widget-view.json                  # Flow control valve
├── pic-250-001-widget-view.json          # Pressure controller
├── ## Simple Indicators (19)
├── ti-widget-view.json                   # Temperature indicator
├── ti8r-widget-view.json                 # Temperature indicator (°C)
├── fi7f-widget-view.json                 # Flow indicator (LPM)
├── fx7f-widget-view.json                 # Flow indicator (LMH)
├── ai501-widget-view.json                # Analog indicator
├── pcv7x-widget-view.json                # Pressure indicator (psig)
├── hv-250-001-widget-view.json           # Valve position (%)
├── hv-250-003-widget-view.json           # Valve position (%)
├── hv-250-004-widget-view.json           # Valve position (%)
├── dpi7m-widget-view.json                # Differential pressure (psig)
├── wi-250-001-widget-view.json           # Weight indicator (kg)
├── wi17k-widget-view.json                # Weight indicator (kg)
├── chr-widget-view.json                  # Chromatography (with EU)
├── chr01-v-widget-view.json              # Chromatography variant
├── uv8r-widget-view.json                 # UV absorbance (AU)
├── sr8r-widget-view.json                 # Shear rate (s⁻¹)
├── aic-250-002-widget-view.json          # Analyzer status
├── sum500-widget-view.json               # Summation (formula)
├── sum500-47ab92d1-widget-view.json      # Summation (status)
│
├── # Vendor UDT Widgets (OPC-UA Companion Spec)
├── compressor-widget-view.json           # Air compressor operational widget
├── compressor-config-view.json           # Air compressor config/metadata view
│
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

## Compressor Widget

**File:** `compressor-widget-view.json`

Operational monitoring widget for air compressors using vendor OPC-UA companion spec UDTs. Features grouped data sections and visual operating state indicator.

| Section | Feature | Tag Path |
|---------|---------|----------|
| Header | Component Name (tooltip) | `_metadata/Identification/ComponentName` |
| Header | Operating State | `Operational/OperatingState/valueName` |
| Operating State | 2x4 state grid (active = blue) | `Operational/OperatingState/value` + `_metadata/.../enumValues/0-7` |
| Pressures | Outlet pressure + EU | `ProcessFluidCircuit/Outlet/GaugePressure/value` |
| Pressures | Delta pressure + EU | `ProcessFluidCircuit/Delta/GaugePressure/value` |
| Temperatures | Outlet temp + EU | `ProcessFluidCircuit/Outlet/Temperature/value` |
| Temperatures | Oil temp + EU | `Operational/OilTemperature/value` |
| Temperatures | Dew point + EU | `ProcessFluidCircuit/Outlet/DewPoint/value` |
| Motor Current | Current + EU | `ElectricalCircuit/Input/Current/value` |
| Maintenance | Running time progress bar (max 1000 hrs) | `Statistics/RunningTime/value` |

**Dynamic Engineering Units:** Values display with units fetched from `_metadata/.../engineeringUnits/displayName`.

**Operating State Grid:** Each of the 8 enum states is displayed in a 2x4 grid. The active state is highlighted with a blue (#2196F3) background using conditional expression bindings.

**Size:** 320 x 500 px

---

## Compressor Config View

**File:** `compressor-config-view.json`

Configuration/metadata display for air compressor UDTs. Shows all `_metadata` in a wide layout for reference and commissioning.

| Section | Feature | Tag Path |
|---------|---------|----------|
| Header | Component Name | `_metadata/Identification/ComponentName` |
| Identification | Asset ID | `_metadata/Identification/AssetId` |
| Identification | Component Name | `_metadata/Identification/ComponentName` |
| Identification | Device Class | `_metadata/Identification/DeviceClass` |
| Operating State | Data Type | `_metadata/Operational/OperatingState/dataType` |
| Operating State | Enum definitions (0-7) | `_metadata/Operational/OperatingState/enumValues/0-7` |
| Engineering Units | Namespace URI (shared, shown once) | `_metadata/.../engineeringUnits/namespaceUri` |
| Engineering Units | 7 measurements: displayName + unitId | `_metadata/.../engineeringUnits/displayName`, `unitId` |

**Layout:** Side-by-side sections (Identification | Operating State) on top, full-width Engineering Units grid on bottom. All 8 enums in a single row, all 7 EU measurements in a single row.

**Size:** 960 x 380 px

---

---

## Enterprise C Widgets

Enterprise C widgets are process-focused, differing from Enterprise B's OEE-centric approach.

### Key Differences from Enterprise B

| Aspect | Enterprise B | Enterprise C |
|--------|--------------|--------------|
| Metrics | OEE-focused (_metric/oee, availability, performance, quality) | Process-focused (no standard OEE) |
| Asset Name | `_metadata/assetidentifier/displayname` | `Description` tag at root |
| State | `State/name`, `State/duration` | `State/StateCurrent`, `State/StateReason` |
| Data | Time metrics, counts, rates | Process values (PV), setpoints (SP), edge data |

### Widget Categories

#### Category 1: Complex Equipment (9 widgets)

| File | UDT | Key Tags | Size |
|------|-----|----------|------|
| `forehearth-widget-view.json` | Forehearth | State, Status/GobTemp, Status/Temperature | 320×420 |
| `inspector-widget-view.json` | Inspector | State, Production counts (PassCount, RejectCount, Defects) | 320×480 |
| `batchmixer-widget-view.json` | BatchMixer | State, Status/BatchWeight | 320×320 |
| `silo-widget-view.json` | Silo | Status/Material, Status/Level | 320×240 |
| `lehr-widget-view.json` | Lehr | State, Status/BeltSpeed, ZoneTemp1-3 | 320×420 |
| `furnace-widget-view.json` | Furnace | State, Status/Temperature, Status/GlassLevel | 320×360 |
| `ismachine-widget-view.json` | ISMachine | State, Production, Status/MachineSpeed, SectionsActive | 320×480 |
| `palletizer-widget-view.json` | Palletizer | State, Production/ContainersPerPallet, PalletsCompleted | 320×360 |
| `batchcharger-widget-view.json` | BatchCharger | State, Status/FeedRate | 320×320 |

#### Category 2: Batch Controllers (2 widgets)

| File | UDT | Key Tags | Size |
|------|-----|----------|------|
| `tff300-widget-view.json` | TFF300 | RECIPE-NAME, BATCH-ID, FORMULA-NAME | 320×280 |
| `chr01-widget-view.json` | CHR01 | STATE_PV, PHASE_PV, BATCH-ID, RECIPE-NAME, PROD_PV, WASTE_PV | 320×380 |

#### Category 3: Controller Instruments with PV/SP (15 widgets)

| File | UDT | Key Tags | Unit | Size |
|------|-----|----------|------|------|
| `tic-widget-view.json` | TIC | PV_Celsius, SP_Celsius | °C | 320×280 |
| `tic501-widget-view.json` | TIC501 | PV_Celsius, SP_Celsius, MODE | °C | 320×320 |
| `sic-widget-view.json` | SIC | PV_RPM, SP_RPM | RPM | 320×280 |
| `sic501-widget-view.json` | SIC501 | PV_RPM, SP_RPM, MODE | RPM | 320×320 |
| `sic-250-002-widget-view.json` | SIC-250-002 | PV_LPM, SP_LPM, START | LPM | 320×320 |
| `sic-250-005-widget-view.json` | SIC-250-005 | PV_mL_per_min, SP_mL_per_min, START | mL/min | 320×320 |
| `sic-250-006-widget-view.json` | SIC-250-006 | PV_L_per_min, SP_L_per_min, START | L/min | 320×320 |
| `sic-250-008-widget-view.json` | SIC-250-008 | PV_LPM, SP_LPM, START | LPM | 320×320 |
| `sic-7c8a8608-widget-view.json` | SIC-7C8A8608 | PV_SLPM, SP_SLPM, START | SLPM | 320×320 |
| `aic-250-001-widget-view.json` | AIC-250-001 | PV_percent, SP_percent, START | % | 320×320 |
| `aic-250-003-widget-view.json` | AIC-250-003 | PV_pH, SP_pH, START | pH | 320×320 |
| `fic-widget-view.json` | FIC | PV, SP | (generic) | 320×280 |
| `fic-250-002-widget-view.json` | FIC-250-002 | PV_SLPM, SP_SLPM, START | SLPM | 320×320 |
| `fcv-widget-view.json` | FCV | PV, SP | (generic) | 320×280 |
| `pic-250-001-widget-view.json` | PIC-250-001 | PV_psi, SP_psi, START | psi | 320×320 |

#### Category 4: Simple Indicators (19 widgets)

| File | UDT | Key Tags | Unit | Size |
|------|-----|----------|------|------|
| `ti-widget-view.json` | TI | PV | (generic) | 320×200 |
| `ti8r-widget-view.json` | TI8R | Celsius | °C | 320×200 |
| `fi7f-widget-view.json` | FI7F | LPM | LPM | 320×200 |
| `fx7f-widget-view.json` | FX7F | LMH | LMH | 320×200 |
| `ai501-widget-view.json` | AI501 | PV, DESC | (generic) | 320×240 |
| `pcv7x-widget-view.json` | PCV7X | psig | psig | 320×200 |
| `hv-250-001-widget-view.json` | HV-250-001 | PV_percent | % | 320×200 |
| `hv-250-003-widget-view.json` | HV-250-003 | PV_percent | % | 320×200 |
| `hv-250-004-widget-view.json` | HV-250-004 | PV_percent | % | 320×200 |
| `dpi7m-widget-view.json` | DPI7M | psig | psig | 320×200 |
| `wi-250-001-widget-view.json` | WI-250-001 | PV_kg | kg | 320×200 |
| `wi17k-widget-view.json` | WI17K | kg | kg | 320×200 |
| `chr-widget-view.json` | CHR | Description, PV, EU | (dynamic) | 320×280 |
| `chr01-v-widget-view.json` | CHR01-V | Description, PV | (generic) | 320×240 |
| `uv8r-widget-view.json` | UV8R | AU | AU | 320×200 |
| `sr8r-widget-view.json` | SR8R | sec_-1 | s⁻¹ | 320×200 |
| `aic-250-002-widget-view.json` | AIC-250-002 | ACTIVE | (status) | 320×200 |
| `sum500-widget-view.json` | SUM500 | FORMULA-NAME | (text) | 320×200 |
| `sum500-47ab92d1-widget-view.json` | SUM500 variant | STATUS | (text) | 320×200 |

### Enterprise C Tag Path Patterns

| Widget Data | Tag Path |
|-------------|----------|
| Asset Name | `Description` |
| State | `State/StateCurrent` |
| State Reason | `State/StateReason` |
| Status values | `Status/{tagname}` |
| Production | `Production/{tagname}` |
| Process Value | `PV`, `PV_Celsius`, `PV_RPM`, etc. |
| Setpoint | `SP`, `SP_Celsius`, `SP_RPM`, etc. |

### Enterprise C Binding Patterns

**Indirect Tag Binding** (for Description, State):
```json
{
  "binding": {
    "config": {
      "fallbackDelay": 2.5,
      "mode": "indirect",
      "references": { "basePath": "{view.params.basePath}" },
      "tagPath": "{basePath}/Description"
    },
    "type": "tag"
  }
}
```

**Expression Binding** (for Status values with units):
```json
{
  "binding": {
    "config": {
      "expression": "numberformat(tag({view.params.basePath} + \"/Status/Temperature\"), '#,##0.0') + ' °C'"
    },
    "type": "expr"
  }
}
```

---

## Vendor UDT Widgets

Vendor UDT widgets differ from Enterprise B/C by using OPC-UA companion specification tag structures from equipment manufacturers.

### Key Differences from Enterprise B/C

| Aspect | Enterprise B/C | Vendor UDT |
|--------|----------------|------------|
| Asset Name | `_metadata/assetidentifier/displayname` or `Description` | `_metadata/Identification/ComponentName` |
| State | `State/name` or `State/StateCurrent` | `Operational/OperatingState/valueName` |
| Engineering Units | Hardcoded in widget (e.g., "°C", "RPM") | Dynamic from `_metadata/.../engineeringUnits/displayName` |
| Metadata | Minimal (`_metadata/assetidentifier`) | Rich (`_metadata/Identification`, `_metadata/.../engineeringUnits`, enum definitions) |
| Tag Paths | Flat (e.g., `Status/Temperature`) | Hierarchical (e.g., `ProcessFluidCircuit/Outlet/Temperature/value`) |

### Vendor UDT Tag Structure (Compressor)

```
compressor/
├── _metadata/
│   ├── Identification/
│   │   ├── AssetId                    # Asset identifier
│   │   ├── ComponentName              # Display name
│   │   └── DeviceClass                # Equipment classification
│   ├── Operational/
│   │   └── OperatingState/
│   │       ├── dataType               # Value data type
│   │       └── enumValues/0-7         # State name definitions
│   ├── ProcessFluidCircuit/
│   │   ├── Outlet/GaugePressure/engineeringUnits/   # displayName, unitId, namespaceUri
│   │   ├── Outlet/Temperature/engineeringUnits/
│   │   ├── Outlet/DewPoint/engineeringUnits/
│   │   └── Delta/GaugePressure/engineeringUnits/
│   ├── ElectricalCircuit/Input/Current/engineeringUnits/
│   ├── Operational/OilTemperature/engineeringUnits/
│   └── Statistics/RunningTime/
│       ├── description                # Tag description
│       └── engineeringUnits/          # displayName, unitId, namespaceUri
├── Operational/
│   ├── OperatingState/
│   │   ├── value                      # Int4 (0-7)
│   │   ├── valueName                  # String (current state name)
│   │   └── timestamp
│   └── OilTemperature/value           # Float8
├── ProcessFluidCircuit/
│   ├── Outlet/
│   │   ├── GaugePressure/value        # Float8
│   │   ├── Temperature/value          # Float8
│   │   └── DewPoint/value             # Float8
│   └── Delta/
│       └── GaugePressure/value        # Float8
├── ElectricalCircuit/Input/Current/value  # Float8
├── Statistics/RunningTime/value       # Float8
└── Widget/                            # Navigation metadata
```

### Vendor UDT Binding Patterns

**Dynamic Engineering Units** (value + unit from metadata):
```json
{
  "binding": {
    "config": {
      "expression": "numberformat(tag({view.params.basePath} + '/ProcessFluidCircuit/Outlet/GaugePressure/value'), '#,##0.0') + ' ' + tag({view.params.basePath} + '/_metadata/ProcessFluidCircuit/Outlet/GaugePressure/engineeringUnits/displayName')"
    },
    "type": "expr"
  }
}
```

**Conditional State Highlighting** (active state = blue):
```json
{
  "binding": {
    "config": {
      "expression": "if(tag({view.params.basePath} + '/Operational/OperatingState/value') = 0, '#2196F3', 'transparent')"
    },
    "type": "expr"
  }
}
```

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
- [x] Create Enterprise C widgets (45 total)
- [x] Create vendor UDT compressor widget with operating state visualization
- [x] Create vendor UDT compressor config/metadata view
- [ ] Add additional vendor UDT equipment types (pumps, valves, etc.)
