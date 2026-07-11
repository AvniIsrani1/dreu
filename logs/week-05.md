# Week 5

**Dates:** 07-06 to 07-12

## Goals
- Continue building the synthetic quantum reliability dataset
- Expand the circuit set based on related work
- Evaluate how reliability metrics change under different noise types and error rates.
- Explore real IBM hardware execution for selected circuits
- Begin preparing for the machine learning prediction stage.

## Approach and Implementation

This week, I expanded the implementation pipeline for generating and evaluating noisy quantum circuits, with a focus on keeping the benchmark grounded in the literature rather than creating (random) arbitrary circuits.

I tested circuits across different code distances and qubit sizes. For each circuit, I evaluated the behavior under multiple noise types. I also compared several reliability-related metrics. I ran the circuit set on IBM quantum hardware and collected PST results. The hardware results showed the expected trend that circuits with more two-qubit gates tend to have lower PST.

During my meeting with Dr. Asadinia, we discussed the current dataset structure, metrics, and feature set. We also discussed adding larger circuits as a separate robustness or sensitivity analysis, while keeping the main benchmark aligned with circuit sizes from related work. She gave me guidance about important ML models to add for next week's implementation.

## Results
- Expanded the circuit dataset
- Evaluated circuits across different qubit sizes and code distances.
- Updated the error-rate sweep to include smaller, more realistic error probabilities.
- Ran the circuit set on IBM quantum hardware and collected PST results
- Confirmed the planned feature set for the machine learning stage
- Identified strong initial models to try for prediction

## Notes
- Continue adding circuits with more gates and larger qubit sizes for sensitivity analysis.
- Prepare the dataset for machine learning by organizing circuit features, noise features, and reliability labels.
- Begin training baseline ML models.