# Methodology

This document explains the workflow behind the Tableau portfolio dashboard.

## 1) Data lifecycle (what I did)
1. **Data selection & profiling**
   - Loaded the Stack Overflow 2025 survey and audited missingness / high-cardinality fields.
2. **Cleaning & standardization**
   - Normalized pay to reduce outlier influence (winsorization) and created `LogPay` for modeling.
   - Standardized cohort fields (role buckets, experience bands, org size bins, remote status).
3. **Feature engineering**
   - Built skill breadth measures (language / DB / cloud counts, plus SQL/BI flags).
   - Constructed AI adoption intensity: `AI_IntensityScore`, and a binary segment `HighAI` (top ~20%).
4. **Modeling & sensitivity**
   - Compared outcomes across HighAI vs LowAI (ATE-style comparisons) and by cohorts (CATE slices).
   - Modeled AI adoption drivers using enablement/barrier signals and context controls.
5. **Exports for Tableau**
   - Generated a Tableau-ready flat file + compact lever/ROI tables (and long format versions).

## 2) Research questions
1. AI intensity → pay & productivity proxies  
2. Skill complementarity: which foundations amplify AI impact  
3. Heterogeneity: who benefits (or loses) across cohorts  
4. Barriers to AI ROI: enablement, policy, compute access  
5. Policy simulation: which levers move adoption/outcomes most with manageable friction  

## 3) Key constructs
- **AI_IntensityScore**: composite AI usage score built from survey AI behavior/components.
- **HighAI**: top ~20% of AI_IntensityScore (segment used for comparisons).
- **Pay_USD / LogPay**: pay normalized for stability and modeling.
- **Productivity proxies**: tool usage at work/personal and related workflow measures.

## 4) Interpretation and limitations
This is self-reported, observational survey data. Results should be treated as **associations and directional signals**, not strict causal estimates.
