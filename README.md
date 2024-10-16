# LinNet: A Shift-Invariant Transformer Network with Linear Computational Complexity for Side Channel Analysis

This repository contains the implementation of LinNet, a shift invariant transformer network for Side Channel Analysis. LinNet has linear time 
and memory complexity with respect to input length.

The implementation is composed of the following files:
* **fast_attention.py:** It contains the code of the proposed self-attention layer.
* **normalization.py:** It contains the code of layer-centering layer.
* **transformer.py:** It contains the code of LinNet model.
* **train_trans.py** It contains the code for training and evaluating the LinNet model.
* **data_utils.py:** It contains the code for reading data from the ASCADf or ASCADr dataset.
* **data_utils_ches20.py:** It contains the code for reading data from the CHES20 dataset.
* **evaluation_utils.py:** It contains the code for computing the guessing entropy for the ASCAD datasets.
* **evaluation_utils_ches20.py:** It contains the code for computing the guessing entropy for the CHES20 dataset.
* **run_trans_\<dataset\>.sh:** It is the bash script with proper hyper-parameter setting to perform experiments 
on dataset \<dataset\> where \<dataset\> is one of ASCADf ([ASCAD fixed key](https://github.com/ANSSI-FR/ASCAD/tree/master/ATMEGA\_AES\_v1/ATM\_AES\_v1\_fixed\_key)), ASCADr ([ASCAD random key](https://github.com/ANSSI-FR/ASCAD/tree/master/ATMEGA\_AES\_v1/ATM\_AES\_v1\_variable\_key)) and CHES20 ([CHES CTF 2020](https://ctf.spook.dev/)).

## Data Pre-processing:
* The traces of the CHES CTF 2020 dataset have been multiplied by the constant 0.004 to keep the range of the feature values within [-120, 120].
