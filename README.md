# MaskRCNN
## Mask-Rcnn- Implementation of instance segmentation model in Keras
---

### Catalog
1. [Environment]
2. [Download]
3. [How to train]
4. [Reference]

### Required environment
tensorflow-gpu==1.13.1  
keras==2.1.5  

### file download
This trained weight is based on the coco data set and can be directly used for instance segmentation of the coco data set。  
### Training steps
#### 1. Prepare the data set
a. Use labelme to label the data set. Note that when labeling the same class, use different serial numbers. For example, if there are ** two apples in the screen, the label of one apple is apple1 and the other is apple2.**    
b. Put the jpg/png file and json file in the before folder under the root directory after the annotation is completed.  
c、Then run json_to_dataset.py to generate the train_dataset folder。  
#### 2. Modify the training parameters.
a. Modify the classes you want to classify in dataset.py, which are the class-related content in the load_shapes function and load_mask function, that is, modify the original labels into the classes you want to classify.    
b、Modify the contents of ShapesConfig (Config) under the train folder, NUM_CLASS is equal to the number of classes you want to classify + 1.  
c、IMAGE_MAX_DIM, IMAGE_MIN_DIM, BATCH_SIZE and IMAGES_PER_GPU are modified according to their own RAM conditions. RPN_ANCHOR_SCALES is modified according to IMAGE_MAX_DIM and IMAGE_MIN_DIM.  
d、STEPS_PER_EPOCH represents how many times each generation trains.   
#### 3. Forecast
a. Download the h5 file（trained） and run it during the test. The test file WeldIDXXX.jpg is stored in the img.  
b、When testing your own code, modify the parameters in _defaults to the parameters used during training.

### Reference
https://github.com/matterport/Mask_RCNN

