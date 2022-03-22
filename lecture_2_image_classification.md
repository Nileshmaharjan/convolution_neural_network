## Image Classification 

The Semantic Gap
- The semantic gap characterizes the difference between two descriptions of an object by different linguistic representations. For instance, distinguishing an object in terms of human eye and computers.

Challenges
  - Viewpoint variation
  - Illumination
    - Our image classification system should be able to handle the variation in illumination. When any picture of the same object with different illumiation is given, the system should be able to assign the same level.
      ![illumination](https://user-images.githubusercontent.com/41963640/159409025-91726da4-4b3a-41a5-9506-b7ae2812bfe0.png)

  - Occlusion
    - Lot of objects which we can classify in image but are not able to view completely, as large part of it is hidden behind other objects.
      ![occlusion](https://user-images.githubusercontent.com/41963640/159409233-e7028a1e-d3b7-43eb-96ac-75c2a87d4090.jpeg)

  - Deformation
    - An altered form of an image. For instance cats in these images are deformed.
      ![deformation](https://user-images.githubusercontent.com/41963640/159409434-5a1d8c15-60c8-401e-8a0c-c832a4a5f7e5.PNG)
      
  - Background Clutter
    - It means there are lot of objects in the image and an observer has a tough time to find the particular object.
      ![clutter](https://user-images.githubusercontent.com/41963640/159409626-ddfe42e0-5206-4f07-b6d3-32c316098086.PNG)
      
  - Intra class variation
    - Variation between the images of the same class.
      ![intra-class variation](https://user-images.githubusercontent.com/41963640/159409780-429e1bd5-140f-40e7-bfc4-7e28f210c5fc.png)
      
Data-Driven Approach
  - Collect a dataset of images and labels.
  - Use Machine Learning to train a classifier.
  - Evaluate the classifier on new images.

Nearest Neighbor
  - The optimization problem of finding the point in a given set that is closest to given point.
  - Memorize all data and labels
  - Predict the lable of the most similar training image.

Distance Metrics
  - Distance metrics are used in both supervised and unsupervised learning to calcuate the similarity between data points.

Euclidean Distance
  - Represents shortest distance between two points.
  - ![euclidean](https://user-images.githubusercontent.com/41963640/159410797-0c857266-86de-4166-bd57-fa7cfa6de989.png)
  - Formula for euclidean distance
    ![eformula](https://user-images.githubusercontent.com/41963640/159410871-556f5f2b-99e6-4e6f-ab03-f112a4f26df1.PNG)
    
 Manhattan Distance
  - Represents sum of absolute differences between points across all the dimensions
  - ![manhattan](https://user-images.githubusercontent.com/41963640/159410968-52cc6f49-3959-4439-bad9-ac837ad02bef.png)
  - Formula for manhattan distance
  - ![mformula](https://user-images.githubusercontent.com/41963640/159411044-177374fc-df1f-40a6-9ce0-f9950563c865.PNG)

Hyperparameters
 - What is the best value of k?
 - What is the best distance to use?
 - Very problem dependent.
 - Must try them all out and see what works best.

Setting Hyperparameters
 - Idea 1
  - Chosse hyperparameters that work best on the data. (K = 1, always works on perfectly on training data, Bad idea!)
 - Idea 2
  - Split data into train and test, choose hyperparameters that work best on test data. (Bad: now idea on how algorithm will perform on new data)
 - Idea 3
  - Split data into train, val and test; choose hyperparameters on val and evaluate on test. (Better !)
 - Idea 4
  - Cross Validation: Split data into folds, try each fold as validation and average the results.
  - Usefull for small datasets; but not used too frequently in deep learning.

K-Nearest Neighbors
 - Assumes that similar things exist in close proximity, similar things are near to each other.
 - Instead of copying label from nearest neighbor, take majority vote from K closes points
  ![knearest](https://user-images.githubusercontent.com/41963640/159410631-24509303-7669-448b-b909-8dba8a340abe.PNG)
 - Never used on images as very slow at test time and distance metrics on pixels are not informative.

Linear Classifier
 - Classification decision based on value of a linear combination of characterstics.
 - Works best on problems that is linear seperable.

Intrepreting a Linear Classifier

![linear_classifier](https://user-images.githubusercontent.com/41963640/159411997-ec741c28-80f4-4307-bc85-8d894f4c7681.PNG)
- The weight matrix will have one row for every class that needs to be classified, and one column for every feature.

Hard cases for a linear classifier
  
  ![hardcases](https://user-images.githubusercontent.com/41963640/159412257-56ddbfe0-7bc1-4865-81b6-f531c6533ff5.PNG)


    




    

    

