# LinNet: A Shift-Invariant Transformer Network with Linear Computational Complexity for Side-Channel Analysis

This repository provides the implementation of LinNet, a shift-invariant Transformer network designed for Side-Channel Analysis (SCA).
LinNet achieves linear time and memory complexity with respect to the input length, making it scalable for long traces.

---

## Repository Structure
- **`fast_attention.py`**  — Implementation of the proposed efficient self-attention layer.
- **`normalization.py`**  — Implementation of the layer-centering normalization layer.
- **`transformer.py`** — Definition of the full LinNet model.
- **`train_trans.py`** — Training and evaluation pipeline for LinNet.
- **`data_utils.py`** — Data loading utilities for ASCADf and ASCADr datasets.
- **`data_utils_ches20.py`** — Data loading utilities for the CHES20 dataset.
- **`evaluation_utils.py`** — Functions to compute guessing entropy/mean key rank for ASCAD datasets.
- **`evaluation_utils_ches20.py`** — Functions to compute guessing entropy/mean key rank for CHES20 dataset.
- **`run_trans_\<dataset\>.sh`**  — Bash scripts with recommended hyperparameters for:
    - **ASCADf** ([ASCAD fixed key](https://github.com/ANSSI-FR/ASCAD/tree/master/ATMEGA_AES_v1/ATM_AES_v1_fixed_key))
    - **ASCADr** ([ASCAD random key](https://github.com/ANSSI-FR/ASCAD/tree/master/ATMEGA_AES_v1/ATM_AES_v1_variable_key))
    - **CHES20** ([CHES CTF 2020](https://ctf.spook.dev/))

---

## Data Pre-processing:
- **CHES CTF 2020 dataset:** Traces are scaled by multiplying with `0.004` to keep feature values within the range **[-120, 120]**.  

---

## Tested on
- Python 3.8.10  
- absl-py == 2.3.1 
- numpy == 1.24.3
- scipy == 1.10.1
- h5py == 3.11.0
- tensorflow == 2.13.0

---

## Getting Started

1. **Clone the repository:**
   ```bash
   git clone https://github.com/suvadeep-iitb/LinNet.git
   cd LinNet
   ```
2. **Install dependencies (Python >= 3.8 recommended):**
   ```bash
   pip install -r requirements.txt
   ```
3. **Set dataset path in the bash script:**
   ```
   Open run_trans_\<dataset\>.sh and set the dataset path variable properly.
   ```
4. Train LinNet:
   ```bash
   bash run_script_\<dataset\>.sh train
   ```
5. Perform Evaluation:
   ```bash
   bash run_script_\<dataset\>.sh test
   ```
----
