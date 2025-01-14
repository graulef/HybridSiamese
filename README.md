# HybridSiamese

## Install Matconvnet

1) Download the beta [23 version](http://www.vlfeat.org/matconvnet/download/) of matconvnet 

2) unpack the downloaded file into a directory of your choosing
   Call the path to this directory <MatConvNet>
   
3) Compile matconvnet (GPU) by following the instructions specified at the original matconvnet [website](http://www.vlfeat.org/matconvnet/install/)

## Datasets

Vis-Nir:

1) Dowload the original [dataset](https://ivrl.epfl.ch/supplementary_material/cvpr11/) 

2) Extract the dataset to datasets/Vis-Nir/data

3) Using Matlab, run the 'CreateTrainingData' and 'CreateTestData' scripts inside datasets/Vis-Nir directory

Vis-Nir_grid:

1) After already downloading the original dataset for the Vis-Nir in the keypoint config,
   run the 'CreateTrainingDataWithLabels' inside Vis-Nir_grid directory

vedai:

1) Dowload the original [dataset](https://downloads.greyc.fr/vedai/)
   download only the 512x512 two parts.
2) Extract the dataset to 'datasets/vedai/data'
3) There are some unrelevant images with polygons overlaid on original images, Delete them
4) Run the 'CreateTrainingDataWithLabels' inside 'datasets\vedai' directory

cuhk:

1) Dowload the original [dataset](http://mmlab.ie.cuhk.edu.hk/archive/facesketch.html)
   download only the cuhk dataset, using the cropped sketches and cropped photos from both training and test.
   overall 188 images
2) Extract all the images and sketches to 'datasets\cuhk\data'
3) Run the 'CreateTrainingDataWithLabels' inside 'datasets\cuhk' directory

We supply CSV files referencing all train and test pairs for research in other platforms than matlab

## Train

in order to train any of the models specified in the paper just edit the TrainModels.m script as your wish.

To replicate training as specified in the paper, follow the details in the paper:
* Use default learning parameters:
    * Train for 40 epochs in the L2 config and 100 in the softmax
    * Use Learning rate of 0.01 and weight decay of 0.0005
    * hard mining factor of 0.8 is optimal

## Eval

We supply our trained models + results for evaluation
Evaluation code is inside the Eval directory

There are two scripts
* EvaluateFar_Grid - general evaluation script for all the grid like datasets, i.e. cuhk,vedai and Vis-Nir_grid
* EvaluateFar_Vis_Nir - Dedicated script for the Vis-Nir dataset in its keypoint setup

Training and Evaluation code all need GPU installed



