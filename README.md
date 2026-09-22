# 📊 Investor Intelligence Dashboard

<p align="center">
  <img src="Investor-Intelligence-Dashboard/Screenshots/Screenshot%202026-09-22%20144411.png" width="100%">
</p>

<p align="center">
  <b>Interactive Power BI dashboard for investor intelligence, source analysis, company coverage, and geographic insights.</b>
</p>

---

## 📌 Project Overview

The **Investor Intelligence Dashboard** is an interactive Power BI business intelligence project designed to consolidate, clean, analyze, and explore investor information collected from multiple sources.

The project combines investor records from **websites** and **LinkedIn**, transforms the raw data using **Excel and Power Query**, and presents the results through an interactive Power BI dashboard.

The dashboard provides a centralized view of investor distribution, company coverage, geographic distribution, investor sources, and detailed investor records.

---

## 🎯 Project Objectives

* Consolidate investor information from multiple sources
* Clean and standardize raw investor data
* Combine Website and LinkedIn investor datasets
* Preserve company and LinkedIn URLs as clickable links
* Analyze investor distribution by source
* Analyze investor distribution by country
* Identify companies with the highest number of investors
* Provide an interactive investor exploration table
* Build a professional business intelligence dashboard

---

## 📂 Data Sources

The project uses two primary investor datasets:

### 🌐 Website Investors

Investor records collected from website-based sources.

### 💼 LinkedIn Investors

Investor records collected from LinkedIn connections.

The two datasets were **appended** into a unified master table rather than merged because the objective was to retain investor records from both sources.

### Final Dataset

| Metric             | Value |
| ------------------ | ----: |
| Total Records      |   444 |
| Distinct Investors |   432 |
| Website Investors  |   244 |
| LinkedIn Investors |   188 |
| Company Coverage   |   97% |
| Email Coverage     |   78% |

---

## 🔄 Data Preparation & Transformation

The data preparation workflow included:

1. Raw data collection
2. Excel-based data preparation
3. Hyperlink extraction
4. Removal of unnecessary fields
5. Data cleaning and standardization
6. Missing-value handling
7. Power Query transformation
8. Appending Website and LinkedIn datasets
9. Creation of the `Investors Source` field
10. Creation of the final `Append1` master table
11. URL configuration for clickable links
12. DAX-based analytical measures
13. Power BI dashboard development

---

## 🔗 URL & Hyperlink Handling

Company and LinkedIn URLs were preserved during the data preparation process.

Within the Power BI dashboard:

* **Company Name** → clickable company website
* **Full Name** → clickable LinkedIn profile

The raw URL fields were retained in the underlying data model while being hidden from the final dashboard table for a cleaner user experience.

---

## 📊 Dashboard Features

### KPI Cards

The dashboard includes:

* **Total Investors**
* **Website Investors**
* **LinkedIn Investors**
* **Company Coverage**
* **Email Coverage**

### Interactive Visualizations

* **Top 10 Companies**
* **Investors by Country**
* **Investor Source Distribution**
* **Investor Explorer**

### Interactive Filters

* Investor Source
* Country

The visuals dynamically respond to the selected filters.

---

## 🧮 DAX Measures

The dashboard uses DAX measures for investor analysis and data-quality coverage.

### Total Investors

```DAX
Total Investors =
DISTINCTCOUNT(Append1[Full Name])
```

### Website Investors

```DAX
Website Investors =
CALCULATE(
    DISTINCTCOUNT(Append1[Full Name]),
    REMOVEFILTERS(Append1[Investors Source]),
    Append1[Investors Source] = "Website"
)
```

### LinkedIn Investors

```DAX
LinkedIn Investors =
CALCULATE(
    DISTINCTCOUNT(Append1[Full Name]),
    Append1[Investors Source] = "LinkedIn"
)
```

### Email Coverage

