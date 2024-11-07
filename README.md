# NSSP_Mini_Project_1_Group_M

For this project we used a dataset of participants that listened to positive versus negative emotional musical and nonemotional - nonmusical stimuli during fMRI scanning. 
Our goal was to determine which brain region is activated according to the stimuli mentioned before. For simplicity we focused only on the control subject number 1. We preprocessed the anatomical and functional data in order to do a kMeans analysis and find relevant brain networks. 

## Part1_1_img_preprocessing : 
In the notebook "part1_1_img_preprocessing.ipynb" we load and preprocessed all the anatomical and functional data : 
  - The anatomical one were preprocess using  FSL's fsl\_anat tool to perform all essential steps for T1-weighted MRI data.
  - For the functional one, each BOLD files were motion corrected. Each run were normalized, and the concatenated into a           single continuous time series. Then a Gaussian smoothing with a 6 mm full-width at half-maximum (FWHM) is applied on           concatenated data.
  - The mean intensity of voxels after normalization was analized, we and identified 2 volumes in Run 2 with aberrant intensities which we decided to delete
  - The FD displacement was studied, and this allowed us to identify two additional problematic volumes corresponding to the timeframes of transitions betweens runs.

For the GLM only the fMRI data without removing the problematic volumes to prevent shifts in the design matrix is used.
For the KMeans clustering, the functional data without 'abnormal' volumes is used.

## Part1_1_tsv_files_preprocessing : 

This notebook concatenated each events files of each runs. 

## Part1_2_GLM_AAL : 

In the notebook "part1_2_GLM_AAL.ipynb", we focus on analyzing brain region activations using a General Linear Model (GLM) approach, paired with the AAL (Automated Anatomical Labeling) atlas to identify specific brain regions.

This notebook performs the following steps:

- **GLM Analysis**: We apply a GLM to model brain activity in response to positive versus negative musical stimuli. The design matrix incorporates drift and motion regressors to improve accuracy, and contrasts are computed to compare responses to the different stimuli.
  
- **Region-Based Mapping with AAL Atlas**: The AAL atlas is used to locate and analyze specific brain regions of interest (e.g., Vermis and Olfactory regions). By mapping GLM-derived activation data onto these regions, we can visualize the intensity of responses to the experimental conditions.

- **Visualization**: We create detailed visualizations of the contrast maps and highlighted regions, with a color-coded intensity scale to represent varying levels of activation.

This notebook allows us to identify specific regions involved in emotional processing during musical stimuli and forms part of our broader analysis of control subject number 1's brain activity.

## Part2_Kmeans : 

This notebook applies K-means clustering on the subject fMRI runs, considering one volume as one sample. This is done in order to find relevant activated brain network involved in listening of positive versus negative music.  




