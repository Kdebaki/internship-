# Face Recognition System

This project uses **Google Teachable Machine** to train a model for face recognition and integrates it with **OpenCV** for real-time image processing. The trained model identifies individuals based on webcam input.

---

## Features
- Real-time face recognition using a webcam.
- Custom-trained model with Google Teachable Machine.
- Confidence-based prediction for accurate results.

---

## Technologies Used
- **Python**: Programming language for implementing the system.
- **OpenCV**: For capturing and processing webcam images.
- **TensorFlow/Keras**: For loading and using the trained face recognition model.
- **Google Teachable Machine**: For training the face recognition model.


## Prerequisites
Ensure you have the following installed:
- **Python 3.7 or higher**
- Required Python libraries:
  - `opencv-python`
  - `numpy`
  - `tensorflow`

---

## Installation

### **Step 1: Clone the Repository**
Download the project files:
```bash
git clone https://github.com/username/face-recognition-system.git
cd face-recognition-system
```
![image](https://github.com/user-attachments/assets/a016fe25-f81e-4257-9057-86099225368f)

### **2. Install dependencies:**
   ```bash
   pip install -r requirements.txt
```
![image](https://github.com/user-attachments/assets/bcd68c81-1c2e-4db7-8700-392aab26440b)
### **3. Place the following files in the project directory:**
   - `keras_model.h5` (Trained model file)
   - `labels.txt` (Labels corresponding to the trained model)

## How It Works
### Face Recognition:
-The webcam captures video frames.
-Each frame is resized and preprocessed for the model.
-The trained model predicts the identity of the person based on the captured frame.

### Model Prediction:
-The system compares the processed frame with the trained classes.
-If the confidence score is above the threshold (e.g., 95%), it displays the recognized name and confidence.

## Training the model:
Training a model using Google's Teachable Machine is a straightforward process that allows you to create machine learning models without extensive coding knowledge. Here's how you can get started:

Step 1: Access Teachable Machine

Open your browser and visit Teachable Machine.
![image](https://github.com/user-attachments/assets/3d531afa-83f4-4b11-9bc1-23937984934d)

Step 2: Choose a Project Type

Click "Get Started".
![image](https://github.com/user-attachments/assets/36c9d313-85bd-4e83-9ae6-f4cd16f33d99)

Select Image Project since you’re working with face recognition.

Step 3: Add Classes
You’ll see two default classes (Class 1, Class 2). These represent the categories your model will classify.

Rename the classes to meaningful names like:

Your Name (e.g., "John")


Another Person (e.g., "Alice")

Background (optional, for cases where no face is detected).

Add more classes by clicking "Add a Class" if needed.
![image](https://github.com/user-attachments/assets/de4ec51d-7c60-483c-9fbb-ccae466001d6)

Step 4: Collect Images for Each Class
Use your webcam or upload images for each class:

Using Webcam:

Click "Webcam" under the desired class.

Collect images of yourself or another person by holding the button.

Take images from multiple angles (front, left, right) and in different lighting conditions.

Step 5: Train the Model

Once images for all classes are collected, click "Train Model".

The system will train the model using your provided data. This usually takes a few seconds to a couple of minutes, depending on the number of images.
![image](https://github.com/user-attachments/assets/fb1fb6c2-677e-4028-8df5-062a74c116c4)

Step 6: Test the Model

Use the Preview Webcam option to test the model in real-time.

Ensure the model correctly identifies faces for each class.

If the accuracy is low:

Add more training images, especially for poorly performing classes.

Include diverse conditions (e.g., different lighting, angles).
![image](https://github.com/user-attachments/assets/048b8598-f4ae-4619-b85e-b48af0701dda)

Step 7: Export the Model
Once you’re satisfied with the accuracy:
Click "Export Model".
![image](https://github.com/user-attachments/assets/3f73fed0-a278-4422-9e85-3c86c8fd831e)

Choose the TensorFlow tab (for integration with Python).

Download the following files:
![image](https://github.com/user-attachments/assets/6914d897-de04-4c0a-9537-9005d7cfb9b7)

keras_model.h5: The trained model file.

labels.txt: Contains the class names.

Step 8: Integrate the Model into Your Code
Place keras_model.h5 and labels.txt in your project directory.
Modify the code to load the model and use it for face recognition.
![image](https://github.com/user-attachments/assets/43b86731-3b81-4b10-a47f-3a2f7dbfa0d9)

### Tips for Better Accuracy
Lighting: Train the model with images in varied lighting conditions.
Angles: Capture images from different angles for better generalization.
Diverse Expressions: Include a range of facial expressions.
Class Balance: Ensure all classes have a similar number of images to avoid bias.

## Running the Program
To start the face recognition system, execute the following command:
```bash
python face_recognition.py
```
### Project Files
face_recognition.py: Main Python script for running the face recognition system.

keras_model.h5: Trained face recognition model.


labels.txt: Labels for the trained model.

requirements.txt: List of Python libraries to install.

README.md: Documentation for the project.

### Future Enhancements
Improve model accuracy by adding more training data.

Implement a graphical user interface (GUI) for ease of use.

Extend functionality to recognize multiple people in the same frame.

## License
This project is licensed under the MIT License. Feel free to use and modify it as needed.

## Acknowledgements
Google Teachable Machine for easy model training.

OpenCV for real-time image processing.

TensorFlow for deploying the trained model.
