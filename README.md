Software Defect Prediction System

A web-based defect prediction system built using Django and Machine Learning to predict software defects from uploaded software metrics.
The project provides REST APIs, real-time predictions, asynchronous model training, and analytics dashboards for monitoring model performance.

Features
Upload software metrics for defect analysis
Predict software defects in real time using machine learning models
REST APIs for data upload and prediction
Asynchronous model training using background threading
Training logs and evaluation metric tracking
Dashboard for prediction history and analytics
Model performance visualization
Tech Stack
Python
Django
Django REST Framework
Pandas
Scikit-learn
Machine Learning
REST API
Project Modules
1. Metrics Upload
Upload software metrics dataset
Validate and preprocess input data
2. Defect Prediction
Predict whether a software module is defective or not
Generate predictions using trained ML models
3. Model Training
Train machine learning models asynchronously
Store training logs and status updates
4. Dashboard Analytics
View evaluation metrics
Monitor training logs
Track prediction history
Machine Learning Workflow
Dataset Upload
Data Preprocessing
Feature Selection
Model Training
Model Evaluation
Real-Time Prediction
API Features
Dataset upload API
Model training API
Prediction API
Logs and analytics API
Installation
git clone https://github.com/your-username/software-defect-prediction.git

cd software-defect-prediction

pip install -r requirements.txt

python manage.py migrate

python manage.py runserver
Usage
Start the Django server
Upload software metrics dataset
Train the machine learning model
Use prediction APIs for defect analysis
Monitor logs and analytics from dashboard
Future Enhancements
Add deep learning models
Deploy using Docker and cloud platforms
Add user authentication and role management
Improve dashboard visualizations
Support multiple datasets and models
Author

Developed by Durgeshwar Gadila
