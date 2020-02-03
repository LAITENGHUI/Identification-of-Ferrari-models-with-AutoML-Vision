# Identification-of-Ferrari-models-with-AutoML-Vision
## Introduction
When my sister sees a nice car, she always asks me what car it is, but I don’t know much about cars. Sometimes when I see my idol post his cool cars, I have to slide down the screen to get information about the car from the comments. Inspired by computer vision, I made this project to recognize cars. Considering the short period, I will only use Ferrari models to do this. This project can discern 42 famous models. You can collect all Ferrari models’ or even other cars’ photos to make a perfect application. Let’s get started!
## What you’ll learn
- How to train an image classification model using AutoML Vision Edge.
- How to run it in an iOS app using Tensorflow Lite.
## Pre-requisites
- Goole Cloud Platform
- A recent version of XCode (v10.2+)
- iOS Simulator or a physical iOS device (v9.0+)
- Tensorflow Lite
## Data source and collection
- Method1: Here, you may need a tool called Download All Images, which will help you download all pictures on a google images website. Copy this link to your chrome to install it: chrome://extensions/?id=ifipmflagepipjokmbdecpmjbibjnakm. Then search for pictures of the model you want, and scroll the web to the bottom to load all images and click the button of that extension to download images. 
- Method2: You can also download all the URLs of images and save them as a txt file. You may need this extension: chrome://extensions/?id=nndknepjnldbdbepjfgmncbggmopgden (it’s more complicated than the former method). 
More than 200 images for each car model would be great. However, more training images will generally lead to better models. For extensive use, I uploaded the photos to Google Drive. You can check my [dataset]() for a quick start!
## Prepare training dataset
- Check the GCS link here. You can finish this step according to the following ways:
- Create a bucket. (Location type: Region, Location: us-central1)
- Copy the sample images into your bucket. If your data is on Google Drive, check this notebook to transfer the data from Google Drive to GCS.
- Create a CSV file. The sample dataset contains a CSV file with all of the image locations and the labels for each image. This step is also included in the notebook.
- Visit the AutoML Vision UI to begin the process of creating your dataset. 
- In Model objective, choose Single-label classification, as the training data only contains one label per image.
- Select Create-->Choose ‘Select a csv file on Cloud Storage’ and upload the csv file.
## Train a model
- Check the tutorial, and follow the steps. Then the Auto ML will train the model automatically. You will receive an email when it is finished.
- Make a prediction. Deploy your model and select the Upload images tab to send an image to test your model for a prediction.
## Use the model in mobile apps
- Download the TensorFlow Lite model. Now, you already have the model and a txt file with labels in it now.
- Use Xcode to deploy the model on your iPhone. Here is the framework you can use for a quick start. 
- Rename your two files to AutoML.tflite and labels.txt, and put them into the ‘Model’ folder.
- Connect your iPhone to your computer, and run the project. Don’t forget to select your iPhone on Xcode.
## Recommendations
- Make your dataset better. It is inevitable to download duplicate images on Google Images, and you need to delete them since there should be no overlap between training data and test data. I suggest you install an app called Duplicate File Finder. You can use it to delete duplicate photos.
- Delete unrelated photos. There will be some steering wheels and seats when you search for a car, you should delete them to improve the accuracy of your model.
- Tradeoffs. There are three kinds of models you can train on AutoML, which are higher accuracy, best trade-off, and faster predictions. They are all the same in size(My model size is 2.8M). However, the faster your model is, the less accurate it is. I think it’s accurate and fast enough for the best trade-off model, and the accuracy improves little if changing to the higher accuracy model.
- If you have some problems, the video below might help you.
## Show my work
- Check the screencast
- Check the video
