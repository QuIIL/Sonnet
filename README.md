# Sonnet: A self-guided ordinal regression neural network for segmentation and classification of nuclei in large-scale multi-tissue histology images

## Overview

This repository contains a tensorflow implementation of SONNET: a self-guided ordinal regression neural network that performs simultaneously nuclei segmentation and classification. By introducing a distance decreasing discretization strategy, the network can detect nuclear pixels (inner pixels) and high uncertainty regions (outer pixels). The self-guided training strategy is applied to high uncertainty regions to improve the final outcome. <br />
As part of this research, we introduce a new dataset for Gastric Lymphocyte Segmentation And Classification (GLySAC), which includes 59 H&E stained image tiles, of size 1000x1000. More details can be found in the SONNET paper. 

The repository includes:
- Source code of SONNET.
- Training code for SONNET.
- Datasets employed in the SONNET paper.
- Pretrained weights for the SONNET encoder.
- Evaluation on nuclei segmentation metrics (DICE, AJI, DQ, SQ, PQ) and nuclei classification metrics (Fd and F1 scores).

## Installation
```
conda create --name sonnet python=3.6
conda activate sonnet
pip install -r requirements.txt
```

## Dataset
Download the CoNSeP dataset from this [link](https://warwick.ac.uk/fac/sci/dcs/research/tia/data/hovernet/). <br />
Download the PanNuke dataset from this [link](https://warwick.ac.uk/fac/cross_fac/tia/data/pannuke) <br />
Download the MoNuSAC and GLySAC from this [link](https://drive.google.com/drive/folders/1p0Yt2w8MTcaZJU3bdh0fAtTrPWin1-zb?usp=sharing) <br />
If you use any of these datasets for your research, please citing its corresponding paper.

## Step by Step Instruction
To help with debugging and applying the model for nuclei segmentation and classification, it requires three steps:

### Step 1: Extracting the original data into patches
To train the model, the data needs to be extracted into patches. To do this, simply run:
``` python extract_patches.py```