
Diabetes Prediction API - README

## Overview
This project is a **Diabetes Prediction API** built using the **FastAPI** framework. It allows users to predict whether a person is diabetic based on various health parameters using a pre-trained machine learning model. The API accepts input in JSON format and returns a prediction as a string.

## Features
- **RESTful API** for diabetes prediction.
- Uses a **pre-trained model** for predictions (stored in `diabetes_model.sav`).
- **Pydantic** models for input validation.

---

## Installation

1. Clone the repository:
   ```bash
   git clone <repository_url>
   cd <repository_name>
   ```

2. Install dependencies:
   ```bash
   pip install fastapi pydantic uvicorn scikit-learn
   ```

3. Ensure the `diabetes_model.sav` file is present in the root directory.

---

## Usage

### Starting the Server
Run the FastAPI application:
```bash
uvicorn main:app --reload
```

- Replace `main` with the filename if it's different.
- The API will be available at: `http://127.0.0.1:8000`

### API Endpoint
#### `POST /diabetes_prediction`

- **Description**: Predicts whether a person is diabetic based on the provided input parameters.
- **Input**: JSON object with the following fields:
  - `pregnancies` (int): Number of pregnancies.
  - `Glucose` (int): Glucose level.
  - `BloodPressure` (int): Blood pressure level.
  - `SkinThickness` (int): Skin thickness measurement.
  - `Insulin` (int): Insulin level.
  - `BMI` (float): Body Mass Index.
  - `DiabetesPedigreeFunction` (float): Diabetes pedigree function.
  - `Age` (int): Age of the person.

- **Example Input**:
  ```json
  {
    "pregnancies": 3,
    "Glucose": 120,
    "BloodPressure": 80,
    "SkinThickness": 25,
    "Insulin": 130,
    "BMI": 28.5,
    "DiabetesPedigreeFunction": 0.627,
    "Age": 32
  }
  ```

- **Response**:
  - `"The person is diabetic"` if the prediction is positive.
  - `"The person is not diabetic"` if the prediction is negative.

---

## License
This project is open-source and available under the MIT License.
