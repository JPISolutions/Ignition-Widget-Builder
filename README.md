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
| SP474 Gas Meter Widget | Complete |

### Area Rollup Widgets (Dashboard Components)

| Widget | Status |
|--------|--------|
| Area OEE Widget | Complete |
| Area Production Widget | Complete |
| Area Availability Widget | Complete |
| Area Status Widget | Complete (placeholders) |

### Line Dashboard Widgets

| Widget | Status |
|--------|--------|
| Line KPI Widget | Complete |
| Line Work Order Widget | Complete |
| Line Summary Widget | Complete |
| Line Dashboard (Composed) | Complete |
| Line Dashboard Compact (No-scroll) | Complete |
| Line Dashboard Tabs (dynamic line switcher) | Complete |

### Liquid Processing Dashboard Widgets

| Widget | Status |
|--------|--------|
| LP Tank Status Widget | Complete |
| LP Vat Status Widget | Complete |
| LP Dashboard Compact (No-scroll) | Complete |
| LP Dashboard Tabs (dynamic sub-area switcher) | Complete |

### Packaging Dashboard Widgets

| Widget | Status |
|--------|--------|
| Packaging Dashboard Compact (No-scroll) | Complete |
| Packaging Dashboard Tabs (dynamic labeler line switcher) | Complete |

### Palletizing Dashboard Widgets

| Widget | Status |
|--------|--------|
| Palletizing Equipment Status Widget | Complete |
| Palletizing Dashboard Compact (No-scroll) | Complete |
| Palletizing Dashboard Tabs (dynamic sub-area switcher) | Complete |

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
│       ├── compressor-UDT.json          # Vendor compressor UDT definition (OPC-UA)
│       └── sp474-udt.json              # SP474 gas meter UDT definition
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
├── sp474-widget-view.json               # SP474 gas meter operational widget
│
├── # Area Rollup Widgets (Dashboard Components)
├── area-oee-widget-view.json              # Area OEE & performance gauges + sparkline
├── area-production-widget-view.json       # Area rate & throughput counts
├── area-availability-widget-view.json     # Area time breakdown bar
├── area-status-widget-view.json           # Area status placeholders (missing KPIs)
│
├── # Line Dashboard Widgets
├── line-kpi-widget-view.json              # Line-level OEE gauges + stats + time metrics (wide)
├── line-workorder-widget-view.json        # Line work order horizontal display (wide)
├── line-summary-widget-view.json          # Compact line summary card (for comparison)
├── line-dashboard-view.json               # Composed dashboard using embedded views + flex repeaters
├── line-dashboard-compact-view.json       # No-scroll compact dashboard (fits in tab containers)
├── line-dashboard-tabs-view.json          # Tab wrapper with dynamic filling line tabs + area metrics
│
├── # Liquid Processing Dashboard Widgets
├── lp-tank-status-widget-view.json        # Tank status card (name + state)
├── lp-vat-status-widget-view.json         # Vat status card (name + state + work order + progress)
├── lp-dashboard-compact-view.json         # No-scroll compact dashboard for LP sub-areas
├── lp-dashboard-tabs-view.json            # Tab wrapper with dynamic sub-area tabs + area metrics
│
├── # Packaging Dashboard Widgets
├── pkg-dashboard-compact-view.json        # No-scroll compact dashboard for labeler lines
├── pkg-dashboard-tabs-view.json           # Tab wrapper with dynamic labeler line tabs + area metrics
│
├── # Palletizing Dashboard Widgets
├── pal-equipment-status-widget-view.json  # Generic equipment status card (name + state)
├── pal-dashboard-compact-view.json        # No-scroll compact dashboard for palletizing sub-areas
├── pal-dashboard-tabs-view.json           # Tab wrapper with dynamic sub-area tabs + area metrics
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

## SP474 Gas Meter Widget

**File:** `sp474-widget-view.json`

Operational monitoring widget for SP474 orifice plate gas flow meters, designed for tracking fuel gas consumption in glass manufacturing furnaces. Features a prominent flow rate display, volume comparison grid, and process condition monitoring.

| Section | Feature | Tag Path |
|---------|---------|----------|
| Header | Meter Name (tooltip) | `_metadata/Name` |
| Header | Run Status | `Operational/hasRun_Status/value` |
| Flow Rate | Gauge (max 250) | `Operational/FlowRate/value` |
| Volume | Current hour volume | `Operational/CurrentHourVolume/value` |
| Volume | Previous hour volume | `_metadata/PreviousHourVolume/value` |
| Volume | Current day volume | `Operational/CurrentDayVolume/value` |
| Volume | Previous day volume | `_metadata/PreviousDayVolume/value` |
| Volume | Accumulated total | `Operational/AccumulatedVolume/value` |
| Process Conditions | Static pressure | `Operational/StaticPressure/value` |
| Process Conditions | Differential pressure | `Operational/DifferentialPressure/value` |
| Process Conditions | Gas temperature | `Operational/Temperature/value` |
| Alarms | Active alarm count (red badge when > 0) | `_metadata/ActiveAlarmCount` |
| Footer | Meter configuration status | `Operational/Status/value` |

