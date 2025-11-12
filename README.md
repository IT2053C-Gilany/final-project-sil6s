# 📊 Final Project — Reported Crime (STARS Category Offenses) after 2024-06-03  
**Course:** IT2053C  
**Author:** Silas Curry  

---

## 🧠 Overview  

This repository contains the **final project submission** for IT2053C, analyzing the *City of Cincinnati's "Reported Crime (STARS Category Offenses)"* dataset (records on or after June 3, 2024).  
The project examines how reported crime varies by **time, category, and neighborhood** following the CPD's transition to a new Records Management System (RMS).  

The analysis provides actionable insights for **public safety stakeholders**, including CPD operations, city leadership, and neighborhood councils.

---

## 🗂️ Project Structure  

The project consists of **three parts**:

1. **Initiation (Part 1)** – Dataset selection, research questions, and visualization plan  
2. **Notebook (Part 2)** – Data loading, cleaning, exploration, visualization, and analysis  
3. **Presentation (Part 3)** – Executive summary, conclusions, recommendations, and references  

**Primary notebook:**  
`final-project.ipynb`  

---

## 🚀 Quick Start  

### 1. Environment Setup  

If you haven't already created the environment for previous assignments, run:  
```bash
# Replace <your_6+2_username> with your UC username
python scripts/setup.py --username <your_6+2_username>
```

**Example:**
```bash
python scripts/setup.py --username currysc
```

Then activate the environment:
```bash
conda activate IT2053C
```

---

### 2. Run the Notebook

Open **`final-project.ipynb`** and run all cells sequentially.

The notebook will automatically detect the dataset:

* Expected path: `data/Reported_STARS_Category_Offenses.csv`
* If not found, it will load a **6-row sample dataset** to allow the notebook to run end-to-end for demonstration.

---

## 📈 Project Contents

### 🔹 Executive Summary

* Defines context, goals, and key findings for Cincinnati's post-transition crime data.
* Identifies **temporal patterns**, **offense category concentration**, and **neighborhood hotspots**.
* Provides actionable recommendations for patrol planning and data governance.

### 🔹 Dataset Selection

* **Source:** [City of Cincinnati Open Data Portal – STARS Category Offenses (after 6/3/2024)](https://data.cincinnati-oh.gov/safety/Reported-Crime-STARS-Category-Offenses-on-or-after/7aqy-xrv9/about_data)
* **Size:** ≈ 37,900 rows × 17 columns (as of Nov 12 2025)
* **License:** Public data with block-level anonymization and randomized coordinates
* **Reason for selection:** Timely, locally relevant, updated daily, and actionable for safety decision-making.

### 🔹 Analysis & Visualization

The notebook includes **8 static visualizations + 2 interactive charts** (Plotly).
Each chart is paired with an actionable **stakeholder takeaway**.

Visuals include:

* Incidents by **day of week**
* Incidents by **hour**
* **Day × Hour** heatmap
* Top **STARS offense categories**
* Top **neighborhoods** by incident volume
* **Weekly trendline** of reported incidents
* **Clearance status** distribution
* **Correlation matrix** for numeric features
* **Interactive map** (spatial distribution)
* **Interactive dropdown chart** (monthly trend by offense type)

### 🔹 Conclusions

Summarizes key insights and operational implications:

* Peak incidents occur **11 AM–6 PM**, especially **Mondays**.
* Property-related crimes dominate, led by **Part 2 offenses** and **thefts**.
* High-activity neighborhoods include **Westwood, CBD/Riverfront, Over-the-Rhine, West Price Hill**.
* Clearance data show quick resolution rates but highlight cooperation gaps.
* Findings support **time-targeted patrols** and **neighborhood-focused outreach**.

### 🔹 Limitations

* **Geolocation randomized** to block level (cannot use for address-specific mapping).
* Dataset **excludes** arrests, service calls, or outcomes.
* RMS transition (June 3 2024) may affect cross-year comparison; harmonization required before merging older data.

---

## 📚 References & Resources

* **City of Cincinnati Open Data Portal:**
  [Reported Crime (STARS Category Offenses) after 6/3/2024](https://data.cincinnati-oh.gov/safety/Reported-Crime-STARS-Category-Offenses-on-or-after/7aqy-xrv9/about_data)
* **Historical Dataset (before 6/3/2024):**
  [Reported Crime (STARS Category Offenses) before 6/3/2024](https://data.cincinnati-oh.gov/safety/Reported-Crime-STARS-Category-Offenses-before-6-3-/8xzn-kpn7/about_data)
* **CincyInsights Dashboard:**
  [CincyInsights — Public Safety Overview](https://insights.cincinnati-oh.gov/stories/s/8eaa-xrvz)
* **City Data Usage Guide:**
  [Open Data How-To Guide](https://data.cincinnati-oh.gov/dataset/Open-Data-How-To-Guide/gdr9-g3ad)
* **Related Agencies:**
  * [Cincinnati Police Department (CPD)](https://www.cincinnati-oh.gov/police/)
  * [Office of Performance & Data Analytics (OPDA)](https://performance.cincinnati-oh.gov/)
  * [FBI UCR Program](https://www.fbi.gov/services/cjis/ucr)
  * [National Incident-Based Reporting System (NIBRS)](https://nibrs.fbi.gov)
  * [U.S. Bureau of Justice Statistics (BJS)](https://bjs.ojp.gov/)

---

## 🧩 Submission Instructions

1. Push your completed notebook and data file to your **GitHub Classroom repository**.
2. Ensure the repository contains:
   * `final-project.ipynb`
   * `data/Reported_STARS_Category_Offenses.csv`
   * This `README.md`
3. Submit your GitHub repository URL to **Canvas**.

The instructor will review your dataset choice, questions, and visualizations, then provide feedback or approval.
Once approved, proceed with refinement for final grading.

---

**✅ Project Deliverables:**

* [x] Initiation — dataset, rationale, and visualization plan
* [x] Notebook — analysis, visuals, and stakeholder takeaways
* [x] Presentation — summary, conclusions, and references

**🎯 Goal:**
Demonstrate practical data analysis and visualization skills through a **real-world public safety dataset** that informs decision-making and supports evidence-based community outcomes.