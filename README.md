# SpaceAware-LEO-Analysis
Analysis of LEO satellites and debris using UDL(Elset) + CelesTrak + SatCat data. Visualizations of hotspots, growth trends, and overlap with Starlink.

SpaceAware – Enhancing Space Situational Awareness

📌 Project Overview

This project analyzes satellites and debris in Low Earth Orbit (LEO) using data from the Unified Data Library  (UDL) Elset, CelesTrak and SatCat.
By combining multiple open datasets, we provide a clearer picture of the orbital environment, highlight altitude hotspots, quantify debris risks, and assess the growing role of Starlink satellites.

The analysis was developed as part of the 2025 Space Situational Awareness Datathon.

⸻

🎯 Objectives
	•	Identify altitude ranges and inclination bands with the highest congestion in LEO.
	•	Quantify the presence of debris vs active satellites.
	•	Compare Starlink vs non-Starlink satellites and their overlap with debris.
	•	Flag satellites at decay risk (perigee < 300 km).
	•	Provide insights for space traffic management and orbital safety.

⸻

🗂️ Data Sources
	•	Unified Data Library (UDL) – Elset data (via authenticated API).
	•	CelesTrak SatCat – Satellite catalog (OBJECT_TYPE, OWNER, etc.).
	•	CelesTrak Starlink TLEs – List of Starlink satellites for tagging.

These datasets were merged into a unified analysis frame, ensuring active satellites, payloads, and debris are all captured.

⸻

🛠️ Methodology & Tools
	•	Python for analysis and visualization.
	•	Pandas / NumPy for data cleaning & aggregation.
	•	Matplotlib / Seaborn for visualizations.
	•	Requests for pulling UDL and CelesTrak data.
	•	EDA artifacts: schema checks, missingness, numeric summaries, sample rows.

Workflow:
	1.	Fetch raw UDL data via API → normalize JSON.
	2.	Perform data cleaning & validation (missing values, duplicates, schema).
	3.	Merge with SatCat metadata to classify debris vs payloads.
	4.	Tag Starlink satellites using CelesTrak TLEs.
	5.	Analyze altitude hotspots, RAAN–inclination planes, debris overlap, and decay-risk candidates.

⸻

📊 Key Findings
	•	LEO Congestion Hotspots: Most satellites cluster around ~500–600 km and ~1100–1200 km.
	•	Debris Load: 26% of LEO objects are debris, with hotspots overlapping with active payloads.
	•	Starlink Impact: Starlink dominates the 53° inclination band, significantly contributing to congestion.
	•	Decay Risk: Hundreds of satellites are below 300 km perigee, indicating likely re-entry in the near term.
	•	Overlap Zones: Certain altitude bands contain Starlink, non-Starlink, and debris together, raising collision risks.

⸻

📈 Visualizations

Key plots (included in repo):
	•	leo_altitude_hotspots.png – LEO congestion by altitude.
	•	leo_debris_hotspots.png – Debris distribution in LEO.
	•	raan_vs_inclination_heatmap.png – Orbital plane density.
	•	leo_overlap_hotspots.png – Starlink, non-Starlink, and debris overlap.
	•	leo_decay_risk_histogram.png – Satellites with reentry risk.

⸻

 === SpaceAware – Key Numbers Recap ===
All objects: 30000
LEO objects: 27752
Debris in LEO: 7371  (26.56%)
Starlink (all): 9675
Starlink in LEO: 9666  (34.83%)
Decay-risk in LEO (<300 km perigee): 180  (0.65%)
Top 5 LEO altitude hotspots (100-km bins):
   500–600  km : 7188 objects
   400–500  km : 5326 objects
   700–800  km : 2562 objects
   800–900  km : 2500 objects
   900–1000 km : 1942 objects

(Exact counts available in spaceaware_kpis.json and spaceaware_kpis.txt)

Intallation

clone the repo: 
git clone https://github.com/YOUR-USERNAME/SpaceAware-LEO-Analysis.git
cd SpaceAware-LEO-Analysis

Install dependencies:
pip install -r requirements.txt

Run the Jupyter Notebook:
jupyter notebook Final_udl_elset.ipynb

👩‍🚀 Team
Datathon Team: Space Aware Trio 
Focused on advancing space sustainability through data-driven analysis.  
- [@kayeneii](https://github.com/kayeneii) 
- Shruthi Bhaskaran 
