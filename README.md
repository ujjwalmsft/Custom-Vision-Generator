# Custom Vision Generator
A tool for generating a custom vision projects. It will automatically find and download images of topics you imput, train the model and export a confusion matrix in CSV format.

## Pre-requisites
You'll need to install [Visual Studio](https://www.visualstudio.com/vs/community/) to build and run this code. 

## Steps to run the sample
1. Sign in or create a new account on [customvision.ai](https://www.visualstudio.com/vs/community/)
2. After login - click on cog icon on the right hand side and copy key values into the appropriate app settings

![subscription keys](documents/CustomVision1.PNG)

    
3. Register for the free [Bing Search service](https://azure.microsoft.com/try/cognitive-services/?api=bing-web-search-api) then copy the key value into the app settings

![getting an API key](documents/BingSearch.PNG)

## Running the application

The app will create a project in your custom vision dashboard with a random GUID. Please note that each time you run the app, a new project will be created. Next the app reads all the tags in the `tags.csv` file. The system searches Bing Images for each tag to prepare the source set of images for the classifier. 

![list of tags to download in tags.csv](documents/CustomVision2.PNG)


By default it downloads eight images for each tag - five images for training the model and three images for the testing the model.
After downloading the images, the app will then upload the photos into the customvision.ai project and tag them accordingly.

Now the model has enough data to be trained. The app will train the model and set the default iteration to the newly trained model.

The model is ready for testing so the app will try to test the model the results of which are  exported as a confusion matrix into `result.csv`.
You can check the quality of your model by reviewing the [confusion matrix](https://en.wikipedia.org/wiki/Confusion_matrix).

As you are running the app you should see output similar to this animation. 
![process running](documents/running-sample.gif)


##  More information on the Azure Custom Vision Service

- [Start here](https://docs.microsoft.com/en-au/azure/cognitive-services/custom-vision-service/home)
- [Custom Vision API C# Tutorial](https://docs.microsoft.com/en-au/azure/cognitive-services/custom-vision-service/csharp-tutorial)
