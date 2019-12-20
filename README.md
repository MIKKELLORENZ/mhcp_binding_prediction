
# Prediction of peptide and HLA binding-interaction
This repository allows for the training of three different models to predict whether a particular peptide is likely to bind to a given HLA allele. The models constitutes of a random forest(Sci-kit), simple ANN (Keras) and a deep convolutional neural network(PyTorch). Repository also contains the approx 300 MB of training and test data. The dataset used for the evaluation of the prediction methods comes from [1]. It consists of relative binding affinity
measurements of 35 alleles of MHC class I. The target value of the binding affinity is rescaled between 0 and 1, applying
the equation 1 − log(a)/log(50.000) , to the measured IC50 affinity value in nM [3]. When discretizing the target values
for AUC analysis, a threshold of 500nM was used as the reference value; IC50 < 500nM is classified as a binder,
IC50 >= 500nM is a non-binder [1]. Preparation of the input was done by blosum encoding the sequences using the
blosum 50 matrix. These functions, in essence, give prior knowledge regarding the substitution preferences for the
models to enhance learning.

# HOW TO RUN
Download repository and run main.py located in 

# PERFORMANCE MEASURE:
AUC and PCC

# CROSS VALIDATION:
Cross Validation
To find the optimal performance of a model trained on a dataset, cross validation is a means to do that. The data is split
into separate training and test sets, where the training set has no overlap with the test set and the amount of these
splits is called the fold of cross validation, i.e. in k-fold cross validation with k=5, one refers to as 5-fold cross validation.
In the data used in this work, five such splits were already prepared, each with one training and one corresponding test
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

# LITTERATURE & SOURCES
[1]Trolle T, Metushi IG, Greenbaum JA, et al. Automated benchmarking of peptide-MHC class I binding predictions. Bioinfor-
matics (Oxford, England) 2015;31:2174–2181.
