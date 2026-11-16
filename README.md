# World of Warcraft — Player Progression & Engagement Analysis

### Python | SQL | Pandas | Data Visualization | Game Analytics

## Project Overview

This project analyzes historical World of Warcraft character observations from 2008 to explore character progression, observed activity, and differences across character classes.

The goal is to identify patterns that may inform game design decisions while accounting for differences in starting levels, observation histories, and data quality.

## Dataset

**Source:** [World of Warcraft Avatar History — Kaggle](https://www.kaggle.com/datasets/mylesoneill/warcraft-avatar-history)

- **10,826,734** recorded observations
- **37,354** unique character identifiers
- **Observation period:** January 1 – December 31, 2008
- **Character levels:** 1–80

The dataset includes character identifiers, levels, races, classes, guilds, zones, and observation timestamps.

**Important:** Character identifiers do not necessarily represent unique players, and observations are not complete gameplay session records.

## Business Questions

1. How are characters distributed across levels?
2. How much do characters progress between their first and last observations?
3. How does progression differ across character classes?
4. How frequently are characters observed on multiple days?
5. How do starting levels and observed activity relate to progression?
6. Are the findings sensitive to character-identifier anomalies?

## Tools & Methods

- **Python / Pandas:** Data cleaning, grouping, character-level aggregation, and sensitivity analysis
- **SQLite / SQL:** Character progression and class-level comparisons
- **Matplotlib / Seaborn:** Distribution plots and comparative visualizations
- **Exploratory Data Analysis:** Level distributions, engagement segmentation, and descriptive statistics

## Key Findings

### 1. Character Progression

The average observed level change across 37,354 character identifiers was **5.91 levels**, while the median was **0**.

Approximately **48.2%** of characters showed positive net progression.

### 2. Class-Level Differences

Druids and Paladins had the highest average observed level gains:

| Class | Average Level Gain |
|---|---:|
| Druid | 9.60 |
| Paladin | 9.17 |
| Warlock | 7.34 |
| Hunter | 7.13 |
| Warrior | 2.54 |

These differences are descriptive and do not establish that certain classes level faster.

### 3. Observed Engagement

Approximately **56.47%** of characters were recorded on more than one distinct date.

The median number of observed days was **2**, compared with a mean of **18.51**, indicating a strongly right-skewed distribution of observed activity.

### 4. Engagement and Progression

Characters observed on more distinct days tended to show larger level gains.

Among characters first observed at levels 1–20, those recorded on 21 or more distinct days gained an average of **38.25 levels**, compared with **0.67 levels** among characters recorded on only one day.
Observation duration and progression opportunities differ across segments, so these patterns should not be interpreted as causal relationships.

### 5. Data Quality and Sensitivity Analysis

The analysis identified **101 character identifiers (0.27%)** with negative net level changes.

Some identifiers also displayed inconsistent character attributes, suggesting possible identifier reuse or data collection issues.

Excluding these 101 identifiers increased average observed level gain from **5.91 to 5.97 levels**, while the median remained unchanged.

These results suggest that the main descriptive findings are relatively insensitive to these particular anomalies.

## Business Recommendations

**1. Investigate early-stage character activity**

Many characters were observed only at low levels or on a limited number of dates. Additional telemetry would be needed to determine whether this reflects short observation histories, alternate characters, or engagement challenges.

**2. Compare progression within similar character groups**

Starting level, observation duration, and level-cap constraints should be considered before drawing conclusions about class-specific progression difficulty.

**3. Improve character tracking and data quality**

More reliable character identifiers and complete session-level records would support more accurate engagement and progression metrics.

**4. Use multiple engagement indicators**

Observed activity, progression, and actual player retention should be analyzed separately rather than treated as interchangeable outcomes.

## Limitations

- Historical observations from 2008 may not reflect current game design.
- Unique character identifiers do not necessarily correspond to unique players.
- Recorded observations do not measure exact gameplay duration or conventional retention.
- Some character identifiers show inconsistent levels or character attributes.
- Differences between groups may reflect observation-history and level-cap effects.
- Observational associations do not establish causation.

## Conclusion

The analysis illustrates how character progression and observed activity can vary substantially across a game population.

By combining Python, SQL, segmentation, data visualization, and data-quality sensitivity analysis, the project demonstrates an evidence-based approach to game analytics.

**Key takeaway:** Reliable game analytics requires understanding how data was collected before translating observed behavior into product decisions.
