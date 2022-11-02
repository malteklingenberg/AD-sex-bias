# Higher performance for females than males in MRI-based Alzheimer's disease detection

**Malte Klingenberg, Didem Stark, Fabian Eitel, Mohamad Habes, and Kerstin Ritter**

**Preprint:** https://www.researchsquare.com/article/rs-1964110

### Abstract

**Introduction:**
Although machine learning classifiers have been frequently used to detect Alzheimer's disease (AD) based on structural brain MRI data, potential bias with respect to sex and age have not yet been addressed. Here, we examine a state-of-the-art AD classifier for potential sex and age bias even in the case of balanced training data.

**Methods:**
Based on an age- and sex-balanced cohort of 432 subjects (306 healthy controls, 126 subjects with AD) extracted from the ADNI data base, we trained a convolutional neural network to detect AD in MRI brain scans and performed ten different random training-validation-test splits to increase robustness of the results. Classifier decisions for single subjects were explained using layer-wise relevance propagation.

**Results:**
The classifier performed significantly better for female subjects (balanced accuracy $87.58\pm1.14$%) than for male subjects (balanced accuracy $79.05\pm1.27$%). No significant differences were found in clinical AD scores, ruling out a disparity in disease severity as a cause for the performance difference. Analysis of the explanations revealed a larger variance in regional brain areas for male subjects compared to female subjects.

**Discussion:**
The identified sex differences cannot be attributed to an imbalanced training dataset, and therefore points to the importance of examining and reporting classifier performance across population subgroups to increase transparency and algorithmic fairness.



## Code structure
To reproduce our results, follow the Jupyter Notebooks in order:
- `0_identify_converters_cn_to_mci_or_ad` identifies subjects which entered the ADNI study as healthy, but at a later visit received a diagnosis of MCI or AD
- `1_create_dataset_splits_stratified` balances the study population for sex and age and then creates the train-val-test splits using stratified sampling
- `2_train_models_multiGPU` contains the code for training the model described in the paper on the balanced splits
- `3_raw_predictions` saves the raw predictions (i.e. the AD class score) for all trained models on their respective test sets
- `4_calculate_LRP_heatmaps` generates the LRP heatmaps for all trained models on all subjects of their respective test sets
- `5_average_heatmaps` calculates the average heatmaps for male/female AD/HC subjects across all trained models
- `6_plot_heatmap_comparisons` creates the heatmap comparison plots from the paper (Figures 4 and 5)



## Image IDs
To ensure reproducibility, we provide a full list of the ADNI Image UIDs of our dataset splits in the file `imageuids.csv`. The file contains a column `SPLIT` ranging from 0 to 9, and a column `DATASET`, which has the values `train`, `val`, and `test` for each of the ten splits. The subject ID, group, sex, age, and visit code are also given for ease of use.



## Attributions

The code written for this study is based on and uses code created by Moritz Böhle, Fabian Eitel, Martin Weygandt, and Kerstin Ritter for their paper "Layer-wise relevance propagation for explaining deep neural network decisions in MRI-based Alzheimer’s disease classification" (https://doi.org/10.3389/fnagi.2019.00194, https://github.com/moboehle/Pytorch-LRP). If you use code from this repository, please cite both their paper and ours.
