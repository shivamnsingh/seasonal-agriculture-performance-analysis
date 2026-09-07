# Seasonal Agriculture Performance Analysis

A data analytics project looking at how farming performance changes across India's three growing seasons — Kharif, Rabi, and Zaid. Built as a major project for VOIS AICTE Batch 1, 2026–2027.

## Why this project

Farming doesn't happen in a vacuum. Rainfall, temperature, humidity, and soil conditions shift with the season, and so do the choices farmers make around irrigation, fertilizer, and pesticide use. What isn't always obvious from raw data is *how much* those seasonal shifts actually matter — whether they show up mainly in yield, in cost, in profit, or somewhere else entirely.

Instead of running a generic pass over every column in the dataset, this analysis was built around a specific set of questions:

- How do environmental conditions actually differ across seasons, and does the data back up what we'd expect?
- Does yield genuinely differ by season, or is that difference smaller (or noisier) than it looks?
- Which season is the most profitable — and is that the same season with the best yield?
- Does using more water or fertilizer actually translate into better outcomes?
- Is disease and pest risk really driven by humidity, or is that assumption wrong?
- Do seasonal patterns hold up across every state, or do some regions break the trend?

## What's in this repo

```
├── Seasonal_Agriculture_Performance_Analysis.ipynb   # Main analysis notebook
├── seasonal_agriculture_performance_dataset.csv      # Dataset (4,000 farm records)
└── README.md
```

## About the dataset

4,000 farm-level records across 8 Indian states, 8 crops, and 3 seasons, covering:

- **Environmental conditions** — rainfall, temperature, humidity, sunlight hours, soil pH and moisture
- **Farming inputs** — nitrogen/phosphorus/potassium levels, fertilizer, pesticide, irrigation method, seed quality
- **Outcomes** — yield, production, market price, cost, revenue, profit, water usage and efficiency, disease/pest risk

## What the notebook actually does

1. **Cleans the data** — fills a small number of missing values (season-wise medians, since rainfall and soil moisture vary a lot by season), checks for duplicates, and sanity-checks that nothing is outside a plausible range.
2. **Confirms the seasons are real** — checks that Kharif, Rabi, and Zaid actually look climatically distinct in the data before assuming any performance difference is "seasonal."
3. **Compares yield across seasons**, backed by a statistical test (one-way ANOVA) rather than just eyeballing a chart.
4. **Digs into profitability separately from yield** — because a season can look fine on production and still be a weak season financially once cost and price are factored in.
5. **Looks at resource efficiency**, not just resource volume — using more water or fertilizer isn't automatically better, and the data shows where returns flatten out.
6. **Checks irrigation method effectiveness by season**, since drip/sprinkler/flood/rainfed don't necessarily rank the same way in every season.
7. **Tests the humidity → disease/pest risk assumption** rather than taking it for granted.
8. **Breaks results down by state** to see whether national-level patterns actually hold locally, or whether some states are outliers worth treating separately.
9. **Flags specific outlier farms** — both over- and under-performers relative to their season/crop peers — as a sanity check on the averages.
10. **Wraps up with findings and recommendations** that are tied directly back to the evidence in the notebook, not generic advice.

## How to run it

```bash
git clone <your-repo-url>
cd <repo-folder>
pip install pandas numpy matplotlib seaborn scipy jupyter
jupyter notebook Seasonal_Agriculture_Performance_Analysis.ipynb
```

The notebook runs top to bottom with no manual steps in between — just run all cells.

## A note on the findings

The conclusions in the notebook are written to be evidence-based rather than assumed. A couple of things worth calling out up front: profitability doesn't move in lockstep with yield in this data, and the "more humidity = more disease risk" assumption turns out to be weaker than expected. Both are explained with the actual numbers in the relevant sections rather than asserted.

## Author

Built as part of the VOIS AICTE Data Analytics program, 2026–2027.
