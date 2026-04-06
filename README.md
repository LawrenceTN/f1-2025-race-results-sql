# f1-2025-race-results-sql

# F1 2025 Race Results – SQL Modeling & Data QA

This project uses a 2025 Formula 1 race results dataset (from Kaggle) to practice creating basic analytics and data quality techniques via SQL using duckDB.

In the notebook, I:

- Load the raw F1 2025 race results as a table `raw_race_results` using DuckDB in a Kaggle notebook.
- Create a cleaned fact-style table `fact_driver_race_results`  
  (one row per driver per race, with columns like track, team, position, laps, points).
- Build a `dim_driver` table with `driver_id` and `driver_name`.
- Create `fact_driver_race_results_with_ids` by joining the fact table to `dim_driver`.
- Run data quality checks:
  - Row count reconciliation between base and modeled tables.
  - Check for null `driver_id`.
  - Basic sanity checks on `points` and `fastest_lap_time`.
- Run example analysis queries such as total points by driver.

The goal is to show a small but realistic example of:

- Fact vs dimension tables.
- Thinking about grain (one driver–race per row).
- Writing warehouse-style SQL and simple data quality checks.
