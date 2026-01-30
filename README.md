# Non-wear detection data preparation

This repository contains the data and Quarto workflow used to prepare wearable sensor data (VEET and ActLumus) and accompanying activity logs for non-wear detection analyses.

## Contents

- `scripts/`
  - `data_preparation.qmd`: Quarto analysis that imports the raw data, cleans it, aggregates timestamps, merges wear-state logs, generates exploratory summaries/plots, and exports a cleaned dataset.
  - `data_preparation.html`: Rendered HTML output of the Quarto document.
- `data/`
  - `ActLumus/`: Raw ActLumus exports.
  - `VEET/`: Raw VEET exports (light and activity data).
  - `log/`: Activity and non-wear log (Excel).
  - `cleaned/`: Output directory for the cleaned dataset (`wear_data_cleaned.RData`).
- `photos/`: Reference photos related to the study setup.

## Workflow overview

1. Open `scripts/data_preparation.qmd` in RStudio (or run `quarto render`).
2. The script loads raw VEET and ActLumus data, aligns timestamps, joins the activity log, and filters for dates with logs.
3. A cleaned dataset is saved to `data/cleaned/wear_data_cleaned.RData` for downstream analysis.

## Requirements

The Quarto script uses the following R packages:

- `tidyverse`
- `LightLogR`
- `readxl`
- `here`
- `gt`

See the Quarto file for full details on parameters and processing steps.
