# Orbital Congestion Report

### Navigation
[Overview](##overview)
[Contributors](##contributors)
[Presentation](##presentation)
[Objectives](##objectives)
[Data Sources](##data-sources)
[Methodology](##methodology)
[Key Findings](##key-findings)
[Terminology](##terminology)
[Key Numbers Recap](##key-numbers-recap)

## Overview
This report is the result of a team effort to enhance space situational awareness (SSA) using open data during the Women in Data Space Aware Datathon August 14-September 15, 2025. We conducted an analysis of satellites and debris in Low Earth Orbit (LEO) using data from the Unified Data Library (UDL) Elset, CelesTrak and SatCat. By combining multiple open datasets, we provide a clearer picture of the orbital environment, highlight altitude hotspots, quantify debris risks, and assess the growing role of Starlink satellites.

---

## Contributors
[Veronica Luisana Polk](https://www.linkedin.com/in/veronicaluisanapolk): Data analyst with a background and masters in Agribusiness

[Shruthi Bhaskaran MK](https://www.linkedin.com/in/shruthi-bhaskaran-m-k-4084b1323): Data analyst with years of contribution to the education sector

[Favour "Nimi" Adebayo](https://www.linkedin.com/in/kayeneii):** Data analyst using analytics and allied ML in the defence industry

---
## Presentation

(https://github.com/kayeneii/OrbitalCongestionReport/blob/main/Orbital%20Congestion%20Report_-_Space%20Aware%20Trio-2025.mp4)

---

## 🎯 Objectives
- Identify altitude ranges and inclination bands with the highest congestion in LEO.
- Quantify the presence of debris vs active satellites.
- Compare Starlink vs non-Starlink satellites and their overlap with debris.
- Flag satellites at decay risk (perigee < 300 km).
- Provide insights for space traffic management and orbital safety.

---

## 🗂️ Data Sources
* Unified Data Library (UDL) – Elset data (via authenticated API)
* CelesTrak SatCat – Satellite catalog (OBJECT_TYPE, OWNER, etc.)
* CelesTrak Starlink TLEs – List of Starlink satellites for tagging

These datasets were merged into a unified analysis frame, ensuring active satellites, payloads, and debris are all captured.

---

## 🛠️ Methodology
### Tools
- Python for analysis and visualization
- Pandas / NumPy for data cleaning & aggregation
- Matplotlib / Seaborn for visualizations
- Requests for pulling UDL and CelesTrak data
- EDA artifacts: schema checks, missingness, numeric summaries, sample rows

### Workflow
1. Fetch raw UDL data via API → normalize JSON
2. Perform data cleaning & validation (missing values, duplicates, schema)
3. Merge with SatCat metadata to classify debris vs payloads
4. Tag Starlink satellites using CelesTrak TLEs
5. Analyze altitude hotspots, RAAN–inclination planes, debris overlap, decay-risk candidates and growth trend

---

## 📊 Key Findings
**LEO Congestion Hotspots:** Most satellites cluster around ~500–600 km and ~1100–1200 km.

**Debris Load:** 26% of LEO objects are debris, with hotspots overlapping with active payloads.

**Starlink Impact:** Starlink dominates the 53° inclination band, significantly contributing to congestion.

**Decay Risk:** Hundreds of satellites are below 300 km perigee, indicating likely re-entry in the near term.

**Overlap Zones:** Certain altitude bands contain Starlink, non-Starlink, and debris together, raising collision risks 

LEO satellites are growing at ~28% CAGR, projected to exceed 45,000 by 2030 — raising risks of congestion and collisions

---

## 🗝️ Terminology
### 1. Orbits & Regions

* **LEO (Low Earth Orbit):** 200–2,000 km; crowded (Starlink, imaging satellites).
* **MEO (Medium Earth Orbit):** 2,000–35,000 km; navigation (GPS, Galileo).
* **GEO (Geostationary Orbit):** \~35,786 km; appears fixed over Earth (comms, weather).
* **HEO (Highly Elliptical Orbit):** Stretched, high apogee (military, weather).


### 2. Common Data Types

* **TLE (Two-Line Element set):** Compact text format describing a satellite’s orbit. Used with propagation models (SGP4).
* **Ephemeris Data:** High-precision list of satellite positions/velocities at times.
* **State Vector:** Snapshot of position (x, y, z) and velocity (vx, vy, vz).
* **Elset (Element Set):** Same idea as TLE, sometimes extended or from different sources.
* **SGI (Spacecraft Geolocation Info):** Logs of tracking/telemetry data.


### 3. Key Orbital Parameters (from TLEs)

* **Inclination (i):** Tilt of orbit relative to equator.
* **RAAN (Right Ascension of Ascending Node):** Where the orbit crosses the equator heading north.
* **Eccentricity (e):** Orbit shape (0 = circle, >0 = ellipse).
* **Perigee:** Closest point to Earth.
* **Apogee:** Farthest point from Earth.
* **Mean Motion (n):** Number of orbits per day.
* **Epoch:** Reference time for orbital data validity.


### 4. Core Concepts

* **Propagation:** Predicting future satellite positions using orbital models (SGP4 is standard).
* **Conjunction:** Close approach between two objects (potential collision).
* **SSA (Space Situational Awareness):** Monitoring space objects & environment.
* **Space Debris:** Non-functional objects (spent satellites, rocket parts, fragments).
* **Orbital Decay:** Gradual lowering of a satellite’s orbit due to drag.


### 5. Tools & Libraries

* **Python:**

  * `sgp4` → orbit propagation.
  * `skyfield` → satellite positions & visualization.
  * `poliastro` → orbital mechanics simulations.
  * `astropy` → astronomy/time utilities.
* **Visualization:** `matplotlib`, `plotly`, CesiumJS (3D orbits).


### 6. Space Jargon Made Simple

* **Catalog Number / NORAD ID:** Unique ID for each tracked object.
* **UDL (Unified Data Library):** Repository of satellite + orbit data.
* **Conjunction Data Message (CDM):** Standardized warning of possible collision.
* **Sustainability in Orbit:** Preventing “Kessler Syndrome” (runaway debris collisions)


---

## 📍 Key Numbers Recap

**All objects:** 30000

**LEO objects:** 27752

**Debris in LEO:** 7371 (26.56%)

**Starlink (all):** 9675

**Starlink in LEO:** 9666 (34.83%)

**Decay-risk in LEO (<300 km perigee):** 180 (0.65%)

**Top 5 LEO altitude hotspots (100-km bins):** 500–600 km : 7188 objects 400–500 km : 5326 objects 700–800 km : 2562 objects 800–900 km : 2500 objects 900–1000 km : 1942 objects


---

Thank you for reading our report!❤️
