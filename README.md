# Chest X-Ray Image Classification
    
## Final Results:
Recall: 100%     
Accuracy: 97%
    
## Steps:
In this project I'll create Neural Networks to classify whether an X-Ray image is of a chest with pneumonia or without.    
 - split the data into train / validation / test sets.   
 - preprocess the images for inputting them into the model.   
 - look into the images and class balance
 - create a baseline model using a Dense Neural Network
 - create models using CNNs and trying different options
 - use transfer learning: building off of the base of a previously trained network
 - create a final model
 - visualise layers within the model
 
### Data:
![data split slide](https://github.com/Maltanno/Phase4_Project/blob/main/pics/data_split.png)

![XRay slide](https://github.com/Maltanno/Phase4_Project/blob/main/pics/X-Rays.png)

### Baseline Model:
#### Results:     
Recall: 95%    
Accuracy: 96%     
     
### CNNs:
Tried models with convolution and dilated convolution layers.    
Tried different:
 - Activation Functions
 - Weight Initializers
 - Numbers of epochs
 - Regularisation methods      
     
     
For the most part they weren't quite as good as the Dense Neural Network. Perhaps because the pneumonia wasn't so much a solid shape to be found and more a vague mistiness in the image.   
Perhaps the pneumonia is detected more by how it makes the rest of the structures in the image harder to discern?   
I decided against using data augmentation as the images were very uniform.    

### Transfer Learning

I use VGG19 as a base and try it both with and without fine tuning the last block.    
With fine tuning gave the best results I used this for my final model -with a tweak.   

## Final Model
I wanted to optimise my final model for recall to minimise the number of people with undetected pneumonia.   
To do this I took the probabilities predicted by the model and classified anything predicted with more than 5% chance of having pneumonia as having it.       
![Results slide](https://github.com/Maltanno/Phase4_Project/blob/main/pics/Results.png)

### Feature Maps
For interest I then looked at some of the feature maps:    
![Feature map slide](https://github.com/Maltanno/Phase4_Project/blob/main/pics/feature_maps.png)
