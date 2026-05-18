# Software Defect Prediction System - Django Implementation

A comprehensive web application for predicting software defects using intelligent ensemble-based machine learning models built with Django.

## 🚀 Features

- **Web Interface**: Modern Bootstrap-based UI for easy interaction
- **Machine Learning Pipeline**: Ensemble model combining Random Forest, Gradient Boosting, and XGBoost
- **Real-time Training**: Background model training with progress tracking
- **Prediction API**: RESTful API for making defect predictions
- **Data Management**: Store and manage software modules and prediction history
- **Model Evaluation**: Comprehensive performance metrics and visualization
- **Admin Interface**: Django admin for data management

## 🛠 Tech Stack

- **Backend**: Django 4.2, Django REST Framework
- **Frontend**: Bootstrap 5, JavaScript, Chart.js
- **Machine Learning**: scikit-learn, XGBoost, pandas, numpy
- **Database**: SQLite (development), PostgreSQL (production)
- **Deployment**: Docker, Gunicorn

## 📋 Requirements

- Python 3.8+
- Django 4.2+
- See `requirements.txt` for full dependencies

## 🔧 Installation

### Option 1: Quick Setup

\`\`\`bash
# Clone the repository
git clone <repository-url>
cd django-defect-prediction

# Run setup script
python scripts/setup_project.py

# Start the development server
python manage.py runserver
\`\`\`

### Option 2: Manual Setup

\`\`\`bash
# Install dependencies
pip install -r requirements.txt

# Run migrations
python manage.py makemigrations
python manage.py migrate

# Create superuser
python manage.py createsuperuser

# Collect static files
python manage.py collectstatic

# Start server
python manage.py runserver
\`\`\`

### Option 3: Docker Setup

\`\`\`bash
# Build and run with Docker Compose
docker-compose up --build

# Access the application at http://localhost:8000
\`\`\`

## 🎯 Usage

### 1. Access the Application
- Main application: http://localhost:8000
- Admin interface: http://localhost:8000/admin

### 2. Train Models
1. Navigate to the "Train Models" section
2. Click "Start Training" to begin the ML pipeline
3. Monitor progress in real-time
4. View training results and model performance

### 3. Make Predictions
1. Go to "Predict Defects" section
2. Upload CSV data with software metrics
3. Click "Predict Defects" to get results
4. View detailed predictions with risk levels

### 4. View Evaluation
- Check "Model Evaluation" for comprehensive metrics
- Compare different model performances
- View confusion matrices and accuracy scores

## 📊 Data Format

Your CSV data should include these columns:

\`\`\`csv
Module_ID,LOC,Cyclomatic_Complexity,Num_Functions,Halstead_Volume,Maintainability_Index
M1,120,8,5,350.6,75.3
M2,230,12,10,480.2,60.8
\`\`\`

### Required Columns:
- **Module_ID**: Unique identifier for the software module
- **LOC**: Lines of Code
- **Cyclomatic_Complexity**: Measure of code complexity
- **Num_Functions**: Number of functions in the module
- **Halstead_Volume**: Halstead complexity metric
- **Maintainability_Index**: Code maintainability score

## 🔌 API Endpoints

### Prediction API
\`\`\`bash
POST /api/predict/
Content-Type: application/json

{
  "csv_data": "Module_ID,LOC,Cyclomatic_Complexity,Num_Functions,Halstead_Volume,Maintainability_Index\nM1,120,8,5,350.6,75.3"
}
\`\`\`

### Training API
\`\`\`bash
# Start training
POST /api/train/

# Check training status
GET /api/train/?training_id=1
\`\`\`

### Other APIs
- `GET /api/evaluation/` - Get model evaluation metrics
- `GET /api/stats/` - Get dashboard statistics
- `GET /api/history/` - Get prediction history
- `GET /api/modules/` - Get software modules

## 🏗 Project Structure

\`\`\`
django-defect-prediction/
├── defect_prediction/          # Django project settings
├── prediction/                 # Main Django app
│   ├── models.py              # Database models
│   ├── views.py               # API views and logic
│   ├── ml_models.py           # Machine learning pipeline
│   ├── serializers.py         # API serializers
│   └── urls.py                # URL routing
├── templates/                  # HTML templates
├── static/                     # Static files (CSS, JS)
├── scripts/                    # Setup and utility scripts
├── requirements.txt            # Python dependencies
├── Dockerfile                  # Docker configuration
└── docker-compose.yml         # Docker Compose setup
\`\`\`

## 🧠 Machine Learning Pipeline

### 1. Data Preprocessing
- Feature engineering (complexity per function, LOC per function, etc.)
- Data scaling using StandardScaler
- Train/test split with stratification

### 2. Base Models
- **Random Forest**: Ensemble of decision trees
- **Gradient Boosting**: Sequential weak learners
- **XGBoost**: Optimized gradient boosting

### 3. Ensemble Model
- **Voting Classifier**: Combines all base models
- **Soft Voting**: Uses prediction probabilities
- **Performance**: Typically achieves 85-95% accuracy

### 4. Evaluation Metrics
- AUC-ROC Score
- Precision, Recall, F1-Score
- Confusion Matrix
- Accuracy

## 🚀 Deployment

### Production Settings
1. Set `DEBUG = False` in settings.py
2. Configure proper database (PostgreSQL)
3. Set up static file serving
4. Use environment variables for secrets

### Docker Deployment
\`\`\`bash
# Production build
docker-compose -f docker-compose.prod.yml up --build

# With environment variables
docker-compose --env-file .env.prod up
\`\`\`

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🆘 Support

For support and questions:
- Create an issue on GitHub
- Check the documentation
- Review the API endpoints

## 🔮 Future Enhancements

- [ ] Real-time model retraining
- [ ] Advanced visualization dashboards
- [ ] Integration with CI/CD pipelines
- [ ] Support for more ML algorithms
- [ ] Automated feature selection
- [ ] Model explainability features
