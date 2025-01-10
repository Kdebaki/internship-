## How to Train, Download and Use
1. **training the model**:

Training a model using Google's Teachable Machine is a straightforward process that allows you to create machine learning models without extensive coding knowledge. Here's how you can get started:

Access Teachable Machine:
Navigate to the Teachable Machine website.
![image](https://github.com/user-attachments/assets/bd231120-86ee-4fa1-8983-11f757856359)

Choose a Project Type:
![image](https://github.com/user-attachments/assets/3c01eac4-e2f6-4c34-a2f8-8d8f993ed606)

Select the type of model you wish to train:

Image Project: For classifying images.
![image](https://github.com/user-attachments/assets/f40d4c20-c5f4-4989-b32a-0a29ccbd049e)

For Image Projects:
Upload images from your device or use your webcam to capture photos directly into each class.
![image](https://github.com/user-attachments/assets/0b34b66c-9237-424e-84eb-3743841f4dbb)

Once you've gathered sufficient data for each class, click the "Train Model" button.
The platform will process the data and train a model based on your inputs.
![image](https://github.com/user-attachments/assets/af7fbc85-a260-49aa-9336-401f3eb9f3fc)

Test the Model:

After training, test your model by providing new inputs (images, sounds, or poses) to see how accurately it classifies them.
Export the Model:
![image](https://github.com/user-attachments/assets/91770d4e-9af9-4fb8-9b47-011ec46f3e52)


If you're satisfied with the model's performance, you can export it for use in various applications.
Teachable Machine offers options to download the model or host it online.

1. **Download the Files**:
   - Click the green **Code** button at the top of the repository.
   - ![image](https://github.com/user-attachments/assets/597b4581-f49a-4c25-bfd2-4d71bf3c902e)

   - Select **Download ZIP** to download the project files.
   - ![image](https://github.com/user-attachments/assets/43d7a272-21c3-4968-a663-2f54fa4c53b3)

   - Extract the ZIP file to your desired location.
   - make sure the keras model and labels are also in the same directory

2. **Run the Project**:
   - Open the attendance_record file ( `code.py`) to launch the application.
   - ![image](https://github.com/user-attachments/assets/b9b03de3-067b-4d7c-8ca6-033c679c71cd)

   - install necessary libraries in the terminal 
   - pip install mysql-connector-python
   - pip install tensorflow==2.10.0
   - pip install opencv-python==4.5.5.64
   - pip install numpy==1.21.6
   - run the code
3. **Customize as Needed**:
   - Edit files to fit your requirements.
   - Add custom branding or functionality.
   - 
3. **Code Explaination**:
4. This Python script utilizes TensorFlow's Keras API and OpenCV to perform real-time image classification through a webcam. Here's a breakdown of its functionality:

Import Necessary Libraries:

tensorflow.keras.models: For loading the pre-trained Keras model.
cv2 (OpenCV): For accessing the webcam and handling image processing tasks.
numpy: For numerical operations, particularly array manipulations.
Configure Numpy Print Options:

np.set_printoptions(suppress=True): Disables scientific notation in numpy printouts for better readability.
Load the Pre-trained Model:

model = load_model("keras_Model.h5", compile=False): Loads the pre-trained Keras model from the specified .h5 file without compiling it, as it's unnecessary for inference.
Load Class Labels:

class_names = open("labels.txt", "r").readlines(): Reads the class labels from labels.txt into a list, where each line corresponds to a class name.
Initialize Webcam:

camera = cv2.VideoCapture(0): Opens a connection to the default webcam (device 0).
Real-time Image Processing Loop:

The script enters an infinite loop to continuously capture frames from the webcam.
ret, image = camera.read(): Captures a frame from the webcam.
image = cv2.resize(image, (224, 224), interpolation=cv2.INTER_AREA): Resizes the captured image to 224x224 pixels, matching the input size expected by the model.
cv2.imshow("Webcam Image", image): Displays the resized image in a window titled "Webcam Image".
Pre-process the Image:

image = np.asarray(image, dtype=np.float32).reshape(1, 224, 224, 3): Converts the image to a numpy array of type float32 and reshapes it to match the model's input dimensions.
image = (image / 127.5) - 1: Normalizes the image data to the range [-1, 1], assuming the model was trained with this normalization.
Model Prediction:

prediction = model.predict(image): Feeds the pre-processed image into the model to obtain predictions.
index = np.argmax(prediction): Identifies the index of the highest confidence score in the prediction array.
class_name = class_names[index]: Retrieves the class name corresponding to the highest confidence score.
confidence_score = prediction[0][index]: Extracts the confidence score for the predicted class.
Display Prediction and Confidence:

Prints the predicted class name and its confidence score to the console.
Exit Condition:

keyboard_input = cv2.waitKey(1): Listens for keyboard input.
If the 'Esc' key (ASCII code 27) is pressed, the loop breaks, terminating the program.
Release Resources:

camera.release(): Releases the webcam resource.
cv2.destroyAllWindows(): Closes any OpenCV windows opened during execution.


## Contribution
Feel free to contribute to this project by submitting a pull request or opening an issue.

---
