# SpaceX Falcon 9 First-Stage Landing Prediction

IBM Applied Data Science Capstone-style project: collect, wrangle, explore, map, dashboard, and model SpaceX Falcon 9 launch records to understand and predict first-stage landing outcomes.

> **Reproducibility note:** This repository is a runnable project scaffold. The execution environment used to prepare it had no network access, so model scores, plots, and data-derived findings have **not** been run or verified here. Run the notebooks with internet access to generate genuine results before presenting them as findings.

## Research question
Can launch-related features such as payload mass, orbit, launch site, flight number, booster configuration, and reuse history help predict Falcon 9 first-stage landing success?

## Repository layout
- `notebooks/`: eight notebooks covering API, scraping, wrangling, EDA, SQL, maps, dashboard exploration, and ML.
- `src/`: reusable data download/wrangling and evaluation helpers.
- `dashboard/app.py`: interactive Dash application.
- `data/`: downloaded and processed data (not populated initially).
- `reports/`: project report and presentation PDF; update results after running notebooks.

## Data sources
- SpaceX API launch records: https://api.spacexdata.com/v4/launches/past
- IBM Skills Network course dataset (API-derived): https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DS0321EN-SkillsNetwork/datasets/dataset_part_2.csv
- IBM Skills Network feature dataset: https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DS0321EN-SkillsNetwork/datasets/dataset_part_3.csv
- Launch records from Wikipedia (scraping lab): https://en.wikipedia.org/wiki/List_of_Falcon_9_and_Falcon_Heavy_launches

## Quick start
```bash
python -m venv .venv
# Windows: .venv\Scripts\activate | macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
````
Open `notebooks/` in Jupyter or Colab and run in order. Notebooks fetch course data into `data/raw/` when run.

Run dashboard after downloading dashboard CSV (or provide `SPACEX_DASH_DATA` path):
```bash
python dashboard/app.py
```
Then open the local Dash URL shown in terminal.

## Methods
API collection and scraping; missing-value handling; feature engineering; exploratory visualization; SQLite SQL analysis; Folium maps and proximity calculations; Plotly Dash; classification pipelines for Logistic Regression, SVM, Decision Tree, and KNN; test-set metrics and confusion matrices.

## Model evaluation
Report accuracy, precision, recall, F1, Jaccard and confusion matrix on a held-out test set. Avoid presenting scores until the ML notebook has run. Consider class imbalance and explain the selected model using the metrics rather than accuracy alone.

## Limitations
Historical launch records are relatively small; launch outcomes and booster technologies evolve; public data may contain missing or inconsistent records; predictions are not a substitute for engineering or mission safety assessment.

## Author
Add your name, course details, date, and GitHub repository URL before publishing.
