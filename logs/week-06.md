# Week 6

**Dates:** 07-13 to 07-19

## Goals
- Begin training ML models for quantum reliability prediction.
- Evaluate whether circuit-level and noise-related features can predict reliability labels.
- Compare different reliability labels and metrics, including fidelity and PST.
- Analyze feature importance and identify which circuit properties most strongly affect reliability

## Approach and Implementation

This week, I moved from dataset generation into the ML stage of the project. I organized the dataset using circuit-level features and benchmark-inspired features.

I trained several baseline ML models, including linear regression, random forest, gradient boosting, SVR, MLP, and XGBoost. The models were evaluated for both regression and classification behavior. For regression, I evaluated how well the models predicted reliability scores such as fidelity. For classification, I used a fidelity threshold to label circuits as reliable or unreliable and evaluated classification performance using metrics such as F1, accuracy, and ROC-AUC.

I also tested how sensitive the results were to the selected reliability threshold. Since the initial threshold was chosen as a starting point, I compared performance across multiple threshold values to see whether the classification results changed substantially. In addition, I examined feature importance to understand which features contributed most to the predictions. As expected, two-qubit gate count had a stronger relationship with reliability degradation than single-qubit gate count.

I compared model behavior with and without the identified-most-important feature to make sure the model was not relying only on one engineered input. The results remained strong without that feature, although performance was slightly lower. I also began testing cleaner evaluation settings where related circuit families are removed from training before testing, so the results better reflect generalization to less familiar circuit structures.

During my meeting with Dr. Asadinia, we discussed next steps for making the analysis more realistic and hardware-aware. She recommended adding IBM calibration data so that error rates can vary by gate and device properties rather than being identical across all gates. She also suggested adding swap overhead as a secondary sensitivity analysis, since real IBM hardware does not always allow direct interaction between arbitrary qubits. This would help evaluate how routing and hardware topology affect reliability. Dr. Asadinia also advised me to start drafting the methodology section of our paper. 

## Results
- Trained and compared several baseline models, including random forest, gradient boosting, MLP, and XGBoost.
- Evaluated both regression performance and reliable/unreliable classification performance.
- Found that XGBoost performed best among the tested models.
- Tested classification behavior across different fidelity thresholds.
- Analyzed feature importance and confirmed that two-qubit gate count strongly affects reliability degradation.
- Began evaluating generalization by testing on held-out circuit families.

## Notes
- Add IBM calibration data so error rates better reflect hardware-specific behavior.
- Add swap overhead as a secondary sensitivity or ablation study rather than replacing the current dataset.
- Continue tracking PST because it can be measured on hardware, even though fidelity remains useful for simulation labels.
- Add weighted F1, confusion matrix, and per-class recall for classification evaluation.
- Consider adding mean time to failure as an additional reliability metric.
- Start drafting the proposed method section, including the input features, model configurations, labels, and evaluation setup.