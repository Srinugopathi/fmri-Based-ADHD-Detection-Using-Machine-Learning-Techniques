fMRI-Based ADHD Detection Using Machine Learning


Author: Srinu Gopathi
University: Georgia State University
Program: M.S. in Data Science and Analytics

⸻

Project Overview

Attention-Deficit/Hyperactivity Disorder (ADHD) is a neurological condition that can affect attention, behavior, and impulse control. ADHD is usually diagnosed through clinical evaluations, behavioral observations, and a review of medical history. However, studying patterns in brain activity may provide additional information to support this process.

In this project, I explored how machine learning can be used to distinguish between individuals with ADHD and typically developing individuals using functional Magnetic Resonance Imaging (fMRI) data.

The main goal was to identify meaningful differences in brain activity, extract useful features from fMRI scans, and compare different machine learning models to determine which approach performed best.

Instead of feeding the entire brain scan directly into a model, the project focused on selecting informative brain voxels and using statistical features to improve classification.

Dataset

For this project, we used the ADHD-200 dataset, a publicly available neuroimaging dataset that contains resting-state fMRI scans.

Our analysis focused on the New York University (NYU) subset, which includes 263 participants from two groups:

* ADHD: Individuals diagnosed with Attention-Deficit/Hyperactivity Disorder.
* Typically Developing (TD): Individuals without an ADHD diagnosis.

The scans contain Blood Oxygen Level Dependent (BOLD) signals, which provide an indirect measure of changes related to brain activity.

By examining how these signals change over time, we can explore possible differences between the two groups.

Project Methodology

The project was completed in several stages, beginning with brain signal analysis and ending with machine learning model evaluation.

1. Understanding Brain Activity

We began by analyzing the BOLD signals from the fMRI scans.

Each brain scan contains thousands of voxels, and each voxel has a time series that shows how its signal changes over time.

We calculated the standard deviation of each voxel’s time series to measure how much its signal fluctuated.

This allowed us to create a 3D representation of signal variability for each participant.

2. Comparing ADHD and Non-ADHD Brain Patterns

After calculating the standard deviation values, we compared the ADHD and typically developing groups.

We used histograms, density plots, and box plots to examine differences in voxel-level signal variability.

Our analysis showed differences in the distribution of brain signal fluctuations between the two groups.

Some of these differences appeared in areas such as the frontal lobe and thalamus, which have been studied in connection with attention and behavioral regulation.

3. Selecting Important Brain Voxels

One of the main challenges was working with the large number of voxels in each brain scan.

Not every voxel contains useful information for distinguishing ADHD from typical development.

To address this, we tested several percentile thresholds, including the 70th, 80th, 90th, and 98th percentiles.

We also applied Otsu’s thresholding, which automatically selects a threshold based on the distribution of voxel values.

The calculated threshold was approximately 0.199, which corresponded to the 87th percentile in our analysis.

This process helped us focus on the most informative voxels instead of using the entire brain image.

4. Clustering Brain Regions

After selecting the relevant voxels, we used K-means clustering to group them into six clusters.

The goal was to visualize how the selected voxels were distributed across different brain regions.

This helped us examine the spatial patterns of the selected voxels and better understand which areas were highlighted by the analysis.

5. Feature Extraction

We selected 22,404 voxels for further analysis.

From these voxels, we extracted statistical features from the BOLD signal time series.

The main features included:

* Standard deviation: Measures how much the brain signal changes over time.
* Range: Measures the difference between the highest and lowest signal values.
* Median: Represents the middle value of the signal distribution.

These features converted the complex brain imaging data into a format that could be used for machine learning.

6. Machine Learning Models

We evaluated three supervised machine learning algorithms:

Random Forest

An ensemble model that combines multiple decision trees to make predictions.

Support Vector Machine (SVM)

A classification algorithm that finds a decision boundary between different groups.

XGBoost

A gradient-boosting algorithm that builds a sequence of decision trees to improve prediction performance.

We trained and evaluated these models using different feature representations to determine which approach worked best.

7. Dimensionality Reduction Using PCA

Working with 22,404 features created a high-dimensional machine learning problem.

To reduce the number of features, we applied Principal Component Analysis (PCA).

PCA transformed the original features into a smaller set of components while preserving 95% of the variance.

For the standard deviation features, PCA reduced the dimensionality from 22,404 features to 135 components.

For the range features, it reduced the dimensionality to 129 components.

We then compared model performance before and after applying PCA.

Model Results

We evaluated model performance using accuracy, precision, recall, and F1 score.

