# FreshGuard AI 🍎🥦

### AI-Powered Fruit and Vegetable Freshness Detection

FreshGuard AI is an AI-powered web application designed to help users assess the freshness of fruits and vegetables using image analysis and manual quality parameters. It uses machine learning and deep learning techniques to classify produce as **Good to Eat** or **Bad to Eat**.

The project provides two analysis methods: uploading an image for AI-based freshness prediction and entering quality-related details for machine learning-based prediction.

## ✨ Features

* **Image Analysis:** Upload a fruit or vegetable image to predict its freshness.
* **Manual Analysis:** Enter fruit characteristics and storage details to estimate freshness.
* **Confidence Score:** Displays the model's confidence percentage with the prediction.
* **User Login:** Sign in using your full name and email address or phone number.
* **Prediction History:** View previous predictions associated with your account.
* **Profile Management:** Access your saved user information.
* **Responsive Interface:** A user-friendly interface designed for desktop and mobile screens.
* **REST API:** Flask backend connects the frontend with trained AI models.

## 🧠 Machine Learning Models

FreshGuard AI uses two trained models for different types of analysis.

| Model                    | Purpose                              | Input                         |
| ------------------------ | ------------------------------------ | ----------------------------- |
| MobileNetV2              | Image-based freshness classification | Fruit or vegetable image      |
| Random Forest Classifier | Manual freshness classification      | Structured quality parameters |

### 1. MobileNetV2

A deep learning model used to analyze uploaded images and classify visible freshness conditions.

### 2. Random Forest Classifier

A supervised machine learning algorithm used to predict freshness from manually entered characteristics, such as fruit type, color, size, weight, firmness, sugar level, acidity, days since harvest, and storage temperature.

**Note:** Predictions are estimates based on the trained models. They do not guarantee food safety or detect invisible contamination.

## 🛠️ Technologies Used

**Frontend**

* React.js
* Vite
* HTML5
* CSS3
* JavaScript

**Backend**

* Python
* Flask
* REST API

**Machine Learning**

* TensorFlow / Keras
* MobileNetV2
* Scikit-learn
* Random Forest
* NumPy
* Pandas
* Joblib

**Tools**

* Visual Studio Code
* Git and GitHub
* Google Colab (for model development, if applicable)

## 📂 Project Structure

```text
FreshGuardAI/
│
├── backend/
│   ├── app.py
│   ├── model/
│   │   ├── FreshGuard_Good_Bad_MobileNetV2.keras
│   │   └── FreshGuard_random_forest.pkl
│   └── requirements.txt
│
├── frontend/
│   ├── index.html
│   ├── package.json
│   ├── src/
│   │   ├── App.jsx
│   │   ├── main.jsx
│   │   └── ...
│   └── ...
│
└── README.md
```

*The structure above is illustrative. Adjust file names and folders to match your actual GitHub repository.*

## ⚙️ Installation and Setup

### Prerequisites

Install the following before running the project:

* Python 3.10 or another version supported by your dependencies
* Node.js and npm
* Git

### Step 1: Clone the Repository

```bash
git clone https://github.com/vangatarunnagarevanth-afk/FreshGuardAI.git
cd FreshGuardAI
```

### Step 2: Set Up the Backend

Open a terminal in the project directory:

```bash
cd backend
```

Create and activate a virtual environment (recommended):

```bash
python -m venv venv
```

On Windows:

```bash
venv\Scripts\activate
```

Install the required Python dependencies:

```bash
pip install -r requirements.txt
```

If `requirements.txt` is missing, install the dependencies specified by your application, including Flask, TensorFlow, scikit-learn, NumPy, Pandas, and Joblib as applicable.

Start the backend:

```bash
python app.py
```

The backend should run on `http://localhost:5000` if configured with that port.

### Step 3: Set Up the Frontend

Open another terminal:

```bash
cd frontend
npm install
npm run dev
```

Open the local URL displayed by Vite, typically:

```text
http://localhost:5173/
```

Make sure the frontend API configuration points to the running backend.

## 🔌 API Endpoints

The Flask backend provides endpoints for image-based and manual analysis.

| Method | Endpoint          | Purpose                                          |
| ------ | ----------------- | ------------------------------------------------ |
| GET    | `/`               | Backend status, if configured                    |
| POST   | `/predict`        | Predict freshness from an uploaded image         |
| POST   | `/predict-manual` | Predict freshness from manual quality parameters |

### Image Prediction

**Endpoint:** `/predict`

Send an image using a multipart/form-data request with the field name expected by the backend.

Example response:

```json
{
  "prediction": "Good to Eat",
  "confidence": 78.28
}
```

### Manual Prediction

**Endpoint:** `/predict-manual`

Send the structured quality parameters in the request format expected by the backend.

Example response:

```json
{
  "prediction": "Good to Eat",
  "confidence": 100.0
}
```

The values above are illustrative examples of successful responses, not guaranteed results. A confidence score represents the model's output and should not automatically be interpreted as the probability that food is safe to eat.

## 🔄 How It Works

1. **User Input:** The user uploads an image or enters produce-quality information.
2. **Preprocessing:** Images are resized and normalized as required by the trained image model; manual inputs are validated and prepared for prediction.
3. **Model Prediction:** MobileNetV2 processes images, while the Random Forest model processes structured data.
4. **Classification:** The application returns either `Good to Eat` or `Bad to Eat`.
5. **Confidence Display:** The result is presented with a model confidence score.
6. **History:** Signed-in users can review previously saved predictions.

## 🎯 Project Objectives

* Apply artificial intelligence to fruit and vegetable freshness classification.
* Demonstrate the use of deep learning and traditional machine learning in one application.
* Provide an accessible interface for image-based and attribute-based analysis.
* Explore how computer vision and structured data can support produce-quality assessment.
* Develop a complete full-stack machine learning project.

## 🚀 Future Enhancements

* Expand the dataset to include more fruit and vegetable categories.
* Add artificial or plastic produce detection as a separate, trained classification task.
* Improve model accuracy using diverse images captured under different lighting conditions.
* Provide visual explanations highlighting potentially damaged or discolored regions.
* Add multilingual support.
* Deploy the application to a cloud platform.
* Improve validation using independent test datasets and additional evaluation metrics.
* Add food-safety guidance that clearly distinguishes visible freshness from actual safety.

## ⚠️ Limitations

* Classification quality depends on the training dataset and image conditions.
* Surface appearance alone cannot establish whether food is safe to consume.
* Manual predictions depend on the accuracy of user-entered values.
* The current models classify produce into `Good to Eat` and `Bad to Eat`; artificial produce detection requires a separately trained and validated model.
* Model confidence is not a substitute for laboratory testing or food-safety assessment.

## 👩‍💻 Contributors

Developed as an academic machine learning project to explore AI-powered fruit and vegetable freshness classification.

## 📄 License

Choose and add an appropriate open-source license if you intend to distribute or reuse the project publicly.

---

**FreshGuard AI — Smarter Freshness Assessment Through AI** 🍏
