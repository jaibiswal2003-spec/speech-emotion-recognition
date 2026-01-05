# 🎵 Speech Emotion Recognition (Streamlit App)

This project detects human emotions (like **happy**, **sad**, **angry**, etc.) from speech using **MFCC feature extraction** and a **Random Forest Classifier** — all wrapped in a simple, interactive **Streamlit web app**.

---

## 🚀 Features
- 🎙️ Record voice directly in Streamlit  
- 📁 Upload `.wav` audio files  
- 🔍 Extracts MFCC (Mel Frequency Cepstral Coefficients) features  
- 🧠 Trains or loads a Random Forest emotion classifier  
- 💾 Automatically saves trained model for reuse  
- 🧮 Displays training accuracy  

---

## 🧰 Tech Stack
- **Python 3.8+**
- **Streamlit**
- **Librosa**
- **SoundFile / SoundDevice**
- **NumPy**
- **scikit-learn**
- **Joblib**

---

## 📂 Project Setup

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/jaibiswal2003-spec/speech-emotion-recognition.git
cd speech-emotion-recognition
```

### 2️⃣ Create and Activate Virtual Environment
```bash
python -m venv venv
venv\Scripts\activate  # For Windows
# or
source venv/bin/activate  # For Mac/Linux
```

### 3️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```

### 4️⃣ Download the Dataset
- Download the **RAVDESS Speech Emotion Dataset** (Ryerson Audio-Visual Database of Emotional Speech and Song).  
- You can get it from Kaggle or Zenodo:
  - [Kaggle Link](https://www.kaggle.com/uwrfkaggler/ravdess-emotional-speech-audio)
- Extract it and **rename the folder** to:
  ```
  speech/
  ```
  Place it inside your project root directory, so structure looks like:
  ```
  ├── speech/
  │   ├── Actor_01/
  │   ├── Actor_02/
  │   └── ...
  ├── app.py
  ├── requirements.txt
  └── README.md
  ```

### 5️⃣ Run the Streamlit App Locally
```bash
streamlit run app.py
```

This will open a local web app in your browser.

---

## 🧠 How It Works
1. **Feature Extraction:** Uses `librosa` to compute 40 MFCC features per audio clip.  
2. **Model Training:** If a pre-trained model (`models/rf_emotion_model.pkl`) exists, it loads it. Otherwise, it trains a new Random Forest model on the RAVDESS dataset.  
3. **Prediction:** The app lets you either:
   - Record your voice using `sounddevice`, or  
   - Upload a `.wav` file  
   The extracted MFCCs are passed to the trained model to predict the emotion.

---

## 📊 Supported Emotion Labels
| Code | Emotion   |
|------|------------|
| 01 | Neutral |
| 02 | Calm |
| 03 | Happy |
| 04 | Sad |
| 05 | Angry |
| 06 | Fearful |
| 07 | Disgust |
| 08 | Surprised |

---

## 🪄 Tips
- Ensure your **microphone is enabled** when recording.
- If Streamlit throws an error for audio device or ffmpeg, install ffmpeg and add it to your PATH.
- You can delete `models/rf_emotion_model.pkl` anytime to retrain from scratch.

---

## 🧑‍💻 Author
**JAIPRAKASH**
Full Stack & AI Developer  
[GitHub](https://github.com/jaibiswal2003)

---

## 📜 License
This project is open-source and available under the [MIT License](LICENSE).
