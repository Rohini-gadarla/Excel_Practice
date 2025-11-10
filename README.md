# ✅ ESPN Cricinfo – India vs South Africa ODI Player Stats Analysis (Power BI + Web Scraping)

## 📌 Project Overview
This project demonstrates end-to-end data extraction, transformation, and reporting in Power BI, using web scraping from ESPN Cricinfo Statsguru.  
The goal is to collect batting, bowling, and fielding records for India vs South Africa ODI matches, clean and prepare the dataset using Power Query, and build interactive reports for player-wise performance insights.

---

## 🔥 Key Skills Used
- Web Scraping using Power BI Web Connector  
- Advanced Power Query (M Language)  
- Dynamic Pagination Function  
- Data Cleaning & Transformation  
- Data Modelling  
- Creating User-Interactive Dashboards  
- Card Visualization, Slicers, Shapes & Formatting  

---

## 🏏 Dataset Source
ESPN Cricinfo Statsguru (ODI – India vs South Africa)

### Categories scraped:
- Batting  
- Bowling  
- Fielding  

Each category contained 3 pages:
- Page 1 → 50 records  
- Page 2 → 50 records  
- Page 3 → 19 records  

✅ Total: **119 records per category**

---

## 🚀 Web Scraping Process

### ✔ Step 1: Select Web Source
- Open ESPN Cricinfo Statsguru.  
- Select ODI category.  
- Choose:  
  - Team = India  
  - Opposition = South Africa  
- Copy the URL of page 1 and paste it inside:  
  **Power BI → Get Data → Web**

---

### ✔ Step 2: Extract the Table Using “Add Table Using Examples”
Power BI shows multiple HTML elements such as tables, styles, images, scripts, etc.  

Instead of manually selecting the table:
1. Select **Add Table Using Examples**
2. Enter the first two rows manually  
3. Power BI auto-detects all 50 rows from Page 1

---

### ✔ Step 3: Enable Pagination (Web Scraping)
Power BI loads only page 1 by default.  
To scrape multiple pages:

✅ Create a Dynamic Function  
- Open **Advanced Editor**  
- Wrap existing script inside a function:

```powerquery
(ps as text) =>
let
    Source = Web.Page(Web.Contents("yourURL&page=" & ps))
in
    Source
```

- Name this function: **batting_fx**

---

### ✔ Step 4: Create Page List (1 to 3)
Create a blank query.

In the formula bar:

```powerquery
={1..3}
```

Convert list → table → change column type to **text**.

---

### ✔ Step 5: Invoke Custom Function
- Select **Invoke Custom Function**
- Table = list table  
- Function = **batting_fx**

This produces 3 expanded tables (one per page).  
Expand all rows → remove unwanted columns/prefixes.

---

### ✔ Step 6: Append Headers
Scraped tables do not include original column headers.

Steps:
1. Create a manual table using **Enter Data**
2. Name it: **batting_headers**
3. Copy column headers from CSV/Excel (use Ctrl + Alt + V + V)
4. Append: **batting_headers + batting_raw_data**
5. Rename final table → **batting**

---

### ✔ Step 7: Data Cleaning
Perform the following transformations:

- Replace null with 0 (for 7 columns)
- Change data types:
  - Text → Text
  - Whole number → Int
  - Average/Rate → Decimal number
- Remove temporary columns

✅ Repeat same steps for:
- Bowling  
- Fielding  

---

## 📊 Power BI Reporting

### ✔ Report Pages (3)
- Batting Dashboard  
- Bowling Dashboard  
- Fielding Dashboard  

---

### ✔ UI Design
- Background canvas with 0% transparency  
- Shapes used for headers:
  - Rectangle  
  - Parallelogram  
  - Additional rectangle to close header gap  

- Custom Title Styles:
  - **“Batting Data Analysis”**
  - **“Bowling Data Analysis”**
  - **“Fielding Data Analysis”**

---

### ✔ Interactive Features
- Player dropdown slicer  
- KPI Cards (with soft orange glow shadow)
- Clean layout  
- Stat cards for each important metric  
- Hidden queries for cleaner report:
  - batting_raw_data  
  - bowling_raw_data  
  - fielding_raw_data  

---

## 🧠 What I Learned From the Project
✅ How to import data via web source  
✅ How to scrape multi-page datasets  
✅ How to create Power Query functions  
✅ How to dynamically generate parameterized URLs  
✅ How to clean and transform messy web data  
✅ How to build user-friendly dashboards  
✅ How to structure professional Power BI report design  

---

## 📁 Project Structure

```
/PowerBI_ESPN_Analysis
│
├── Batting.pbix
├── Bowling.pbix
├── Fielding.pbix
│
└── README.md
```

---

## 📌 Future Enhancements
- Add overall combined player ranking  
- Merge batting + bowling + fielding for all-rounder analysis  
- Add Power BI bookmarks for advanced navigation  
- Add DAX measures for averages, strike rates etc.  
- Add dynamic tooltips with rich player insights  

---

## 🏆 Conclusion
This project helped me understand the complete workflow of collecting data from ESPN Cricinfo using Power BI’s Web Connector and preparing the dataset through practical Power Query steps. I successfully implemented multi-page web scraping using a simple parameter function, handled pagination, extracted tables using examples, and cleaned the raw data for further analysis.  
The dashboards created allowed me to visualize player statistics in a structured and interactive manner.  
Through this project, I gained confidence in using Power Query, working with pagination, improving data cleaning techniques, and designing clean, user-friendly report pages in Power BI.

