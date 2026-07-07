# The Perfect Fit — DataFest Team Name

**ASA DataFest 2026 · Northwestern University**
*How geography shapes care efficiency across medical conditions*

---

## Overview

Stormont Vail Health (SVH) — a nonprofit integrated health system serving Kansas for over 130 years — sees only a static snapshot of each patient's experience. Our project reconstructs longitudinal **patient journeys** from four years of encounter-level data to help SVH understand where inefficiencies occur and how geography and access to care shape those inefficiencies.

### Core Question
> How do geographical location and access to healthcare impact inefficiencies in the patient journey across three core diagnosis families?

We framed this around a single persona, **Emre** — a man in his 30s from Wichita, Kansas, managing multiple conditions with limited nearby specialist access — to keep the analysis grounded in a real patient experience rather than abstract metrics. *(Emre's conditions are fictional and not representative of any real person.)*

---

## Approach

1. **Defined the patient journey** as the sequence of encounters linked by a common diagnosis, from first visit through resolution.
2. **Selected three diagnosis families** — Cancer, Bone Fractures, and Depression — chosen because they represent a meaningful share of total diagnoses while reflecting very different care patterns (multi-stage coordinated care, acute/episodic care, and longitudinal outpatient care, respectively).
3. **Defined inefficiency** primarily as wait time between visits, segmented by region and diagnosis family.
4. **Mapped healthcare access equity** by comparing SVH's department locations against Census population data across Kansas counties.
5. **Clustered patient journeys** using KMeans (on visit count, department count, and journey duration) to distinguish patients who inherently need more complex care from those experiencing inefficiency-driven delays — and found a strong correlation between journey complexity and county population density.
6. **Built a live dashboard** so SVH can track access and wait-time disparities on an ongoing basis, not just as a one-time analysis.

---

## Repository Structure

```
notebooks/
├── 01_data_cleaning.ipynb            # Load raw data, null audits, department name cleanup,
│                                      # diagnosis-family share checks, county/region mapping
├── 02_geographic_access_map.ipynb    # Interactive map: SVH department locations vs. Census
│                                      # population + access equity by county
├── 03_journey_clustering.ipynb       # KMeans clustering of patient journeys by complexity
├── 05_wait_time_analysis.ipynb       # Wait-time-between-visits computation and region ×
│                                      # diagnosis comparisons (cancer, fracture, depression)
└── 06_Hannah_Dashboard.ipynb                # Build for the live SVH tracking dashboard

docs/
├── The_Perfect_Fit_DataFest2026.pdf  # Final presentation deck
├── External Files Used.docx           # Required External Files disclosure
└── AI Usage Documentation.docx        # Required AI usage disclosure

kansas_access_map_FINAL_MAP.html     # html for the final map used for the visualization
.gitignore
README.md
```

> **Note:** Raw SVH patient data (`encounters.csv`, `patients.csv`, `diagnosis.csv`, `social_determinants.csv`, etc.) is **not included** in this repository per our DataFest confidentiality agreement, and was deleted from all local machines after the competition. Notebooks are provided for methodology reference; they will not run end-to-end without access to the original (confidential) dataset. All cells containing outputs in the notebooks have been hidden for confidentiality purposes.

---

## Key Insights

1. Several regions outside of Northeast Kansas are **underserved** relative to population.
2. Patients residing in higher-density counties tend to experience **more complex care pathways** — counties with fewer patients (a proxy for rural, harder-to-reach areas) correspond to simpler, but not necessarily better, care journeys.
3. Wait times between visits are **highly variable** across both region and diagnosis family, with no single consistent pattern — southeast and southwest Kansas showed some of the largest disparities.

## Proposed Solutions

- **Direct Access** — Explore opening a new clinic in the underserved, highly-populated Southeast Kansas region.
- **Digital Access** — Modernize SVH's MyChart scheduling experience to be proactive (e.g. a clear "timeline of care" / "next steps" view) rather than reactive, and pair it with physical **access hubs** (trusted community locations like libraries offering telehealth booths) for patients with limited connectivity.
- **Data Tracking** — A live dashboard tracking access equity, wait times, and patient volume by region and diagnosis, for both internal use and donor-facing reporting.

## Live Demos
- Interactive dashboard: see presentation deck for link
---

## Team — "The Perfect Fit"
Kay · Sophia · Selina · Hannah · Takeshi

## AI Usage
This project used Northwestern's Microsoft Copilot as an assistant for debugging code, writing functions, gaining domain/healthcare knowledge, and formatting visualizations — never for generating insights or recommendations directly from the data. Full disclosure in `docs/AI Usage Documentation.docx`.

## Acknowledgments
Thanks to Stormont Vail Health and the DataFest organizing committee for the problem statement and data, and to Isabel Knight for her guidance on healthcare data analysis during the DataFest competition.
