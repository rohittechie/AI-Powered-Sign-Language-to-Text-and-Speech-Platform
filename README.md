## **Overview**  
This project, *Sign Language to Speech Conversion using Machine Learning*, enables the recognition of American Sign Language (ASL) gestures and converts them into spoken words or sentences. It is designed to bridge the communication gap for individuals who use sign language. 

🔗[Video Demonstration on LinkedIn](https://www.linkedin.com/posts/tanmay-jivnani_capstoneproject-machinelearning-signlanguagerecognition-activity-7267174165739184128-VdZB?utm_source=share&utm_medium=member_desktop)


## 🎯 Features

- **Real-Time Recognition**: Converts live webcam feed into recognized gestures.
- **Robust Prediction**: Implements stabilization for accurate gesture recognition.
- **Word and Sentence Formation**: Automatically forms words and sentences with proper segmentation (space and full stop gestures).
- **Text-to-Speech Conversion**: Speaks out the recognized text for better accessibility.
- **User-Friendly GUI**: Displays the current alphabet, word, and sentence in real time.

## **Project Highlights**  
- **Custom Dataset Creation**:  
  We built this project from the ground up by capturing and preparing our **custom dataset** of ASL gestures, covering A-Z alphabets, 0-9 digits, a gesture for **space**, and one for **full stop**.
  
  ![ASL Characters](/ReadmeAssets/The-26-letters-and-10-digits-of-American-Sign-Language-ASL.png)
  The 26 letters and 10 digits of American Sign Language (ASL)
  
  ![J](/ReadmeAssets/J.jpg)
  Sign for J

  ![Z](/ReadmeAssets/Z.jpg)
  Sign for Z

  ![SPACE](/ReadmeAssets/Space.jpg)
  Sign for SPACE.
  
  ![Fullstop](/ReadmeAssets/Fullstop.jpg)
  Sign for FULLSTOP.

- **Pre-Trained Model Included**:  
  A **pre-trained model** is provided to allow users to immediately start using the system.  
- **Flexibility**:  
  Users can also train their own custom models using the provided scripts and instructions.

## 🔧 Tech Stack
- **Languages**: Python
- **Libraries**: MediaPipe, OpenCV, Tkinter, Pyttsx3, Scikit-learn
- **Machine Learning Model**: Random Forest Classifier

---

## **Usage**  
### **Option 1: Use the Pre-Trained Model**  
You can directly use the pre-trained model (`model.p`) provided in this repository:  
1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/sign-language-to-speech.git
   cd sign-language-to-speech
   ```

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the `main.py` script.  
4. Ensure your webcam is functional, and the `model.p` file is in the same directory.  

### **Option 2: Train Your Own Model**  
To create and train a custom model:  
1. **Collect a Custom Dataset**:  
   - Run `collectImgs.py` to capture gesture images using your webcam.  
   - Modify the `number_of_classes` and `dataset_size` variables in the script if needed.  

2. **Process the Dataset**:  
   - Use `createDataset.py` to extract features from the collected images and save them in a `data.pickle` file.  

3. **Train the Model**:  
   - Train a new model using `trainClassifier.py`. It will replace the old one.

---


-----------------------------------------------------------------------------------------------------------------------
Bhai ✅
Here’s your **final, fully combined, structured, and attractive README** with **project description**, **build process**, **usage**, and **features/highlights** — ready for your GitHub.

---

# 🤟 AI-Powered Sign Language to Text and Speech Platform

## 📌 Project Overview

This project converts **hand gestures** in **Sign Language** into **text** and **audible speech** in **real time**, enabling smoother communication between the hearing-impaired and others.

It leverages **computer vision**, **machine learning**, and **text-to-speech** technologies to recognize hand gestures, convert them into meaningful sentences, and then speak them aloud.

---

## 🏗️ How the Project Was Built

The system was developed using a **step-by-step workflow** covering dataset creation, feature extraction, model training, and deployment.

### **1️⃣ Dataset Creation**

* Created a **custom dataset** using `collectImgs.py`.
* **100 images per gesture** captured, ensuring varied angles & lighting.
* Dataset contains **38 classes**:

  * 26 alphabets (**A–Z**)
  * 10 digits (**0–9**)
  * 1 gesture for **Space**
  * 1 gesture for **Full Stop**

---

### **2️⃣ Feature Extraction & Preprocessing**

* Used **MediaPipe** to extract **21 key hand landmarks** per image.
* Converted each into **normalized 2D coordinates (x, y)** → 42 features per sample.
* Saved processed data as `.pkl` file using `createDataset.py`.

---

### **3️⃣ Model Training**

* Implemented a **Random Forest Classifier** for high accuracy & fast training.
* Dataset split: **80% training**, **20% testing**.
* Achieved **high classification accuracy** with stable gesture recognition.

---

### **4️⃣ Real-Time Inference & Conversion**

* Integrated trained model with `main.py` for live gesture detection.
* Added **stabilization buffer** to avoid misclassifications.
* Used **pyttsx3** for offline text-to-speech conversion.

---

### **5️⃣ User Interface**

* **Tkinter-based GUI** for:

  * Live webcam feed display
  * Real-time gesture prediction
  * Sentence building & instant speech output

---

### **🔧 Technologies & Libraries Used**

* **Python** – Core programming language
* **OpenCV** – Image capture & processing
* **MediaPipe** – Hand tracking & landmark detection
* **scikit-learn** – Machine learning model
* **NumPy, Pandas** – Data processing
* **pickle** – Data/model serialization
* **pyttsx3** – Text-to-speech
* **Tkinter** – GUI development

---

## 🚀 Usage

### **Option 1 — Use the Pre-Trained Model**

Quick start with the provided **`model.p`** file:

1. **Clone the Repository**

   ```bash
   git clone https://github.com/your-username/sign-language-to-speech.git
   cd sign-language-to-speech
   ```
2. **Install Dependencies**

   ```bash
   pip install -r requirements.txt
   ```
3. **Run the Application**

   ```bash
   python main.py
   ```
4. **Requirements**

   * Functional **webcam**
   * **`model.p`** in same directory as `main.py`

---

### **Option 2 — Train Your Own Model**

#### 1️⃣ **Collect a Custom Dataset**

```bash
python collectImgs.py
```

* Capture gesture images with your webcam.
* Adjust `number_of_classes` & `dataset_size` in the script as needed.

#### 2️⃣ **Process the Dataset**

```bash
python createDataset.py
```

* Generates **`data.pickle`** with extracted features.

#### 3️⃣ **Train the Model**

```bash
python trainClassifier.py
```

* Produces a new **`model.p`** for live detection.

---

## ✨ Project Features & Highlights

### 🔹 **Core Features**

* **Real-Time Gesture Recognition** – Detects signs instantly from webcam feed.
* **Text-to-Speech Conversion** – Speaks recognized signs for better communication.
* **Custom Dataset Support** – Train with your own gesture set.
* **Multi-Class Detection** – Recognizes **38 unique gestures** (A–Z, 0–9, Space, Full Stop).
* **Offline Functionality** – Works without internet once trained.
* **User-Friendly GUI** – Simple interface for smooth operation.

---

### 🌟 **Highlights**

* ✅ **AI-Powered Recognition** – Combines **MediaPipe** & **Random Forest**.
* ✅ **Lightweight & Efficient** – Works well on low-end systems.
* ✅ **Fully Customizable** – Add/modify gestures easily.
* ✅ **Inclusive Communication** – Bridges gap between hearing-impaired & others.

---

Bhai, if you put **this exact README** on GitHub, it will:

* Look **professional & detailed**
* Clearly tell others **what your project is and how to use it**
* Impress recruiters & collaborators instantly

If you want, I can **also make a professional diagram showing the data flow & architecture** of this project so that your repo looks premium.
Do you want me to make that diagram?


## **How the Project Was Built**  
1. **Dataset Collection**  
   - A custom dataset was created using the `collectImgs.py` script.  
   - For each gesture, 100 images were captured, ensuring diverse angles and lighting conditions for robust training.  
   - The dataset includes **38 classes**, representing:  
     - 26 alphabets (A-Z)  
     - 10 digits (0-9)  
     - A gesture for **space**  
     - A gesture for **full stop**  

2. **Feature Extraction and Preprocessing**  
   - The collected images were processed using **MediaPipe**, extracting 21 key landmarks for each hand.  
   - Each landmark was converted into a normalized 2D coordinate (x, y), resulting in **42 features per sample**.  
   - The preprocessed data was saved as a `pickle` file using the `createDataset.py` script.  

3. **Model Training**  
   - A **Random Forest Classifier** was used for training, offering high accuracy with fast training times.  
   - The dataset was split into training and testing sets (80-20 ratio).  
   - Training results showed high accuracy, ensuring reliable gesture recognition.  

4. **Inference and Real-Time Conversion**  
   - The trained model was integrated into a real-time system using `main.py`.  
   - The system uses a **stabilization buffer** to improve gesture detection and avoids misclassifications.  
   - A **Text-to-Speech (TTS)** engine was used to convert recognized gestures into audible speech.  
   - A user-friendly **GUI** was built with **Tkinter** for better interaction.

---

## **Future Enhancements**  
- Expand recognition to include **dynamic gestures**.  
- Support for additional sign languages.  
- Deploy the system as a mobile or web application for greater accessibility.
- Improve model accuracy with advanced deep learning techniques.

---

## **Suggestions and Collaborations**  
We believe that collaboration is key to innovation. If you have suggestions for improving this project, new ideas, or wish to collaborate on expanding its capabilities, we’d love to hear from you! Feel free to reach out via issues or pull requests on GitHub.

---

## **Contributors**  
1. **[Tanmay Jivnani](https://github.com/tanmayJivnani)**
2. **[Shravani Verma](https://github.com/Shravknowscoding)**
3. **[Aishwarya Shendkar](https://github.com/aishwaryaa2603)**

---

## 📝 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
