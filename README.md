🧠 fMRI-Based ADHD Detection Using Machine Learning

Author: Srinu Gopathi
University: Georgia State University
Program: M.S. in Data Science and Analytics

⸻

📌 Project Overview

Attention-Deficit/Hyperactivity Disorder (ADHD) is a neurodevelopmental condition that affects attention, behavior, and impulse control. ADHD is typically diagnosed through clinical evaluations, behavioral observations, and medical history. However, analyzing brain activity may provide additional insights to support clinical assessments.

In this project, we explored how machine learning can identify ADHD-related patterns using functional Magnetic Resonance Imaging (fMRI) data.

Our goal was to analyze differences in brain activity between individuals with ADHD and typically developing individuals, extract meaningful features, and evaluate multiple machine learning algorithms.

Rather than using entire brain scans directly, we focused on voxel-level statistical analysis, feature selection, and dimensionality reduction to build classification models.

📊 Dataset

We used the publicly available ADHD-200 dataset, focusing on the New York University (NYU) subset, which includes 263 participants.

The dataset contains two groups:

* ADHD: Participants diagnosed with Attention-Deficit/Hyperactivity Disorder.
* Typically Developing (TD): Participants without an ADHD diagnosis.

The resting-state fMRI scans contain Blood Oxygen Level Dependent (BOLD) signals, which indirectly reflect changes associated with brain activity.

We analyzed variations in these signals to identify patterns that could help distinguish the two groups.

🔬 Methodology

Our project followed a structured machine learning workflow:

fMRI Data → Voxel Analysis → Feature Selection → Feature Extraction → PCA → Machine Learning → Evaluation

1. Voxel-Level Brain Activity Analysis

We calculated the standard deviation (SD) of each voxel’s BOLD signal over time.

This produced a 3D representation of signal variability for each participant, allowing us to examine differences between ADHD and typically developing groups.

2. Brain Pattern Comparison

We compared voxel-level signal variability using:

* Histograms
* Box plots
* Density plots
* 3D brain visualizations

Our analysis highlighted differences in signal variability across brain regions, including areas such as the frontal lobe and thalamus.

3. Voxel Selection Using Otsu’s Thresholding

To reduce unnecessary information, we experimented with percentile-based thresholds and applied Otsu’s thresholding to select relevant voxels.

The calculated threshold was approximately 0.199, corresponding to the 87th percentile in our analysis.

This helped identify regions with potentially useful information for classification.

4. K-Means Clustering

We applied K-means clustering to organize selected voxels into six clusters.

This helped us visualize spatial patterns and examine how the selected voxels were distributed across different regions of the brain.

5. Feature Extraction

We selected 22,404 voxels and extracted statistical information from their BOLD signal time series.

The main features were:

* Standard Deviation: Measures signal variability over time.
* Range: Difference between maximum and minimum signal values.
* Median: Middle value of the signal distribution.

These features were used to train our machine learning models.

6. Machine Learning Models

We evaluated three classification algorithms:

* Random Forest: An ensemble learning algorithm that combines multiple decision trees.
* Support Vector Machine (SVM): Finds a decision boundary that separates classes.
* XGBoost: A gradient-boosting algorithm that combines sequential decision trees.

We compared their performance using different feature sets.

7. Dimensionality Reduction Using PCA

Since the dataset contained thousands of features, we applied Principal Component Analysis (PCA) to reduce dimensionality while retaining 95% of the original variance.

Feature Type	Original Features	After PCA
Standard Deviation	22,404	135
Range	22,404	129

We then evaluated how PCA affected the performance of each machine learning model.

📈 Model Performance

The following results were obtained using PCA-transformed standard deviation features.

Model	Accuracy	Precision	Recall	F1 Score
Random Forest + PCA	65.6%	67.4%	80.6%	73.4%
SVM + PCA	77.1%	80.6%	80.6%	80.6%
XGBoost + PCA	67.2%	72.2%	72.2%	72.2%

🏆 Best Performing Model

The Support Vector Machine (SVM) with PCA-transformed standard deviation features achieved the strongest overall performance.

Key Results:

* Accuracy: 77.1%
* Precision: 80.6%
* Recall: 80.6%
* F1 Score: 80.6%

These results demonstrate that combining voxel-level statistical features with PCA can provide useful information for machine learning-based ADHD classification.

💡 Key Findings

Our experiments led to several important observations:

1. BOLD signal variability provided useful features for distinguishing ADHD and typically developing participants.
2. Voxel selection helped us focus on potentially informative regions instead of treating every voxel equally.
3. PCA significantly reduced dimensionality while preserving most of the original variance.
4. SVM with PCA-transformed SD features achieved the best overall classification performance.
5. PCA did not improve every model, showing that dimensionality reduction needs to be evaluated alongside model selection.

🛠️ Technologies Used

Category	Technologies
Programming	Python
Machine Learning	Scikit-learn, Random Forest, SVM, XGBoost
Feature Engineering	Standard Deviation, Range, Median
Dimensionality Reduction	PCA
Clustering	K-Means
Image Processing	Otsu’s Thresholding
Data Analysis	NumPy, Pandas
Visualization	Matplotlib
Domain	fMRI, BOLD Signal Analysis, Neuroimaging

🎯 Challenges and Learning Experience

One of the main challenges was working with high-dimensional fMRI data, where each brain scan contains thousands of voxels.

Selecting useful features and identifying meaningful signal variations required experimenting with different statistical methods and thresholding techniques.

Another important challenge was understanding how machine learning models responded to dimensionality reduction. While PCA improved some results, it reduced the performance of others.

Through this project, I gained practical experience in neuroimaging data analysis, feature engineering, dimensionality reduction, machine learning, and model evaluation.

The project reinforced the importance of understanding the data and experimenting with different approaches rather than focusing only on model accuracy.


✅ Conclusion

This project explored the use of machine learning to identify ADHD-related patterns from resting-state fMRI data.

By combining voxel-level signal analysis, Otsu’s thresholding, feature extraction, PCA, and classification algorithms, we evaluated different approaches to distinguishing individuals with ADHD from typically developing individuals.

Our best-performing approach was SVM with PCA-transformed standard deviation features, achieving 77.1% accuracy and an 80.6% F1 score.

The results highlight the potential of statistical feature engineering and machine learning for analyzing complex neuroimaging data.

📚 References

1. Kim, B., et al. (2021). Finding essential parts of the brain in rs-fMRI can improve diagnosing ADHD by Deep Learning.
2. Nash, C., Nair, R., & Naqvi, S. M. (2022). Machine Learning and ADHD Mental Health Detection – A Short Survey.
3. Ashraf, I., et al. (2024). A systematic literature review of neuroimaging coupled with machine learning approaches for diagnosis of attention deficit hyperactivity disorder. Journal of Big Data.
4. Cao, M., et al. (2023). Machine learning in attention-deficit/hyperactivity disorder: New approaches toward understanding the neural mechanisms.
5. Zhang-James, Y., et al. (2023). Machine Learning and MRI-based Diagnostic Models for ADHD: Are We There Yet?

⸻

👨‍💻 Author

Srinu Gopathi
M.S. in Data Science and Analytics
Georgia State University

Research Interests: Machine Learning | Artificial Intelligence | Data Science | Neuroimaging | Healthcare Analytics
