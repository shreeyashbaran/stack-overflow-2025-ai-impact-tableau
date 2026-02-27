# Data Dictionary (Key Fields)

This is a simplified dictionary for the engineered fields used in the Tableau dashboard.

## AI constructs
- `AI_IntensityScore`: composite score for AI usage intensity (derived from multiple AI-related survey fields).
- `HighAI`: 1 if respondent is in the top ~20% of AI_IntensityScore, else 0.

## Pay
- `Pay_USD`: annual pay in USD after winsorization (outlier control).
- `LogPay`: natural log of `Pay_USD` (model-friendly scale).

## Outcomes & signals
- `JobSat`: job satisfaction (survey scale).
- `ToolCountWork`: number of tools used at work (proxy for workflow/tool complexity).
- `ToolCountPersonal`: number of tools used personally (proxy).
- `SOFriction`: friction / workflow pain signal (engineered proxy from relevant survey items).
- `AIThreat`: perceived threat/concern signal around AI (engineered proxy).

## Skill breadth
- `NumLangs`: count of programming languages used.
- `NumDBs`: count of databases used.
- `NumClouds`: count of cloud platforms used.
- `SQL_any`: 1 if SQL is used, else 0.
- `BI_any`: 1 if BI tools are used, else 0.

## Cohorts / controls (examples)
- `DevType_bucket`: bucketed developer role.
- `ExpBand`: experience band.
- `OrgSize_clean`: standardized organization size bins.
- `RemoteWork_clean`: standardized remote vs hybrid vs on-site.
- `Country` / `Region`: location fields when available.
- `EdLevel`, `Employment`, `Industry`, `ICorPM`: context controls.

> Note: Exact field names depend on the final engineered dataset produced by Notebook 01.
