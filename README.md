# Task 10: Scrape and Analyze Job Listings for Data Analyst Roles

## 🎯 Objective
The goal of this task was to collect job listing data for **Data Analyst roles** from a job portal, clean the data, perform basic analysis, and visualize the results.

---

## 🛠 Tools & Libraries
- **Python**
- **Libraries:**
  - `requests` → for sending HTTP requests
  - `BeautifulSoup4` → for parsing HTML pages
  - `pandas` → for data cleaning and analysis
  - `matplotlib` → for visualizations
  - `re`, `collections.Counter` → for skill extraction and frequency analysis
  - `time` → to add delays between requests (avoid blocking)

---

## 📌 Approach

1. **Scraping**
   - Targeted **Internshala** job portal for "Data Analyst" internships.  
   - Used `requests` with browser-like headers to avoid blocking.  
   - Parsed job details using `BeautifulSoup`.  

2. **Data Extracted**
   - Job Title  
   - Company Name  
   - Location  
   - Salary / Stipend  
   - Skills / Job Description  

3. **Data Cleaning**
   - Removed extra whitespace, tabs, and newlines.  
   - Replaced missing values with `"Not Specified"`.  
   - Extracted relevant skill keywords using regex.  

4. **Analysis**
   - Counted **total jobs scraped**.  
   - Found **Top 5 job locations**.  
   - Extracted most **in-demand skills** using `Counter`.  

5. **Visualization**
   - **Bar chart** → Top 5 job locations.  
   - **Pie chart** → Most in-demand skills.  

6. **Fallback**
   - Since some job portals block scraping (`403 Forbidden` errors), the script includes a **mock dataset generator** to simulate job listings.  
   - This ensures analysis and visualizations still run even if live scraping fails.

---

## 📊 Example Output
- **Total Jobs Scraped:** 60  
- **Top Locations:** Bengaluru, Pune, Hyderabad, Mumbai, Gurugram  
- **Top Skills:** Python, SQL, Excel, Tableau, Power BI  

---

## ⚠️ Challenges
- Many job portals use **bot protection** (CAPTCHA, 403 Forbidden).  
- **Dynamic websites** (JS-rendered content) require Selenium/Playwright instead of BeautifulSoup.  
- HTML **class names change often**, so scraping logic must adapt.

---

## ✅ Deliverables
- `Task_10_DA.ipynb` → Jupyter Notebook with full scraping + analysis.  
- `scraped_data_analyst_jobs.csv` → CSV output (scraped or mock data).  
- `README.md` → This document.  
- Plots saved as `.png` files for **Top Locations** and **Top Skills**.  
