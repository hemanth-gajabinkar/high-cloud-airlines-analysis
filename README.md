# High Cloud Airlines Analysis

Interactive dashboard analyzing airline operations data — passenger volume, carrier performance, route distribution, and load factors across a decade of flight data.

## 📊 Project Overview

Analyzed a large-scale airline operations dataset to surface insights on passenger traffic, carrier performance, and flight distance patterns. The analysis was built entirely on custom SQL logic — date engineering, load factor calculations, and window-function-based rankings — then visualized across Excel, Power BI, and Tableau dashboards with drill-down by Year, Month, and Financial Quarter.

## 🗂️ Dataset

- **Scope:** 208 airlines, 18.4K cities, 104 countries
- **Volume:** 187M total passengers, 82M total distance covered
- Multi-year data (2008–2013)

## 🛠️ Tools Used

![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Tableau](https://img.shields.io/badge/Tableau-E97627?style=for-the-badge&logo=tableau&logoColor=white)

## 🔧 What I Did (SQL)

**1. Date dimension engineering**
Built a full date breakdown from Year/Month/Day fields, including Year, Month No., Month Name, Quarter, Year-Month, Weekday No./Name, Financial Month, and Financial Quarter.

**2. Load Factor analysis**
Calculated Load Factor (`Transported Passengers ÷ Available Seats × 100`) at multiple levels:
- Yearly Load Factor + overall average across years
- Monthly Load Factor + overall average across months
- Quarterly Load Factor + overall average across quarters
- Load Factor by Carrier Name (top 20)

**3. Carrier & route ranking (window functions)**
- **Top 10 carriers by passenger preference** — using `DENSE_RANK()` over total transported passengers
- **Top 10 routes by number of flights** — ranked by total departures performed per From–To city pair

**4. Weekday vs. weekend analysis**
Flagged each record as Weekday or Weekend based on weekday number, then compared load factor between the two groups.

**5. Distance group analysis**
Joined `maindata` with a distance-group lookup table to rank flight volume by distance interval using `DENSE_RANK()`.

## 📈 Dashboard Highlights

**Key Metrics (KPI cards):**
- Total Airlines: 208
- Total Cities: 18.4K
- Total Passengers: 187M
- Total Countries: 104
- Total Distance: 82M

**Visuals:**
- **Top Airlines by From–To City** — chart showing departure volume across top routes
- **Total Transported Passengers by Carrier Name** — horizontal bar chart ranking carriers (Southwest Airlines, Delta, US Airways, Continental, JetBlue, AirTran, SkyWest leading)
- **Total Departures by Distance** — bar chart showing departure count by distance group
- **Count of Load Factor by Carrier Name** — pie chart comparing load factor % across carriers (Globespan Air, Allegiant Air, XL Airways, Sichuan Airlines, Skyservice, Corsair, Jin Air, and others)
- **Weekday vs. Weekend split** — donut chart comparing operational load factor

**Filters/Slicers:**
- Year (2008–2013)
- Month (January–December)
- Financial Quarter (Q1–Q4)

![High Cloud Airlines Dashboard](attach_screenshot_here.png)

## 📁 Repo Contents

- `HighCloud.sql` — full SQL script (date engineering, load factor analysis, carrier/route ranking)
- `Combined_Workbook.xlsx` — Excel dashboard workbook
- `HIGH_CLOUD_AIRLINE_DASHBOARD.pbix` — Power BI dashboard file
- `HighCloud_Tableau_Combined_edited.twbx` — Tableau workbook
- `screenshots/dashboard.png` — dashboard preview image

## 💡 Key Takeaways

- Practiced multi-level aggregate analysis (yearly/monthly/quarterly load factor) in SQL
- Used window functions (`DENSE_RANK()`) to rank carriers and routes
- Built the same analytical story across three BI tools — Excel, Power BI, and Tableau

---
*Part of my Data Analyst portfolio — see my [profile README](../../) for more projects.*
