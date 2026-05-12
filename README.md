# 📊 IS 107 — Laboratory Work 4
## Forecasting Time-Series Data in Power BI
https://drive.google.com/drive/folders/1DSMOl5pDzvJXw8I811Vzo2N9riNPf6Cr?usp=drive_link

> **Course:** IS 107 - Management Information Systems  
> **Activity:** Laboratory Work 4 — Forecasting Time-Series Data in Power BI  
> **Student:** Kian Nathaniel D. Saga 
> **Student No.:** 2022-0972 
> **Instructor:** Joseph Vistal 
> **Date Submitted:** April 29, 2026  

---

## 📁 Submission Contents

```
IS107_LW4_Submission/
│
├── 📄 README.md                          ← You are here
│
├── 📊 Datasets/
│   ├── tourism-data.csv                  ← Part 1: Original dataset (2012–2019)
│   └── tourism_data_modified.csv         ← Part 2: Modified dataset with COVID-19 disruptions (2012–2021)
│
├── 📝 Report/
│   └── IS107_LW4_Final_Report.docx       ← Complete written laboratory report
│
└── 💼 Power BI Files/
    ├── LW4_Part1_Tourism_Forecast.pbix   ← Part 1: Original tourism forecast
    └── LW4_Part2_Modified_Forecast.pbix  ← Part 2: Imperfect data forecast
```

---

## 🎯 Objective

To understand and apply the **forecasting capabilities of Microsoft Power BI** using time-series data — by replicating a tourism data forecast (Part 1) and extending the learning to a dataset containing real-world disruptions (Part 2).

---

## 📂 File Descriptions

### 1. `tourism-data.csv` — Part 1 Dataset
| Attribute | Details |
|-----------|---------|
| **Source** | [PacktPublishing GitHub Repository](https://raw.githubusercontent.com/PacktPublishing/Artificial-Intelligence-with-Power-BI/main/Chapter04/tourism-data.csv) |
| **Coverage** | January 2012 – December 2019 |
| **Records** | 96 monthly observations |
| **Columns** | `Period` (Date), `Total tourists` (Integer) |
| **Used in** | Part 1 — Steps 1 through 7 |

### 2. `tourism_data_modified.csv` — Part 2 Dataset
| Attribute | Details |
|-----------|---------|
| **Source** | Extended from the original tourism-data.csv |
| **Coverage** | January 2012 – December 2021 |
| **Records** | 120 monthly observations (+24 new data points) |
| **Columns** | `Period` (Date), `Total tourists` (Integer), `Notes` (Text) |
| **Disruption** | March 2020 – December 2021 (COVID-19 pandemic simulation) |
| **Used in** | Part 2 — Steps 8 through 12 |

### 3. `IS107_LW4_Final_Report.docx` — Laboratory Report
A complete written report covering all 12 steps of the activity, including:
- Step-by-step documentation of Power BI procedures
- All required visualizations (line charts, trend lines, forecasts)
- Analysis of forecast accuracy and confidence intervals
- Three forecast experiments (Ignore Last variations, CI comparisons)
- Conclusions on Power BI forecasting strengths and limitations

### 4. `LW4_Part1_Tourism_Forecast.pbix` — Part 1 Power BI File
Contains the following visuals on the report canvas:
- ✅ Line chart — Total tourists by Year (2012–2019)
- ✅ Line chart — Total tourists by Month (seasonal view)
- ✅ Trend line added to yearly chart
- ✅ 12-month forecast for 2020 (95% CI, Seasonality = 12)

### 5. `LW4_Part2_Modified_Forecast.pbix` — Part 2 Power BI File
Contains the following visuals on the report canvas:
- ✅ Line chart — Full dataset 2012–2021 showing COVID-19 disruption
- ✅ Forecast Experiment A: Ignore Last = 0
- ✅ Forecast Experiment B: Ignore Last = 6
- ✅ Forecast Experiment C: CI at 90% and 99%

---

## ⚙️ How to Open the Power BI Files

1. Install **[Power BI Desktop](https://powerbi.microsoft.com/desktop/)** (free)
2. Double-click any `.pbix` file to open it
3. If prompted about data source, click **"Keep current"**
4. All visuals and forecasts will load automatically

---

## 📊 Dataset Column Reference

### tourism-data.csv
```
Period          → Date (M/D/YYYY format, e.g., 1/1/2012 = January 1, 2012)
Total tourists  → Integer (monthly tourist count for the Netherlands)
```

### tourism_data_modified.csv
```
Period          → Date (M/D/YYYY format)
Total tourists  → Integer (monthly tourist count)
Notes           → Text (describes disruption type for 2020–2021 records)
```

> ⚠️ **Important:** When importing into Power BI, set the `Period` column data type to  
> **Date using Locale: English (United States)** to ensure correct M/D/YYYY parsing,  
> especially on systems using Philippine (D/M/YYYY) date format.

---

## 🔑 Key Concepts Demonstrated

| Concept | Description |
|---------|-------------|
| **Time-Series Forecasting** | Using historical patterns to predict future values |
| **Exponential Smoothing (ETS)** | Power BI's built-in forecasting algorithm |
| **Seasonality** | Set to 12 — representing the 12-month tourism cycle |
| **Confidence Interval** | The shaded band showing forecast uncertainty range |
| **Ignore Last** | Excludes recent data points from training for validation |
| **Trend Line** | Linear fit confirming upward/downward direction of data |

---

## 📈 Forecast Configuration Summary

### Part 1 Settings
| Setting | Value |
|---------|-------|
| Forecast Length | 12 points |
| Ignore Last | 0 |
| Confidence Interval | 95% |
| Seasonality | 12 |

### Part 2 Experiments
| Experiment | Forecast Length | Ignore Last | CI | Seasonality |
|------------|----------------|-------------|-----|-------------|
| A (Baseline) | 12 | 0 | 95% | 12 |
| B (Validation) | 12 | 6 | 95% | 12 |
| C (CI Compare) | 12 | 0 | 90% / 99% | 12 |

---

## 📌 Key Findings

1. **Clean data = reliable forecasts** — The Part 1 model produced a narrow confidence interval, indicating high forecast precision when trained on consistent, seasonal data.

2. **Disrupted data = wider uncertainty** — The Part 2 model trained on COVID-19 affected data produced significantly wider confidence bands, reflecting reduced reliability.

3. **Power BI cannot predict black swan events** — The forecasting model could not anticipate the COVID-19 pandemic since there was no historical precedent in the training data.

4. **Confidence interval width is a quality signal** — Narrow CI = trustworthy forecast; Wide CI = treat predictions with caution.

---

## 📚 References

- Russo, M., Ferrari, A., & Webb, C. (2021). *Artificial Intelligence with Power BI*. Packt Publishing.
- Microsoft Corporation. (2024). *Forecasting in Power BI visuals*. https://learn.microsoft.com/en-us/power-bi
- Hyndman, R.J., & Athanasopoulos, G. (2021). *Forecasting: Principles and Practice* (3rd ed.). OTexts. https://otexts.com/fpp3/

---

*Submitted as partial fulfillment of the requirements for IS 107 — Management Information Systems*
