# Higher performance for females than males in MRI-based Alzheimer's disease detection

**Malte Klingenberg, Didem Stark, Fabian Eitel, and Kerstin Ritter**

### Abstract

**Introduction:**
Although machine learning classifiers have been frequently used to detect Alzheimer's disease (AD) based on structural brain MRI data, potential bias with respect to sex and age have not yet been addressed. Here, we examine a state-of-the-art AD classifier for potential sex and age bias even in the case of balanced training data.

**Methods:**
Based on an age- and sex-balanced cohort of 432 subjects (306 healthy controls, 126 subjects with AD) extracted from the ADNI data base, we trained a convolutional neural network to detect AD in MRI brain scans and performed ten different random training-validation-test splits to increase robustness of the results. Classifier decisions for single subjects were explained using layer-wise relevance propagation.

**Results:**
The classifier performed significantly better for female subjects (balanced accuracy $87.58\pm1.14$%) than for male subjects ($79.05\pm1.27$%). No significant differences were found in clinical AD scores, ruling out a disparity in disease severity as a cause for the performance difference. Analysis of the explanations revealed a larger variance in regional brain areas for male subjects compared to female subjects.

**Discussion:**
The identified sex differences cannot be attributed to an imbalanced training dataset, and therefore points to the importance of examining and reporting classifier performance across population subgroups to increase transparency and algorithmic fairness.
