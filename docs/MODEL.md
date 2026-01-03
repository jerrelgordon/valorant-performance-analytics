# Data Modeling Approach

## Grain
The grain of the model is one row per match played by me.

## Fact Table
The fact table stores match-level performance metrics such as kills, deaths, ACS, and win/loss outcome.

## Dimensions
- Date: used for time-based analysis and trends
- Agent: provides context around playstyle and role
- Map: enables environment-specific analysis

## Modeling Notes
The model follows a star schema design to support clear filtering, simple DAX, and extensibility as new metrics are added.
