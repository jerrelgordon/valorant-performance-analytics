# Data Sources & Structure

## Data Sources
The data used in this project comes from my personal Valorant match history, exported from publicly available match-tracking tools and in-game statistics summaries.

The data represents real gameplay sessions and was collected manually rather than through a fully automated pipeline. As a result, the dataset reflects realistic conditions, including occasional inconsistencies and missing values.

This project focuses on analytics and modeling rather than data acquisition automation.

## Data Overview
The dataset contains match-level gameplay data describing individual performance across competitive matches.

The intent is not to sanitize the data excessively, but to work with it in a way that mirrors real-world analytics scenarios.

## Scope of Analysis
The analysis focuses exclusively on my individual performance. Each row in the dataset represents my performance in a single match.

Playing as a duo is treated as contextual information only, allowing performance comparisons across different play conditions. No partner-level metrics are calculated or evaluated.

## Fact Table: Match Performance
The primary fact table stores match-level performance metrics.

**Grain:**  
One row per match played by me.

**Core Fields:**
- `match_id` – Unique identifier for each match
- `match_date` – Date the match was played
- `queue_type` – Solo or Duo
- `map_id` – Reference to map dimension
- `agent_id` – Reference to agent dimension
- `win` – Match outcome (win / loss)
- `kills`
- `deaths`
- `assists`
- `average_combat_score`
- `damage_dealt`
- `headshot_percentage`

## Dimension Tables
To support analysis and filtering, the model uses a small number of descriptive dimension tables:

- **Date** – Enables time-based analysis and trend evaluation
- **Agent** – Provides context around role and playstyle
- **Map** – Supports environment-specific performance analysis

Queue type is stored directly in the fact table due to its low cardinality and purely contextual role.

## Data Quality Considerations
- Some matches may have missing or partial statistics
- Agent and map names may require normalization
- Outliers are preserved unless clearly invalid
- Small sample sizes are flagged during analysis to avoid misleading conclusions

These considerations are intentionally documented rather than hidden to reflect realistic data conditions.
