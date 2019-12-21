
# Prediction of peptide and HLA binding-interaction
This repository allows for the training of three different models that all attempts to predict whether a particular peptide is likely to bind to a given HLA allele. The models constitutes of a random forest(Sci-kit learn), simple ANN (Keras) and a deep convolutional neural network(PyTorch). Repository also contains the approx 300 MB of training and test data. The dataset used for the evaluation of the prediction methods comes from [1]. It consists of relative binding affinity
measurements of 35 alleles of MHC class I. The target value of the binding affinity is rescaled between 0 and 1, applying
the equation 1 − log(a)/log(50.000) , to the measured IC50 affinity value in nM [3]. When discretizing the target values
for AUC analysis, a threshold of 500nM was used as the reference value; IC50 < 500nM is classified as a binder,
IC50 >= 500nM is a non-binder [1]. Preparation of the input was done by blosum encoding the sequences using the
blosum 50 matrix. 

Authors of this repository: Mikkel Vind Lorenz, Jonas Sindlinger, Oleksandr Maksimov

# HOW TO RUN
Download repository and run main.py located in the src folder

# PERFORMANCE MEASURES:
AUC and PCC

# CROSS VALIDATION:
In the data used in this work 5 k-fold cross validation splits was already prepared, each with one training and one corresponding test
set. All models were trained independently on one of these sets and validated on the corresponding test set, such that in
the end for each algorithm, five models were trained on each dataset. From the resulting model, the highest scoring one
validated with AUC and PCC on the test set was chosen as the model that generalizes the best.

# LIBRARY REQUIREMENTS:
Seaborn,
PyTorch,
Keras,
Scipy stats,
Pandas,
Matplotlib

# LITTERATURE & DATA SOURCES
[1]Trolle T, Metushi IG, Greenbaum JA, et al. Automated benchmarking of peptide-MHC class I binding predictions. Bioinfor-
matics (Oxford, England) 2015;31:2174–2181.
