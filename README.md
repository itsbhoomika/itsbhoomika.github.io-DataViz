# Data Visualization Portfolio

> Interactive Vega-Lite visualizations published as a GitHub Pages site — IS 445 Data Visualization @ UIUC.

[![Live](https://img.shields.io/badge/Live%20Site-GitHub%20Pages-blue)](https://itsbhoomika.github.io/itsbhoomika.github.io-DataViz)
[![Vega-Lite](https://img.shields.io/badge/Vega--Lite-5-purple)](https://vega.github.io/vega-lite/)

## Project: UFO Sightings in the United States (1950–2014)

Visual analysis of 63,410 reported UFO sightings using NUFORC data — exploring geographic distribution and temporal trends by shape category.

## File Guide

| File | What it does |
|------|--------------|
| `Workbook-3.ipynb` | **Analysis notebook** — data cleaning, coordinate filtering, shape aggregation, Vega-Lite JSON spec generation |
| `_posts/` | Jekyll blog posts — each hosts one visualization with design rationale and data transformation notes |
| `assets/` | Generated Vega-Lite JSON specs (`ufo_map.json`, `ufo_timeseries.json`) consumed by the live site |
| `index.md` | Site landing page listing all posts |
| `_config.yml` | Jekyll configuration |

## Visualizations

### 1. Geographic Distribution Map
- 5,000 sampled US sightings plotted by latitude/longitude (AlbersUSA projection)
- Color-encoded by UFO shape (category-20 scheme, 20+ shape categories)
- Tooltips: city, state, shape, year, duration

### 2. Sightings Over Time by Shape (Interactive)
- Line chart: sightings per year (1950–2014), broken down by top-10 shapes
- **Interactive dropdown** — select a shape to highlight its trend line; others dim to gray
- Reveals the dramatic post-1995 surge in reported sightings (likely correlated with internet reporting)

## Data Transformations (in `Workbook-3.ipynb`)

- Filtered to US sightings only (`country == 'us'`)
- Removed records with missing lat/long, shape, or year
- Clipped to valid US coordinate ranges
- Sampled 5,000 from 63,410 to reduce overplotting
- Extracted top-10 shapes for time series to avoid visual clutter

## Tech Stack

`Python` · `Pandas` · `Vega-Lite 5` · `Jekyll` · `GitHub Pages`

## Data Source

[UIUC iSchool UFO dataset](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/ufo-scrubbed-geocoded-time-standardized-00.csv)
