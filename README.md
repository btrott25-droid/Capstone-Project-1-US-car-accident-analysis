# US Traffic Accident Severity Analysis

## Project Overview

This project analyzes US traffic accident records from 2016 through 2023 to identify patterns in accident frequency and severe-accident risk. The analysis was developed for a Department of Transportation audience with the goal of identifying actionable opportunities to improve road safety and prioritize safety resources.

The project includes data cleaning, exploratory data analysis, statistical hypothesis testing, recommendations, and an interactive Tableau dashboard.

## Business Problem

Traffic accidents create major public safety, economic, and infrastructure challenges. For transportation agencies, it is not enough to know where accidents happen most often. Agencies also need to understand where accidents are more likely to become severe.

This project investigates patterns in accident severity across time, weather conditions, roadway features, and geography. Severe accidents were defined as accidents with Severity 3 or 4, while Severity 1 or 2 accidents were classified as non-severe.

## Dataset

The analysis uses the US Accidents dataset, which contains traffic accident records across the United States from 2016 through 2023.

After cleaning, the dataset contained:

* **7,728,394 accident records**
* **1,504,047 severe accidents**
* **6,224,347 non-severe accidents**
* **Overall severe-accident rate:** 19.46%

The cleaned dataset was used for exploratory analysis, statistical testing, and dashboard preparation. Large raw and processed data files are not included in this repository due to file-size limitations.

## Main Findings

### 1. Junction-related accidents are a major severity concern

Junction-related accidents had a severe-accident rate of **26.79%**, compared to **18.88%** for non-junction accidents. This was the strongest tested relationship among the main categorical factors and suggests that intersections, ramps, merges, and other junction areas should be prioritized for safety audits and infrastructure improvements.

### 2. Precipitation is associated with higher accident severity

Accidents with recorded precipitation had a severe-accident rate of **22.89%**, compared to **19.21%** for accidents without recorded precipitation. Statistical testing confirmed this relationship, although the effect size was modest. Precipitation is best interpreted as a contributing environmental risk factor rather than a standalone cause of severe accidents.

### 3. Accident frequency and accident severity do not always follow the same patterns

Weekdays had more total accidents, but weekends had a higher severe-accident rate: **21.60%** compared to **19.06%** on weekdays. Geographic analysis also showed that high accident-count areas are not always the same as high severe-rate areas. This means safety planning should consider both accident volume and severe-accident rate.

## Statistical Analysis

The project used several statistical methods to validate patterns found during EDA:

* Chi-square tests of independence for categorical relationships
* Mann-Whitney U tests for nonparametric comparison of precipitation amounts
* ANOVA and Kruskal-Wallis tests to compare precipitation amount across original severity levels
* Spearman correlation analysis for numeric variables

The three main chi-square tests found statistically significant associations between accident severity and:

* Recorded precipitation
* Weekend status
* Junction status

Because the dataset is very large, p-values were interpreted alongside severe-rate differences and effect sizes such as Cramér’s V.

## Recommendations

Based on the analysis, the project recommends:

1. **Prioritize safety improvements at high-risk junctions and intersections**

   * Conduct roadway safety audits.
   * Improve signal timing, signage, lighting, turn lanes, and lane markings.
   * Track severe-accident rates before and after interventions.

2. **Strengthen weather-responsive traffic safety measures during precipitation**

   * Use dynamic message signs and weather-based alerts.
   * Improve drainage in high-risk wet-weather locations.
   * Track severe accidents during precipitation events.

3. **Target weekend severe-accident risk**

   * Increase weekend safety messaging and enforcement.
   * Focus on high-risk weekend travel periods.
   * Track weekend severe-accident rates over time.

4. **Use both accident volume and severe-accident rate for geographic prioritization**

   * High accident-count areas are not always the highest severity-risk areas.
   * DOT planning should consider both total accident counts and severe-accident rates.

## Tableau Dashboard

An interactive Tableau dashboard was created to help users explore accident patterns by year, state, junction status, precipitation status, and weekend status.

**Dashboard Link:**
[US Traffic Accident Severity Dashboard](https://public.tableau.com/app/profile/bennett.trott/viz/USTrafficAccidnetSeverityDashboard/USAccidentSeverityDashboard?publish=yes)

The dashboard includes:

* Total accidents
* Severe accidents
* Overall severe-accident rate
* Junction severe-accident rate
* Accident count by year
* Top states by accident count
* Severe rate by junction status
* Severe rate by precipitation status
* Severe rate by weekend status
* State and year filters

## Repository Structure

```text
Capstone-Project-1-US-car-accident-analysis/
│
├── Data/
│   └── Large raw and processed data files are excluded from GitHub
│
├── Images/
│   └── Tableau Screenshot.png
│
├── US_Traffic_Accidents_Analysis.ipynb
├── DS_Capstone_Notebook.ipynb
├── requirements.txt
├── README.md
├── LICENSE
└── .gitignore
```

## How to Run the Notebook

1. Clone this repository.
2. Install the required Python packages using `requirements.txt`.
3. Add the required US Accidents dataset files to the `Data/` folder.
4. Open `US_Traffic_Accidents_Analysis.ipynb`.
5. Run the notebook cells in order.

Example:

```bash
pip install -r requirements.txt
```

Large CSV and parquet files are excluded from this repository to avoid exceeding GitHub file-size limits.

## Tools Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* SciPy
* Jupyter Notebook
* Tableau Public
* Git/GitHub

## Limitations

Several limitations should be considered:

* The dataset includes recorded accidents only and may be affected by reporting differences across locations and agencies.
* 2023 data is partial through March 31 and should not be compared directly with full prior years.
* Statistical significance is influenced by the very large sample size, so practical significance was evaluated using severe-rate differences and effect sizes.
* Weather and roadway variables may contain missing values, measurement error, or inconsistent reporting.
* The analysis identifies associations, not causation.
* Large data files are excluded from the GitHub repository due to file-size limitations.

## Conclusion

This project found that accident severity is influenced by a combination of roadway, weather, temporal, and geographic factors. Junction-related accidents stood out as the most actionable severity-related finding, while precipitation and weekend status were also associated with higher severe-accident rates.

The results suggest that transportation agencies should look beyond total accident counts and prioritize locations and conditions where accidents are more likely to become severe.
