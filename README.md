# CST4245 CW1 — Global Metabolic Syndrome Dashboard

**Student:** Mohammad Talha Mohammad Salim Shaikh
**Student ID:** M01090463
**Module:** CST4245 — Data Visualisation, Computer Vision and Imaging

**Live Dashboard:** https://cst-4245-cw-1-submission.vercel.app
**GitHub:** https://github.com/noobhacker02/CST4245_CW1_Submission

---

## File Structure

```
CST4245_CW1_Submission/
├── README.md
├── CST4245_CW1_Report.docx        Written report with all 6 charts and commentary
├── CST4245_Dashboard.html         Self-contained dashboard, open in any browser
└── charts/
    ├── png/                       Static chart images used in the report
    │   ├── chart1_global_trends.png
    │   ├── chart2_gender_gap.png
    │   ├── chart3_top_bottom_obesity.png
    │   ├── chart4_scatter_bmi_diabetes.png
    │   ├── chart5_heatmap_region_decade.png
    │   └── chart6_choropleth_diabetes.png
    └── html/                      Individual interactive Vega-Lite chart files
        ├── chart1_global_trends.html
        ├── chart2_gender_gap.html
        ├── chart3_top_bottom_obesity.html
        ├── chart4_scatter_bmi_diabetes.html
        ├── chart5_heatmap_region_decade.html
        └── chart6_choropleth_diabetes.html
```

---

## How to Open the Dashboard

Just double-click `CST4245_Dashboard.html` in any browser. No installation needed.
It works fully offline. All chart images are embedded inside the file.

---

## Dataset

Source: NCD Risk Factor Collaboration (NCD-RisC)
Three conditions: raised blood pressure, obesity (BMI 30+), age-standardised diabetes
Coverage: 200 countries, 1980 to 2014
Merged dataset: 14,000 rows, zero nulls

## Data Transformations

| Step | What was done |
|---|---|
| Column rename | Standardised headers across all three sheets for the merge |
| Unit conversion | Proportions multiplied by 100 to give percentages |
| Region mapping | Each country assigned to one of six WHO regions using a manual Python dictionary |
| Year restriction | Restricted to 1980 to 2014 (common coverage window across all three conditions) |
| Inner join merge | Joined on Country, Sex and Year so every row has valid values for all three conditions |
| Gender gap column | Men minus Women per country per year, used in Chart 2 |

## Charts

| Chart | Type | What it shows |
|---|---|---|
| 1 | Line chart (small multiples) | Global prevalence trends 1980 to 2014 split by sex |
| 2 | Line chart | Hypertension gender gap by WHO region over time |
| 3 | Stacked bar chart | Top and bottom 15 countries by obesity in 2014 |
| 4 | Scatter plot | Obesity vs diabetes by country, coloured by region |
| 5 | Heatmap | Mean hypertension by WHO region and decade |
| 6 | Choropleth map | Global diabetes prevalence by country in 2014 |

## Key Findings

- Hypertension fell by about 5 to 6 percentage points globally from 1980 to 2014. Obesity more than doubled. Diabetes roughly doubled.
- Africa is the only WHO region that showed no improvement in hypertension across all four decades.
- Europe is the only region where women consistently have higher hypertension than men throughout the entire study period.
- The Eastern Mediterranean cluster sits above the regression line in Chart 4, meaning these countries have more diabetes per unit of obesity than the global trend predicts.
- UAE female obesity was 41.4% in 2014 with diabetes at 15.2%, both well above global averages.

## References

Cleveland and McGill (1984). Journal of the American Statistical Association, 79(387).
Few (2009). Now You See It. Analytics Press.
Mills et al. (2016). Circulation, 134(6).
Misra and Khurana (2011). International Journal of Obesity, 35(2).
Munzner (2014). Visualization Analysis and Design. CRC Press.
NCD-RisC (2016a). The Lancet, 387(10026).
NCD-RisC (2016b). The Lancet, 387(10027).
NCD-RisC (2017). The Lancet, 389(10064).
Ng et al. (2014). The Lancet, 384(9945).
Popkin et al. (2012). Nutrition Reviews, 70(1).
Tsugane and Sawada (2014). Japanese Journal of Clinical Oncology, 44(9).
