# NYC Motor Vehicle Collisions Analytics

An end-to-end data engineering and analytics project using NYC Motor Vehicle Collision data.

The project cleans, validates, integrates, and analyzes crash and person-level datasets before preparing a dashboard-ready dataset for interactive visualization.

## Project Overview

The project uses two related NYC Open Data datasets:

- Motor Vehicle Collisions – Crashes
- Motor Vehicle Collisions – Person

The datasets are connected using:

`COLLISION_ID`

Because multiple people can be associated with one collision, person-level records are aggregated before integration to preserve one row per collision.

## Data Engineering Workflow

The notebook performs:

- Dataset loading and schema inspection
- Missing-value analysis
- Duplicate detection
- Data-type conversion
- Category standardization
- Invalid age and coordinate handling
- Casualty validation
- Person-level aggregation
- One-to-one dataset integration
- Post-integration cleaning
- Data-quality validation
- Dashboard-ready data export

## Crash Data Cleaning

The crash dataset cleaning includes:

- Removing records without valid collision IDs
- Removing duplicate collision IDs
- Converting crash dates and times
- Cleaning injury and fatality columns
- Replacing invalid negative casualty values
- Standardizing borough names
- Validating latitude and longitude values
- Standardizing contributing factors
- Standardizing vehicle types

## Person Data Cleaning

The person dataset cleaning includes:

- Removing records without valid collision IDs
- Removing exact duplicates
- Removing duplicate person identifiers
- Validating person ages
- Standardizing person type
- Standardizing injury status
- Standardizing sex values

## Person-Level Aggregation

Person records are aggregated to collision level using measures such as:

- Total person records
- Unique persons
- Pedestrian count
- Cyclist count
- Motor vehicle occupant count
- Injured person count
- Killed person count
- Male and female counts
- Average age
- Median age

## Data Integration

A validated left join is used to preserve all crash records.

The integration includes:

- One row per collision validation
- Matched and unmatched collision analysis
- Missing person-data handling
- Comparison of crash-level and person-level casualty totals

## Research Areas

The project investigates:

- Collision trends from 2012 to 2025
- Borough-level collision severity
- Hourly and weekday patterns
- Daytime versus nighttime severity
- Contributing factors
- Vehicle type and contributing-factor combinations
- Pedestrian and cyclist involvement
- Age-group severity
- Geographic collision hotspots
- Multi-person collision severity

## Visualizations

The notebook creates:

- Annual collision trends
- Borough comparisons
- Weekday and hourly charts
- Day-versus-night analysis
- Contributing-factor charts
- Person-type injury charts
- Age-group analysis
- Geographic collision maps
- Multi-person collision severity charts

## Dashboard Preparation

The final integrated dataset is exported in:

- Parquet format for efficient dashboard loading
- CSV sample format for inspection and testing

The exported dataset is designed for use with Plotly Dash.

## Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Plotly
- PyArrow
- Google Colab
- NYC Open Data

## Execution Note

The uploaded executed notebook uses a deterministic offline demonstration sample because the execution environment could not connect to the NYC Open Data endpoint.

To run the project using the full official datasets, set:

```python
USE_SAMPLE = False
