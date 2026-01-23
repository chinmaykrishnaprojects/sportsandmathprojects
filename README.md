# Sports and Math Projects

Quantitative sports analytics projects combining probabilistic modeling, statistical inference, and data visualization. Includes win probability models, ranking systems, playoff simulations, and predictive analytics.

![Project Showcase](assets/project_showcase.png)

## Overview

This repository contains formal documentation and code for selected sports analytics projects. Many originated as visualizations and threads posted to [X](https://x.com/search?q=from%3Asportsandmath1%20Here%27s&f=media) ([no login required](https://xcancel.com/search?q=from%3Asportsandmath1%20Here%27s)).

Projects here emphasize reproducibility, clear methodology, and technical depth.

**Topics:** `python` `data-science` `sports-analytics` `statistics` `machine-learning` `bayesian-statistics`

---

## 🏈 NFL Playoffs Odds Engine

**[→ Try the Live App](https://nfl-playoff-odds-engine.vercel.app/)**

A web app for reverse-engineering playoff odds—initially shipped within a week before the 2026 Playoffs. Takes 14 teams, enumerates all 2^13 = 8,192 bracket possibilities, and finds team strengths that best align with Super Bowl odds via KL divergence optimization.

**Key Features:**
- Live win probability charts
- Injury adjustments  
- Conference winner odds integration

> [!NOTE]
> The same enumeration approach powers my **NBA Series Odds** work (8C4 = 70 outcomes per series) and was extended to the **NCAA bracket** (64 teams, 2^60 possibilities). The 2025 March Madness ranked as the 114 millionth most likely outcome—historically chalk.

<details>
<summary>📊 Related Work on X</summary>

- [Detailed NBA Series Odds](https://x.com/search?q=from%3Asportsandmath1%20detailed%20series&src=typed_query&f=live)
- [Bayesian Odds Visualization](https://x.com/SportsandMath1/status/1933733491331772746)
- [2025 March Madness Analysis](https://x.com/SportsandMath1/status/1906499635025215532)

</details>

---

## 🏀 MOV to W-L Calculator

**[→ Try the Live App](https://mov-calculator.vercel.app/)** *(Work in Progress)*

Takes a league's margin-of-victory distribution, convolves it N times to find the total MOV distribution, then decomposes it into conditional W-L probabilities. This yields **exact odds** via modeling rather than simulation.

**Coming Soon:** A Bayesian view showing how a single MOV result updates your prior belief about a team's true record.

<details>
<summary>📊 Related Work on X</summary>

- [NFL MOV Analysis](https://x.com/SportsandMath1/status/1876090785558626746)
- [Bayesian Framework Thread](https://x.com/SportsandMath1/status/2013433795123273873)
- [Team Strength as Probability Distributions](https://x.com/SportsandMath1/status/1846414761619054801)
- [Pregame W% → Exact Results Mapping](https://x.com/SportsandMath1/status/1839723373674295679)

</details>

---

## 🏀 NBA Player Rankings

**[→ Live Rankings App](https://nba-ranking-app-282129715603.us-central1.run.app/)**

A player ranking system developed since 2020 using linear regression on per-game stats, trained against the consensus of "expert" rankings. Achieves **R² > 0.9** on out-of-sample data.

**Why it's different from standard metrics (RAPM, BPM, etc.):**
- Per-game (not per-possession)—properly values volume
- More "sample efficient"—reacts faster to changes in player talent
- Avoids overrating role players like Danny Green or Alex Caruso as superstars

**Highlight:** I ["solved" the NBA GOAT debate](https://x.com/SportsandMath1/status/1929032284478349336) with a peak-performance chart of all top players since 1977.

<details>
<summary>📊 Insights & Related Work</summary>

- [Ranking Insights Example](https://x.com/SportsandMath1/status/1904000845152170078)
- [Correlation with RAPM (per-game scale)](https://x.com/SportsandMath1/status/1731102558251364592)
- [Comparison vs Leading Metrics](https://x.com/SportsandMath1/status/2009366811985252508)
- [Unique Use Cases Thread](https://x.com/SportsandMath1/status/1988114052443242695)

</details>

---

## 🏈 NFL QB Rankings

**[→ Live Rankings](https://nba-ranking-app-282129715603.us-central1.run.app/nfl)** | **[→ Compare Players](https://nba-ranking-app-282129715603.us-central1.run.app/nfl/compare)**

Uses ESPN's EPA/QBR scores (which properly divide credit between QB and teammates) combined with a **Gaussian Process (Random Walk)** model to track player trajectories over time.

**Key Differentiators:**
- Per-game metric (rewards volume, unlike rate stats)
- Double-sided filtering—uses all career games, including future ones, to "revise" estimates and minimize variance
- Enables robust **Most Improved Player** metrics even with limited samples

<details>
<summary>📈 Age Curves & More</summary>

- [Age Curve Predictions (XGBoost, Neural Nets)](https://x.com/search?q=From%3ASportsandmath1%20age%20curve&src=typed_query&f=live)
- [Ranking Engine v1](https://sportsandmath1.github.io/RankingEngine/)
- [v2 with Uncertainty Visualization](https://x.com/SportsandMath1/status/1923882530308059236/photo/1)

</details>

---

## 📈 Win Probability Models

Self-consistent Markov models using **time (1s resolution) + MOV** instead of feature-based logistic regression. Prioritizes self-consistency over raw accuracy, resulting in smoother play-by-play probability curves.

<details>
<summary>📊 Examples on X</summary>

- [Self-Consistent WP Model](https://x.com/SportsandMath1/status/1922483030368637025)
- [Example 1](https://x.com/SportsandMath1/status/1778252615626727920)
- [Example 2](https://x.com/SportsandMath1/status/1789006738819006916)
- [Example 3](https://x.com/SportsandMath1/status/1792312529487597705)

</details>

---

## Methodology

| Approach | Description |
|----------|-------------|
| **Bayesian Inference** | Robust parameter estimation and uncertainty quantification |
| **Monte Carlo Simulations** | Modeling complex game scenarios and playoff outcomes |
| **Exact Enumeration** | When feasible (e.g., 2^13 brackets), prefer exact solutions over simulations |
| **Gaussian Processes** | Trajectory modeling with minimal prior assumptions |

## Technologies

**Languages:** Python, JavaScript/TypeScript  
**Libraries:** Pandas, NumPy, Scikit-learn, PyMC, XGBoost, Matplotlib/Seaborn/Plotly  
**Deployment:** Vercel, Google Cloud Run  
**Tools:** Jupyter Notebooks, Next.js, React

---

## Connect

- [LinkedIn](https://www.linkedin.com/in/chinmaykrishna/)
- [X / Twitter](https://x.com/SportsandMath1)
- krishna.chinmay@gmail.com

---

*This repository is a work in progress. New projects and documentation are being added regularly.*
