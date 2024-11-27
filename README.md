---

# Celebrity Image Classifier

This project is a machine learning-based image classification system that identifies celebrities from images and provides a probability score for each classification. It includes a Flask-based API for easy interaction.

## Table of Contents

- [Project Overview](#project-overview)
- [Directory Structure](#directory-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Using PyCharm](#using-pycharm)
- [API Endpoints](#api-endpoints)
- [Model Training](#model-training)
- [Contributing](#contributing)
- [License](#license)

## Project Overview

The Celebrity Image Classifier uses machine learning algorithms to classify images of celebrities. The classifier is trained on a dataset of celebrity images and can return the probability of each class for a given input image.

### Components

- **Model Training**: Scripts and notebooks for training the image classification model.
- **Server**: A Flask-based server that hosts the image classification API.
- **Utilities**: Helper functions for loading artifacts, preprocessing images, and performing classifications.
- **Wavelet Transform**: Wavelet transformations for feature extraction from images.
- **UI**: User Interface for interacting with the classifier.

## Directory Structure

```
Project
│
├───Model
│   └───classifier_model.ipynb
│
├───Server
│   │   server.py
│   │   util.py
│   └───artifacts
│           class_dictionary.json
│           model.pkl
│
└───UI
    │   app.html
    │   app.css
    │   app.js
    │   dropzone.min.css
    │   dropzone.min.js
    └───images
```

## Installation

### Prerequisites

- Python 3.x
- Virtual Environment (optional but recommended)

### Steps

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/celebrity-image-classifier.git
   cd celebrity-image-classifier
   ```

2. **Create and activate a virtual environment**:
   ```bash
   python -m venv myenv
   source myenv/bin/activate  # On Windows: myenv\Scripts\activate
   ```

3. **Install the required libraries**:
   ```bash
   pip install numpy opencv-python matplotlib PyWavelets scikit-learn pandas seaborn joblib flask
   ```

4. **Verify the installation**:
   Ensure all required packages are installed by running:
   ```bash
   python -m pip freeze
   ```

## Usage

### Running the Server

1. **Navigate to the Server directory**:
   ```bash
   cd Server
   ```

2. **Run the server**:
   ```bash
   python server.py
   ```

   The server will start and you should see output indicating that the Flask server is running.

### Making Predictions

You can use tools like `curl` or Postman to send images to the API endpoint for classification.

## Using PyCharm

1. **Open PyCharm** and select `Open` to open the project directory.
2. **Configure the Python Interpreter**:
   - Go to `File > Settings > Project: <your_project_name> > Python Interpreter`.
   - Select the virtual environment you created (`myenv`).
3. **Run/Debug Configuration**:
   - Go to `Run > Edit Configurations`.
   - Add a new Python configuration.
   - Set the script path to `Server/server.py`.
   - Set the working directory to the project root.
4. **Run the Project**:
   - Click the Run button to start the server.
   - Use the built-in PyCharm terminal to interact with the server.

## API Endpoints

### POST /predict

- **Description**: Accepts an image file and returns the predicted celebrity with probability scores.
- **Request**:
  - Content-Type: `multipart/form-data`
  - Parameters: `image` (file)
- **Response**: JSON object with the predicted class and probability scores.

#### Example Request

```bash
curl -X POST -F "image=@path/to/your/image.jpg" http://localhost:5000/predict
```

#### Example Response

```json
{
    "class": "Celebrity Name",
    "probability": 0.85
}
```

## Model Training

### Steps

1. **Open the Jupyter Notebook**:
   ```bash
   jupyter notebook
   ```

2. **Navigate to the `classifier_model.ipynb` file**:
   Open the notebook and follow the steps to preprocess the data, train the model, and evaluate its performance.

3. **Save the Model and Artifacts**:
   Save the trained model and other artifacts (like the class dictionary) in the `artifacts` directory.

## Screenshots
![Screenshot 2024-11-27 124714](https://github.com/user-attachments/assets/5117dbbb-002d-43b8-899c-fea821c8ee8c)
![Screenshot 2024-11-27 124744](https://github.com/user-attachments/assets/328e8594-40d3-4de1-afac-389c3febb25c)

## Architecture
![Screenshot (372)](https://github.com/user-attachments/assets/fd001233-9586-4755-938e-50ed43359e6f)


## Contributing

Contributions are welcome! Please fork the repository and create a pull request with your changes.

### Guidelines

- Follow the existing code style.
- Write clear, concise commit messages.
- Ensure your code passes existing tests and add new tests for your changes.

## License

This project is licensed under the Apache 2.0 License. See the [LICENSE](LICENSE) file for details.

---
