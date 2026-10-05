# 🏥 Patient Management System API

A simple **Patient Management System REST API** built using **FastAPI, Pydantic, and JSON**.

This project demonstrates how to build a backend API with patient data management, data validation, BMI calculation, sorting, patient creation, and patient updates.

## 🚀 Features

* Create a new patient
* View all patients
* View a specific patient by ID
* Update patient information
* Sort patients by height, weight, or BMI
* Automatic BMI calculation
* Automatic BMI health verdict
* Pydantic data validation
* JSON file-based data storage
* HTTP error handling
* Swagger API documentation

## 🛠️ Technologies Used

* Python
* FastAPI
* Pydantic
* Uvicorn
* JSON
* REST API

## 📁 Project Structure

```text
patient-management-system/
│
├── main.py
├── patients.json
├── requirements.txt
└── README.md
```

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/your-username/patient-management-system.git
```

### 2. Open the project

```bash
cd patient-management-system
```

### 3. Create a virtual environment

```bash
python -m venv venv
```

### 4. Activate the virtual environment

**Windows:**

```bash
venv\Scripts\activate
```

**Mac/Linux:**

```bash
source venv/bin/activate
```

### 5. Install dependencies

```bash
pip install -r requirements.txt
```

## ▶️ Run the Application

Start the FastAPI server:

```bash
uvicorn main:app --reload
```

The API will run at:

```text
http://127.0.0.1:8000
```

## 📚 API Documentation

FastAPI automatically provides interactive API documentation.

### Swagger UI

```text
http://127.0.0.1:8000/docs
```

### ReDoc

```text
http://127.0.0.1:8000/redoc
```

## 🔗 API Endpoints

| Method | Endpoint                | Description                |
| ------ | ----------------------- | -------------------------- |
| GET    | `/`                     | API welcome message        |
| GET    | `/about`                | API information            |
| GET    | `/view`                 | View all patients          |
| GET    | `/patient/{patient_id}` | View a specific patient    |
| GET    | `/sort`                 | Sort patients              |
| POST   | `/create`               | Create a new patient       |
| PUT    | `/edit/{patient_id}`    | Update patient information |

## 🧑‍⚕️ Patient Data

A patient contains:

```json
{
    "id": "P001",
    "name": "Rahul",
    "city": "Delhi",
    "age": 25,
    "gender": "male",
    "height": 1.75,
    "weight": 70
}
```

The API automatically calculates:

```text
BMI = weight / height²
```

For example:

```text
BMI = 70 / (1.75²)
BMI = 22.86
```

The system also generates a health verdict:

* Underweight
* Normal
* Overweight
* Obese

## ➕ Create Patient

**POST**

```text
/create
```

Example request:

```json
{
    "id": "P006",
    "name": "Amit",
    "city": "Gurugram",
    "age": 24,
    "gender": "male",
    "height": 1.75,
    "weight": 72
}
```

## 🔍 View Patient

**GET**

```text
/patient/P001
```

This returns information about patient `P001`.

## 🔄 Update Patient

**PUT**

```text
/edit/P001
```

You can update one or more fields.

Example:

```json
{
    "weight": 75
}
```

The API validates the updated patient information and recalculates BMI automatically.

## 📊 Sort Patients

### Sort by height

```text
/sort?sort_by=height&order=asc
```

### Sort by weight

```text
/sort?sort_by=weight&order=desc
```

### Sort by BMI

```text
/sort?sort_by=bmi&order=asc
```

Supported sorting fields:

```text
height
weight
bmi
```

Supported orders:

```text
asc
desc
```

## ✅ Data Validation

Pydantic validates patient information before processing it.

Examples:

* Age must be greater than `0` and less than `120`
* Height must be greater than `0`
* Weight must be greater than `0`
* Gender must be `male`, `female`, or `others`
* Patient ID must be unique

Invalid data automatically returns a validation error.

## 💾 Data Storage

For simplicity, this project uses a local `patients.json` file as the database.

The application:

```text
Request
   ↓
FastAPI
   ↓
Pydantic Validation
   ↓
patients.json
   ↓
JSON Response
```

This project uses JSON for learning purposes. In a production application, a database such as **PostgreSQL, MySQL, or MongoDB** would be more appropriate.

## 🎯 Learning Objectives

This project helped me practice:

* FastAPI fundamentals
* REST API development
* GET, POST, and PUT requests
* Path parameters
* Query parameters
* Pydantic models
* Optional fields
* Data validation
* Computed fields
* HTTP exceptions
* JSON data handling
* API documentation with Swagger
* CRUD-style backend development

## 🔮 Future Improvements

* Add DELETE patient endpoint
* Replace JSON storage with PostgreSQL
* Add SQLAlchemy ORM
* Add authentication and authorization
* Add JWT authentication
* Add pagination
* Add search and filtering
* Add Docker support
* Deploy the API to a cloud platform

## 👨‍💻 Author

**Sumit Kumar**

B.Tech CSE (AI & ML)

---

⭐ If you find this project useful, consider giving the repository a star!
