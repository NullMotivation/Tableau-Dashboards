# 📊 Tableau Dashboards Portfolio

A collection of four interactive Tableau dashboards built on real-world datasets, covering e-commerce sales, HR analytics, book data, and streaming content. All workbooks are built in **Tableau 2025.3** and use `.twb` (unpackaged) format, so the source data files must be placed in the correct directories before opening.

---

## 📁 Dashboards Overview

| Dashboard | Data Source | Format | Key Focus |
|---|---|---|---|
| Amazon Sales Dashboard | `Amazon Sale Report.csv` | CSV | Sales, fulfilment & shipping |
| HR Analytics Dashboard | `HR Data.xlsx` | Excel | Attrition & workforce metrics |
| Goodreads Dashboard | `books.csv` | CSV | Books, authors & ratings |
| Netflix Dashboard | `netflix_titles.csv` | CSV | Content library & distribution |

---

## 1. 🛒 Amazon Sales Dashboard
**File:** `Amazon_sales_dashboard.twb`

### About
Analyzes Amazon India sales order data to uncover trends in revenue, product categories, fulfilment, and geographic distribution of orders.

### Data Source
- **File:** `Amazon Sale Report.csv`

### Worksheets & Visualizations
- **KPI Tiles** – Total Quantity, Total Amount, Total Products, Total Categories, Total Sizes
- **Amount by Week & Category** – Weekly revenue trend broken down by product category
- **Quantity by Week & Category** – Weekly units sold by category
- **MAP: Quantity by State** – Geographic heat map of order volume across Indian states
- **Top 10 States by Quantity and Category** – Bar chart ranking top states
- **Quantity by Status & Category** – Order status breakdown (Shipped, Cancelled, etc.)
- **Quantity by Courier Status & Category** – Delivery status analysis
- **Quantity by Sales Channel & Category** – Channel performance comparison
- **Quantity by Size & Category** – Size distribution per category
- **B2B Sales Quantity** – B2B vs B2C split

---

## 2. 👥 HR Analytics Dashboard

**File:** `HR_ANALYTICS_DASHBOARD.twb`

### About
Explores employee attrition patterns across an organization using IBM-style HR data. The dashboard helps HR teams identify which departments, age groups, education fields, and job roles are most at risk of attrition.

### Data Source
- **File:** `HR Data.xlsx` (sheet: `HR data`)
- **Expected path:** `C:/Tableau Workbooks/HR Dashboard/HR Data.xlsx`
- **Records:** ~1,470 employees


### Calculated Fields
- **Attrition Count** – `IF [Attrition] = 'YES' THEN 1 ELSE 0 END`
- **Attrition Rate** – `SUM(Attrition Count) / SUM(Employee Count)`
- **Active Employees** – `SUM(Employee Count) - SUM(Attrition Count)`

### Worksheets & Visualizations
- **KPI Tiles** – Total Employees, Attrition Count, Attrition Rate, Active Employees
- **Department Wise Attrition** – Pie/donut chart by department
- **Education Field Wise Attrition** – Bar chart by education background
- **Attrition by Gender** – Gender-based attrition breakdown
- **Attrition Rate by Gender by Age Group** – Heatmap / matrix view
- **No. of Employees by Age** – Histogram with dynamic bin size (parameter: 2–10)
- **No. of Employees by Age Group** – Grouped bar chart
- **Job Satisfaction Rating** – Cross-tab matrix of job roles vs satisfaction scores

### Parameters
- **Bin Size** – Controls histogram bin width for age distribution (range: 2–10, default: 3)

---

## 3. 📚 Goodreads Dashboard

**File:** `goodreads_dashboard.twb`

### About
Visualizes the Goodreads books dataset to surface trends in publishing, author popularity, language distribution, and reader ratings. Features advanced chart types including a custom **radial bar chart**.

### Data Sources
- **Primary:** `books.csv`
- **Secondary:** `Radial Bar chart values.txt` (helper file for radial chart calculations)
- **Expected path:** `C:/Tableau Workbooks/goodreads/`
- **Join type:** Inner join on a constant (cross join for radial chart scaffolding)

=

### Calculated Fields
- **Radial chart axes** – Trigonometric SIN/COS calculations for radial bar rendering
- **Rank** – `RANK_UNIQUE()` for ordered chart displays
- **% of Total** – Ratio of count to window maximum for proportional views

### Worksheets & Visualizations
- **Authors** – Author listing and book counts
- **Authors by Total Books** – Ranked bar of most prolific authors
- **Publishers by Total Books** – Top publishers by volume
- **Books by Publication Date** – Timeline of publications
- **Titles by Rating Count** – Most-rated books
- **Ratings Count / Avg Rating** – Distribution of ratings and scores
- **Num Pages** – Page count distribution
- **Text Reviews Count** – Review volume analysis
- **Top 10 Language Codes** – Radial bar chart of language distribution
- **Language Code** – Supplementary language breakdown
- **Publication Date / Publisher** – Reference detail views

### Custom Styling
This dashboard uses a custom warm brown color theme (`#463020`) applied across axes, gridlines, and titles for a book-inspired aesthetic. Gridlines and zero lines are disabled for a clean look.

---

## 4. 🎬 Netflix Dashboard
**File:** `netflix_dashboard.twb`

### About
Provides a comprehensive view of the Netflix content library — exploring the split between movies and TV shows, content by country, genre trends, release year distribution, and content ratings.

### Data Source
- **File:** `netflix_titles.csv`


### Worksheets & Visualizations
- **Movie & TV Shows Distribution** – Overall split between Movies and TV Shows
- **Movies & TV Shows by Country** – Geographic map of content origins
- **Movies & TV Shows by Year** – Annual trend of content releases
- **TOP 10 GENRE** – Most common genres across the library
- **RATINGS** – Breakdown by content rating category
- **Date Added** – Timeline of when content was added to the platform
- **Duration** – Distribution of runtimes and season counts
- **Genre** – Detailed genre analysis
- **Description / Release Year / Rating** – Supporting detail views for drill-down

---

## 🚀 Getting Started

### Prerequisites
- **Tableau Desktop** 2025.3 or later (workbooks use version 18.1 format, compatible with Tableau 10.5+)

---

## 🛠️ Tools & Technologies

- **Tableau Desktop 2025.3**
- **Data formats:** CSV, Excel (.xlsx)
- **Techniques used:** Calculated fields, parameters, table calculations, radial bar charts, geographic maps, KPI tiles, heatmaps, histograms

---

## 📌 Notes

- All workbooks are in `.twb` (XML) format — data is **not** embedded. Source files are required separately.
- The Goodreads dashboard requires **both** `books.csv` and `Radial Bar chart values.txt` to render the radial chart correctly.
- The HR dashboard includes a dynamic **Bin Size parameter** for the age histogram (adjustable from 2–10).
- Locale settings are `en_IN`; number formatting may reflect Indian conventions (lakhs/crores) in some charts.