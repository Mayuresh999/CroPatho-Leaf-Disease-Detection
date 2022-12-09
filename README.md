# 🌾CroPatho-Leaf-Disease-Detection

  ![CroPatho](https://user-images.githubusercontent.com/95702726/206638337-873009a3-b33f-4c75-8bda-11d5347d6fd0.png)


# 🌾CroPatho Application for Crop Disease Detection and Fungicide Recommendation using Computer Vision. 

This is one of my Internship projects at Sumago Infotech Pvt. Ltd. The project statement was to build a system that can predict the disease the crop is suffering from and suggest a fungicide. 

The project is based on Image Classification which is a branch of Computer Vision. CroPatho App can correctly classify between images and it has separate model for each class. There are total six classes namely "Bell pepper", "Corn", "Grapes", "Potato", "Rice" and "Wheat". 

All of these models are CNN models of which few are custom made and some are pre trained models which are then trained on custom data. The app takes an image as an input either from phone's gallery or the camera, converts it into required size of (224 x 224), feeds it to the model and returns the prediction. 

The models are converted to TFlite Format to facilitate on-device deployment which also reduces latency. This video is recorded real-time so you can see that the prediction is instantaneous.

You can see the Video Demo for app here: [LinkedIn Post](https://www.linkedin.com/feed/update/urn:li:activity:7003056787633418240/)

# 📁Dataset

The dataset for "Bell pepper", "Corn", "Grapes" and "Potato" was sourced from TensorFlow's datasets which can be found here: [Plant_Village](https://www.tensorflow.org/datasets/catalog/plant_village)

I have altered the dataset by dropping some of the plant species. 

For "Wheat" and "Rice" data, I used the dataset available here: [Wheat Dataset](https://github.com/MMFa666/WheatDiseaseDataset) & [Rice Dataset](https://github.com/caesarars/rice-leaf-diseases)

# 📱How does the Application work?

The Application can predict whether the plant has disease or not. If yes, it will show what is the name of disease and will recommend a fungicide to counter the diseases.

The App takes input image from user either from smartphone's camera or internal storage. The image is then fed to the model which is locally present in the device. The output from model is then shown on screen along with a predefined text about the fungicide.

There are six classes (six crops) that can be predicted. The app contains six models (one for each class) to do the prediction precisely.

# 🤖Predictor Models

The models are trained on the dataset using Google Colab. There are some models which are made using custom CNN Architecture and some have architecture from pre-trained models (Mobilenet) taken from [Keras Applications](https://keras.io/api/applications/)

These models were saved in .h5 extension after training. Later they were converted to .tflite as it is the only model to integrate with android easily. These tflite models were Quantized to int8 format to reduce file size and latency. 

The models take input image of size 224 x 224 px in 3 colour channels. If the input image is of different size, it will be resized before processing.

The models work on CNN architecture thus process the images accordingle. This problem of disease detection is an Image Classification problem so the model is trained of number of images from each disease class of a crop. The last layer in model is softmax layer which gives out probability of classes and the class with highest probability is shown.

# 📈Performance of models

All the models are pretty accurate. 

| Model | Accuracy (h5) | Accuracy (tflite) |
| :---:        |     :---:      |       :---:   |
| Grape   | 98.04%     | 98.28%   |
| Potato     | 89.35%       | 89.35%      |
| Bell Pepper     | 100%       | 100%      |
| Corn     | 87.05%      | 85.68%      |
| Rice     | 91.67     | 91.66      |
| Wheat     | 80.22%       | 83.51%      |

Following Image shows graph between Accuracy and Validation Accuracy vs number of epochs for Grape Model:

![image](https://user-images.githubusercontent.com/95702726/206655214-d0c3de0c-a599-429e-ad7b-0d79c0fa52c9.png)

And this one shows graph for Loss and Validation loss vs number of epochs for Grape Model:

![image](https://user-images.githubusercontent.com/95702726/206660042-9528d8b1-e30e-4c47-a9f5-68a41b3d73a6.png)

Finally we can see the Actual Classification vs the Predicted Classification for Grape Leaves along with Confidence in Following plot:

![image](https://user-images.githubusercontent.com/95702726/206654664-ff000158-65cf-4ee6-ac16-e6fa2d57fefc.png)


# 📸 Screenshots from the App:

![image](https://user-images.githubusercontent.com/95702726/206668292-4fe07cea-9323-46af-8dc4-627d6f0a64af.png)

Welcome Page --> Main Page --> Grape Model --> Selection of image source --> Prediction


# Thank You!!
Do ⭐ the Repo if you find this helpful.

# Connect with me

LinkedIn   [<img src="https://user-images.githubusercontent.com/95702726/206672195-06b2bd57-cabd-4687-a757-5303e9dc57b1.png" width="25"/>](https://www.linkedin.com/in/mayureshmadiwale/)

# Subscribe to my LinkedIn Newsletter 

Data-Blog-Post  [<img src="https://user-images.githubusercontent.com/95702726/206673316-6116df43-0c1c-474e-ac7c-6038ab333d13.png" width="25"/>](https://www.linkedin.com/newsletters/data-blog-post-6926611439939923968/)

# Subscribe to Data-Blog-Post for email updates

Data-Blog-Post website  [<img src="https://user-images.githubusercontent.com/95702726/206673316-6116df43-0c1c-474e-ac7c-6038ab333d13.png" width="25"/>](https://mayuresh0501.wixsite.com/data-blog-post)
