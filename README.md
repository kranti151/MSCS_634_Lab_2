# MSCS 634 – Lab 2: KNN and RNN Classifier Performance

## Purpose

This lab explores the performance of two different nearest neighbor classification algorithms, K-Nearest Neighbors (KNN) and Radius Neighbors Classifier (RNN), on the Wine dataset. The goal is to understand how the choice of parameters (K for KNN and radius for RNN) affects the accuracy of the classifiers.

## Key Insights and Accuracy Trends

*   **KNN Classifier:**
    *   The accuracy of the KNN classifier varied with the value of K.
    *   Higher accuracy was observed at K = 5, 11, 15, and 21.
    *   This suggests that for this dataset, a small number of neighbors (K=1) might be too sensitive to noise, while increasing K helps to smooth the decision boundaries and improve generalization.

*   **RNN Classifier:**
    *   The accuracy of the RNN classifier also varied with the specified radius.
    *   Performance generally decreased as the radius increased.
    *   This indicates that a larger radius might include too many irrelevant samples, negatively impacting the classification accuracy. A smaller radius seems to be more effective for this dataset.

## Challenges and Decisions

*   **Choosing Parameter Values:** Selecting appropriate values for K in KNN and radius in RNN was a key challenge. We explored a range of values for both algorithms to observe the impact on accuracy.
*   **Interpreting Results:** Analyzing the accuracy trends required careful consideration of how each algorithm works and how the parameters influence the decision boundaries.
*   **Data Splitting:** The dataset was split into training and testing sets (80/20 split with stratification) to ensure the models were evaluated on unseen data and to maintain the class distribution in both sets. The `random_state` was set for reproducibility.
*   **Outlier Handling in RNN:** For the Radius Neighbors Classifier, we used the `outlier_label=0` parameter to assign a specific label to samples that have no neighbors within the specified radius.
