# Alzheimers-Disease-Classification
Using Multiview Representation learning for Prediction of the Course of Alzheimer’s Disease

This project proposes to use multi-view representation learning using the bag of featuresbased on the bag of words method for disease and MCI classification using sagittal,coronal,  and  axial  slices  of  MRI  images. The  bag  of  features  method  is  an  adaptationof the bag of words method used in text classification.  In the bag of words method, ahistogram of feature occurrences for each image are created by extracting the keypointsand clustering the features. The histograms are then used to train the classifier.

## Data

The  data  in  this  project  used  was  obtained  from  the  Alzheimer’s  Disease  Neuroimag-ing Initiative (ADNI) and the Minimal Interval Resonance Imaging in Alzheimer’s Disease (MIRIAD) databases. The MRI scans retrieved from ADNI were T1- weighted magnetization-prepared rapid gradient-echo (MP-RAGE). The MRI scans from MIRIAD were T1 weighted inversion recovery prepared fast spoiled gradient recalled (IRPFSG) sequence.

## Architecture

The model is designed to be multi-view in its feature representation and multi modal in its architecture. Thereby, its architecture can be split into four parts. The first component is data cleaning and data augmentation. The second component is feature extraction and the final component is disease classification and MCI classification. 
