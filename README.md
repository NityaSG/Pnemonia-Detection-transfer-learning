 # Detection of Pneumonia 
 ### Using Transfer learning 
 Nitya Singh
 nityasingh030301@gmail.com

 ### Dataset 
 https://data.mendeley.com/datasets/rscbjbr9sj/2

 Dataset consist of chest X-ray scans of patient with normal lungs as well as pneumonic lungs.
 
The dataset is organized into 3 folders (train, test, val) and contains subfolders for each image category (Pneumonia/Normal). There are 5,863 X-Ray images (JPEG) and 2 categories (Pneumonia/Normal).

Chest X-ray images (anterior-posterior) were selected from retrospective cohorts of pediatric patients of one to five years old from Guangzhou Women and Children’s Medical Center, Guangzhou. All chest X-ray imaging was performed as part of patients’ routine clinical care.

For the analysis of chest x-ray images, all chest radiographs were initially screened for quality control by removing all low quality or unreadable scans. The diagnoses for the images were then graded by two expert physicians before being cleared for training the AI system. In order to account for any grading errors, the evaluation set was also checked by a third expert.   (kaggle : https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia?resource=download)



### Model 
For image classification Convolutional Neural Network(CNN) is used
Fundamental approach is to train the CNN from scratch using the dataset.

However in this experiment we use a pretrained CNN on a wider dataset

"VGG-16 is a convolutional neural network that is 16 layers deep. You can load a pretrained version of the network trained on more than a million images from the ImageNet database. The pretrained network can classify images into 1000 object categories, such as keyboard, mouse, pencil, and many animals. As a result, the network has learned rich feature representations for a wide range of images. The network has an image input size of 224-by-224." - Mathworks

We have added a pooling layer as well as a Dense layer to tune the neural network for our dataset.


### Training 
Here we have done training of two types :

1. Keeping the weights of vgg 16 constant i.e non trainable. only the last dense layer' are trainable.

2. The weights of the whole CNN are trainable.


### Result 
The accuracy of the method one is slightly lesser than the method two but the training speed of the later is significantly slower (given the larger number of nodes' weight to be trained).