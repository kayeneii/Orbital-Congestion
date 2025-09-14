# 🛰️Orbital Congestion Report

This report is the result of a team effort to enhance space situational awareness (SSA) using open data during the Women in Data Datathon August 14-15, 2025.

## Contributors
**Veronica Luisana Polk:** Data analyst with a background and masters in Agribusiness

**Shruthi Bhaskaran MK:** Data analyst with years of contribution to the education sector

**Favour "Nimi" Adebayo:** Data analyst using analytics and allied ML in the defence industry

## Terminology

### 1. Orbits & Regions

* **LEO (Low Earth Orbit):** 200–2,000 km; crowded (Starlink, imaging satellites).
* **MEO (Medium Earth Orbit):** 2,000–35,000 km; navigation (GPS, Galileo).
* **GEO (Geostationary Orbit):** \~35,786 km; appears fixed over Earth (comms, weather).
* **HEO (Highly Elliptical Orbit):** Stretched, high apogee (military, weather).

---

### 2. Common Data Types

* **TLE (Two-Line Element set):** Compact text format describing a satellite’s orbit. Used with propagation models (SGP4).
* **Ephemeris Data:** High-precision list of satellite positions/velocities at times.
* **State Vector:** Snapshot of position (x, y, z) and velocity (vx, vy, vz).
* **Elset (Element Set):** Same idea as TLE, sometimes extended or from different sources.
* **SGI (Spacecraft Geolocation Info):** Logs of tracking/telemetry data.

---

### 3. Key Orbital Parameters (from TLEs)

* **Inclination (i):** Tilt of orbit relative to equator.
* **RAAN (Right Ascension of Ascending Node):** Where the orbit crosses the equator heading north.
* **Eccentricity (e):** Orbit shape (0 = circle, >0 = ellipse).
* **Perigee:** Closest point to Earth.
* **Apogee:** Farthest point from Earth.
* **Mean Motion (n):** Number of orbits per day.
* **Epoch:** Reference time for orbital data validity.

---

### 4. Core Concepts

* **Propagation:** Predicting future satellite positions using orbital models (SGP4 is standard).
* **Conjunction:** Close approach between two objects (potential collision).
* **SSA (Space Situational Awareness):** Monitoring space objects & environment.
* **Space Debris:** Non-functional objects (spent satellites, rocket parts, fragments).
* **Orbital Decay:** Gradual lowering of a satellite’s orbit due to drag.

---

### 5. Tools & Libraries

* **Python:**

  * `sgp4` → orbit propagation.
  * `skyfield` → satellite positions & visualization.
  * `poliastro` → orbital mechanics simulations.
  * `astropy` → astronomy/time utilities.
* **Visualization:** `matplotlib`, `plotly`, CesiumJS (3D orbits).

---

### 6. Jargon Made Simple

* **Catalog Number / NORAD ID:** Unique ID for each tracked object.
* **UDL (Unified Data Library):** Repository of satellite + orbit data.
* **Conjunction Data Message (CDM):** Standardized warning of possible collision.
* **Sustainability in Orbit:** Preventing “Kessler Syndrome” (runaway debris collisions)
