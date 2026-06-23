# IMD Weather Data Fetching and Extraction

## Overview

This project automates the download and extraction of gridded weather datasets from the Indian Meteorological Department (IMD). It consists of two Python scripts:

1. **imd_data_fetching.py** – Downloads IMD daily weather datasets (Tmax, Tmin, Rainfall).
2. **imd_data_extraction.py** – Extracts weather data for selected Indian cities and compiles the results into a CSV file.

---

## Features

### Data Fetching
- Downloads daily IMD weather datasets.
- Supports:
  - Maximum Temperature (Tmax)
  - Minimum Temperature (Tmin)
  - Rainfall
- Converts downloaded data into GeoTIFF format.

### Data Extraction
- Reads IMD `.grd` files.
- Extracts weather data for predefined locations.
- Handles missing values using nearest-neighbor spatial search.
- Generates a consolidated CSV dataset for analysis.

---

## Dependencies

Install the required packages:

```bash
pip install imddaily numpy pandas
```

---

## Project Structure

```text
.
├── imd_data_fetching.py
├── imd_data_extraction.py
└── README.md
```

---

## Workflow

### Step 1: Download IMD Data

Run:

```bash
python imd_data_fetching.py
```

The script downloads:

- Tmax (Maximum Temperature)
- Tmin (Minimum Temperature)
- Rainfall

and stores them in the configured directories.

### Step 2: Extract Weather Data

Run:

```bash
python imd_data_extraction.py
```

The script:

- Reads all downloaded `.grd` files.
- Extracts weather information for:
  - Delhi
  - Mumbai
  - Bengaluru
  - Kolkata
  - Chennai
- Compiles the results into:

```text
comprehensive_weather_data.csv
```

---

## Output Dataset

Example columns:

```text
Date
Delhi_Tmax_C
Delhi_Tmin_C
Delhi_Rainfall_mm
Mumbai_Tmax_C
Mumbai_Tmin_C
Mumbai_Rainfall_mm
...
```

---

## Configuring Locations

Additional cities can be added by updating the `locations` dictionary in `imd_data_extraction.py`:

```python
locations = {
    "City": {"lat": latitude, "lon": longitude}
}
```

---

## Applications

- Climate Analysis
- Weather Monitoring
- Agricultural Research
- Time-Series Forecasting
- Machine Learning Datasets
- Urban Climate Studies

---

## Notes

- Update all directory paths and dates before running the scripts.
- Ensure data downloading is completed before extraction.
- Temperature and rainfall datasets use different spatial resolutions.
- Missing temperature values are handled using nearest valid grid-cell lookup.

---

## Author

IMD Weather Data Processing Workflow
