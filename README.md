# Proto-Moleculo
* This is the repository containing the end-to-end training and inference notebook for predicting the binding affinity of small molecules to specific protein targets.

## Pre-Processing
* Pre-processing involves encoding of molecule smiles using a set vocabulary map.
* The entire process is parallelized using joblib library and the encoded smiles are stored for later usage.

## Modelling
* The model used is a stack of 1D CNN layers over an the encoded smiles passed through an encoder layer.
* The output of the 1D CNN stack is passed through a stack of dense layers with the final output being the three classes of protiens required.

## Training
Following are the training settings used:
- Optimizer : Adam
- Metric : AUC Curve for average precision (AP)
- Stratified K-Fold
- Scheduler : Reduce LR on Plateau 
