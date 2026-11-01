# Mansik-Santulan-Score
🧠 Mental Health Score Prediction
An end-to-end Machine Learning project that estimates a student's mental health score from lifestyle, academic, social-media usage, and self-reported stress-related factors.

The project combines a trained machine-learning model with a FastAPI backend and a simple HTML, CSS, and JavaScript frontend to demonstrate how an ML model can be used to generate predictions through a web interface.
Disclaimer: This project is for educational and informational purposes only. Its output is not a medical diagnosis, psychological assessment, or substitute for advice from a qualified healthcare professional.

📌 Project Overview
Mental well-being can be associated with several aspects of everyday life, including sleep, physical activity, study routine, digital habits, and perceived stress. This project explores how these features can be used by a supervised machine-learning model to estimate a mental health score.
Objectives
- Explore and prepare lifestyle and behavioral data for machine learning.
- Build and use a trained model to predict a numerical mental health score.
- Validate user inputs before passing them to the model.
- Serve predictions through a REST API built with FastAPI.
- Connect the API to a browser-based interface.
✨ Features
- Score prediction: Estimates a mental health score from user-provided information.
- Multiple input factors: Uses demographic, academic, social-media, activity, sleep, and stress-related features.
- Input validation: Uses Pydantic to validate API request fields and accepted values.
- REST API: Exposes a /predict endpoint for model inference.
- Web interface: HTML, CSS, and JavaScript files provide the frontend.
- Reusable trained model: Loads the saved model from Mental_Health_Model.pkl.
- Country grouping: Maps countries outside the configured set of common countries to an Other category.
🧾 Input Features
The API accepts the following fields:
Feature	Description
age	User's age
gender	Gender (Male or Female)
country	Country
academic_level	Academic level (Undergraduate, Graduate, or High School)
most_used_platform	Most-used social media platform
purpose_of_use	Main purpose (Networking, Education, Entertainment, or News)
avg_daily_usage_hours	Average daily social-media usage in hours
daily_unlocks	Number of daily phone unlocks
study_hours	Daily study hours
physical_activity_hours	Daily physical activity in hours
sleep_hours_per_night	Sleep duration per night in hours
stress_level	Self-reported stress (Low, Medium, High, or Very High)


The API validates numeric ranges for fields such as age and daily hours, along with the allowed values for categorical fields.
🛠️ Technology Stack
Area	Technologies
Programming language	Python
Data handling	Pandas
Machine learning	Scikit-learn
Model persistence	Joblib
Backend / REST API	FastAPI
Request validation	Pydantic
API server	Uvicorn
Frontend	HTML5, CSS3, JavaScript
Development / analysis	Jupyter Notebook


🔄 Machine Learning Workflow
1. Data exploration — examine the dataset and understand the available features.
2. Data preprocessing — prepare numerical and categorical inputs for model training.
3. Model training — train a supervised machine-learning model to predict the target score.
4. Model persistence — save the trained model so it can be loaded by the API.
5. API development — load the model in FastAPI and define a /predict endpoint.
6. Input validation — validate incoming data using a Pydantic model.
7. Prediction — transform the request into a DataFrame, generate a prediction, and return the score rounded to two decimal places.
8. Frontend integration — use the web interface to collect inputs and communicate with the prediction service.
📁 Repository Structure
Mental_Health_Score_Prediction/
├── ML_Project.ipynb
├── ML Project.html
├── Mental_Health_Model.pkl
├── Student Social Media And Mental Health Impact.csv
├── main.py
├── requirements.txt
├── index.html
├── style.css
├── script.js
└── README.md
- ML_Project.ipynb — notebook containing the machine-learning work.
- ML Project.html — HTML export of the notebook.
- Student Social Media And Mental Health Impact.csv — dataset used in the project.
- Mental_Health_Model.pkl — saved model loaded by the API.
- main.py — FastAPI application and prediction endpoint.
- requirements.txt — Python dependencies.
- index.html, style.css, script.js — frontend files.
🚀 Getting Started
Prerequisites
- Python 3.9 or a compatible Python version
- pip
- A modern web browser
1. Clone the repository
git clone https://github.com/pramodsharma7851-collab/Mental_Health_Score_Prediction.git
cd Mental_Health_Score_Prediction
2. Create and activate a virtual environment (recommended)
Windows:
python -m venv venv
venv\Scripts\activate
macOS / Linux:
python3 -m venv venv
source venv/bin/activate
3. Install dependencies
pip install -r requirements.txt
4. Start the API
Run this command from the project directory, where main.py and Mental_Health_Model.pkl are located:
uvicorn main:app --reload
The API will usually be available at:
- API base: http://127.0.0.1:8000
- Interactive API documentation: http://127.0.0.1:8000/docs
5. Open the frontend
Open index.html in your browser. The frontend must be configured to send requests to the running API. If the page cannot connect to the API, check the API URL in script.js and ensure that it points to the correct local server and /predict endpoint.
Note: The backend and frontend must use matching API addresses and request fields. Browser and deployment security settings may also affect cross-origin requests.

🔌 API Usage
The prediction endpoint is:
POST /predict
Example request body:
{
  "age": 21,
  "gender": "Male",
  "country": "India",
  "academic_level": "Undergraduate",
  "most_used_platform": "Instagram",
  "purpose_of_use": "Education",
  "avg_daily_usage_hours": 3.5,
  "daily_unlocks": 50,
  "study_hours": 4,
  "physical_activity_hours": 1,
  "sleep_hours_per_night": 7.5,
  "stress_level": "Medium"
}
Example response format:
{
  "predicted_mental_health_score": 7.25
}
The score shown above is only an illustrative response format, not a guaranteed prediction. Actual output depends on the saved model and the supplied input.

You can explore and test the endpoint through FastAPI's interactive documentation at /docs after starting the server.
⚠️ Limitations and Responsible Use
- The model learns patterns from its training dataset; predictions may not generalize to every person or population.
- Relationships in observational data do not establish that a lifestyle factor causes a particular mental health outcome.
- The score should not be interpreted as a clinical diagnosis or definitive measure of mental health.
- The application should not be used as the sole basis for healthcare, educational, employment, or other consequential decisions.
- Protect personal information when testing or extending the project.
🔮 Possible Future Improvements
- Add a clear description of the target score and how it is measured.
- Document model-selection experiments and report test-set metrics after verifying them.
- Add feature-importance or explainability visualizations.
- Improve automated tests for preprocessing and API validation.
- Pin dependency versions for more reproducible model loading.
- Deploy the frontend and API with documented configuration and a working demo link.
👨‍💻 Author
Pramod Sharma
- GitHub: @pramodsharma7851-collab
- Project repository: Mental_Health_Score_Prediction
If you find this project useful, consider giving the repository a ⭐ on GitHub.
