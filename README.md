# MLP_Group14
2021-1_MLP_Group14_JunhongKim


I worked the project using Goolge Colab, so all the codes and corresponding datasets are on my Google drive folder.
I shared the working folder link for anyone using Yonsei google email.


Because of the original datset issue, we used public dataset which have 7 classes labeling instead.


On our group project(Group14), I was in charge of CT segmentation using 2D U-Net.
I used keras framework for this image segmentation project.

## Preprocessing
Before applying the U-Net, I preprocessed the datasets
1. Resolution resizing 512X512 --> 256X256
2. Data split (train : 8 patients (3686), val : 2 patients (1090), test : 5 patients (2615))
3. Choose two specific classes (lung, liver) for considering original dataset
4. Make label data from grey-channel(1) to RGB-channel(3) for multi-class segmentation
5. Save original nii format image files to npy format files

## Train model
1. Number of classes = 3
2. Learning rate = 0.0002
3. Batch normalization
4. Epoch = 50
5. Batch size = 32


## Evaluation for each class
1. Dice coefficient(DSC) : Avg lung DSC = 0.825, Avg liver DSC = 0.813
2. mIOU : Avg lung mIOU = 0.703, Avg liver mIOU = 0.689

# Final code
- Goolge drive folder sharing link(Anyone in Yonsei with this link can view) : https://drive.google.com/drive/folders/1i9GZSLYYCJKc6Tq7NDuDQ1XDvvAs0_IY?usp=sharing
- Final data preprocessing code is '20210607_CNN_preprocessing_postprocessing_keras_multi_channel.ipynb' in this repos
- Final trained model is "U_Net_lung_20210603_256x256_lung_liver.h5" in 'U-Net_CT-Image-Segmentation-master/trained_model/'
- Final 2D U-Net segmentation main code is '20210604_UNet_multi_class_keras.ipynb' in 'U-Net_CT-Image-Segmentation-master/'
