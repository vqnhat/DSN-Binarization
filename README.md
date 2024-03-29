# DSN-Binarization
Multi-scale DSNs for degraded document image binarization

### Introduction

We propose a novel supervised binarization method by learning multi-scale deep supervised networks. Our model is directly trained from image regions using pixel values as inputs and the binary ground truth as labels. By extracting high-level features, the networks can differentiate text pixels from background noises, and thus can deal with severe degradations occurring in document images. Comparing to traditional algorithms, binary images generated by our method have a cleaner background and better-preserved strokes. The proposed approach achieves state-of-the-art results over widely used DIBCO datasets.

### Installing

1. Install the modified Caffe for pixel prediction with DSN: https://github.com/s9xie/hed
2. Copy our created dataset to the root directory of the DSN library: https://drive.google.com/file/d/0B5q_fE0K48IVN0VWcy01U0pGUVU/view?usp=sharing&resourcekey=0-7xWcr8Vw873WmS9oljAXiA
3. Copy the training and testing source code to \examples directory of the DSN library: https://drive.google.com/file/d/0B5q_fE0K48IVOWlDSG9kRWhrVEU/view?usp=sharing&resourcekey=0-PK3J2pWHMZKbyt8dwoEXQw

### Requirement: hardware

GPU: GTX 980Ti, GTX 1070.

### Training

To reproduce our results:

1. Download our created dataset, this dataset is created from the DIBCO 2009 & 2013, H-DIBCO 2010 & 2012& 2014, Bickley diary, PHIDB, and S-MS datasets.
1. The training parameters are defined in solver.prototxt files.
2. Three DSN structures are defined in train_val_conv3.prototxt, train_val_conv4.prototxt, and train_val_conv5.prototxt
2. Run the python code for training thee DSN structure: solve_conv3.py, solve_conv4.py, and solve_conv5.py.

### Testing

The pre-trained DSNs models are provided in conv_3, conv_4, and conv_5 folders. Run the python code multiscale_DSN.py for binarizing the document images. These pre-trained models are tested with H-DIBCO 2016 and DIBCO 2011 datasets.

$ python multiscale_DSN.py arg1 arg2 

arg1: Input gray scale or color image

arg2: Resulting binary image


### Acknowledgement

This code is based on Caffe and the implementation of DSN.

### Citations

If you are using the code/model/data provided here in a publication, please cite our paper:

    @proceedings{vqnhat,
      Author = {Quang Nhat, Vo,  Soo Hyung, Kim,  Hyung Jeong, Yang, and Gueesang, Lee},
      Title = {Binarization of degraded document images based on hierarchical deep supervised network},
      Year  = {2017},
      Booktitle = {Pattern Recognition}
    }
