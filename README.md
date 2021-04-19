# Assignment
Procedure:


While applying logistic regression both class images were loaded and resized into 64x64x3and then flattened and concatenated to form the data set.
The corresponding labels were created for both the classes.
Now, the data set and labels are splitted into train and validation set with ratio 0.2.
Train set is used for training and the validation set is used to validate the model.
Using logistic regression we obtained an accuracy of 0.83 on validation set.
While applying multiclass classification using softmax as activation to the last layer, to improve the performance of the model we adopted the method of transfer learning.
Here, VGG16 with pretrained weights on image net is used along with some other pooling and fully connected layers.
Layers in VGG16 are not trained, only the layers that we have added are trained using the given data.
Without using any augmentations, with model architecture as a 5-layered neural network with Global max pooling, layers containing 1000,500,50,2 neurons respectively, we obtained an accuracy of 0.9 on train data and 0.8 on test data.
Model1,model2,model3 have the architecture with a GlobalMaxpooling layer,Gaussian Noise layer,and Fc layers with 1280,500,50,2 neurons respectively.
Model4 has the architecture with Global max pooling layer, and Fc layers 1000,50,2 neurons respectively. 

Model Accuracy with Different augmentations:

| Name  | Rotation range|Width shift range|Height shift range|Shear range|Zoom range|Brightness range|Channel shift range|Fill mode|Random eraser|Train accuracy, val accuracy|
| ------|:-------------:|:---------------:|:----------------:|:---------:|:--------:|:--------------:|:-----------------:|:-------:|:-----------:|:--------------------------:|
| model1|40             |0.2              |0.2               |none       |none      |0.1-0.9         |150                |nearest  |no           |0.85,0.72                   |
| model2|90             |0.2              |0.2               |0.4        |none      |0.1-0.9         |150                |nearest  |no           |0.8,0.72                    |   | | model3|180            |0.2              |0.2               |0.2        |none      |0.1-0.9         |150                |nearest  |no           |0.82,0.77                   |  
| model4|90             |0.2              |0.2               |0.2        |none      |0.1-0.9         |150                |nearest  |yes          |0.76,0.72                   |






