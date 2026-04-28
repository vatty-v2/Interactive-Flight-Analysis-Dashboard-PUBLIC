# ◈ Interactive Flight Analysis Dashboard

> **Analyse 12,500+ simulated flight records to surface delay patterns, peak disruption windows, and turnaround bottlenecks — running entirely in the browser.**

[![HTML](https://img.shields.io/badge/HTML-Single_File-E34F26?style=flat&logo=html5&logoColor=white)](https://github.com/vatty-v2/Interactive-Flight-Analysis-Dashboard-PUBLIC)
[![Chart.js](https://img.shields.io/badge/Chart.js-4.4.1-FF6384?style=flat&logo=chartdotjs&logoColor=white)](https://www.chartjs.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Active-brightgreen)]()

---

## What is this?

This project is a **browser-based flight operations analytics dashboard**. It models the kind of data analysis a planning or performance team would run after a disrupted quarter. Identifying which carriers delay most, when disruptions peak, and where turnaround time is being lost.

It simulates a dataset of 12,500+ flight records across 8 European carriers, with a seeded PRNG engine that produces consistent, realistic-looking operational data on every load. The dashboard lets you filter by airline, cross-reference delay causes, and read bottleneck data from a turnaround stage breakdown.

**Built to explore:** how operational flight data can be turned into clear, decision-ready insight for non-technical stakeholders. Without a backend, database, or data pipeline.

---

## Development Note

This project was originally developed as a private prototype and later published here as a public portfolio project. The commit history has been condensed as part of that transition.

---

## Demo

> Live dashboard showing airline delay comparison, peak disruption heatmap, and turnaround bottleneck breakdown

![Dashboard Preview](flight_dashboard_showcase.gif)

---

## Features

- **Airline Delay Comparison** - horizontal bar chart across 8 carriers, colour-coded by severity (within target / exceeds target / best-in-class)
- **Delay Cause Breakdown** - doughnut chart across 5 root-cause categories (late aircraft, weather, ATC restriction, maintenance, crew scheduling)
- **Peak Disruption Heatmap** - hour × day-of-week grid showing average delay intensity across a full operational week, with hover tooltips per cell
- **Turnaround Bottleneck Chart** - scheduled vs actual time per stage (deboarding through boarding), isolating where overruns accumulate
- **Airline Filter** - click any carrier badge to scope all metrics and summary cards to that airline instantly
- **Operational Insight Panel** - plain-language summary of the three most actionable findings at the bottom of the dashboard
- **Zero dependencies to install** - Chart.js loaded from CDN; everything else is vanilla JS and CSS

---

## Tech Stack

| Layer | Technology |
|---|---|
| Charts | [Chart.js 4.4.1](https://www.chartjs.org/) via CDN |
| Heatmap | Vanilla HTML/CSS grid - no library |
| Logic | Vanilla JavaScript (ES6+) |
| Styling | Pure CSS with CSS variables |
| Data | Simulated - seeded PRNG for deterministic output |
| Deployment | Single HTML file - open in any browser |

---

## Getting Started

### 1. Clone the repo

```bash
git clone https://github.com/vatty-v2/Interactive-Flight-Analysis-Dashboard-PUBLIC.git
cd Interactive-Flight-Analysis-Dashboard-PUBLIC
```

### 2. Open the dashboard

No build step required. Open the file directly in your browser:

```bash
open flight_analysis_dashboard.html        # macOS
start flight_analysis_dashboard.html       # Windows
xdg-open flight_analysis_dashboard.html    # Linux
```

Or just double-click the file in Finder / File Explorer.

---

## Usage

### Filtering by airline

Click any badge in the filter bar at the top to scope the delay chart and summary metrics to a single carrier. Click **All airlines** to reset.

### Reading the heatmap

Each cell represents the average delay (minutes) for a given hour and day of the week. Colours run from cream (low, <5 min) through amber to dark brown (high, >25 min). Hover any cell for the exact value.

> Friday 17:00–19:00 is consistently the highest-disruption window in the dataset - cascading delays affect 34% of evening rotations.

### Reading the turnaround chart

Any bar where **red (actual)** exceeds **green (scheduled)** marks a bottleneck stage. Catering is the largest single overrun at +8 min average, followed by boarding at +6 min.

---