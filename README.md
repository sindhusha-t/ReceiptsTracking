#                                                     Smart Receipts
Hackathon Spring 2019

## Use Case:
Every time when we purchase any items, we get a receipt. If merchant does not have email facility, we just take the printed receipt.Now such receipts are just stacked in our homes, waiting to be trashed.This app can help us analyze our purchases smartly.   
Develop mobile app to analyze purchases after scanning a receipt.
1. App should be able to scan receipts.
2. Scanned receipts data should be shown on App in nice format.
3. Such receipts data can be grouped by various categories such as good, clothes, etc.
4. All the steps should be automated with minimal manual intervention.
5. Extra points for adding any deep learning aspect in terms of analysis of receipts data.

## Team Members:
1. Naga Srividya Varanasi
2. Chandrasekhar Pentakota
3. Sindhusha Tiyyagura
4. Srininvas Vidiyala

## Technologies Used:
Angular   
NodeJS   
ExpressJS   
Python    
Flask   

## Architecture:
![](https://github.com/sindhusha-t/ReceiptsTracking/raw/master/Documentation/Screenshots/Architecture.png)

## Design and Implementation
1. In the First step, we created a basic web application where user can select whether to use webcam or upload the images from the local device. User can select multiple images.   
2. After user uploads the image, the image is classified as whether it is receipt or not.   
3. About Receipt Classifier ->                
        a) It internally uses pytesseract to convert the image to text.             
        b) Using the text it classifies whether the text is actually the receipt content or not.               
        c) The model for classifying is trained with equal set of images conutaining both Receipts and not Receipts.              
        d) The model is tested with few receipts where it turned out to classify few and other few receipts which are blur it is unable to identify -> Where this is the problem in converting the image to text format.                
        e) converting image to text(pytesseract OCR) is not doing that good and so it becomes a hurdle at classifier stage.          
4. So using the classifier Information we uploaded the images ( identified as receipts ) to the Google Drive Database service.   
5. After Uploading the images to the server -> We have used Microsoft API service to get the text information from the image.    
            a) In this initially we thought of using Tesseract OCR, but it is not classifying the words correctly.    
            b) So we choosed to use Microsoft open API for identifying the text on the Image.    
6. After Identifying the text from the image -> We have used semantic similarity model to categorize the receipt items into different fields.    
            a) We have choosed set of category words.    
            b) On giving a word -> semantic similarity model gives to which category word the input word is closer.    
            c) So we use that information to categorize the words.    
            d) This is taking a lot of time to execute. So we are planning to use "clustering" instead of semantic similarity model.   
7. As it is taking lot of time to categorize, for now we have stored the information in JSON file and displayed the JSON file data in the form of table and also the pie chart view.    

## Final Output:
1. Using command `ng serve` command to start the web application.    
(listening on localhost 4200)    

![](https://github.com/sindhusha-t/ReceiptsTracking/raw/master/Documentation/Screenshots/angular.png)

2. Using command `nodemon server.js` to start the backend API.   
(listening on localhost 3000)   

![](https://github.com/sindhusha-t/ReceiptsTracking/raw/master/Documentation/Screenshots/nodeJS%20server.png)

3. Using command `python model_name` to start the backend API.    
(Listening on localhost 5000)   
There are 2 models:   
         a) Classifying whether the Images are receipt or not.   
         b) Converting the Image to Text using Microsoft Congnitive service API.   
         c) Output from b) is then is used for categorizing the text to different fields using semantic similarity model.  
         
![](https://github.com/sindhusha-t/ReceiptsTracking/raw/master/Documentation/Screenshots/model1.png)

![](https://github.com/sindhusha-t/ReceiptsTracking/raw/master/Documentation/Screenshots/model2.png)
         
4. The Home page of the web application.    
User can either take a snapshot of the receipt or can upload it from the local device.  

![](https://github.com/sindhusha-t/ReceiptsTracking/raw/master/Documentation/Screenshots/Home%20Page.png)

5. Uploading files to server.   
Before uploading it the image is given to the classifier to filter out the receipts.   
Only the receipts will be added to the server.   

![](https://github.com/sindhusha-t/ReceiptsTracking/raw/master/Documentation/Screenshots/uploading%20files.png)
![](https://github.com/sindhusha-t/ReceiptsTracking/raw/master/Documentation/Screenshots/uploading%20to%20server.png)

6. User can view list of all receipts that are uploaded to the server.   

![](https://github.com/sindhusha-t/ReceiptsTracking/raw/master/Documentation/Screenshots/Images%20on%20server.png)

7. User can view the list of categories.   
All the receipts information is divided into the categories.    

![](https://github.com/sindhusha-t/ReceiptsTracking/raw/master/Documentation/Screenshots/summary.png)

8. We are dispalying the summarized data in pie chart so that users can easily visualize the data.   

![](https://github.com/sindhusha-t/ReceiptsTracking/raw/master/Documentation/Screenshots/pie%20chart%20for%20summary.png)

## Strugggles and Issues Faced:
1) Initially we tried to create Ionic Application -> but we ran out of many issues for building the apk file. The Ionic Application is running completely fine on the web. So we have spent enough amount of time on this and so we shifted to angular for developing web applications.
2) We thought of using semantic similarity model to train and test the receipt categorization. It is taking hours to categorize a single receipt. So we are planning to change the model.

## Youtube Link:
https://www.youtube.com/watch?v=K1BVGcjD4QQ&t=1s

## PPT Link:
https://drive.google.com/open?id=19A4PNe4881jYeyPrnFbxK4xx-wwMdAZT
