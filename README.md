This Repo has two parts-
## 1. Through Webcam including training and testing of the model using Keras and TensorFlow.
## 2. From the images, using Face_Recognition Library 

## Requirements
Run the command-

		pip install -r requirements.txt

To install all the dependencies.
For installing Dlib library refer to-   https://github.com/davisking/dlib.git

# `Part 1`
### Add New Faces

Run the command-

		python save_face.py
to add a new face which will be stored in a new folder- new_faces.
Enter the id as 1.
After that it will ask the initial value, enter it as 1(if you are entering for the first time), otherwise as 301.
Webcam will take your 300 photos, or you can also add own photos in the new_faces folder. 

### Running the csv file

Run the command-

		python store_facial_features.py 

What this file does is it iteratively searches for every face in the faces folder, then computes the embeddings of each of them.
These embeddings are stored in a csv file called dataset.csv.

### Getting training and testing data from the csv file

Run the csv_to_pickle.py file
	
		python csv_to_pickle.py

4 new files will be created train_features, train_labels, test_features and test_labels.

### Train the model

Run the train_model_tf.py file to train using Tensorflow. Remember to delete the tmp/ folder first if other faces are added or else you will face errors with shape of the output data.

		python train_model_tf.py
Run the train_model_keras.py file to train using Keras

		python train_model_keras.py

Take Atleast 4 different faces for best result.

### Recognition

Make sure to run the train_model_keras.py file first.
		
		python recognize.py

# `Part 2`

To install the Face_recognition library run-

        pip install face_recognition
or refer to https://github.com/ageitgey/face_recognition.git

### Structure  
from_image/
- fr.py 
- ak.jpg
- images/
        -akshay.jpg
        -donald.jpg
        -manmohan.jpg
        -rahul.jpg

### How to run-
Run the file fr.py as-

        python fr.py

where 'ak.jpg' is the image being checked.

It will produce output as- 

        Not matched: rahul.jpeg
        Matched: akshay.jpg
        Not matched: donald.jpeg
        Not matched: manmohan.jpg

### What is being done-
Looping over each image.
Encoding the image into a feature vector.
Comparing the loaded image with the image to be recognized.
If it is a match, we print that. If it is a mismatch, we print that as well.



    


