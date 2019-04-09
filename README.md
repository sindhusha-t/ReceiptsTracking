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
1. Srividya Varnasi
2. Chandra Sekhar Pentakota
3. Srinivas Vidiyala
4. Sindhusha Tiyyagura

## Technologies Used:
Angular   
NodeJS   
ExpressJS   
Python    
Flask   

## Architecture:
![](https://github.com/sindhusha-t/ReceiptsTracking/raw/master/Documentation/Screenshots/Architecture.png)

## Design and Implementation


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

## Youtube Link:
https://www.youtube.com/watch?v=K1BVGcjD4QQ&t=1s

## PPT Link:
https://drive.google.com/open?id=19A4PNe4881jYeyPrnFbxK4xx-wwMdAZT
