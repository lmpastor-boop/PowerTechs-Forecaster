⚡ PowerTechs · Workforce Skills Intelligence Tool
A data-driven skills intelligence tool for California's Construction, Energy, Transportation, and Agriculture (ACET) workforce. Built as part of the UC Davis MSBA Practicum in partnership with PowerTechs, a Techstars-backed startup building an AI-driven reskilling platform.

🔗 Live Tool
👉 Open the Skills Intelligence Tool
No installation required — opens directly in any web browser.

📌 What This Tool Does
This tool helps workforce planners, HR managers, and policymakers understand how AI and automation are reshaping skill demand across California's key industries.
Given a sector, job role, time horizon, and scenario, the tool returns:

Annual sector growth rate — based on ARIMA forecast of CA EDD employment data
Directional trend — how skill demand is shifting over the selected time horizon
AI effect on sector jobs — the additional job impact from AI exposure adjustment
Role AI exposure score — how strongly AI augments or disrupts this specific role
Skill demand profile — which macro skills are growing (AI-positive) vs declining (AI-negative)
Sector comparison chart — SARIMA baseline vs AI-Adjusted across all four ACET sectors


⚠️ Important: This is a sector-level trend signal, not a company headcount forecast. Use it to inform hiring priorities and reskilling investments alongside your internal business planning.


🧠 Methodology
The tool is powered by two models working together:
1. SARIMA Baseline Forecast

Source: California EDD monthly employment data (1990–2025)
Model: ARIMA(1,1,1) fit to each ACET sector
Output: History-driven baseline employment projection to 2033

2. AI Exposure Adjustment

Source: O*NET macro skill matrix (occupation-level skill shares)
Method: Weighted skill exposure score per occupation

Computers: +1.0, Information: +0.6, Management: +0.3, Communication: +0.2, Machinery: −0.8


Scaling parameter: α = 0.10
Output: AI-adjusted employment projection by sector

3. IO Matrix Integration

Source: California IO Matrix (2023–2033 occupation projections)
Used as fallback growth factor where ARIMA coverage is unavailable

Shift-Share Decomposition
France/EU decomposition data used as external validation benchmark, decomposing skill demand change into Scale Effect (economy-wide growth) and Mix Effect (structural change within sector).

📊 Data Sources
DatasetSourceCA Employment by Sector (1990–2025)California EDDCA IO Matrix Occupation ProjectionsCalifornia EDD / BLSO*NET Macro Skill MatrixO*NET OnlineFrance/EU Decomposition BenchmarkEurostat ESCO

🗂️ Repository Contents
FileDescriptionindex.htmlStandalone Skills Intelligence Tool (open in browser)forecaster_v3_cells.pyPython version for Google Colab / Cursoracet_panel_forecast.csvFinal sector-level SARIMA + AI forecast outputsonet_macro_skill_matrix.csvO*NET skill shares by occupation

🚀 How to Use
Option A — Live web tool (recommended):
Click the link above. No setup needed.
Option B — Run locally in Python:
bashpip install matplotlib ipywidgets pandas
Open forecaster_v3_cells.py in Google Colab or Cursor and run all cells.

👥 Team
NameRoleLarry PastorARIMA pipeline, AI exposure scoring, Skills Intelligence ToolAmal Farhad ShajiEmerging Tasks Database, transition pathways, stakeholder website
Industry Partners:

Ksenia Solomatina — CEO, PowerTechs
Scott Mauvais — Advisor (ex-Microsoft, Senior Director AI & Global Partnerships)


🎓 Academic Context
Program: UC Davis Master of Science in Business Analytics (MSBA)
Practicum Partner: PowerTechs (Techstars-backed)
Year: 2025

⚠️ Limitations

Projections reflect California sector-level trends — not company-specific forecasts
ARIMA(1,1,1) assumes future trends resemble historical patterns — AI scenario adjusts for structural change
AI exposure weights are methodological choices informed by published literature — results are directional, not prescriptive
Agriculture and Energy sectors use IO matrix fallback growth factors where ARIMA coverage is limited


📄 License
This project was developed as part of an academic practicum. Data sources retain their respective licenses. Code is available for educational and research purposes.
