# Sports and Math Projects

Quantitative projects combining probabilistic modeling, statistical inference, and data visualization. Includes sports analytics (win probability models, ranking systems, playoff simulations), chess AI and analysis tools, and financial modeling.

<details>
<summary>📸 Project Showcase</summary>

![Project Showcase](assets/project_showcase.png)

</details>

## Overview

This repository contains formal documentation and code for selected sports analytics projects. Many originated as visualizations and threads posted to [X](https://x.com/search?q=from%3Asportsandmath1%20Here%27s&f=media) ([no login required](https://xcancel.com/search?q=from%3Asportsandmath1%20Here%27s)).

Projects here emphasize reproducibility, clear methodology, and technical depth.

**Topics:** `python` `data-science` `sports-analytics` `chess` `finance` `statistics` `machine-learning` `bayesian-statistics` `transformers`

---

## 🏈 NFL Playoffs Odds Engine

**[→ Try the Live App](https://nfl-playoff-odds-engine.vercel.app/)** | **[LinkedIn Primer + Video Demo](https://www.linkedin.com/posts/chinmaykrishna_i-built-a-web-app-that-lets-you-play-what-if-activity-7418402538728759296-BUo8/)**

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

## ♟️ ChessLLM

**[→ Play Against the Model](https://chess-llm-316391656470.us-central1.run.app/)** | **[LinkedIn Primer](https://www.linkedin.com/posts/chinmaykrishna_chessllm-what-a-50m-transformer-says-about-activity-7414315796530814976-_FoI)** | **[Full Writeup](https://chinmaysnotebook.substack.com/p/chessllm-what-a-50m-transformer-says)**

A 50M parameter transformer trained to play chess. Play against two variants—Stockfish-trained and Lichess-trained—both performing at ~1600-2000 Lichess level.

**Key Features:**
- Full visibility into probability distributions over moves (key differentiator from traditional bots—LLMs lack entropy)
- Adjustable parameters like temperature
- Analysis Board and LLM vs LLM mode

<details>
<summary>🔮 Future Ideas (v2)</summary>

- Adaptive strength adjustment
- Fine-tuned versions to match specific player styles
- Mechanistic interpretability: visualize "why" it chose each move and "how" it represents board state internally

</details>

---

## ♟️ Chess Game Analyzer

**[→ Try the Live App](https://chess-improvement.vercel.app/)**

*Find your worst collapses and best comebacks.*

Enter a Lichess username to analyze your games using Lichess's Stockfish evaluations. Originally built to replay games before you collapsed—to improve closing out winning positions.

**Key Features:**
- **Worst losses** and **best comebacks** based on win probability swings
- **Most exciting games** ranked by total probability change
- Per-move-phase analysis showing where you win/lose games (opening, middle, endgame)
- Multiple loss functions: Brier score (squared error), Log Loss (cross-entropy), and binary loss (lead changes only)
- Filters by result, color, and time control

<details>
<summary>🔮 Future Ideas</summary>

- Custom win probability model using state-space (Markov) approach
- Incorporate time remaining (critical in bullet), whose turn, rating differentials
- More granular phase breakdowns

</details>

---

## 📈 Stock Historical Analysis

**[→ Try the Live App](https://market-primer.vercel.app/)**

Analyzes stock volatility through the lens of hypothetical leveraged returns (rebalanced daily). Shows optimal leverage multipliers based on Kelly criterion.

**Key Insight:** Stocks like GOOGL, NVDA, MSFT have optimal leverage in the 2-3x range—meaning 1x is conservative. A volatile stock like TSLA (~9% annual returns) has optimal leverage of ~0.75x—you'd be better off holding 25% in cash. If a stock's optimal leverage exceeds 1, you should theoretically take a loan to buy more; if it's below 1, hold cash instead.

<details>
<summary>📊 How It Works</summary>

- Computes geometric mean returns across leverage multipliers
- Optimal leverage corresponds to full Kelly criterion
- Half-Kelly (~75% returns, ~50% risk) means look for stocks with optimal leverage > 2
- Future: add risk-free rate input to properly price hypothetical loans

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