```DAX
Email Coverage % =
DIVIDE(
    CALCULATE(
        COUNTROWS(Append1),
        Append1[Email] <> BLANK()
    ),
    COUNTROWS(Append1)
)
```

### Company Coverage

```DAX
Company Coverage % =
DIVIDE(
    CALCULATE(
        COUNTROWS(Append1),
        Append1[Company Name] <> BLANK()
    ),
    COUNTROWS(Append1)
)
```

---

## 🏗️ Power BI Data Model

The project uses a consolidated master table:

**`Append1`**

with the following final fields:

```text
Full Name
Role
Company Name
Email
Country
Company_URL
LinkedIn_URL
Investors Source
```

The dashboard separates the investor population using the `Investors Source` field:

```text
Website
LinkedIn
```

---

## 📈 Dashboard Insights

The dashboard enables users to explore:

* Overall investor volume
* Investor source distribution
* Geographic distribution
* Companies with the highest investor representation
* Investor roles
* Company information
* Available investor contact information
* Company websites
* LinkedIn profiles

---

## 🛠️ Tools & Technologies

| Category              | Technologies                 |
| --------------------- | ---------------------------- |
| Business Intelligence | Power BI                     |
| Data Transformation   | Power Query                  |
| Analytics             | DAX                          |
| Data Preparation      | Microsoft Excel              |
| Visualization         | Power BI                     |
| Data Cleaning         | Excel, Power Query           |
| Hyperlink Handling    | Excel VBA / Power BI Web URL |

---

## 💼 Business Use Cases

The dashboard can support:

* Investor research
* Investor discovery
* Company-level analysis
* Geographic analysis
* Business development research
* Relationship management
* Contact discovery
* Data-driven investor intelligence

---

## 📸 Dashboard Preview

The dashboard provides an interactive interface containing KPI cards, filters, charts, and an investor exploration table.

The screenshot above provides a static preview of the Power BI dashboard.

---

## 📁 Project Structure

```text
Investor-Intelligence-Dashboard/
│
├── README.md
│
└── Investor-Intelligence-Dashboard/
    │
    ├── Investors Database Dashboard.pbix
    │
    ├── Investor_Intelligence_Dashboard_Complete_Documentation.pdf
    │
    └── Screenshots/
        │
        └── Screenshot 2026-09-22 144411.png
```

---

## 📚 Project Documentation

Detailed project documentation is included in the repository.

The documentation covers:

* Project objective
* Data sources
* Data cleaning
* Hyperlink extraction
* Power Query transformations
* Append vs. Merge
* Master table creation
* DAX measures
* Dashboard development
* KPI design
* Visual configuration
* Dashboard layout
* Technical architecture
* Business use cases

---

## 🧠 Skills Demonstrated

* Power BI
* Power Query
* DAX
* Excel
* Data Cleaning
* Data Transformation
* Data Modeling
* Data Visualization
* Dashboard Design
* Business Intelligence
* Analytical Thinking
* Data Quality Analysis

---

## 👨‍💻 Project Focus

This project demonstrates an end-to-end **Business Intelligence workflow**:

```text
Raw Investor Data
        ↓
Excel Data Preparation
        ↓
Hyperlink Extraction
        ↓
Power Query Cleaning
        ↓
Data Transformation
        ↓
Append Multiple Sources
        ↓
Master Investor Table
        ↓
DAX Measures
        ↓
Power BI Visualization
        ↓
Interactive Investor Intelligence Dashboard
```

---

## ⚠️ Data Privacy

The underlying investor information may contain personal or contact information.

For public portfolio use, sensitive or personally identifiable information should be **anonymized, redacted, or replaced with demonstration data** before publishing the dataset or screenshots publicly.

---

## ⭐ Project Summary

**Investor Intelligence Dashboard** demonstrates how raw multi-source investor information can be transformed into a structured, interactive, and business-ready Power BI solution using **Excel, Power Query, DAX, and Power BI**.
