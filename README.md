# ✅ ESPN Cricinfo – India vs South Africa ODI Player Stats Analysis  
### *(Power BI + Web Scraping + Power Query)*

---

## 🌟 Project Summary
This project showcases end-to-end data extraction, transformation, and interactive reporting in Power BI using web scraping from ESPN Cricinfo Statsguru.  
Scraped 3 categories — **Batting, Bowling, Fielding** — for ODI matches between India vs South Africa, processed 119 rows per category using Power Query functions, cleaned the dataset, and built an interactive dashboard.

---

## 🛠️ Tech Used
![Power BI](https://img.shields.io/badge/PowerBI-Data%20Visualization-yellow)
![Power Query](https://img.shields.io/badge/Power%20Query-M%20Language-blue)
![Web Scraping](https://img.shields.io/badge/Web%20Scraping-Dynamic%20Pagination-orange)
![ESPN Cricinfo](https://img.shields.io/badge/Data-ESPN%20Cricinfo-red)
![ETL](https://img.shields.io/badge/ETL-Extract%20Transform%20Load-green)

---

# 📂 Repository Structure


---

# 🏏 Project Workflow

## 1️⃣ Data Scraping (Web Source)
- ESPN Cricinfo Statsguru  
- Team = India  
- Opposition = South Africa  
- Categories: Batting, Bowling, Fielding  
- Each category: Page 1 = 50 rows, Page 2 = 50 rows, Page 3 = 19 rows  
- ✅ Total = 119 rows

---

## 2️⃣ Table Extraction Using “Table From Examples”
- Pasted URL into Power BI web source  
- Used **Add Table From Examples**  
- Entered 2 sample rows → Power BI auto-detected all 50 rows  

---

## 3️⃣ Pagination Function (Advanced Editor)

```m
(ps as text) =>
let
    Source = Web.Page(Web.Contents("yourURL&page=" & ps))
in
    Source
={1..3}

---

If you want this README converted into:

✅ PDF  
✅ GitHub-friendly short summary  
✅ Resume bullet points  

Just tell me “convert to resume version” or “convert to LinkedIn post”.
