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
