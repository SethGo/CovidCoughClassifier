# COVID-19 Cough Audio Modeling

1. Multiple cepstral features are extracted from the data.
2. Segmentation for each feature is performed using both Varibale Markov Oracle (VMO) and Kmeans clustering.
3. VMO-derived Information Rate (IR) and Kmeans-derived Inertia (I) are used to assess the viability of features and samples.
4. Recurrence Quantification Analysis is performed to observe non-linear dynamical structure in the data and train a classifier.
5. Logistic Regression, K-Nearest Neighbors, and XGBoost algorithms are used for modeling.

#### Description:
This approach is inspired by (Mouawad 2021) who used Information Rate (IR) as an undersampling criteria for the majority class in their dataset of coughing sounds coming from COVID-19 positive vs negative patients. The same dataset is used for this project and both VMO-derived IR and Kmeans-derived Inertia (I) are used to inform undersampling. The two metrics are also used as a means to assess feature viability. For a comparison of methods, undersampling of the majority class is performed using IR, I, and random selection criteria. 

#### Results:
While IR is found to be the best undersampling criteria, both IR and I outperform random selection, meaning that Kmeans segmentation statistics could be useful for informing undersampling from a majority class in the case of class imbalance. When used to inform feature selction, IR and I failed to highlight the highest peforming features.   

*Mouawad, Pauline, Tammuz Dubnov, and Shlomo Dubnov. "Robust Detection of COVID-19 in Cough Sounds: Using Recurrence Dynamics and Variable Markov Model." Sn Computer Science 2.1 (2021).*
