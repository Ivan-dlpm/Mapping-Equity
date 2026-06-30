# 🗺️ Mapping Equity: A GIS Analysis of Nonprofit Service Distribution in Montclair, NJ According to UN Sustainable Development Goals


## Project Overview

This project uses Geographic Information Systems (GIS) to answer a central question: are Montclair, NJ's nonprofit organizations located where they're most needed? It evaluates two dimensions of spatial equity — whether nonprofits are situated in areas of historical and structural disadvantage, and whether they are physically close to and thematically aligned with the needs of vulnerable community facilities like schools, senior housing, and health centers.

The analysis combines nonprofit location data (163 organizations) with the CDC's Social Vulnerability Index, historical HOLC redlining maps, and a 500-meter buffer/SDG-matching analysis against 65 vulnerable sites across town. The project was developed in collaboration with Dr. Lisa Johnson, Environmental and Code Coordinator at the Montclair Office of Sustainability, to support municipal planning, nonprofit coordination, and grant strategy. 

---

## Key Findings

### Structural Vulnerability Overlay (163 nonprofits)

| Metric | Result |
|---|---|
| Nonprofits in Moderate–Very High SVI zones | 101 / 163 (62%) |
| SVI distribution | Very Low: 22 · Low: 40 · Moderate: 32 · High: 51 · Very High: 18 |
| Nonprofits in historically redlined "C" or "D" zones | 114 / 163 (70%) |
| HOLC grade distribution | A ("Best"): 27 · B ("Still Desirable"): 21 · C ("Declining"): 75 · D ("Hazardous"): 39 |

### 500m Buffer & SDG Alignment (65 vulnerable sites)

| Metric | Result |
|---|---|
| Vulnerable sites assessed | 65 (schools, nursing homes, senior/special-needs housing, daycares, animal care, low-income housing) |
| Sites with ≥1 nonprofit within 500m | 64 / 65 (98%) |
| Sites with thematic SDG alignment | 63 / 65 (97%) |
| Sites with a nearby nonprofit but no SDG match | 1 (Bradford Elementary School) |
| Sites with no nearby nonprofit at all | 0 |
| Average nonprofits within range per site | 6.3 (range: 1–14) |
| Sites with 100% SDG alignment | First Montclair House, The Willows Home, Family of Caring |

### Most Common SDG Matches by Facility Type

| SDG | # of Matches | Common Among |
|---|---|---|
| SDG 3 — Good Health and Well-being | 78 | Nursing homes, senior housing |
| SDG 4 — Quality Education | 65 | Schools, daycares |
| SDG 11 — Sustainable Cities and Communities | 59 | Housing, mixed-population sites |
| SDG 10 — Reduced Inequalities | 47 | Low-income housing |
| SDG 2 — Zero Hunger | 29 | Daycares, schools |

### Top SDGs Across All 163 Nonprofits

| SDG | Count | % |
|---|---|---|
| SDG 10 — Reduced Inequalities | 100 | 19.84% |
| SDG 4 — Quality Education | 97 | 19.25% |
| SDG 11 — Sustainable Cities and Communities | 88 | 17.46% |
| SDG 3 — Good Health and Well-being | 49 | 9.72% |
| SDG 16 — Peace, Justice and Strong Institutions | 37 | 7.34% |
| SDG 5 — Gender Equality | 36 | 7.14% |
| SDG 17 — Partnerships for the Goals | 31 | 6.15% |
| SDG 1 — No Poverty | 18 | 3.57% |
| SDG 2 — Zero Hunger | 15 | 2.98% |
| SDG 13 — Climate Action | 9 | 1.79% |
| SDG 8 — Decent Work and Economic Growth | 9 | 1.79% |
| SDG 12 — Responsible Consumption and Production | 7 | 1.39% |
| SDG 15 — Life on Land | 6 | 1.19% |
| SDG 6 — Clean Water and Sanitation | 1 | 0.20% |
| SDG 9 — Industry, Innovation and Infrastructure | 1 | 0.20% |

---

## Data Sources

- **Nonprofit Organization Data:** Compiled from Montclair's official nonprofit directory and supplemental PDFs; standardized into an Excel database with name, address, mission, category, contact info, and SDG tags for 163 organizations
- **Social Vulnerability Index (SVI):** 2022 CDC/ATSDR SVI dataset for NJ ZIP Code Tabulation Areas, scoring socioeconomic status, household composition, minority status/language, and housing/transportation
- **Historical Redlining Data:** University of Richmond's "Mapping Inequality" project — 1930s HOLC zone boundaries (Best, Still Desirable, Declining, Hazardous)
- **Vulnerable Population Locations:** Montclair's 2023 Climate Change-Related Hazard Vulnerability Assessment (CCRHVA) — nursing homes, schools, daycare centers, animal shelters, senior centers, special needs housing, emergency shelters, low-income housing

---  

## Vulnerable Population Sites (65 total)

