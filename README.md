
## Project Description ( Keywords: Computer vision; Quality control; Manufacturing engineering; Die casting;  defects prediction )


** Project overview **
🏭 Casting is a manufacturing process in which a liquid material is poured into a mould that contains a hollow cavity of the desired shape and then allowed to solidify. There are three types of casting processes: Sand Casting, Die Casting, and Lost Wax Casting.

🛠️ There are many types of defects in casting like holes, burr, shrinkage defects, mould material defects, pouring metal defects, metallurgical defects, etc.

🏭 A foundry that produces bearing bushes, in order of 10,000 parts per day has invested large funding to automate the process of finding defects in its casting production line. Currently, the inspection process is carried out manually by QC personnel. It is a very time-consuming process and due to human error, the process of rejecting defects is not very accurate. This can be the cause of rejection of an entire order which would lead to huge losses. The goal is to build a Machine Learning Model to eliminate this loss of revenue and make the QC process as accurate as possible.

📊 **Dataset**: All images are (512x512) pixels grey-scaled. There are two Folders, the Training, and the Test set, each containing two subfolders of “Defect” and “Okay” parts.  

📝 **Task**: To develop a deep-learning classification model for this problem. Evaluate and validate the model accuracy with this Test set. Later, I will  use the model to predict if a single unknown image (some examples in the Folder, New_set) is a defective or okay part. 

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
1- Simply, I perform a series of convolution + pooling operations, followed by flattening and a number of fully connected layers. Then, I compile and train the model.



**Model Evaluation:**
- 📊 Evaluate model performance using accuracy metrics

- 📉 Analyze confusion matrix

**Model prediction:**

Making predictions

<img width="811" alt="Screen Shot 2023-09-18 at 5 24 18 PM" src="https://github.com/ZTECH10/Die-Casting-Automatic-Defect-Detection-using-Convolutional-neural-networks-CNNs-/assets/53150477/a5bafb20-c11f-49b4-8099-198bba301d50">



