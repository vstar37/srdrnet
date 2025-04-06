<h1 align="center">Structural Reconstruction and Dual-Prototype Refinement for
Few-Shot 3D Point Cloud Semantic Segmentation</h1>


## News :newspaper:
* **`Mar 11, 2025`:** First release.

## Overview  
This repository provides a PyTorch implementation of **SR-DRNet**, a **Structural Reconstruction Dual-Prototype Refinement Network** for **Few-shot 3D Point Cloud Semantic Segmentation** (FS-PCS). SR-DRNet addresses the challenges of limited annotations and structural integrity loss by introducing **Diffusion Reasoning (DR)** to reconstruct complete 3D structures and restore **Explicit Structure (ES)**. Additionally, **Confidence-Based Logit Refinement (CBLR)** integrates local and global structural prototypes for enhanced segmentation, while **Adversarial Dynamic Adjustment Loss (ADAL)** mitigates prototype conflicts for stable optimization. Extensive experiments on S3DIS and ScanNet benchmarks demonstrate its state-of-the-art performance.

## Usage

### Installation
To use this repository, follow the steps below to set up the environment:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/vstar37/srdrnet.git
   cd srdrnet

2.	**Install the required dependencies:**
    It is recommended to create a virtual environment first, then install the dependencies.
    ```bash
    # PyTorch==2.0.1 is used for faster training with compilation.
    conda create -n sanet python=3.10 -y && conda activate sanet
    pip install -r requirements.txt

3. **Download the datasets:**
   [Download datasets](https://drive.google.com/drive/folders/1ehBdZcQWRVshFxR2u7-E1Uv-fwhkdOiE?usp=drive_link)
    After setting up the environment, you can download the training and test datasets from the provided links. Once downloaded, please unzip the datasets into the data folder under the root directory of the project. The folder structure should look like this:
   ```bash
   srdrnet/
   ├── datasets/
   │   ├── S3DIS/
   │   ├── ScanNet/
   ├── requirements.txt
   └── … (other project files)
4. **Download the weights:**
   [Download weights](https://drive.google.com/drive/folders/1ehBdZcQWRVshFxR2u7-E1Uv-fwhkdOiE?usp=drive_link)
   After downloading the datasets, you will need to download the pretrained weights for the model and the backbone. These weights are required to initialize the model for training and inference.

   - **Model Weights:** The model weights should be placed in the `dataset/COD` directory.
   - **Backbone Weights:** The backbone weights should be placed in the `lib/weights/backbones` directory.

### Run
```shell
# Train & Test & Evaluation
./sub.sh RUN_NAME GPU_NUMBERS_FOR_TRAINING GPU_NUMBERS_FOR_TEST
# Example: ./sub.sh  0,1,2,3,4,5,6,7 0

# See train.sh / test.sh for only training / test-evaluation.
# After the evaluation, run `gen_best_ep.py` to select the best ckpt from a specific metric (you choose it from Sm, wFm).
```




   
