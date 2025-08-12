
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