**Key Visualizations:**
- **Flow Rate Gauge:** Simple gauge (91.8px arc, width 10) with label row beneath; maxValue 250
- **Volume Comparison Grid:** 2x2 grid showing Current Hour vs Previous Hour and Current Day vs Previous Day side-by-side, enabling instant consumption trend recognition
- **Process Conditions Grid:** 3-column layout showing static pressure, differential pressure, and gas temperature that affect measurement accuracy
- **Alarm Indicator:** Conditional red (#F44336) background on alarm count when active alarms > 0

**Values:** All numeric values use `numberformat` expressions without appended engineering units.

**Size:** 320 x 600 px

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

## Area Rollup Widgets

A set of modular widget views designed to be composed on an area-level dashboard in Perspective Designer. Each widget takes a `basePath` parameter pointing to the **area level** of the tag hierarchy.

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `basePath` | String | Root path to the area-level UDT instance (e.g., `[default]Cappy Hour Inc/Site2/fillerproduction`) |

### Areas

| Area Folder | Display Name | Description |
|-------------|-------------|-------------|
| `fillerproduction` | Filler Production | Core filling lines (depalletizer, rinse/fill/cap, washer, dryer) |
| `liquidprocessing` | Liquid Processing | Mix rooms, tank storage, pasteurization vats |
| `packaging` | Packaging | Labeling, grouping, wrapping, sealing |
| `palletizing` | Palletizing | Manual and automated palletizers |

### Widget 1: Area OEE Widget

**File:** `area-oee-widget-view.json`

Primary area health widget showing OEE prominently with supporting A/P/Q metrics and trend.

| Feature | Tag Path |
|---------|----------|
| OEE Gauge | `_metric/oee` |
| Availability Gauge | `_metric/availability` |
| Performance Gauge | `_metric/performance` |
| Quality Gauge | `_metric/quality` |
| OEE Sparkline | `_metric/oee` (8hr tag-history) |

**Size:** 320 x 360 px

---

### Widget 2: Area Production Widget

**File:** `area-production-widget-view.json`

Rate and throughput output metrics for the area.

| Feature | Tag Path |
|---------|----------|
| Rate Progress Bar | `_metric/input/rateactual` / `ratestandard` |
| Throughput Bar | `_metric/input/countoutfeed` / `countdefect` |
| Infeed Count | `_metric/input/countinfeed` |
| Outfeed Count | `_metric/input/countoutfeed` |
| Defect Count | `_metric/input/countdefect` |

**Size:** 320 x 220 px

---

### Widget 3: Area Availability Widget

**File:** `area-availability-widget-view.json`

Time breakdown showing how time is being spent in the area.

| Feature | Tag Path | Color |
|---------|----------|-------|
| Running Time | `_metric/input/timerunning` | Green (#4CAF50) |
| Idle Time | `_metric/input/timeidle` | Yellow (#FFC107) |
| Planned Downtime | `_metric/input/timedownplanned` | Orange (#FF9800) |
| Unplanned Downtime | `_metric/input/timedownunplanned` | Red (#F44336) |

**Size:** 320 x 140 px

---

### Widget 4: Area Status Widget

**File:** `area-status-widget-view.json`

Placeholder widget for KPIs that are not yet available in the tag structure.

| KPI | Current Display | Why It Matters |
|-----|----------------|---------------|
| Equipment Active Count | "-- / --" | Shows area utilization (X of Y running) |
| Active Alarm Count | "--" | Alerts needing attention in this area |
| Active Work Orders | "--" | Production orders in progress |
| MTBF | "-- hrs" | Mean Time Between Failures - reliability metric |
| MTTR | "-- hrs" | Mean Time To Repair - maintenance responsiveness |

**Size:** 320 x 220 px

---

### Dashboard Composition

Place 4 widget instances per area on a Perspective dashboard. For a full site with 4 areas, that's 16 widget instances:

```
┌─── Filler Production ──┬─── Liquid Processing ──┬──── Packaging ────────┬──── Palletizing ──────┐
│ [OEE Widget]           │ [OEE Widget]           │ [OEE Widget]          │ [OEE Widget]          │
│ [Production Widget]    │ [Production Widget]    │ [Production Widget]   │ [Production Widget]   │
│ [Availability Widget]  │ [Availability Widget]  │ [Availability Widget] │ [Availability Widget] │
│ [Status Widget]        │ [Status Widget]        │ [Status Widget]       │ [Status Widget]       │
└────────────────────────┴────────────────────────┴───────────────────────┴───────────────────────┘
```

Example basePath values per area:
- `[default]Cappy Hour Inc/Site2/fillerproduction`
- `[default]Cappy Hour Inc/Site2/liquidprocessing`
- `[default]Cappy Hour Inc/Site2/packaging`
- `[default]Cappy Hour Inc/Site2/palletizing`

### Sites & Area Availability

Not all sites have all 4 areas:

| Site | fillerproduction | liquidprocessing | packaging | palletizing |
|------|-----------------|-----------------|-----------|-------------|
| Site1 | Yes | Yes | -- | -- |
| Site2 | Yes | Yes | Yes | Yes |
| Site3 | Yes | Yes | Yes | Yes |

---

## Line Dashboard Widgets

A set of wide and compact widgets for composing a filling line dashboard, inspired by the React dashboard layout in `_ref/rollups/EntB/react-dashboard-example-layout.json`. Each widget takes a `basePath` parameter pointing to the **line level** of the tag hierarchy.

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `basePath` | String | Root path to the line-level instance (e.g., `[default]Cappy Hour Inc/Site1/fillerproduction/fillingline01`) |

### Dashboard Layout

```
┌─────────────────────────────────────────────────────────────────────────────┐
│ LINE METRICS (line-kpi-widget-view.json, 960×240)                          │
│ [OEE] [AVAIL] [PERF] [QUAL] │ Rate Actual  Rate Std  IN    OUT    DEF    │
│ gauge  gauge  gauge  gauge   │ value        value     count count  count  │
│ [Time Running]  [Time Idle]  [Planned DT]  [Unplanned DT]                 │
├─────────────────────────────────────────────────────────────────────────────┤
│ WORK ORDER (line-workorder-widget-view.json, 960×100)                      │
│ WO-2026-1042  │  [████████████████░░░░░░]  75.2%  │  Defects  │  Yield   │
│               │  8,234 / 24,000 bottles            │  42       │  99.65%  │
├──────────────────┬──────────────────┬───────────────────────────────────────┤
│ Filler           │ Cap Loader       │ Washer                               │
│ (filler-widget)  │ (caploader-widg) │ (washer-widget)                      │
│ 320×500          │ 320×500          │ 320×500                              │
├──────────────────┼──────────────────┼───────────────────────────────────────┤
│ ALL LINES COMPARISON (3x line-summary-widget-view.json, 320×180 each)      │
│ Line 01          │ Line 02          │ Line 03                              │
│ 85.2% OEE       │ 78.4% OEE       │ 91.0% OEE                           │
│ A/P/Q values     │ A/P/Q values     │ A/P/Q values                        │
│ [WO progress]    │ [WO progress]    │ [WO progress]                       │
└──────────────────┴──────────────────┴───────────────────────────────────────┘
```

### Widget 1: Line KPI Widget

**File:** `line-kpi-widget-view.json`

Wide line-level metrics widget with 4 OEE gauges, 5 stat cards, and 4 time metric values.

| Section | Feature | Tag Path |
|---------|---------|----------|
| Gauges | OEE | `_metric/oee` (× 100) |
| Gauges | Availability | `_metric/availability` (× 100) |
| Gauges | Performance | `_metric/performance` (× 100) |
| Gauges | Quality | `_metric/quality` (× 100) |
| Stats | Rate Actual (green) | `_metric/input/rateactual` |
| Stats | Rate Standard (blue) | `_metric/input/ratestandard` |
| Stats | Count Infeed | `_metric/input/countinfeed` |
| Stats | Count Outfeed (green) | `_metric/input/countoutfeed` |
| Stats | Count Defect (red) | `_metric/input/countdefect` |
| Time | Time Running | `_metric/input/timerunning` |
| Time | Time Idle (yellow) | `_metric/input/timeidle` |
| Time | Planned Downtime (orange) | `_metric/input/timedownplanned` |
| Time | Unplanned Downtime (red) | `_metric/input/timedownunplanned` |

**Time Format:** Adaptive — shows minutes (`0.0m`) under 1 hour, hours (`0.0h`) otherwise.

**Size:** 960 x 240 px

---

### Widget 2: Line Work Order Widget

**File:** `line-workorder-widget-view.json`

Horizontal work order display with progress bar, defect count, and calculated yield.

| Feature | Tag Path |
|---------|----------|
| Work Order Number (blue) | `Work Order/workordernumber` |
| Progress Bar | `Work Order/quantityactual` / `quantitytarget` |
| Quantity Label | `quantityactual / quantitytarget uom` |
| Completion % | Calculated: `(actual / target) × 100` |
| Defect Count (red) | `Work Order/quantitydefect` |
| Yield % | Calculated: `(1 - defect / actual) × 100` |

**Size:** 960 x 100 px

---

### Widget 3: Line Summary Widget

**File:** `line-summary-widget-view.json`

Compact card for the "All Lines Comparison" section. Place one per filling line side by side.

| Feature | Tag Path |
|---------|----------|
| Line Name | `_metadata/assetidentifier/displayname` |
| OEE % (green, header) | `_metric/oee` (× 100) |
| Availability % (blue) | `_metric/availability` (× 100) |
| Performance % | `_metric/performance` (× 100) |
| Quality % | `_metric/quality` (× 100) |
| WO Progress Bar | `Work Order/quantityactual` / `quantitytarget` |
| WO Number | `Work Order/workordernumber` |

**Size:** 320 x 180 px

---

### Composed Dashboard: Line Dashboard

**File:** `line-dashboard-view.json`

A single parent view that composes all line widgets together using `ia.display.view` and `ia.display.flex-repeater`, matching the React reference layout.

| Section | Component Type | View Template | Instances |
|---------|---------------|---------------|-----------|
| Line Metrics | `ia.display.view` | line-kpi-widget | 1 (basePath) |
| Work Order | `ia.display.view` | line-workorder-widget | 1 (basePath) |
| Equipment Cards | `ia.display.flex-repeater` | caploader-widget | 3 (filler, caploader, washer) |
| Lines Comparison | `ia.display.flex-repeater` | line-summary-widget | 3 (one per line) |

**Parameters:**

| Parameter | Default | Description |
|-----------|---------|-------------|
| `basePath` | `[default]Cappy Hour Inc/Site1/fillerproduction/fillingline01` | Selected line path |
| `lineKpiViewPath` | `WidgetBuilder/line-kpi-widget` | View path for line KPI widget |
| `lineWorkorderViewPath` | `WidgetBuilder/line-workorder-widget` | View path for work order widget |
| `equipmentViewPath` | `WidgetBuilder/caploader-widget` | View path for equipment cards |
| `lineSummaryViewPath` | `WidgetBuilder/line-summary-widget` | View path for comparison cards |

**Custom Properties (auto-bound):**

- `equipmentInstances` — 3-element array, basePaths derived from `basePath + '/filler'`, `'/caploader'`, `'/washer'`
- `comparisonInstances` — 3-element array, defaults to Site1's 3 filling lines (update for other sites)

**Setup:** After importing all view JSON files into Perspective, update the `*ViewPath` parameters to match the actual view paths in your project.

**Size:** 960 x 1100 px

---

### Composed Dashboard: Line Dashboard Compact

**File:** `line-dashboard-compact-view.json`

A compact dashboard designed to fit within tab containers. Shows line KPI metrics, work order, equipment status (name + state for filler/caploader/washer), and all-lines comparison cards.

| Section | Component Type | Height |
|---------|---------------|--------|
| Line KPI | `ia.display.view` | 200px (fixed) |
| Work Order | `ia.display.view` | 80px (fixed) |
| Equipment Header | `ia.container.flex` | auto |
| Equipment Status | `ia.container.flex` (3 inline cards) | 60px (fixed) |
| Comparison Header | `ia.container.flex` | auto |
| Comparison Cards | `ia.display.flex-repeater` | grow (fills remaining) |

**Equipment Status Section:**
Three side-by-side cards showing name (`assetname`) and state (`State/name`) for each equipment:
- Filler: `{basePath}/filler/_metadata/assetidentifier/assetname` + `State/name`
- Caploader: `{basePath}/caploader/_metadata/assetidentifier/assetname` + `State/name`
- Washer: `{basePath}/washer/_metadata/assetidentifier/assetname` + `State/name`

**Line Comparison Section:**
Uses `ia.display.flex-repeater` with `line-summary-widget` to show all lines side-by-side. Comparison instances are derived from `areaBasePath + '/fillingline01'`, `'/fillingline02'`, `'/fillingline03'`.

**Parameters:**

| Parameter | Default | Description |
|-----------|---------|-------------|
| `basePath` | `[default]Cappy Hour Inc/Site1/fillerproduction/fillingline01` | Selected line path |
| `areaBasePath` | `[default]Cappy Hour Inc/Site1/fillerproduction` | Area path (for comparison instances) |
| `lineKpiViewPath` | `UDT Views/Prove It/Rollups/EntB/line-kpi` | View path for line KPI widget |
| `lineWorkorderViewPath` | `UDT Views/Prove It/Rollups/EntB/line-workorder` | View path for work order widget |
| `lineSummaryViewPath` | `UDT Views/Prove It/Rollups/EntB/line-summary` | View path for comparison cards |

**Size:** 1201 x 750 px

---

### Composed Dashboard: Line Dashboard Tabs

**File:** `line-dashboard-tabs-view.json`

Tab wrapper with a title breadcrumb, area-level KPI metrics, and **dynamic tabs** that automatically discover filling lines from the tag structure. The area metrics section shows aggregate OEE/A/P/Q gauges, production stats, and time breakdown for the entire area, while each tab drills into a specific filling line.

| Section | Component Type | Height |
|---------|---------------|--------|
| Title | `ia.display.view` (`Page/Embedded/Title`) | 50px (fixed) |
| Area Metrics | `ia.container.flex` (inline) | 220px (fixed) |
| Tab Container | `ia.container.tab` | grow (fills remaining) |

**Area Metrics Section:**

| Row | Content |
|-----|---------|
| AreaHeader | Area name from `_metadata/assetidentifier/assetname` |
| TopRow (120px) | 4 OEE gauges (OEE, Avail, Perf, Qual) + 5 stat cards (Rate Actual, Rate Standard, Count In/Out/Defect) |
| TimeRow (60px) | 4 time boxes: Running, Idle (yellow), Planned DT (orange), Unplanned DT (red) |

**Area Metric Bindings (all under `{basePath}/_metric/`):**

| Metric | Tag Path | Color |
|--------|----------|-------|
| OEE Gauge | `_metric/oee` (x100) | -- |
| Availability Gauge | `_metric/availability` (x100) | -- |
| Performance Gauge | `_metric/performance` (x100) | -- |
| Quality Gauge | `_metric/quality` (x100) | -- |
| Rate Actual | `_metric/input/rateactual` | Green (#4CAF50) |
| Rate Standard | `_metric/input/ratestandard` | Blue (#2196F3) |
| Count Infeed | `_metric/input/countinfeed` | -- |
| Count Outfeed | `_metric/input/countoutfeed` | Green (#4CAF50) |
| Count Defect | `_metric/input/countdefect` | Red (#F44336) |
| Time Running | `_metric/input/timerunning` | -- |
| Time Idle | `_metric/input/timeidle` | Yellow (#FFC107) |
| Planned Downtime | `_metric/input/timedownplanned` | Orange (#FF9800) |
| Unplanned Downtime | `_metric/input/timedownunplanned` | Red (#F44336) |

**Parameters:**

| Parameter | Default | Description |
|-----------|---------|-------------|
| `basePath` | `[default]Cappy Hour Inc/Site1/fillerproduction` | Area-level path (bound from `{session.custom.basePath}`, `paramDirection: inout`) |
| `lineDashboardViewPath` | `UDT Views/Prove It/Rollups/EntB/line-overview` | View path for the compact dashboard |

**Dynamic Tab Discovery:**

Tabs are generated dynamically using a `custom.lineData` property with a script transform. The script scans `fillingline01` through `fillingline10` under the area basePath, reading `_metadata/assetidentifier/assetname` for each. Only lines with a valid (good quality, non-null) assetname tag are included.

```python
# Script transform on custom.lineData (triggered by basePath expression binding)
basePath = value
result = {'tabs': [], 'paths': []}
for i in range(1, 11):
    num = str(i).zfill(2)
    lineName = 'fillingline' + num
    tagPath = basePath + '/' + lineName + '/_metadata/assetidentifier/assetname'
    try:
        qv = system.tag.readBlocking([tagPath])
        if qv[0].quality.isGood() and qv[0].value is not None:
            result['tabs'].append(str(qv[0].value))
            result['paths'].append(basePath + '/' + lineName)
    except:
        pass
return result
```

- `custom.lineData.tabs` → bound to `props.tabs` on the tab container (controls tab labels)
- `custom.lineData.paths[N]` → bound to each child's `props.params.basePath` (provides line-level path)
- Site1 with 3 filling lines shows 3 tabs; Site3 with 1 filling line shows 1 tab
- Tab names use `assetname` (e.g., "Filling Line 01") rather than hardcoded strings

**Tab Behavior:**
- Tab menu style: `modern` with responsive font sizing (13px desktop, 10px mobile)
- Title breadcrumb reads the area `.Path` tag and formats as `Site > Area > ...`
- Time values use adaptive format: minutes (`0.0m`) under 1 hour, hours (`0.0h`) otherwise
- Up to 10 filling lines supported per area

**Size:** 1201 x 1080 px

---

### Equipment Cards (Existing Widgets)

The equipment card section uses the existing individual equipment widgets:

| Widget | File | Size |
|--------|------|------|
| Filler | `filler-widget-view.json` | 320×500 |
| Cap Loader | `caploader-widget-view.json` | 320×500 |
| Washer | `washer-widget-view.json` | 320×500 |

---

## Liquid Processing Dashboard Widgets

A set of widgets for composing a liquid processing area dashboard. The liquid processing area contains two sub-areas: **tankstorage** (tanks) and **mixroom** (vats). Equipment count varies by site.

### Tag Hierarchy

```
liquidprocessing/
├── _metric/                    # Area-level KPIs (same as other areas)
├── tankstorage01/
│   ├── _metric/                # Sub-area KPIs
│   ├── tank01/                 # Name + State
│   ├── tank02/
│   └── ... (up to tank06 on Site1)
└── mixroom01/
    ├── _metric/                # Sub-area KPIs
    ├── vat01/                  # Name + State + Work Order
    ├── vat02/
    └── ... (up to vat02 on Site2)
```

### Equipment by Site

| Site | Tanks (tankstorage01) | Vats (mixroom01) |
|------|----------------------|------------------|
| Site1 | 6 | 1+ |
| Site2 | 3 | 2 |
| Site3 | 2 | 1 |

### Widget 1: LP Tank Status Widget

**File:** `lp-tank-status-widget-view.json`

Simple status card showing tank name and current state.

| Feature | Tag Path |
|---------|----------|
| Tank Name | `_metadata/assetidentifier/assetname` |
| State | `State/name` |

**Size:** 320 x 60 px

---

### Widget 2: LP Vat Status Widget

**File:** `lp-vat-status-widget-view.json`

Status card showing vat name, state, associated work order number, and production progress.

| Feature | Tag Path |
|---------|----------|
| Vat Name | `_metadata/assetidentifier/assetname` |
| State | `State/name` |
| Work Order Number (blue) | `Work Order/workordernumber` |
| Progress Value | `Work Order/quantityactual` |
| Progress Max | `Work Order/quantitytarget` |

**Size:** 320 x 120 px

---

### Composed Dashboard: LP Dashboard Compact

**File:** `lp-dashboard-compact-view.json`

Compact dashboard for liquid processing sub-areas (tab content). Shows sub-area KPI metrics and dynamically detected equipment cards. Auto-detects whether the sub-area contains tanks or vats and switches the widget view path accordingly.

| Section | Component Type | Height |
|---------|---------------|--------|
| Sub-Area KPI | `ia.display.view` | 200px (fixed) |
| Equipment Header | `ia.container.flex` | auto |
| Equipment Cards | `ia.display.flex-repeater` | grow (fills remaining) |

**Auto-Detection Script:**

The `custom.equipmentData` property uses a script transform that scans for both `tank01-10` and `vat01-10` under the basePath. Returns `{type: 'tank'|'vat', instances: [...]}`. The flex-repeater path binding uses a conditional expression:

```
if({view.custom.equipmentData.type} = 'vat', vatViewPath, tankViewPath)
```

**Parameters:**

| Parameter | Default | Description |
|-----------|---------|-------------|
| `basePath` | `[default]Cappy Hour Inc/Site1/liquidprocessing/tankstorage01` | Sub-area path |
| `lineKpiViewPath` | `UDT Views/Prove It/Rollups/EntB/line-kpi` | View path for KPI widget |
| `tankStatusViewPath` | `UDT Views/Prove It/Rollups/EntB/lp-tank-status-widget-view` | View path for tank cards |
| `vatStatusViewPath` | `UDT Views/Prove It/Rollups/EntB/lp-vat-status-widget-view` | View path for vat cards |

**Size:** 1201 x 750 px

---

### Composed Dashboard: LP Dashboard Tabs

**File:** `lp-dashboard-tabs-view.json`

Tab wrapper with a title breadcrumb, area-level KPI metrics (identical to filler production tabs), and **dynamic tabs** for sub-areas. The script scans for `tankstorage01` and `mixroom01` under the area basePath, reading `assetname` to generate tab labels.

| Section | Component Type | Height |
|---------|---------------|--------|
| Title | `ia.display.view` (`Page/Embedded/Title`) | 50px (fixed) |
| Area Metrics | `ia.container.flex` (4 gauges + 5 stats + 4 time boxes) | 220px (fixed) |
| Tab Container | `ia.container.tab` | grow (fills remaining) |

**Dynamic Sub-Area Discovery:**

```python
basePath = value
result = {'tabs': [], 'paths': []}
subAreas = ['tankstorage01', 'mixroom01']
for sa in subAreas:
    tagPath = basePath + '/' + sa + '/_metadata/assetidentifier/assetname'
    try:
        qv = system.tag.readBlocking([tagPath])
        if qv[0].quality.isGood() and qv[0].value is not None:
            result['tabs'].append(str(qv[0].value))
            result['paths'].append(basePath + '/' + sa)
    except:
        pass
return result
```

- Tab names come from `assetname` (e.g., "Tank Storage 01", "Mix Room 01")
- Only sub-areas with valid tags appear as tabs
- Each tab embeds `lp-dashboard-compact-view.json` which auto-detects equipment type

**Parameters:**

| Parameter | Default | Description |
|-----------|---------|-------------|
| `basePath` | `[default]InPlay Oil/Cardium/Leafland/14-32-039-05W5/SAT 14-32-039-05W5` | Area-level path (bound from `{session.custom.basePath}`, `paramDirection: inout`) |
| `lineDashboardViewPath` | `UDT Views/Prove It/Rollups/EntB/lp-dashboard-compact-view` | View path for the compact dashboard |

**Size:** 1201 x 1080 px

---

## Packaging Dashboard Widgets

A set of dashboard views for the packaging area. The packaging area follows the **same structure as filler production** — labeler lines with 3 equipment each. Reuses the existing `line-kpi-widget`, `line-workorder-widget`, and `line-summary-widget`.

### Tag Hierarchy

```
packaging/
├── _metric/                    # Area-level KPIs
├── labelerline01/
│   ├── _metric/                # Line-level KPIs
│   ├── labeler/                # Name + State + OEE metrics
│   ├── sealer/                 # Name + State + OEE metrics
│   ├── packager/               # Name + State + OEE metrics
│   └── Work Order/             # Work order tracking
├── labelerline02/
└── ... (up to labelerline04 on Site1)
```

### Lines by Site

| Site | Labeler Lines |
|------|--------------|
| Site1 | 4 (labelerline01-04) |
| Site2 | 2 (labelerline01-02) |
| Site3 | 1 (labelerline01) |

### Composed Dashboard: Packaging Dashboard Compact

**File:** `pkg-dashboard-compact-view.json`

Compact dashboard for a single labeler line (tab content). Same layout as filler compact view with equipment swapped.

| Section | Component Type | Height |
|---------|---------------|--------|
| Line KPI | `ia.display.view` (reuses line-kpi-widget) | 200px (fixed) |
| Work Order | `ia.display.view` (reuses line-workorder-widget) | 80px (fixed) |
| Equipment Header | `ia.container.flex` | auto |
| Equipment Status | `ia.container.flex` (3 inline cards) | 60px (fixed) |
| Comparison Header | `ia.container.flex` | auto |
| Comparison Cards | `ia.display.flex-repeater` (reuses line-summary-widget) | grow |

**Equipment Status Cards:**
- Labeler: `{basePath}/labeler/_metadata/assetidentifier/assetname` + `State/name`
- Sealer: `{basePath}/sealer/_metadata/assetidentifier/assetname` + `State/name`
- Packager: `{basePath}/packager/_metadata/assetidentifier/assetname` + `State/name`

**Comparison Script:** Scans `labelerline01-10` under `areaBasePath`.

**Parameters:**

| Parameter | Default | Description |
|-----------|---------|-------------|
| `basePath` | `[default]Cappy Hour Inc/Site1/packaging/labelerline01` | Selected line path |
| `areaBasePath` | `[default]Cappy Hour Inc/Site1/packaging` | Area path (for comparison instances) |
| `lineKpiViewPath` | `UDT Views/Prove It/Rollups/EntB/line-kpi` | View path for line KPI widget |
| `lineWorkorderViewPath` | `UDT Views/Prove It/Rollups/EntB/line-workorder` | View path for work order widget |
| `lineSummaryViewPath` | `UDT Views/Prove It/Rollups/EntB/line-summary` | View path for comparison cards |

**Size:** 1201 x 750 px

---

### Composed Dashboard: Packaging Dashboard Tabs

**File:** `pkg-dashboard-tabs-view.json`

Tab wrapper with title breadcrumb, area-level KPI metrics, and dynamic tabs for labeler lines. Identical structure to filler tabs view.

| Section | Component Type | Height |
|---------|---------------|--------|
| Title | `ia.display.view` (`Page/Embedded/Title`) | 50px (fixed) |
| Area Metrics | `ia.container.flex` (4 gauges + 5 stats + 4 time boxes) | 220px (fixed) |
| Tab Container | `ia.container.tab` | grow (fills remaining) |

**Dynamic Tab Discovery:** Scans `labelerline01-10` under basePath. Tab names from `assetname` tags.

**Parameters:**

| Parameter | Default | Description |
|-----------|---------|-------------|
| `basePath` | `[default]Cappy Hour Inc/Site1/packaging` | Area-level path (bound from `{session.custom.basePath}`, `paramDirection: inout`) |
| `lineDashboardViewPath` | `UDT Views/Prove It/Rollups/EntB/pkg-dashboard-compact-view` | View path for the compact dashboard |

**Size:** 1201 x 1080 px

---

## Palletizing Dashboard Widgets

A set of widgets for composing a palletizing area dashboard. Palletizing has a **different structure** from other areas — it contains two types of sub-areas: **manual palletizers** (`palletizermanual01-04`) with `workstation` equipment, and **automated palletizers** (`palletizer01-02`) with `robot` equipment. No Work Order tracking.

### Tag Hierarchy

```
palletizing/
├── _metric/                    # Area-level KPIs
├── palletizermanual01/
│   ├── _metric/                # Sub-area KPIs
│   └── workstation/            # Name + State + OEE metrics
├── palletizermanual02/
├── ... (up to palletizermanual04 on Site1)
├── palletizer01/
│   ├── _metric/                # Sub-area KPIs
│   ├── robot/                  # Name + State + OEE metrics
│   └── pallet01/               # Name + State (optional)
└── palletizer02/
```

### Sub-Areas by Site

| Site | Manual Palletizers | Automated Palletizers | Total |
|------|-------------------|----------------------|-------|
| Site1 | 4 (palletizermanual01-04) | 2 (palletizer01-02) | 6 |
| Site2 | 2 (palletizermanual01-02) | 1 (palletizer01) | 3 |
| Site3 | 1 (palletizermanual01) | 0 | 1 |

### Widget 1: Palletizing Equipment Status Widget

**File:** `pal-equipment-status-widget-view.json`

Equipment status card with throughput and time metrics. Works for workstation, robot, or pallet equipment.

```
┌──────────────────────────────────────────┐
│ [Name]                          [State]  │  ← HeaderRow
│ [Rate (green)] [Outfeed (green)] [Defect (red)] │  ← ThroughputRow (36px)
│ [Running] [Idle (yellow)] [Planned (orange)] [Unplanned (red)] │  ← TimeRow (36px)
└──────────────────────────────────────────┘
```

| Section | Feature | Tag Path | Color |
|---------|---------|----------|-------|
| Header | Equipment Name | `_metadata/assetidentifier/assetname` | -- |
| Header | State | `State/name` | -- |
| Throughput | Rate Actual | `_metric/input/rateactual` | Green (#4CAF50) |
| Throughput | Count Outfeed | `_metric/input/countoutfeed` | Green (#4CAF50) |
| Throughput | Count Defect | `_metric/input/countdefect` | Red (#F44336) |
| Time | Time Running | `_metric/input/timerunning` | -- |
| Time | Time Idle | `_metric/input/timeidle` | Yellow (#FFC107) |
| Time | Planned Downtime | `_metric/input/timedownplanned` | Orange (#FF9800) |
| Time | Unplanned Downtime | `_metric/input/timedownunplanned` | Red (#F44336) |

**Time Format:** Adaptive — shows minutes (`0.0m`) under 1 hour, hours (`0.0h`) otherwise.

**Size:** 320 x 120 px

---

### Composed Dashboard: Palletizing Dashboard Compact

**File:** `pal-dashboard-compact-view.json`

Compact dashboard for a single palletizing sub-area (tab content). Shows sub-area KPI metrics and dynamically detected equipment cards. Auto-discovers equipment (workstation, robot, pallet01) under the sub-area.

| Section | Component Type | Height |
|---------|---------------|--------|
| Sub-Area KPI | `ia.display.view` (reuses line-kpi-widget) | 200px (fixed) |
| Equipment Header | `ia.container.flex` | auto |
| Equipment Cards | `ia.display.flex-repeater` | grow (fills remaining) |

**Auto-Discovery Script:**

The `custom.equipmentData` property uses a script transform that scans for `workstation`, `robot`, and `pallet01` under the basePath. Returns a list of `{basePath: ...}` objects for each valid equipment found.

```python
basePath = value
result = []
for name in ['workstation', 'robot', 'pallet01']:
    tagPath = basePath + '/' + name + '/_metadata/assetidentifier/assetname'
    try:
        qv = system.tag.readBlocking([tagPath])
        if qv[0].quality.isGood() and qv[0].value is not None:
            result.append({'basePath': basePath + '/' + name})
    except:
        pass
return result
```

Unlike LP compact (which switches between tank/vat widget paths), palletizing uses a single generic `pal-equipment-status-widget-view` for all equipment types.

**Parameters:**

| Parameter | Default | Description |
|-----------|---------|-------------|
| `basePath` | `[default]Cappy Hour Inc/Site1/palletizing/palletizermanual01` | Sub-area path |
| `lineKpiViewPath` | `UDT Views/Prove It/Rollups/EntB/line-kpi` | View path for KPI widget |
| `equipmentStatusViewPath` | `UDT Views/Prove It/Rollups/EntB/pal-equipment-status-widget-view` | View path for equipment cards |

**Size:** 1201 x 750 px

---

### Composed Dashboard: Palletizing Dashboard Tabs

**File:** `pal-dashboard-tabs-view.json`

Tab wrapper with title breadcrumb, area-level KPI metrics, and **dynamic tabs** for palletizing sub-areas. Uses a dual-prefix discovery script that scans both `palletizermanual01-10` and `palletizer01-10`.

| Section | Component Type | Height |
|---------|---------------|--------|
| Title | `ia.display.view` (`Page/Embedded/Title`) | 50px (fixed) |
| Area Metrics | `ia.container.flex` (4 gauges + 5 stats + 4 time boxes) | 220px (fixed) |
| Tab Container | `ia.container.tab` | grow (fills remaining) |

**Dual-Prefix Tab Discovery:**

```python
basePath = value
result = {'tabs': [], 'paths': []}
for prefix in ['palletizermanual', 'palletizer']:
    for i in range(1, 11):
        num = str(i).zfill(2)
        name = prefix + num
        tagPath = basePath + '/' + name + '/_metadata/assetidentifier/assetname'
        try:
            qv = system.tag.readBlocking([tagPath])
            if qv[0].quality.isGood() and qv[0].value is not None:
                result['tabs'].append(str(qv[0].value))
                result['paths'].append(basePath + '/' + name)
        except:
            pass
return result
```

- Manual palletizers are discovered first, then automated
- Tab names come from `assetname` tags (e.g., "Palletizer Manual 01", "Palletizer 01")
- Up to 6 tabs supported (Site1 maximum: 4 manual + 2 automated)
- Sites with fewer sub-areas show fewer tabs automatically

**Parameters:**

| Parameter | Default | Description |
|-----------|---------|-------------|
| `basePath` | `[default]Cappy Hour Inc/Site1/palletizing` | Area-level path (bound from `{session.custom.basePath}`, `paramDirection: inout`) |
| `lineDashboardViewPath` | `UDT Views/Prove It/Rollups/EntB/pal-dashboard-compact-view` | View path for the compact dashboard |

**Size:** 1201 x 1080 px

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
- [x] Create vendor UDT SP474 gas meter widget with volume comparison
- [ ] Add additional vendor UDT equipment types (pumps, valves, etc.)
- [x] Create area rollup widget set (OEE, Production, Availability, Status)
- [x] Create line dashboard widget set (KPI, Work Order, Summary)
- [x] Create compact no-scroll line dashboard for tab containers
- [x] Create tabbed line dashboard with title breadcrumb
- [x] Dynamic tab discovery from tag structure (assetname-based, conditional visibility)
- [x] Create liquid processing dashboard widget set (tank status, vat status, compact, tabs)
- [x] Auto-detect equipment type (tank vs vat) in LP compact dashboard
- [x] Create packaging dashboard widget set (compact + tabs, reuses line widgets)
- [x] Create palletizing dashboard widget set (equipment status, compact, tabs)
- [x] Auto-detect equipment (workstation/robot/pallet) in palletizing compact dashboard
- [x] Dual-prefix tab discovery for mixed manual/automated palletizing sub-areas
- [ ] Area Status: Add equipment active count tag binding when available
- [ ] Area Status: Add active alarm count tag binding when available
- [ ] Area Status: Add active work order count tag binding when available
- [ ] Area Status: Add MTBF tag binding when available
- [ ] Area Status: Add MTTR tag binding when available