| Site Type | Count | SDGs Tagged |
|---|---|---|
| Schools | 22 | SDG 3, SDG 4, SDG 10 |
| Child / Adult Day Care Centers | 18 | SDG 3, SDG 4, SDG 10 |
| Special Needs Housing / Group Homes | 7 | SDG 3, SDG 10, SDG 11 |
| Nursing Homes | 9 | SDG 3, SDG 10, SDG 11 |
| Animal Care Centers | 5 | SDG 3, SDG 11, SDG 15 |
| Senior Citizen Housing | 5 | SDG 3, SDG 10, SDG 11 |
| Low-Income Housing | 1 | SDG 1, SDG 10, SDG 11 |

---

## Methodology

- **Geocoding:** All address-based data geocoded via ArcGIS's built-in geocoding services
- **Overlay Analysis with Spatial Join:** Nonprofit point data joined against SVI tract scores (classified into 5 tiers via Natural Breaks/Jenks) and HOLC redlining grades to assess structural vulnerability of nonprofit locations
- **Buffer Analysis & Reverse Spatial Join:** 500-meter buffers drawn around each of the 65 vulnerable sites; a "Join One to Many" operation using an INTERSECT relationship captured all nonprofits within each buffer
- **SDG Matching:** Each site tagged with up to 3 relevant SDGs (e.g., schools → SDG 4) and compared against each nearby nonprofit's SDG tags; a match required at least one shared SDG plus physical proximity
- **Map Design:** Four thematic maps built in ArcGIS Pro Layout View (nonprofit/vulnerable site locations, SVI distribution, HOLC redlining overlap, SDG-aligned buffer coverage), plus a published interactive ArcGIS Online map
- **Tools Used:** ArcGIS Pro, ArcGIS Online, Excel

---

## Limitations

- **Static proximity buffers:** A fixed 500m radius doesn't account for real-world walkability, transit access, or physical barriers, and may overstate accessibility for elderly, disabled, or low-income residents
- **Keyword-based SDG tagging:** SDG classification was based on text analysis of mission statements, which can misrepresent an organization's actual service population (e.g., an SDG 4-tagged nonprofit serving adults, not children, near a school)
- **Equal SDG weighting:** All SDGs were treated as equally important across site types, without local input on which needs are most urgent
- **No service quality or capacity data:** Program hours, staffing, and operational capacity weren't evaluated, despite being central to actual impact beyond proximity

---

## Recommendations for Future Work

- Incorporate network-based accessibility (walk-time/drive-time models) instead of static radius buffers
- Verify SDG alignment through direct interviews or surveys with nonprofits
- Conduct a community needs assessment to weight SDG priorities by local context
- Add temporal and gap analysis to track service changes over time and prioritize underserved areas
- Explore nonprofit density per square kilometer and overlay socioeconomic indicators (median income, housing burden) for more granular equity analysis

---

## GIS Maps

<p align="center">

Map 1: Nonprofits and vulnerable populations<br/>
<img src="https://imgur.com/mxkKs5j.png" height="50%" width="50%" alt="Map of nonprofits and vulnerable population sites in Montclair"/>
<br /><br />

Map 2: Nonprofits and vulnerable populations (500m buffers)<br/>
<img src="https://imgur.com/yj4wiF2.png" height="50%" width="50%" alt="Map of 500-meter buffer zones around vulnerable sites"/>
<br /><br />

Map 3: Nonprofits and historical redlining<br/>
<img src="https://imgur.com/agVmouG.png" height="50%" width="50%" alt="Map overlaying nonprofit locations on historical HOLC redlining grades"/>
<br /><br />

Map 4: Nonprofits and SVI<br/>
<img src="https://i.imgur.com/N4bapsB.png" height="50%" width="50%" alt="Nonprofit Locations Overlaid on Social Vulnerability"/>
<br /><br />

</p>

---

## Project Materials

- 📄 **[Full Research Paper — Mapping Equity: A GIS Analysis of Nonprofit Service Distribution](https://docs.google.com/document/d/1IOlxLISJRQHQ0UDY3USy8dm4vVkL9bzO1M6okfyW6qs/edit?usp=sharing)**
- 📊 **[Presentation Slides](https://docs.google.com/presentation/d/12lvabs9Di_bFLCcMH9poYdB6V4sFr7hOXNazqlWmMSs/edit?usp=sharing)**
- 📈 **[Nonprofit Directory & SDG Tags (Excel)](https://docs.google.com/spreadsheets/d/1l0ky42FYGiqcaOuZoQJyX_2gCd6XuC4St6S5J6F-cJU/edit?usp=sharing)**

---

## Context

This project was completed at **Montclair State University** in collaboration with the **Montclair Office of Sustainability**, applying GIS spatial analysis, social vulnerability and historical equity data, and UN SDG-based thematic matching to a real-world municipal planning question.

**Skills demonstrated:** GIS spatial analysis (ArcGIS Pro/Online), overlay and buffer analysis, spatial join techniques, geocoding, data classification (Natural Breaks/Jenks), equity and policy research, interactive web map deployment

---
