
# CO2 Emissions from Global Dietary Data (EMRO Region)

This repository contains tools and scripts for calculating and analyzing CO2 emissions from global dietary data, with a specific focus on countries in the **Eastern Mediterranean Region (EMRO)**. The project includes modules for emissions calculations, diet scoring, and insights into sustainable dietary practices.

## Repository Structure

```
CLIMATE_CHANGE/
│
├── co2_calc/
│   ├── emissions/
│   ├── emissions.ipynb             # Notebook for calculating emissions from dietary data
│   │ 
│   ├── global_emissions/
│   ├── emissions_global.ipynb      # Global-level emissions analysis
│   │ 
│   ├── task1.ipynb                 # Task 1 calculating CO2 emissions for specific food items (details in notebooks)
│   └── task2.ipynb                 # Task 2 calculating CO2 emissions for various food groups (details in notebooks)
│
├── diet_calc/
│   ├── scores/                     # Results of calculations 
│   │ 
│   ├── dash_score.ipynb            # Calculating DASH diet scores
│   ├── eat.ipynb                   # Calculating EAT-Lancet diet scores
│   ├── medit_score.ipynb           # Calculating Mediterranean diet scores
│   └── plant_based_score.ipynb     # Calculating plant-based diet scores
│
├── raw_data/
│   └── (data files)                # Raw input data for analysis *GDD dataset* 
│
├── .gitattributes                  # Git configuration for attributes
├── .gitignore                      # Ignored files for version control
└── README.md                       # Project overview and usage information
```

---

## Objectives

This project aims to:
1. **Quantify CO2 emissions** from dietary patterns using global and EMRO-specific datasets.
2. Provide insights into the environmental impact of different diets, including:
   - Plant-based diets
   - Mediterranean diets
   - DASH (Dietary Approaches to Stop Hypertension)
   - EAT-Lancet recommendations.
3. Highlight sustainable dietary practices for countries in the EMRO region.

---

## Notebooks Overview

### CO2 Emissions Calculations (`co2_calc/`)
- **`emissions/emissions.ipynb`**: Analyze dietary data to estimate CO2 emissions for different food categories.
- **`global_emissions/`**: 
  - `emissions_global.ipynb`: Provides a global perspective on dietary CO2 emissions.
  - `task1.ipynb`: Calculating CO2 emissions for specific food items (details in notebooks)
  - `task2.ipynb`: Calculating CO2 emissions for various food groups (details in notebooks)

### Diet Scoring (`diet_calc/`)
- **`dash_score.ipynb`**: Computes DASH scores for dietary patterns.
- **`eat.ipynb`**: Assesses compliance with the EAT-Lancet guidelines.
- **`medit_score.ipynb`**: Evaluates Mediterranean diet adherence.
- **`plant_based_score.ipynb`**: Scores diets based on plant-based criteria.

---

## Data Sources

The analysis relies on:
- **Global dietary data**: Collected and processed from publicly available sources.
- **EMRO-specific dietary datasets**: Focused on dietary habits in the Eastern Mediterranean Region.

Ensure that raw data is placed in the `raw_data/` folder.

---

## How to Use

1. Clone the repository:
   ```bash
   git clone <repository_url>
   cd CLIMATE_CHANGE
   ```

2. Set up the required Python environment:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the notebooks:
   - Open Jupyter Notebook or Jupyter Lab.
   - Navigate to the desired folder (e.g., `co2_calc/emissions/`) and run the `.ipynb` file.

---

## Contributions

Contributions to improve the analysis, add new diet scoring methods, or refine regional insights are welcome. Please open an issue or submit a pull request.

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
