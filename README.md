# Alzheimers-Disease-Classification
Using Multiview Representation learning for Prediction of the Course of Alzheimer’s Disease

This project proposes to use multi-view representation learning using the bag of features based on the bag of words method for disease and Mild Cognitive Impairment (MCI) classification using sagittal, coronal and axial slices of MRI  images. The bag of features method is an adaptation of the bag of words method used in text classification.  In the bag of words method, ahistogram of feature occurrences for each image are created by extracting the keypointsand clustering the features. The histograms are then used to train the classifier.

## Data

The  data  in  this  project  used  was  obtained  from  the  Alzheimer’s  Disease  Neuroimag-ing Initiative (ADNI) and the Minimal Interval Resonance Imaging in Alzheimer’s Disease (MIRIAD) databases. The MRI scans retrieved from ADNI were T1- weighted magnetization-prepared rapid gradient-echo (MP-RAGE). The MRI scans from MIRIAD were T1 weighted inversion recovery prepared fast spoiled gradient recalled (IRPFSG) sequence.


## Architecture

The model is designed to be multi-view in its feature representation and multi modal in its architecture. Thereby, its architecture can be split into four parts. The first component is data cleaning and data augmentation. The second component is feature extraction and the final component is disease classification and MCI classification. 

## Preprocessing

To clean the data, deepbrain python library was used to strip the non-brain elements. The MRI images were skull stripped using a custom U-Net trained on multiple datasets including the ADNI dataset. To use the deepbrain library, you would be required to replace the extractor.py file by the version attached. 
The MRI images are stored in the form.nii or .nii.gz or as a dicom file. To retrieve a representative slice of the sagittal, coronal, and axial planes, the nibabel library was used to obtain the 3D volume of the images and the slices were manually extracted. MRI images use the anatomical coordinate system to define the planes that describe the anatomical system of a human. The planes are defined as the sagittal, coronal, and axial planes. The sagittal plane/ y-z plane separates left from right, the coronal plane or x-z plane separates the anterior from the posterior / front from the back and the axial plane or x-y-z plane separates the head from the feet. This can be seen in Figure 3.2. The MRI images from the dataset were extracted as 3D volumes in the form of [x,y,z] as the distances from the y-z plane/ anterior from the posterior, x-z plane/left from right and x-y plane/ head from feet respectively. 
Oversampling using data augmentation was performed on the CN category of the MIRIAD dataset increasing the number of subjects. The ADNI and MIRIAD data were combined to train the model on MRI images captured under different conditions. 

## Feature Extraction 
For feature extraction, the Scale Invariant Feature Transform (SIFT) algorithm was used to extract features. The k- means clustering algorithm was used to cluster the keypoints to determine similar features in each view of the MRI scans. After clustering each view, they were combined to form a single feature vector representation of that subject.

## Disease Classification

For disease classification (classification of Alzheimer's disease, Cognitively Normal and Mild Cognitive Impairment), Logistic Regression, Support Vector Machine, Decision Trees, Random Forest were used.

## MCI Classification

For MCI classification (classification of LMCI and EMCI), Support Vector Machines were used.

## How to run the program

Firstly, you would need to request the datasets from the organizations mentioned above. You are required to execute the preprocessng (see above for description) file on all the data. Using an online storage space or server is suggested as the files are quite large. Finally, you can run the project file. 

## References
I. Itzcovich, “deepbrain 0.1,” Accessed on 25 Apr 2021. [Online]. Available:
https://pypi.org/project/deepbrain/

https://nipy.org/nibabel/

## Assets
P. S. Aisen and et al, “Clinical core of the alzheimer’s disease neuroimaging initiative: progress and plans.”,” Alzheimer’s dementia : the journal of the Alzheimer’s
Association, vol. 6, pp. 239–246, 2010.
http://adni.loni.usc.edu/

I. B. Malone and et al., “Miriad–public release of a multiple time point alzheimer’s
mr imaging dataset,” NeuroImage, vol. 70, pp. 33–36, 2013.
https://www.ucl.ac.uk/drc/research/research-methods/minimal-interval-resonance-imaging-alzheimers-disease-miriad
