# Recognising classic Hong Kong style dishes using Transfer Learning with Residual Neural Network

Developed By: Arjun Rao and Mudit Chaudhary - The Chinese University of Hong Kong

# Dataset Provided :
 * Food images classified into 75 "large categories" - each containing up to 1000 images each category.
 * 25 small categories - containing 5 images per category
 
 
![alt text](https://drive.google.com/open?id=1pBE2MA9OdyjXmRwHXwoT2IbzqFn4aY4S)
 
# Solution used : Deep Residual Network with Transfer Learning (ResNet-50)

* Data augmenation was used to enhance
  *Random rotations with range 40 degrees
  *Height and width shift
  *Zoom
  *Shear
  *Horizontal flip

* Training Methodology:
1) Train the ResNet-50 with images from the large sample
2) Freeze the weights of that model and implement a new output layer for training the images from small sample.
3) Train last few layers of the previous model.
4) Transfer Learning from previous models

* Design methodology

For the first model:
We add a Global Average Pooling Layer connecting ResNet.
Add a Fully Connected layer with 1024 nodes
Add a Dropout Layer with 40% dropout rate
Add a Fully Connected output layer with 75 nodes
For the second model:
We add a Global Average Pooling Layer connecting ResNet.
Add a Fully Connected layer with 1024 nodes
Add a Dropout Layer with 40% dropout rate
Add a Fully Connected output layer with 25 nodes

* Future plans :
Future plan include:
Tuning the hyperparameters
Using Inception ResNet
Modify the output layer to reduce overfitting for the small sample



