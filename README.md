# Moneyball_Project

A reproducible sports-analytics pipeline that extracts, cleans, integrates, and models football (soccer) player data to support scouting and valuation analysis. This repository implements stages inspired by the Henderson Sports Analytical Framework and produces analysis-ready CSVs, player scoring metrics, predictive models, and an interactive scouting prototype.

---

Table of Contents
- Project summary
- Key features
- Data & methodology (stages)
- Repository structure
- Quick start — running the project
- Notebooks and workflow order
- Example output
- Future enhancements
- Contributing & contact
- License

Project summary
---------------
This project automates stages 2–6 (and provides stage 7 prototypes) of the Henderson Sports Analytical Model for the 2023–2024 European football season. It:
- Scrapes structured player statistics from FBref.
- Cleans and flattens multi-index tables into analysis-ready DataFrames.
- Integrates multiple statistical domains (standard, defensive, possession).
- Produces cleaned CSVs (by positional group).
- Builds composite Player Score metrics and Random Forest models to investigate player performance and market valuation.
- Includes an interactive scouting prototype built with ipywidgets for dynamic player filtering and comparison.

Key features
------------
- Automated web extraction (pandas.read_html)
- Robust cleaning for multi-level headers and missing values
- Multi-domain integration for richer player profiles
- Reproducible CSV outputs by position (Goalkeepers, Defenders, Midfielders, Forwards)
- Player Score — composite positional metrics with custom weighting
- Predictive modeling (Random Forest) for:
  - Predicted Player Performance (Player Score as target)
  - Predicted Market Value (compared with Transfermarkt estimates)
- Interactive scouting prototype using ipywidgets (IntSlider, dropdowns)

Data & methodology (stages)
---------------------------
- Stage 2 — Extraction:
  - Retrieve HTML tables from FBref using pandas.read_html
- Stage 3 — Preparation:
  - Clean and flatten multi-level column headers, normalize names, handle missing values
- Stage 4 — Integration:
  - Merge standard, defensive and possession datasets; align columns and formats
- Stage 5 — Storage:
  - Export cleaned, position-specific CSVs
- Stage 6 — Modeling:
  - Construct composite Player Score per position and train Random Forest models
- Stage 7 — Scouting Interface (prototype):
  - Jupyter Widgets allow interactive filtering and ranking by custom metric weights
 
Project Purpose
------------
The goal of this project is to develop a robust and scalable sports analytics pipeline capable of handling complex football datasets that can then be used to train machine learning models and/or be used for the scouting football application. It forms the foundation for player scouting, performance evaluation, and strategic decision-making within the Henderson analytical model.

Data sources
------------
- FBref.com — match and player statistics
- Transfermarkt.com — estimated player market values (used as comparison)

Technical Highlights
--------------------
Stage	Focus	Implementation
Stage 2 – Extraction	Retrieve HTML tables from FBref	pandas.read_html()
Stage 3 – Preparation	Clean and flatten multi-level column headers	String manipulation & reset_index()
Stage 4 – Integration	Merge datasets from multiple statistical domains	Column alignment & DataFrame merging
Stage 5 – Storage	Produce clean CSVs for analysis and visualisation	.fillna(0), column renaming, reformatting
Stage 6 – Composite statistics are used for predicitive modeling to help find undervalued footballers. 
Stage 7 – Scouting Interface	Create interactive player filtering system	ipywidgets (IntSlider, dropdowns, dynamic output)


Technologies Used
--------------------

Language: Python 3

Libraries:

pandas — data extraction, cleaning, and manipulation

matplot — data visualisation (graphs)

ipywidgets — interactive visual interfaces (IntSlider widgets)

Environment: Jupyter Notebook / JupyterLab

Repository structure
--------------------
Moneyball_Project/
- Dataset to import: players.csv
- Final Project Code (Data Preparation).ipynb — Extraction, cleaning, integration (Stages 2–5)
  - goalkeepers_cleaned.csv
  - defenders_cleaned.csv
  - midfielders_cleaned.csv
  - forwards_cleaned.csv
- Player Score.ipynb — Building composite Player Score metrics
- Player Score and Predicted Performance.ipynb — Predict Player Score with Random Forest
- Predicted Value and Estimated Transfer Value.ipynb — Value prediction & comparison to Transfermarkt
- Scouting System.ipynb — Interactive scouting interface prototype (ipywidgets)

Quick start — run locally
-------------------------
1. Clone the repository
```bash
git clone https://github.com/Kez123man/Moneyball_Project.git
cd Moneyball_Project
```

2. Create a virtual environment (recommended)
```bash
python -m venv venv
source venv/bin/activate   # macOS / Linux
venv\Scripts\activate      # Windows
```

3. Install dependencies
```bash
pip install -r requirements.txt
```

4. Run the notebooks in order (recommended)
- Open Jupyter Notebook / JupyterLab:
```bash
jupyter lab
```
- Run notebooks in this order:
  1. Final Project Code (Data Preparation).ipynb (Notebook will also import "players.csv" dataset).
  2. Player Score.ipynb
  3. Player Score and Predicted Performance.ipynb
  4. Predicted Value and Estimated Transfer Value.ipynb
  5. Scouting System.ipynb (to use the interactive prototype)

Notes
- The data extraction notebooks scrape FBref; be mindful of site policies and rate limits. Consider saving raw HTML or CSV outputs locally for repeated experimentation.
- If Transfermarkt scraping is used, respect its terms of service — or provide a pre-downloaded CSV of market values if scraping is not desirable.

Usage examples
--------------
- Generate cleaned CSVs for each position and use them to:
  - Find undervalued players (low market value vs high predicted performance)
  - Build custom player profiles via the interactive scouting UI
  - Export filtered player tables for visualization or reports

Example snippet (cleaned outfield players)
| Player             | Age | Team       | xG   | Ast  | Tkl | Carries | Possession% |
|-------------------:|----:|------------|-----:|-----:|----:|--------:|-----------:|
| Max Aarons         |  23 | Bournemouth| 0.00 | 0.07 | 29  | 364     | 56.8       |
| Brenden Aaronson   |  22 | Union Berlin| 0.14| 0.28 | 32  | 406     | 62.3       |

Future enhancements
-------------------
- Add more metrics (e.g., Ground Duels Won, Expected Threat xT)
- Move data storage to SQL or cloud (S3, BigQuery)
- Automate periodic updates (CRON / Airflow)
- Build a deployable interactive dashboard (Streamlit / Dash / Power BI)
- Expand model experiments (different algorithms, cross-validation, hyperparameter tuning)

Skills Demonstrated
-------------------

Data Engineering & ETL Design

Interactive Data Visualisation (ipywidgets & matplot)

Sports Analytics & Predictive Modeling

Python Programming & Data Pipeline Architecture

Reproducible Analytical Workflows


Contributing
------------
Contributions welcome:
- Open an issue to discuss ideas or bugs
- Submit pull requests for improvements, new metrics, or UI enhancements
- Please add tests where appropriate and update documentation

Contact
-------
Repository: https://github.com/Kez123man/Moneyball_Project
Author: Kez123man

License
-------
Specify a license (e.g., MIT) in a LICENSE file if you want others to reuse this work. If you’d like, I can add an MIT license file for you.

Acknowledgements
----------------
Adapted from: Holland and Shaw (2019), Henderson Sports Analytical Framework. This project combines data engineering, statistical modeling and interactive prototyping to demonstrate an end-to-end sports analytics pipeline.




