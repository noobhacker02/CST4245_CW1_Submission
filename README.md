# CST4245 — Coursework 1: Tabular Data Analytics & Dashboard

**Global Metabolic Syndrome Indicators: A Visual Analysis of Hypertension, Obesity, and Diabetes Across 200 Countries (1980–2014)**

**Student:** Mohammad Talha Mohammad Salim Shaikh  
**Student ID:** M01090463  
**Module:** CST4245 — Data Visualisation, Computer Vision and Imaging  
**Tool:** Altair (Python) | **Dataset:** NCD Risk Factor Collaboration (NCD-RisC)

---

## What This Project Is

This coursework analyses how hypertension, obesity, and type 2 diabetes have changed across 200 countries between 1980 and 2014, using data published by the NCD Risk Factor Collaboration (NCD-RisC). The goal was to build a set of visualisations that surface patterns by sex, region, and country — and to explain the design choices behind each chart using Munzner's (2014) What-Why-How framework.

The analysis is presented as both a written report and an interactive HTML dashboard.

---

## Files in This Repository

```
├── CST4245_CW1_Submission_Final.docx   # Full written report (6 charts, framework, findings)
├── CST4245_Dashboard_Final.html        # Interactive dashboard (open in any browser)
├── cw1_cleaned_dataset.xlsx            # Cleaned and merged dataset with all transformations
└── README.md                           # This file
```

### Opening the Dashboard

Just open `CST4245_Dashboard_Final.html` in a browser — no server or installation needed. It loads Vega-Lite from a CDN so it requires an internet connection for the charts to render.

The dashboard includes:
- **Overview** — key stats and summary charts
- **Global Trends** — Chart 1: hypertension, obesity, diabetes trends 1980–2014 by sex
- **Gender Gap** — Chart 2: regional gender gap in hypertension over time
- **Obesity Rankings** — Chart 3: top and bottom 15 countries by obesity (2014)
- **Obesity–Diabetes** — Chart 4: scatter plot of obesity vs diabetes by country
- **Regional Heatmap** — Chart 5: hypertension by WHO region and decade
- **World Map** — Chart 6: global diabetes choropleth (2014)
- **Data Explorer** — searchable and sortable table of all 200 countries

---

## Dataset

**Source:** NCD Risk Factor Collaboration (NCD-RisC)  
Published in three Lancet papers (2016–2017) covering:
- Raised blood pressure (systolic ≥ 140 mmHg)
- Obesity (BMI ≥ 30 kg/m²)
- Age-standardised diabetes prevalence

Each condition is broken down by sex across 200 countries.

### Data Transformations (all documented in `cw1_cleaned_dataset.xlsx`)

| Transformation | Reason |
|---|---|
| Column rename | Standardise headers across sheets for merge |
| ×100 unit conversion | Convert proportions to percentages |
| WHO region mapping (manual dict) | Enable geographic grouping |
| Year restriction to 1980–2014 | Common coverage window across all three conditions |
| Inner join merge on Country × Sex × Year | Ensures no null values in merged rows |
| Gender gap column (Men − Women) | Derived feature used in Chart 2 |

**Merged dataset:** 14,000 rows · 200 countries · 35 years · 2 sexes · 0 null values

---

## Key Findings

**Hypertension is falling, obesity and diabetes are rising** — the three conditions are not telling the same story. Global mean hypertension fell by around 5–6 percentage points from 1980 to 2014, while obesity more than doubled and diabetes roughly doubled. This reflects different mechanisms and needs different policy responses.

**Europe has a reversed gender gap in hypertension** — women in Europe have substantially higher hypertension than men, with the regional gap running at −7 to −9 percentage points throughout the period. This is the opposite of the global pattern and is driven largely by Eastern European countries.

**Africa's hypertension hasn't improved at all** — sitting between 28.6% and 29.6% across all four decades, Africa is the only region that failed to show any meaningful improvement. Every other region improved. The causes are structural: low awareness, patchy screening, and expensive medication.

**The Eastern Mediterranean sits above the obesity-diabetes regression line** — countries in this region have more diabetes than their obesity rate alone would predict, consistent with evidence that South Asian and Arab populations develop type 2 diabetes at lower BMI thresholds than European populations (Misra & Khurana, 2011).

**The UAE sits firmly in the high-risk cluster** — female obesity at 41.4% and diabetes at 15.2% in 2014, both well above global averages and consistent with the wider Gulf pattern.

---

## Tech Stack

- **Python 3** — data cleaning and transformation
- **Pandas** — merging, reshaping, feature engineering
- **Altair / Vega-Lite 5** — all six visualisations
- **openpyxl** — reading and writing the Excel workbook
- **pycountry** — ISO code lookups for the choropleth map
- **HTML/CSS/JS** — dashboard built as a single self-contained file

---

## References

Cleveland, W.S. and McGill, R. (1984) 'Graphical perception: Theory, experimentation, and application to the development of graphical methods', *Journal of the American Statistical Association*, 79(387), pp. 531–554.

Few, S. (2009) *Now You See It: Simple Visualization Techniques for Quantitative Analysis*. Oakland: Analytics Press.

Mills, K.T. et al. (2016) 'Global disparities of hypertension prevalence and control', *Circulation*, 134(6), pp. 441–450.

Misra, A. and Khurana, L. (2011) 'Obesity-related non-communicable diseases: South Asians vs White Caucasians', *International Journal of Obesity*, 35(2), pp. 167–187.

Munzner, T. (2014) *Visualization Analysis and Design*. Boca Raton: CRC Press.

NCD Risk Factor Collaboration (NCD-RisC) (2016a) 'Trends in adult body-mass index in 200 countries from 1975 to 2014', *The Lancet*, 387(10026), pp. 1377–1396.

NCD Risk Factor Collaboration (NCD-RisC) (2016b) 'Worldwide trends in diabetes since 1980', *The Lancet*, 387(10027), pp. 1513–1530.

NCD Risk Factor Collaboration (NCD-RisC) (2017) 'Worldwide trends in blood pressure from 1975 to 2015', *The Lancet*, 389(10064), pp. 37–55.

Ng, M. et al. (2014) 'Global, regional, and national prevalence of overweight and obesity in children and adults during 1980–2013', *The Lancet*, 384(9945), pp. 766–781.

Popkin, B.M., Adair, L.S. and Ng, S.W. (2012) 'Global nutrition transition and the pandemic of obesity in developing countries', *Nutrition Reviews*, 70(1), pp. 3–21.

Tsugane, S. and Sawada, N. (2014) 'The JPHC study: design and some findings on the typical Japanese diet', *Japanese Journal of Clinical Oncology*, 44(9), pp. 777–782.
