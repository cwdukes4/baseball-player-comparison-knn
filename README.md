# Baseball Transfer Portal Player Projection Using KNN

## Project Overview

This project identifies comparable hitters' profiles based on offensive performance metrics using a K-Nearest Neighbors (kNN) Model. The original application was designed to compare incoming transfer portal players with Clemson Baseball players from previous seasons, providing additional statistical context for roster construction and player evaluation.

The model standardizes selected traditional and advanced hitting metrics and uses Euclidean distance to identify players with similar statistical profiles.

This public version uses entirely synthetic data to demonstrate the methodology without exposing proprietary player information.

## Methodology

### 1. Selecting the Comparison Pool

The original model used Clemson Baseball player data dating back to the 2022 season, with a minimum of 150 plate appearances per player-season to reduce the influence of limited sample sizes.

### 2. Selecting Key Performance Indicators

The initial feature set included xwOBA, in-zone swing rate, chase rate, zone contact rate, EV90, ICR, line-drive rate, and fly-ball rate.

### 3. Building the Initial Model

Collin Priest's 2024 Michigan season was used in the original analysis as an example input representing an incoming transfer player. The initial model identified the three closest player comparisons.

### 4. Refining the Model

The initial results did not consistently identify the player types expected from a baseball perspective, particularly regarding power production. I refined the KPI selection to provide a more complete view of offensive performance.

The final KPI set included:

- SLG
- OBP
- ISO
- wOBA
- ZSwing%
- Chase%
- ZContact%
- EV90
- GB%
- Barrel%
- Strikeout%
- Walk%

### 5. Identifying Comparable Players

The model uses `StandardScaler` to standardize the selected metrics and `NearestNeighbors` from scikit-learn to identify players with the smallest Euclidean distances from the input player.

The notebook displays the nearest player comparisons, their distances, and their offensive statistics.

### 6. Visualizing the Results

Visualizations compare the target player with the identified comps across selected offensive metrics, making it easier to interpret similarities and differences in production.

## Tools and Technologies

- Python
- pandas
- NumPy
- scikit-learn
- Matplotlib
- Jupyter Notebook

## Potential Future Improvements

- Test alternative KPI combinations and values of K.
- Evaluate alternative distance metrics.
- Assess how well identified comps provide context for subsequent player performance.
- Explore additional player characteristics when suitable data is available.

## Data Disclaimer

The dataset included in this repository is entirely synthetic and does not represent actual Clemson Baseball player statistics. The public notebook demonstrates the analytical workflow and is not intended to reproduce the original model's results.

The model identifies statistical similarities, not guaranteed future performance. Results should be interpreted alongside scouting evaluation and baseball context.