The following table summarizes the results of the models trained on PCA-transformed standard deviation features.

Model	Accuracy	Precision	Recall	F1 Score
Random Forest + PCA	65.6%	67.4%	80.6%	73.4%
SVM + PCA	77.1%	80.6%	80.6%	80.6%
XGBoost + PCA	67.2%	72.2%	72.2%	72.2%

Best Performing Model: SVM with PCA

Among the approaches we tested, the Support Vector Machine trained on PCA-transformed standard deviation features achieved the best overall performance.

Final Results:

* Accuracy: 77.1%
* Precision: 80.6%
* Recall: 80.6%
* F1 Score: 80.6%

These results suggest that combining statistical features from fMRI data with dimensionality reduction can help identify patterns associated with ADHD.

Key Findings

Several important observations emerged from this project.

First, BOLD signal variability provided useful information for distinguishing participants with ADHD from typically developing participants.

Second, selecting relevant voxels allowed us to focus on potentially meaningful brain regions instead of treating every voxel equally.

Third, PCA greatly reduced the number of features while preserving most of the variation in the original dataset.

Finally, the SVM performed especially well when it was combined with PCA-transformed standard deviation features.

One important finding was that PCA did not improve the performance of every model. Its impact depended on both the selected features and the machine learning algorithm.

This showed the importance of testing multiple approaches rather than assuming that one technique will work best in every situation.

Technologies Used

Programming Language: Python

Machine Learning:

* Scikit-learn
* Random Forest
* Support Vector Machine
* XGBoost
* K-means Clustering
* Principal Component Analysis (PCA)

Data Analysis and Visualization:

* NumPy
* Pandas
* Matplotlib
* Statistical Feature Extraction
* Otsu Thresholding

Domain:

* Functional Magnetic Resonance Imaging (fMRI)
* BOLD Signal Analysis
* Neuroimaging
* ADHD Classification

Challenges and Learning Experience

One of the biggest challenges was working with high-dimensional fMRI data.

Each scan contains a large amount of information, but not all of it is equally useful for classification.

Finding informative voxels, selecting an appropriate threshold, and choosing useful statistical features required several rounds of experimentation.

Another challenge was understanding how different models responded to dimensionality reduction.

Some models performed better after PCA was applied, while others performed worse.

This project gave me practical experience with complex datasets, feature extraction, machine learning algorithms, and model evaluation.

More importantly, it showed me that building a machine learning solution involves much more than training a model. Data preparation, feature selection, experimentation, and interpreting the results are all equally important.

Limitations and Future Improvements

Although the project produced encouraging results, there are several areas that could be improved.

The analysis used only the NYU subset of the ADHD-200 dataset. Testing the models on other datasets and imaging sites would help determine how well they generalize.

Future improvements could include:

* Evaluating deep learning approaches such as CNNs.
* Exploring additional brain connectivity features.
* Testing the models on larger and more diverse neuroimaging datasets.
* Improving feature selection and hyperparameter tuning.
* Applying cross-site validation to evaluate model reliability.

It is also important to note that this project is a research-based classification study and is not intended to replace a professional clinical diagnosis.

Conclusion

This project explored how machine learning can be applied to functional brain imaging data to identify patterns associated with ADHD.

By combining voxel-level statistical analysis, automated thresholding, feature extraction, PCA, and classification algorithms, we developed and evaluated several approaches to ADHD classification.

The strongest results came from an SVM model trained on PCA-transformed standard deviation features, achieving 77.1% accuracy and an 80.6% F1 score.

Overall, this project shows how data science and machine learning can be used to study complex neuroimaging data and support research into neurological conditions.

References

1. Kim, B., et al. (2021). Finding essential parts of the brain in rs-fMRI can improve diagnosing ADHD by Deep Learning.
2. Nash, C., Nair, R., & Naqvi, S. M. (2022). Machine Learning and ADHD Mental Health Detection – A Short Survey.
3. Ashraf, I., et al. (2024). A systematic literature review of neuroimaging coupled with machine learning approaches for diagnosis of attention deficit hyperactivity disorder. Journal of Big Data.
4. Cao, M., et al. (2023). Machine learning in attention-deficit/hyperactivity disorder: New approaches toward understanding the neural mechanisms.
5. Zhang-James, Y., et al. (2023). Machine Learning and MRI-based Diagnostic Models for ADHD: Are We There Yet?

⸻

Author

Srinu Gopathi
Master of Science in Data Science and Analytics
Georgia State University

Research Interests: Machine Learning | Artificial Intelligence | Data Science | Neuroimaging | Healthcare Analytics
