# Real-Time Sign Language Recognition System

This project uses **MediaPipe**, **OpenCV**, and **LSTM-based deep learning** to recognize hand gestures (signs) from a webcam feed and classify them into predefined actions (like letters A, B, C). It captures hand landmarks using MediaPipe, processes them into structured data, trains a model, and performs real-time gesture recognition.

---

##  Key Features

-  Hand landmark detection using MediaPipe
-  Real-time gesture recognition via webcam
-  LSTM-based gesture classification model
-  Structured dataset collection (numpy-based)
-  Action mapping (e.g., A, B, C signs)
-  TensorBoard logging support for model training
-  Modular codebase with reusable `function.py`

---

## Project Structure
SignLanguageRecognition/
├── collectdata.py # Record gesture data using webcam
├── data.py # Convert images to keypoints numpy arrays
├── trainmodel.py # Train LSTM model on the keypoints
├── app.py # Run the real-time recognition system
├── model.json # Saved model architecture
├── model.h5 # Trained model weights
├── function.py # All reusable helper functions
├── MP_Data/ # Numpy array dataset (auto-generated)
├── Image/ # Raw gesture image data (if any)
├── Logs/ # TensorBoard training logs
├── requirements.txt
└── README.md


---

## 📦 Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/SignLanguageRecognition.git
   cd SignLanguageRecognition

Install dependencies:

bash
Copy
Edit
pip install -r requirements.txt


Usage Guide
🔹 Step 1: Data Collection please download the Sign from any Open Source Image of A B C Of Hand Gesture
bash
Copy
Edit
python collectdata.py

Step 2: Convert Images to Numpy Arrays
bash
Copy
Edit
python data.py

: Train the LSTM Model
bash
Copy
Edit
python trainmodel.py


You can launch TensorBoard via:

bash
Copy
Edit
tensorboard --logdir=Logs/

Run Real-Time Prediction
bash
Copy
Edit
python app.py


Model Architecture
text
Copy
Edit
Input: 30 frames x 63 keypoints (21 hand landmarks × 3 [x, y, z])
→ LSTM (64) → LSTM (128) → LSTM (64)
→ Dense (64) → Dense (32)
→ Output: Softmax over actions (A, B, C)


 Example Output
Model prints real-time prediction like:

css
Copy
Edit
A
B
C

Requirements
Example requirements.txt:

txt
Copy
Edit
opencv-python
mediapipe
numpy
pandas
keras
tensorflow
scikit-learn

Install them via:

bash
Copy
Edit
pip install -r requirements.txt

Customization
Add more actions by updating:

python
Copy
Edit
actions = np.array(['A', 'B', 'C', 'Hello', 'Yes', 'No'])

