Engineering Clear Skies at ORD
Flight Difficulty Scoring, EDA, and Post‑Analysis for proactive on‑time performance

Overview
This project builds a practical, data‑driven way to spot hard flights before they depart. It combines exploratory data analysis (EDA), a weighted Flight Difficulty Score, and outcome validation to help frontline teams prioritize staffing, equipment, and attention where delay risk is highest.

What’s in this repo
Understanding_Data_EDA.ipynb

Exploratory analysis of flight, baggage, and passenger features

Delay distribution, time‑of‑day congestion, SSR impact, transfer baggage patterns

Flight_difficulty_Ranking.ipynb

Feature engineering and daily scoring pipeline

Min–max normalization, weighted score, daily rank, and category (Difficult/Medium/Easy)

Post_Analysis.ipynb

Validation of the score vs. actual outcomes

Confusion‑style tables, lift by category, and practical takeaways

test_United_Together.csv

Example output with per‑flight features, score, rank, and category for operational use

How the scoring works
Features captured per flight:

Turnaround pressure = minimum turn − scheduled ground time

Baggage complexity = 2 × hot transfer bags + other transfers

Passenger service load = SSR count

Congestion factor = bucketed by scheduled departure hour

Route difficulty flag = historically challenging stations

Total volume = passengers + checked bags

Per‑day processing:

Min–max normalize each feature (0–1) within the day

Weighted sum (higher weights on turnaround pressure and hot transfers)

Rank flights by score and classify into Difficult/Medium/Easy
