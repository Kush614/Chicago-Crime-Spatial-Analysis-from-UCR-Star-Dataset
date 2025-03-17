# Chicago Crimes & ZIP Code Boundaries Visualization

## Overview

This project performs a spatial analysis of Chicago crime data by joining it with ZIP code boundaries and visualizing the results on an interactive map. The project uses Python along with GeoPandas and Folium to:
- Load and clean the Chicago Crimes CSV dataset.
- Load and process the Chicago ZIP Code Boundaries shapefile.
- Perform a spatial join to associate each crime with its corresponding ZIP code.
- Aggregate and count the number of crimes per ZIP code.
- Generate an interactive choropleth map to visualize the crime distribution across Chicago ZIP codes.

## Project Structure

```
.
├── README.md
├── chicago_crimes.py          # Python script for the analysis
├── chicago_crimes.ipynb       # (Optional) Jupyter Notebook version
├── data
│   ├── Chicago_Crimes.csv     # CSV file with Chicago crime data
│   └── zip_data               # Folder containing the ZIP Code Boundaries shapefile components (.shp, .dbf, .shx, etc.)
└── output
    └── chicago_crime_map.html # Generated interactive map (output)
```

## Requirements

- Python 3.7+
- [Pandas](https://pandas.pydata.org/)
- [GeoPandas](https://geopandas.org/)
- [Shapely](https://shapely.readthedocs.io/)
- [Folium](https://python-visualization.github.io/folium/)

## Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/yourusername/chicago-crime-visualization.git
   cd chicago-crime-visualization
   ```

2. **(Optional) Create and activate a virtual environment:**

   ```bash
   python -m venv venv
   source venv/bin/activate   # For Windows: venv\Scripts\activate
   ```

3. **Install the required packages:**

   ```bash
   pip install pandas geopandas folium
   ```

   Alternatively, if a `requirements.txt` file is provided, run:

   ```bash
   pip install -r requirements.txt
   ```

## Data Preparation
-Download the Chicago Crimes dataset [https://star.cs.ucr.edu/?Chicago%20Crimes#center=41.8337,-87.7174&zoom=11].
-Download the ZIP Code Boundaries dataset in Chicago [https://star.cs.ucr.edu/?TIGER2018/ZCTA5#center=41.8337,-87.7174&zoom=11]
- Place the `Chicago_Crimes.csv` file inside the `data/` directory. 
- Download the Chicago ZIP Code Boundaries shapefile and place all related files (e.g., `.shp`, `.dbf`, `.shx`) inside the `data/zip_data/` folder.

## Running the Project

To execute the analysis and generate the interactive map, run the following command:

```bash
python chicago_crimes.py
```

This script will:
- Load the crime data from `data/Chicago_Crimes.csv` and create a GeoDataFrame.
- Clean and convert coordinate columns to numeric values.
- Load the ZIP Code Boundaries shapefile from `data/zip_data/`.
- Perform a spatial join to assign each crime to the corresponding ZIP code.
- Aggregate crime counts by ZIP code.
- Generate an interactive Folium map and save it as `output/chicago_crime_map.html`.

## Viewing the Results

Open the generated `output/chicago_crime_map.html` file in your web browser to interact with the map. The map displays:
- ZIP code areas color-coded by the number of crimes.
- Tooltips showing the ZIP code and corresponding crime count when hovering over an area.

## Troubleshooting

- **CSV Parsing Issues:**  
  If you experience issues reading the CSV file, ensure the file format is correct and that you have the appropriate column indices for latitude and longitude. Consider using parameters like `on_bad_lines='skip'` if needed.

- **Shapefile Issues:**  
  Verify that all components of the shapefile are present in the `data/zip_data/` folder and that the file paths in the script match your folder structure.

## Future Enhancements

- Extend the analysis to include temporal trends in crime data.
- Add additional interactive features to the visualization.
- Explore alternative spatial analysis or visualization libraries.

## Contact

For any questions or issues regarding this project, please contact:

[Your Name]  
Email: [your.email@example.com]
