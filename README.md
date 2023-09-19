
## Project Description ( Keywords: Computer vision; Quality control; Manufacturing engineering; Die casting;  defects prediction )
🏭 Casting is a manufacturing process in which a liquid material is poured into a mold that contains a hollow cavity of the desired shape and then allowed to solidify. There are three types of casting processes: Sand Casting, Die Casting, and Lost Wax Casting.

🛠️ There are many types of defects in casting like holes, burr, shrinkage defects, mold material defects, pouring metal defects, metallurgical defects, etc.

🏭 A foundry that produces bearing bushes, in order of 10,000 parts per day has invested large funding to automate the process of finding defects in its casting production line. Currently, the inspection process is carried out manually by QC personnel. It is a very time-consuming process and due to human error, the process of rejecting defects is not very accurate. This can be the cause of rejection of an entire order which would lead to huge losses. The goal is to build a Machine Learning Model to eliminate this loss of revenue and make the QC process as accurate as possible.

📊 **Dataset**: The zip folder contains the photos of the parts. All images are (512x512) pixels grey-scaled. There are two Folders, the Training, and the Test set, each contains two subfolders of “Defect” and “Okay” parts.  

📝 **Task**: develop a deep learning classification model for this problem. Evaluate and validate your model accuracy with this Test set. Later, try to use the model to predict if a single unknown image (some examples in the Folder, New_set) is a defective or okay part. 

📂 **Source of the dataset**: (https://www.kaggle.com/ravirajsinh45/real-life-industrial-dataset-of-casting-product)




**Data Pre-processing:**

- 🧩 Split data into training and testing sets

- 🧩Preprocessing the Training Set:

    For the training set, I would apply a series of image transformations to enhance the model's ability to generalize. These transformations would include:

    - 🔄 Rescaling: The pixel values in the images are scaled down to a range between 0 and 1, which helps in standardizing the data.
    - 📏 Shear Range: Images would be subjected to shearing, which involves shifting one part of the image in a fixed direction, creating a sort of 'tilting' effect.
    - 🔍 Zoom Range: Random zooming would be applied to the images to simulate different perspectives.
    - ↔️ Horizontal Flip:  Some images would be horizontally flipped, which can help the model learn more robust features.

- 🧩Preprocessing the Test Set:

    - 🔄 Rescaling: For the test set, I would only perform rescaling to ensure consistency in the data. This is crucial to ensure that the model sees the data in a format similar to what it was trained on.
  
**Building the CNN Model:**

1- Simply, we perform a series convolution + pooling operations, followed by flattening and a number of fully connected layers. Then, we compile and train the model.


2- In detail , a CNN model can be thought as a combination of two components: feature extraction part and the classification part. 
    - The convolution + pooling layers perform feature extraction. For example given an image, the convolution layer detects features such as two eyes, long ears, four legs, a short tail and so on. 
    - The fully connected layers then act as a classifier on top of these features, and assign a probability for the input image being a dog.

3- The convolution + pooling layers as powerhouse:
- The convolution layers are the main powerhouse of a CNN model. Automatically detecting meaningful features given only an image and a label is not an easy task.
- The convolution layers learn such complex features by building on top of each other. 
- The first layers detect edges, the next layers combine them to detect shapes, to following layers merge this information to infer that this is a nose. To be clear, the CNN doesn’t know what a nose is. By seeing a lot of them in images, it learns to detect that as a feature. The fully connected layers learn how to use these features produced by convolutions in order to correctly classify the images.


**Model Training:**
Model.fit(x = training_set, validation_data = test_set, epochs = 50)




**Model Evaluation:**

- 📊 Evaluate model performance using accuracy metrics

- 📉 Analyze confusion matrix

**Model prediction:**


