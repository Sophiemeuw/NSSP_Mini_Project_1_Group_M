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

This notebook à REMPLIR APRES QUE FRANCESCO A FINI DE CLEAN LE NOTEBOOK :)

## Part2_Kmeans : 

This notebook applies K-means clustering on the subject fMRI runs, considering one volume as one sample. This is done in order to find relevant activated brain network involved in listening of positive versus negative music.  




