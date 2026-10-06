# New York Mets Batting Analysis, 1962-2023

Exploratory data analysis and statistical testing on 60+ years of New York Mets batting data, using Python.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/floresthescientist/New-York-Mets-Exploratory-Data-Analysis-Statistical-Modeling-Python/blob/main/New_York_Mets_Batting_Stats_1962_2023.ipynb)

## The question

Who were the best offensive players in Mets history, how rare are elite seasons, and has Mets hitting changed over time?

## Key findings

- **Elite seasons are rare.** Only 73 of 556 qualifying player seasons (13.1%) had an OPS above .850. A normal-distribution model predicted 12.4%, a close match.
- **The best seasons belong to the late-90s lineup.** Mike Piazza (1.024 in 1998, 1.012 in 2000) and John Olerud (.998 in 1998) top the list.
- **David Wright was the most consistent star,** with 6 seasons in the top 10% of OPS. Carlos Beltrán, Mike Piazza and Darryl Strawberry each had 5.
- **Mets hitting improved over time.** Average OPS rose from .669 in the 1960s to a peak of .782 in the 2000s. Before 1990 it was .699 and from 1990 on it was .764 (Welch's t-test, p < 0.001).
- **Power signals production.** Among seasons with 25+ home runs, 80.7% also had an OPS above .800.
- **Getting on base is hard.** Only about 30% of seasons reached a .350 OBP (95% CI: 26.1% to 33.7%), significantly below a 40% target (p < 0.001).

## Data

- **Source:** [Confirm and name your source here. The column names match the public "New York Mets Batting & Pitching (1962-2023)" dataset on Gigasheet.]
- **Size:** 2,728 player-season records with 31 columns, reduced to 10 relevant columns
- **Filter:** Seasons with fewer than 250 at-bats were removed, leaving 556 qualifying seasons from 220 players.
- **Quality checks:** No missing values and no duplicate rows

## Methods

| Technique | Used for |
|---|---|
| Descriptive statistics | Mean and median OPS, OBP, SLG, runs and at-bats |
| Visualization (`seaborn`, `matplotlib`) | Pairplot, OPS histogram, top-10 player chart, elite-seasons scatter |
| Probability (AND, OR, conditional) | How often seasons meet power and on-base thresholds |
| Normal distribution model | Z-scores and the 90th percentile OPS (.862) |
| Confidence intervals | Mean OPS (.725 to .742), mean home runs, and OBP proportion |
| One-sample t-test | Mean OPS vs. a .700 benchmark (t = 7.85, p < 0.001) |
| Welch's two-sample t-test | Pre-1990 vs. 1990+ OPS (t = -7.97, p < 0.001) |
| One-proportion z-test | Share of seasons with OBP of .350 or higher vs. 40% (z = -4.88, p < 0.001) |

## Visuals

![OPS distribution](images/ops_distribution.png)
![Top 10 players by average OPS](images/top10_players.png)

## How to run

1. Click the **Open in Colab** badge above.
2. Choose **Runtime → Run all**. The data loads automatically from a CSV URL.

**Libraries:** pandas, numpy, matplotlib, seaborn, scipy

## Limitations

- Results cover the Mets only, so they don't generalize to other teams.
- The 250 at-bat cutoff is a judgment call, and it excludes part-time players.
- Raw OPS isn't adjusted for era. Hitting environments differ across six decades, so comparing eras would be stronger with OPS+ (included in the original dataset).
- The .700 and 40% benchmarks in the hypothesis tests are chosen thresholds, not official league standards.

## Author

Adonis Flores | Lehman College, Data Analytics
[LinkedIn link]

Licensed under MIT.
