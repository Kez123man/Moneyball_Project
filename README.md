# Moneyball_Project

# Overview

The jupyter notebook files of this project automates stages 2–5 of the Henderson Sports Analytical Model, encompassing:

Data Extraction — Automated retrieval of player statistics from FBref.com
 for the 2023–2024 European football season.

Data Preparation — Cleaning, restructuring, and standardizing complex multi-index tables.

Data Integration — Combining multiple statistical dimensions (standard, defensive, and possession data).

Data Storage — Creating clean, analysis-ready DataFrames for further analytical or visualisation pipelines.

Aggregate Statistic — Using different variables an aggregate/composite statistic is created with different variables weighted differently for each position (e.g., goals are worth more to attacking players than defenders).

Player Score, Market Value & Predictive Modeling — The Random Forest model is used to try and predict players' performance and value, which was done by using the Player Score and Market Value metrics. 

Interactive Scouting System — Visual, user-driven interfaces built with Jupyter Widgets to explore and compare player performance.

Adapted from: Holland and Shaw (2019), Henderson Sports Analytical Framework.

This program demonstrates a fully functional sports analytics pipeline, combining data engineering, statistical modeling, and interactive scouting functionality.

# Project Purpose

The goal of this project is to develop a robust and scalable sports analytics pipeline capable of handling complex football datasets that can then be used to train machine learning models and/or be used for the scouting football application. It forms the foundation for player scouting, performance evaluation, and strategic decision-making within the Henderson analytical model.

# Key Features

✅ Automated Web Data Extraction

Webscrapes structured player data directly from FBref’s HTML sources.

✅ Dynamic Data Cleaning & Transformation

Handles multi-level indexing, missing values, inconsistent column naming and removal of irrelevant columns.

Then the raw web data is converted into consistent, machine-readable formats.

✅ Multi-Domain Data Integration

Combines standard, defensive, and possession football metrics for comprehensive analysis.

✅ Reproducible Data Storage

Cleaned, structured CSVs are then produced for each positional category (Goalkeepers, Defenders, Midfielders, Forwards).

✅ Predictive Modeling (Random Forest)

Two major comparisons were conducted using RF models:

Estimated Market Value vs. Predicted Value

Player Score vs. Predicted Performance

These analyses aimed to evaluate how closely machine learning predictions aligned with real-world player performance and market valuation trends.

✅ Interactive Scouting System (Prototype)

Built using Jupyter Widgets, enabling dynamic filtering and exploration of player performance data.

Four CSV datasets (one per position) are imported — each containing relevant variables.

Three Outfield Player Interfaces (Defender, Midfielder and Attacking Player) that allows users to customise metrics using IntSlider controls to output the desired player profile.

A dedicated Goalkeeper Interface was also created using IntSlider widgets for specialised positional metrics (e.g., saves per games).

The system is modular and extendable — additional metrics (e.g., duels won per game) can be easily integrated in future iterations by updating the widget configuration and underlying data structure.

🧠 Technical Highlights
Stage	Focus	Implementation
Stage 2 – Extraction	Retrieve HTML tables from FBref	pandas.read_html()
Stage 3 – Preparation	Clean and flatten multi-level column headers	String manipulation & reset_index()
Stage 4 – Integration	Merge datasets from multiple statistical domains	Column alignment & DataFrame merging
Stage 5 – Storage	Produce clean CSVs for analysis and visualisation	.fillna(0), column renaming, reformatting
Stage 6 – Composite statistics are used for predicitive modeling to help find undervalued footballers. 
Stage 7 – Scouting Interface	Create interactive player filtering system	ipywidgets (IntSlider, dropdowns, dynamic output)
🧰 Technologies Used

Language: Python 3

Libraries:

pandas — data extraction, cleaning, and manipulation

matplot — data visualisation (graphs)

ipywidgets — interactive visual interfaces (IntSlider widgets)

Environment: Jupyter Notebook / JupyterLab

Data Source: 

FBref.com
 – Official statistics for top European leagues.

 Transfermarkt.com
 – Players estimated transfer market values.

# Project Structure
📂 henderson-sports-analytics/
│

├── 💻 Final Project Code (Data Preparation).ipynb # Data extraction, cleaning, storage & integration (Stages 2–5)                     │   ├── goalkeepers_cleaned.csv
│   ├── defenders_cleaned.csv
│   ├── midfielders_cleaned.csv
│   └── forwards_cleaned.csv # Cleaned and processed datasets
│ 
├── 📊 Player Score.ipynb                          # Player Score metric created for each position
│
├── 📈 Player Score and Predicted Performance.ipynb # Combined analysis of player scoring and predictions
│
├── 💰 Predicted Value and Estimated Transfer Value.ipynb # Market valuation & predictive transfer modeling
│
├── 🧠 Scouting System.ipynb                       # Interactive scouting interfaces (Outfield & Goalkeeper widgets)
│
└── 📘 README.md                                   # Project documentation (this file)

🚀 How to Run
1️⃣ Clone the Repository
git clone https://github.com/<your-username>/henderson-sports-analytics.git
cd henderson-sports-analytics

2️⃣ Install Dependencies
pip install -r requirements.txt

3️⃣ Run the Data Pipeline
python henderson_pipeline.py

4️⃣ Launch the Interactive Scouting Interface

Open the Jupyter Notebook and run the scouting interface:

jupyter notebook scouting_interface.ipynb

📈 Example Output

Cleaned Data Example (Outfield Players):

Player	Age	Team	xG	Ast	Tkl	Carries	Possession%
Max Aarons	23	Bournemouth	0.00	0.07	29	364	56.8
Brenden Aaronson	22	Union Berlin	0.14	0.28	32	406	62.3

Scouting Interface (Example Prototype – Figures 4.1.1–4.1.3)
Users can interactively:

Adjust performance thresholds using sliders.

Filter by position, team, or age group.

Identify players that best match desired statistical profiles.

🧩 Future Enhancements

📊 Add advanced performance metrics (e.g., Ball Recoveries, Expected Threat (xT)).

🧮 Integrate predictive modeling for player ranking.

🗃️ Migrate data to SQL or cloud-based storage.

📈 Create real-time dashboard integration (e.g., Streamlit or Power BI).

⏱️ Automate weekly data updates using Airflow or CRON jobs.

🏆 Skills Demonstrated

Data Engineering & ETL Design

Interactive Data Visualization (ipywidgets)

Sports Analytics & Predictive Modeling

Python Programming & Data Pipeline Architecture

Reproducible Analytical Workflows
