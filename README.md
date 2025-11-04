# French Baby Names Visualization Project

A data visualization project analyzing French baby name trends from 1900 to 2020, using interactive visualizations to explore patterns across departments, time periods, and gender distributions.

## Overview

This project explores the French baby names dataset (`dpt2020.csv`) to answer three key questions about naming trends in France over the past 120 years. The analysis uses Python with pandas for data processing and Altair for creating interactive visualizations.

## Dataset

The project uses the official French baby names dataset, which contains:
- **sexe**: Gender (1 = Male, 2 = Female)
- **preusuel**: First name
- **annais**: Year of birth
- **dpt**: Department code (French administrative division)
- **nombre**: Number of occurrences

The dataset also includes geographic data (`departements-version-simplifiee.geojson`) for mapping visualizations.

## Questions Answered

### Question 1: Name Popularity Over Time
Tracks the evolution of specific names (e.g., Thomas, Lucas, Jean) across different time periods, showing how naming trends have changed throughout the 20th and 21st centuries.

### Question 2: Most Popular Names by Department (2010-2020)
Creates an interactive choropleth map showing the most popular baby name in each French department for births from 2010 onwards, revealing regional naming preferences.

### Question 3: Gender Distribution of Unisex Names
Analyzes names that are used for both males and females (e.g., Camille), showing how the gender distribution of these names has evolved over time through interactive stacked bar charts.

## Requirements

```python
pandas
altair
geopandas
ipywidgets
```

Install dependencies with:
```bash
conda install -c conda-forge geopandas
pip install pandas altair ipywidgets
```

## Usage

1. **Clone the repository** and ensure all data files are in the same directory:
   - `Baby.ipynb`
   - `dpt2020.csv`
   - `departements-version-simplifiee.geojson`

2. **Open the Jupyter notebook**:
   ```bash
   jupyter notebook Baby.ipynb
   ```

3. **Run all cells in order** to generate the visualizations. The notebook includes:
   - Data loading and preprocessing
   - Interactive visualizations for each question
   - A dropdown widget for exploring different names in Question 3

## Key Features

### Interactive Visualizations
- **Choropleth map**: Hover over departments to see the most popular name and occurrence count
- **Line charts**: Compare multiple names over time with color-coded legends
- **Stacked bar charts**: Explore gender proportions with tooltips showing exact counts
- **Dropdown menu**: Select any unisex name to see its gender distribution over time

### Data Processing
- Filters out rare names (marked as `_PRENOMS_RARES`)
- Removes unknown departments (marked as `XX`)
- Aggregates data by department, year, and gender
- Creates 5-year bins for temporal analysis (1900-1905, 1905-1910, etc.)

### Visualization Updates (Post-Revision)
The project was refined based on peer feedback:
- **Question 3** now uses stacked bar charts showing proportions instead of overlapping bars
- Tooltips include both proportions and exact counts for better context
- All year bins are represented even when count is zero
- Clearer gender distinction with consistent color coding (blue for male, red for female)

## Project Structure

```
.
├── Baby.ipynb                              # Main Jupyter notebook
├── dpt2020.csv                             # Baby names dataset
├── departements-version-simplifiee.geojson # Geographic data
└── README.md                               # This file
```

## Notable Findings

The visualizations reveal interesting patterns:
- Names like "Marie" and "Jean" dominated early 20th century French naming
- Regional variations in name popularity are visible across departments
- Names like "Camille" show dramatic shifts in gender association over time
- Recent decades show more diversity in naming choices

## Technical Notes

- **Altair data transformer**: The notebook uses `alt.data_transformers.enable('json')` to handle larger datasets by storing data externally rather than embedding it in the visualization
- **ipywidgets integration**: Question 3 uses ipywidgets for dropdown interactivity, as Altair's native selection doesn't support the required data transformation approach
- **GeoPandas**: Required for handling and visualizing geographic data

## Troubleshooting

**JavaScript visualization not showing**: Run all cells in the notebook. The JavaScript sometimes needs to be reloaded to display visualizations properly.

**Missing dependencies**: Make sure geopandas is installed via conda-forge, as pip installation may have issues with spatial dependencies.

## Future Improvements

Potential enhancements could include:
- Time-slider animation showing name popularity evolution
- Clustering analysis of regional naming patterns
- Prediction models for future naming trends
- Integration with cultural/historical events data

## License

This project uses publicly available French government data. Please check the original data source for usage terms.

## Acknowledgments

Dataset provided by INSEE (Institut national de la statistique et des études économiques) - French National Institute of Statistics and Economic Studies.

---

**Note**: Look for markdown cells with "### Answer to question #" headings in the notebook to identify the final solution for each question.

![image](https://github.com/lisarosilio/igr204-Mini-Project/assets/70438076/b6949446-efd5-4fa7-a679-ba7be99efebe)

*waiting for your interesting thoughts on them!*
