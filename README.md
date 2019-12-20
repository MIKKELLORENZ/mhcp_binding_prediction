# Prediction of peptide and HLA binding-interaction
This repository allows for the training of three different models to predict whether a particular peptide is likely to bind to a given HLA allele. The models constitutes of a random forest, simple artificial neural network and a deep convolutional neural network. Repository also contains the approx 300 MB of training and test data. The dataset used for the evaluation of the prediction methods comes from [1]. It consists of relative binding affinity
measurements of 35 alleles of MHC class I. The target value of the binding affinity is rescaled between 0 and 1, applying
the equation 1 − log(a)/log(50.000) , to the measured IC50 affinity value in nM [3]. When discretizing the target values
for AUC analysis, a threshold of 500nM was used as the reference value; IC50 < 500nM is classified as a binder,
IC50 >= 500nM is a non-binder [1]. Preparation of the input was done by blosum encoding the sequences using the
blosum 50 matrix. These functions, in essence, give prior knowledge regarding the substitution preferences for the
models to enhance learning.

[1]Trolle T, Metushi IG, Greenbaum JA, et al. Automated benchmarking of peptide-MHC class I binding predictions. Bioinfor-
matics (Oxford, England) 2015;31:2174–2181.
