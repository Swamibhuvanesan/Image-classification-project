# Entire Explanation of the project

## Objectives

We aim to detect faces with two eyes using OpenCV and a technique called Haar Cascade. The key objectives include:

1. Detection of faces with two eyes.
2. Utilization of OpenCV and the Haar Cascade method.
3. Creation of a dataset folder for storing collected data.

## Data Collection

Data collection involves the following methods:

1. Manual download.
2. Web scraping using Selenium.
3. Use of the Fatkun Chrome Extension.
4. Utilization of data from other third-party vendors.

## Data Cleaning

Upon data collection, the following cleaning steps are undertaken:

1. Assessment of test images: The `shape` function returns three values, rendering the image three-dimensional. The third value represents the RGB value, which is converted to grayscale to remove RGB data.

## OpenCV Haar Cascade Implementation

The process includes:

1. Downloading the OpenCV Haar cascade XML files (pre-trained classifiers).
2. Utilizing OpenCV Haar cascade for face detection (`face_cascade`) and eye detection (`eye_cascade`).
3. Detection results: The method returns an array of four values (x, y, width, height).
4. Visualization: A red rectangle is drawn around detected faces, while green rectangles indicate detected eyes.
5. Creation of cropped images: Images are cropped to retain only the detected face area.

## Folder Management

Folder management involves:

1. Checking existence: The `os.path.exists()` function is used to verify the presence of a folder for cropped images.
2. Scanning: The `os.scandir` function is employed to check the visibility of detected faces/eyes in images and save them in the cropped folder.
3. Dictionary creation: Names and the corresponding cropped directory are saved in a dictionary for reference.
4. Data generation: The process generates cropped images for every detected face in the provided images.

## Manual Data Cleaning

It is essential to manually review and clean the data by deleting any incorrectly detected images.

## Feature Engineering

1. **Wavelet Transform:**
   - Prerequisites: Signal processing and Fourier Transform.
   - Purpose: To extract important facial features useful for the classifier.
   - Usage: Combined with raw pixel images as input for the classifier.
   - Implementation: Create a combination of wavelet-transformed and raw pixel images.
   - Data Type Conversion: Convert integers to float to ensure smooth operation with scikit-learn.

## Training the Model

1. **Model Selection and Tuning:**
   - **SVM with RBF Kernel:** Tuned with heuristic fine-tuning.
   - **Data Splitting:** Split data into training and test sets (`X_train`, `X_test`, `Y_train`, `Y_test`).
   - **Pipeline:** Utilize `Pipeline` with `StandardScaler()` to preprocess data and find the score.
   - **Model Evaluation:** Assess models based on precision and recall.
   - **Model Comparison:** Through trial and error, determine the best model among SVM, Random Forest, and Logistic Regression. SVM provided the best score in this case.

2. **Model Testing:**
   - Re-evaluate the scores of the three models using `X_test` and `Y_test`.
   - **Confusion Matrix:** Create a confusion matrix to understand model performance.
   - **Visualization:** Use Seaborn to plot the confusion matrix for better visual comprehension.

3. **Model Saving:**
   - Save the trained model as a pickle file using `joblib`.
   - Save the class dictionary as a JSON file.

## Flask Server

1. **Server Setup:**
   - Run the Flask server on Port 5000.
   - Develop a Flask server to use the trained model for image classification.
   - Ensure the UI communicates with the backend server for image classification tasks.

## Building a Website

1. **Frontend Development:**
   - Use HTML, CSS, and JavaScript for the website.
   - Implement jQuery to make HTTP calls to the Python Flask backend.

2. **Website Features:**
   - Create an area on the website where users can drag and drop an image for identification.
