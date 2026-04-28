# 2D-ResNet-UNet-
Binary segmentation of low-grade glioma (LGG) tumors from FLAIR MRI scans Backbone: ResNet-34 encoder (pretrained ImageNet) + U-Net decoder

## Key Features

* **Architecture**: ResNet-34 Backbone + U-Net Decoder.
* **Deep Supervision**: Multi-scale output support for improved gradient flow (implemented in architecture).
* **Advanced Loss**: Combined Dice + Binary Cross-Entropy (DiceBCELoss) for handling class imbalance.
* **Training Robustness:** Full checkpointing (optimizer state, scheduler, and history) for seamless training resumption.
* **Augmentation:** Real-time geometric and color jitters using torchvision.

## Architecture Detail

The model utilizes a "ResUNet" approach where the encoder is a standard ResNet-34. Skip connections are extracted from the four main stages of ResNet to preserve spatial information in the decoder.


## Dataset

The pipeline is designed for the LGG MRI Segmentation dataset.
* Total Pairs: 3,929 image-mask pairs.
* Class Balance: ~35% of slices contain tumors; ~65% are healthy.
* Format: .tif files (RGB MRI, Grayscale Masks).
  
LGG MRI Segmentation Dataset : https://www.kaggle.com/datasets/mateuszbuda/lgg-mri-segmentation

## Model Weights

Available on Hugging Face:
https://huggingface.co/SisyphussDEBUG/best_resunet2

## Results
The model achieves high localization accuracy on the test set:
* Test Dice Score: 0.9038
* Test IoU: 0.8742 
