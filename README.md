# Statistical-Analysis-of-School-Shootings-in-the-U.S

## Project Goal
Analyze patterns, predictors, and severity of school shootings in K-12 institutions (1966–2024) to support evidence-based policies that can reduce incident risk and improve school safety outcomes.

## Motivation
U.S. school shootings continue to climb, with 327 incidents in the 2021–22 school year, reflecting an urgent public health and policy challenge. The analysis identifies key risk factors influencing where, when, and how severe these events become.

## Data & Tools

Dataset:	K-12 School Shooting Database (merged Incident + Shooter + Victim + Weapon files)
Cleaned Observations:	718
Engineered Features:	27
Tools:	R, GLM (Poisson & Logistic Regression), ggplot2, dplyr

## Variable Selection Strategy
We applied a purposeful, domain-driven selection approach to ensure the models captured behavioral, situational, and contextual drivers of severity — not just highly correlated noise.
Variables were selected based on:

Policy relevance (e.g., location type, relationship to school)

Behavioral signal strength (e.g., # shots fired, shooter affiliation)

Measurable exposure (e.g., time of day, school level)

Prior research support + expert guidance

High-importance features included:

School type (elementary/middle/high)

Shooter’s relationship to school (student vs adult vs unknown)

Weapon category

Incident setting (inside vs outside)

Duration

State gun law index

Gang involvement indicator

This ensured interpretability and maintained policy applicability of results.

## Feature Engineering
To improve predictive power:
Binned incident duration from timestamps
Consolidated minor categories into informative groups
Created shooter age groups and affiliation indicators
Added legal context using a state gun-law scoring system
Conducted VIF testing to eliminate multicollinearity
These steps produced a more generalizable and stable model.

## Feature Selection

Stepwise AIC selection to optimize model fit

Likelihood ratio testing for predictor significance

α = 0.05 cutoffs for removal

Result: parsimonious, interpretable predictor sets across all models.

## Models Implemented
Model	Technique	Outcome Predicted
#1	Poisson Regression	Victim count (injuries + fatalities)
#2	Logistic Regression	Probability of in-class incident
#3	Logistic Regression	Likelihood of gang-related event
#4	Logistic Regression	Probability of high-casualty attack

## Key Insights (Evidence-Based Outcomes)
### Victim count increases with:

High schools → 2.5× more victims

Drive-by shootings → ~3× more casualties

Indoor setting → significant severity increase


### In-class incidents are:

12× more likely in high schools

16× more likely during morning hours


### Gang-related events correlate with:

Outdoor locations

Weaker gun-regulation states


### Severe high-casualty attacks driven by:

Sustained fire (# shots fired)

Adult perpetrators


## Policy Recommendations
Prioritize morning class-time protections

Increase perimeter monitoring to prevent drive-bys

Expand gang-prevention strategies in high-risk districts

Monitor access to high-capacity firearms for at-risk groups


