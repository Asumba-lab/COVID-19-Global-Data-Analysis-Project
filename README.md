# COVID-19 Global Data Tracker Project

## Project Overview
This project analyzes global COVID-19 trends including cases, deaths, and vaccination progress across different countries. The analysis focuses on data cleaning, exploratory data analysis (EDA), and visualization to uncover meaningful insights about the pandemic's impact worldwide.

## Project Structure
```
covid-19-tracker/
├── data/                    # Contains raw and processed data
│   └── owid-covid-data.csv  # Source dataset
├── notebooks/               # Jupyter notebooks with analysis
│   └── COVID-19_Analysis.ipynb
├──  index.ipynb reports/    # Generated reports and visualizations
├── README.md                # This file
└── requirements.txt         # Python dependencies
```

## Data Sources
- Primary dataset: [Our World in Data COVID-19 Dataset](https://ourworldindata.org/covid-deaths)
- Alternative source: [Johns Hopkins University GitHub Repository](https://github.com/CSSEGISandData/COVID-19)

## Installation Instructions

### Prerequisites
- Python 3.8+
- Jupyter Notebook/Lab
- Git (optional)

### Setup
1. Clone the repository:
git clone https://github.com/Asumba-lab/COVID-19 Global Data Analysis Project.git
cd covid-19-tracker
```

2. Create and activate a virtual environment:
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
```

3. Install dependencies:
pip install -r requirements.txt
```

4. Launch Jupyter Notebook:
jupyter notebook
```

## Project Implementation

### Key Steps Performed
1. **Data Collection**: Downloaded the OWID dataset
2. **Data Loading & Exploration**: Initial examination of dataset structure
3. **Data Cleaning**: Handled missing values, filtered countries, converted data types
4. **Exploratory Data Analysis**: Analyzed cases, deaths, and vaccination trends
5. **Visualization**: Created various charts and maps
6. **Insights & Reporting**: Documented key findings

### Example Code Snippets
```python
# Load and clean data
import pandas as pd
covid_df = pd.read_csv('data/owid-covid-data.csv')
covid_df['date'] = pd.to_datetime(covid_df['date'])

# Plot cases over time
import matplotlib.pyplot as plt
selected_countries = ['United States', 'India', 'Brazil', 'Germany']
for country in selected_countries:
    country_data = covid_df[covid_df['location'] == country]
    plt.plot(country_data['date'], country_data['total_cases'], label=country)
plt.legend()
plt.show()
```

## Key Findings
1. **Case Trends**: The United States had the highest total cases among analyzed countries
2. **Mortality**: Brazil showed the highest death rate (~4.5%)
3. **Vaccination Progress**: Germany achieved the highest vaccination rate (>75%)
4. **Global Patterns**: Developed nations had higher vaccination rates but also higher case counts

## Deliverables
- Jupyter Notebook with complete analysis
- Interactive visualizations
- PDF report summarizing findings
- This README documentation

## Dependencies
Listed in `requirements.txt`:
```
pandas>=1.3.0
numpy>=1.21.0
matplotlib>=3.4.0
seaborn>=0.11.0
plotly>=5.0.0
jupyter>=1.0.0
```

## Usage
1. Open `notebooks/COVID-19_Analysis.ipynb` in Jupyter
2. Run cells sequentially to reproduce analysis
3. Modify country selections or time periods as needed

## License
This project is licensed under the MIT License

## Acknowledgments
- Our World in Data for the comprehensive dataset
- Johns Hopkins University for alternative data source
- Python data science community for excellent libraries
