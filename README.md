## HDA-CrossTransUnet

![HDA-CrossTransUnet Architecture](figures/architecture.png)

### 1. Prepare pre-trained ViT models
<p align="center">
  <img src="https://drive.google.com/uc?export=view&id=1CeH2WerY4UPvyMK_ScgyHsUx2LVw3lDl" 
       alt="HDA-CrossTransUnet Architecture"
       width="900">
</p>

* [Get models and training parameters in this link](https://drive.google.com/drive/folders/1UqIEPcohjIZdpT5bIc0NPcxkvI8i4ily): R50-ViT-B_16. At the same time, the parameter file (`.pth`) in the paper is also stored. (You can download and compress it, put it into the `model` file and rename it `TU_Synapse224`, and then use the test code
`python test.py --dataset Synapse --vit_name R50-ViT-B_16`
to get the test results.)

### 2. Prepare data

Please use the [preprocessed data](https://drive.google.com/drive/folders/1ACJEoTp-uqfF73qS3eUObQh52nGuzCd?usp=sharing) for research purposes.

### 3. Environment

### 4. Train/Test

Run the train script on the Synapse dataset. The batch size can be reduced to 12 or 16 to save memory (please also decrease the `base_lr` linearly), and both can reach similar performance.

```bash
CUDA_VISIBLE_DEVICES=0 python train.py --dataset Synapse --vit_name R50-ViT-B_16
