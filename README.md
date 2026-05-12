# FINAL YEAR PROJECT REPOSITORY
# Deepfake Detection using Vision Transformers
A comparative study of Vision Transformer architectures for binary deepfake image classification, evaluating three pre-trained modedls against a custom built model trained from scratch.

## Overview
This project investigates the performance of different ViT architecures, based on their ability to distinguish between real and deepfake images.
The research goes beyond comparing accuracy scores, and goes further by analysing the patterns behind the models' failures. The misclassified images are then specifically seperated into three cases: All models misclassified the same images, only the custom model struggled, and where only the pre-trained models predicted incorrectly.

The models compared in this research are:
- Vit-B/16 -> the original, standard baseline Vision Transformer
- DeiT-Tiny -> a distillation-based transformer, efficient for msaller datasets
- CvT-13 -> a hybrid Cnn-Transformer model, middle-ground of parameter size between the previous two models
- Custom Vit -> built and trained from scratch on the dataset used in the study

## Dataset
The dataset used was sourced from Kaggle, and can be found on:
https://www.kaggle.com/datasets/manjilkarki/deepfake-and-real-images?resource=download-directory

It totals to approximately 190,000 images - ~140k training, ~39.4k validation and ~10.9k test images, where each is labelled as either real or fake.

## Prep
The custom model takes 72x72 images, while the pre-trained images take 224x224 images. They were loaded with pre-trained weights and fine-tuned on the dataset.

## Final Results

| Model | Precision | Recall | F1 | Test Accuracy |
| :---: | :---: | :---: | :---: | :---: |
| ViT-B/16 | 0.9337 | 0.9298 | 0.9297 | 92.98% |
| DeiT-Tiny | 0.9259 | 0.9223 | 0.9221 | 92.23% |
| CvT-13 | 0.9095 | 0.8957 | 0.8948 | 89.57% |
| Custom Model | 0.9007 | 0.8995 | 0.8994 | 89.95% |

Total misclassified Images: 2,244 images  
Images Misclassified by All models: 138 images  
Images Misclassified by only Custom model: 641 images  
Images Misclassified by only Pre-trained models: 249 images

## Limitations
- A fixed learning rate was used across all models, which, in handsight, was too high for the pre-trained models and likely is the reason for the large validation-to-test accuracy drops explained in the report.
- Pre-trained models were run for 35 epochs, while the custom model was run for 70
- Test set of images contains some with unrealistic editing and even duplicated, making some clssifications and results unfair
