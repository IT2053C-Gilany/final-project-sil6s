
# 📊 Cincinnati Police STARS Dataset — Final Project Notebook  
### 🧠 Reported Crime (STARS Category Offenses) After 2024‑06‑03  
**Dataset:** *Reported Crime (STARS Category Offenses) on or after 6/3/2024*  
**Source:** City of Cincinnati Open Data Portal  

**IT2053C – Data Tech Programming**  
**Author: Silas Curry**  
**University of Cincinnati — School of Information Technology**

---


## 🔍 Executive Summary

### Context & Stakeholders

The **Cincinnati Police Department (CPD)** adopted a new Records Management System (RMS) on **June 3, 2024**, transitioning all reported incidents to the **STARS (Standardized Tracking and Reporting System)** offense classification model. STARS ensures consistent offense grouping and improved analytical reliability. This dataset represents all reported crime incidents recorded **after the RMS transition**, providing a clean and modern framework for evaluating Cincinnati’s public safety landscape.

Stakeholders who depend on these insights include:

- **CPD Command Staff & Public Safety Leadership**  
- **Neighborhood Councils & Community Safety Partners**  
- **Operational Analysts & Patrol Planners**  
- **City Administrators & Policy Makers**  
- **Community Engagement & Crime Prevention Groups**

Understanding temporal, spatial, and categorical patterns in reported crime is essential for optimizing citywide resource allocation, ensuring equitable service delivery, and guiding long-term policy and prevention strategies.

---

### Goal of This Project

This project performs a full analytical workflow examining **spatial and temporal patterns** in citywide crime incidents following the RMS transition. Focus areas include:

- Identifying **peak times** for crime (hour of day, day of week)  
- Determining **high-frequency offense categories** and monthly shifts  
- Highlighting major **neighborhood hotspots**  
- Understanding **clearance outcomes** and their operational implications  

This project aims to provide insights that support:

- Evidence-based patrol staffing  
- Targeted community safety interventions  
- Public‑facing dashboards and reporting tools  
- Data governance decisions for merging pre‑ and post‑transition datasets  

---

## ⭐ Key Findings (Preview)

### Temporal Patterns
- Crime is heavily concentrated between **11:00 and 18:00**.  
- **Mondays** show significantly higher average daily incident counts than other weekdays.

### Category Concentration
- A small set of offense types—**Part 2 Offenses**, **Theft**, **Auto Theft**, **Burglary/Break‑ins**—account for a substantial share of total activity.  
- **Part 2 Offenses** represent a major portion of community‑facing incidents.

### Geographic Patterns
- Consistent hotspots include **Westwood**, **CBD/Riverfront**, **Over‑the‑Rhine**, and **West Price Hill**.  
- Crime levels vary sharply between neighborhoods, supporting the need for localized strategies.

### Clearance & Operational Patterns
- Many incidents close under **administrative categories** such as “Early Closed” or “Cleared by Arrest (Adult).”  
- A notable portion close as **“Victim Refuses to Cooperate”** or **“Unfounded,”** suggesting engagement or trust challenges.

---

## 🎯 Recommendations (Preview)

- Increase **patrol presence** during the 11:00–18:00 window, especially Mondays.  
- Prioritize **property‐crime prevention** in consistently high‑activity neighborhoods.  
- Develop a **neighborhood‑level weekly dashboard** for CPD and community partners.  
- Integrate this dataset with **calls for service, arrest data, and demographic/contextual layers**.  
- Maintain strict **data governance** for RMS transition boundaries.

---

# 📂 Data Card

## Dataset Origin
- **Publisher:** Cincinnati Police Department  
- **Source:** City of Cincinnati Open Data Portal  
- **Granularity:** Each row represents one reported offense  
- **Timespan:** 2024‑06‑03 onward (post‑RMS implementation)

## Key Fields
- `STARS_Category` — standardized offense type  
- `CLSD` / `CLSD_pretty` — mapped closure/clearance outcomes  
- `date`, `month`, `DAY_OF_WEEK` — derived temporal features  
- `Hour_From`, `Hour_To` — start/end of incident time window  

## Limitations
- Some offense classifications contain missing or ambiguous entries  
- Reported crime ≠ all crime  
- Open data may lag or be updated retroactively  

## License
Public dataset, released under Cincinnati open-data licensing.

---

# 📥 Loading & File I/O

All loading uses a safe, typed helper function with explicit error handling:

```python
from pathlib import Path
import pandas as pd

def load_csv(path: Path) -> pd.DataFrame:
    """Load a CSV with explicit error handling."""
    try:
        df = pd.read_csv(path)
    except FileNotFoundError as e:
        raise FileNotFoundError(
            f"Could not find {path.name}. Check the data/ folder."
        ) from e
    except pd.errors.ParserError as e:
        raise ValueError(
            f"Parsing failed for {path.name}. Check delimiter or problematic rows."
        ) from e
    else:
        return df
```

If the dataset is missing, a small fallback sample is used so the notebook still runs structurally.

---

# 🔍 Exploratory Data Analysis (EDA)

### Preparation Tasks
- Standardize column names  
- Parse dates via `pd.to_datetime(errors="coerce")`  
- Create derived time variables (`month`, `DAY_OF_WEEK`)  
- Map closure codes to readable categories  
- Validate required fields using sets  
- Apply vectorized pandas operations  

### Descriptive Highlights
- Daily incident distribution analysis  
- Category frequency breakdowns  
- Weekly/hourly temporal patterns  
- Missingness and data-type auditing  

### Visualizations Included
- Histogram (distribution)  
- Boxplot (group comparison)  
- Scatter with regression line (numeric relationship)  
- Time‑series line plot (monthly category trends)  
- Multi‑panel facet grid  
- Interactive Plotly visualization  

All visualizations include narrative justification and result interpretation.

---

# 📈 Statistical Insights

This project includes the required statistical insights:

- Distribution characterization with summary statistics  
- Group comparison via appropriate tests  
- Categorical association analysis  
- Numeric correlation with confidence intervals  
- Additional insights on neighborhood and category trends  

---

# 🧠 Conclusions

Key conclusions from the analysis include:

- **Daily incident volume is stable and predictable**, enabling reliable planning.  
- **Mondays produce higher incident activity**, suggesting early‑week resource alignment.  
- **High‑activity neighborhoods** exhibit persistent patterns requiring localized strategies.  
- **Incident timing relationships** reflect strong internal consistency in reporting.  
- **Clearance patterns** highlight operational efficiency and points for procedural improvement.

---

# 📚 Appendix

### References
- Cincinnati Open Data Portal  
- pandas, NumPy, seaborn, matplotlib, Plotly documentation  
- Statistical method references  

---

# ✅ Assignment Requirements Checklist

## Notebook Structure
- Executive summary, data card, EDA, conclusions, appendix ✓  
- Clear narrative connecting code and interpretation ✓  

## Technical Requirements
- Functions with type hints & docstrings ✓  
- Proper use of lists, tuples, sets, dicts ✓  
- Vectorized operations ✓  
- `groupby`, merges, tidy reshaping ✓  

## File & Exception Handling
- Reads from `data/` directory ✓  
- Handles `FileNotFoundError` and `ParserError` ✓  

## Visualization Requirements
- ≥6 visualizations, including all required types ✓  
- Interactive Plotly figure embedded ✓  

## Statistical Requirements
- Distribution characterization ✓  
- Group comparison ✓  
- Categorical association ✓  
- Numeric correlation ✓  
- Additional insight ✓  

---

IT2053C – Data Tech Programming requirements at the **University of Cincinnati, School of Information Technology**.
