# Smoking and Health Analysis Dashboard

A dashboard project built for the Sapphire IQ healthcare analytics brief. It looks at 10,000 patient records and shows how smoking habits, blood pressure, cholesterol and recorded health conditions vary across age groups, gender and region.

This is exploratory work. It doesn't diagnose anyone and it doesn't show that smoking causes any condition.

## What's in this repo

| Path | What it is |
|---|---|
| `data/Smoking_Health_Analysis.csv` | The patient-level dataset (10,000 rows, 15 columns) |
| `Smoking_Health_Analysis_Dashboard.xlsx` | Excel version: KPIs, summary tables and charts, all built with formulas |
| `dashboard/smoking_health_dashboard.html` | Interactive web version. Open it in any browser; click a bar to filter everything |
| `powerbi/smoking_health_powerbi.dax` | DAX columns and measures, for anyone who wants to rebuild this in Power BI |
| `docs/Sapphire_IQ_Smoking_and_Health_Analysis.pdf` | The original project brief |

## What the dashboard answers

1. Overall KPIs: total patients, current smokers, patients with a recorded organ category, patients with a recorded health condition.
2. Derived fields: Age Group (18-29, 30-44, 45-59, 60+) and BP Risk Category (Lower Range, Elevated, High).
3. Smoking patterns: average cigarettes per day by smoking status, organ-wise condition breakdown, smoking status split, and average cholesterol by BP risk category.
4. Demographics: current smokers by age group, and recorded conditions across smoking exposure levels.

## Headline numbers

- 10,000 patients
- 3,015 current smokers (30.2%)
- 7,227 patients with a recorded organ category
- 5,772 patients with a recorded health condition
- Current smokers average about 17 cigarettes a day

## How to use it

- **Excel:** open `Smoking_Health_Analysis_Dashboard.xlsx`. The Dashboard sheet has the KPIs and charts, Organ Conditions has the condition breakdown, and Data holds the raw rows plus the calculated columns.
- **Web dashboard:** open `dashboard/smoking_health_dashboard.html` in a browser. It needs no install and no internet connection.
- **Power BI:** load the CSV, then paste the definitions from the `.dax` file into new columns and measures. The notes at the bottom of that file say which visual to use for each question.

## Assumptions

The brief didn't define these, so I picked them:

- **BP Risk Category:** High is systolic 140 or above, or diastolic 90 or above. Elevated is 120/80 or above. Anything lower is Lower Range.
- **Estimated smoking exposure:** pack-years, calculated as cigarettes per day divided by 20, times years smoking. Bands are None, Low (under 10), Moderate (10-29) and High (30+).
- **Former and never smokers:** the data records their cigarettes per day as 0, so they all fall under an exposure of None, even though former smokers did smoke.
- **Recorded organ category:** any value other than "No Recorded Organ Condition".
- **Recorded health condition:** any value other than "No Diagnosed Condition".

If you change a cut-off, change it in one place (the Data sheet formulas in Excel, or the DAX columns in Power BI) and the charts will follow.

## Data columns

Patient_ID, Age, Gender, Region, Diagnosis_Date, Smoking_Status, Cigarettes_Per_Day, Years_Smoking, Diagnosed_Organ, Health_Condition, Total_Cholesterol_mg_dL, Systolic_BP_mmHg, Diastolic_BP_mmHg, BMI, Resting_Heart_Rate_bpm

## Author

Mohd Moin Mulla
