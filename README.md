# Investor Intelligence Dashboard

## 📊 Project Overview

The Investor Intelligence Dashboard is an interactive Power BI dashboard designed to analyze and explore investor data collected from website and LinkedIn sources.

The dashboard transforms raw investor data into a structured, interactive view that helps users understand investor distribution, company coverage, geographic distribution, and investor details.

## 🎯 Project Objectives

- Consolidate investor data from multiple sources
- Clean and transform raw data using Power Query
- Preserve company and LinkedIn URLs as clickable links
- Analyze investor distribution by source and country
- Identify companies with the highest number of investors
- Provide an interactive investor exploration table
- Build a professional, recruiter-ready Power BI dashboard

## 🗂️ Data Sources

The project combines two investor datasets:

- **Website Investors** – investor records collected from websites
- **LinkedIn Investors** – investor records collected from LinkedIn

After data preparation, the final master table contains **444 investor records** and **432 distinct investors**.

## 🛠️ Tools & Technologies

- Power BI
- Power Query
- DAX
- Microsoft Excel
- Data Cleaning & Transformation
- Data Visualization
- URL / Hyperlink Handling

## 🔄 Data Preparation

The data preparation process included:

1. Cleaning raw investor records
2. Removing unnecessary fields
3. Extracting company and LinkedIn URLs
4. Handling missing values
5. Standardizing investor information
6. Appending Website and LinkedIn datasets
7. Creating an `Investors Source` field
8. Creating the final `Append1` master table

## 📈 Dashboard Features

### KPI Cards

- Total Investors
- Website Investors
- LinkedIn Investors
- Company Coverage
- Email Coverage

### Interactive Visuals

- Top 10 Companies
- Investors by Country
- Investor Source Distribution
- Investor Explorer

### Filters

- Investor Source
- Country

### Interactive Links

Company names can be clicked to open company websites, while investor names can be clicked to access their LinkedIn profiles.

## 🧮 Key DAX Measures

The dashboard uses DAX measures including:

- Total Investors
- Website Investors
- LinkedIn Investors
- Company Coverage %
- Email Coverage %

Example:

```DAX
Total Investors =
DISTINCTCOUNT(Append1[Full Name])
