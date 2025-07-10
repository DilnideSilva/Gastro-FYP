# GastroSphere - Getting Started Guide

## Prerequisites
- Java 17+ (for Spring Boot)
- Python 3.8+ (for AI/ML services)
- Maven 3.6+ (for Spring Boot build)
- Google Cloud SDK
- Git
- A modern web browser

## Technology Stack
- **Frontend**: Bootstrap 5, HTML5, CSS3, JavaScript
- **Backend**: Spring Boot (Java) + Python (Flask/FastAPI)
- **Database**: Google Firestore
- **AI/ML**: Google Vertex AI
- **Cloud**: Google Cloud Platform

## Initial Setup

### 1. Clone the Repository
```bash
git clone <your-repository-url>
cd Gastro-FYP
```

### 2. Google Cloud Setup

#### Create a Google Cloud Project
```bash
gcloud projects create your-project-id
gcloud config set project your-project-id
```

#### Enable Required APIs
```bash
gcloud services enable aiplatform.googleapis.com
gcloud services enable firestore.googleapis.com
gcloud services enable storage.googleapis.com
```

#### Create Service Account
```bash
gcloud iam service-accounts create gastrosphere-service
gcloud projects add-iam-policy-binding your-project-id \
    --member="serviceAccount:gastrosphere-service@your-project-id.iam.gserviceaccount.com" \
    --role="roles/aiplatform.user"
gcloud projects add-iam-policy-binding your-project-id \
    --member="serviceAccount:gastrosphere-service@your-project-id.iam.gserviceaccount.com" \
    --role="roles/datastore.user"
```

#### Download Service Account Key
```bash
gcloud iam service-accounts keys create service-account-key.json \
    --iam-account=gastrosphere-service@your-project-id.iam.gserviceaccount.com
```

### 3. Install Dependencies

#### Python Service Dependencies
```bash
cd backend/python-service
pip install -r requirements.txt
```

#### Spring Boot Service Dependencies
```bash
cd backend/spring-boot-service
mvn clean install
```

### 4. Environment Configuration

#### Python Service (.env file)
```bash
cd backend/python-service
cp .env.example .env
# Edit .env with your configuration
```

#### Spring Boot Service
```bash
cd backend/spring-boot-service/src/main/resources
# Edit application.properties with your configuration
# Place firebase-service-account.json in resources folder
```

### 5. Database Setup (Firestore)

#### Initialize Firestore
```bash
gcloud firestore databases create --region=us-central1
```

#### Create Collections
- Users collection
- Symptoms collection
- Meals collection
- Notifications collection

### 6. Vertex AI Setup

#### Create Dataset
```bash
gcloud ai datasets create \
    --display-name="gastrosphere-dataset" \
    --metadata-schema-uri="gs://google-cloud-aiplatform/schema/dataset/metadata/text_1.0.0.yaml"
```

#### Upload Training Data
```bash
gsutil cp data/gastrosphere_100k_enhanced_dataset.csv gs://your-data-bucket/
```

### 7. Start Development Servers

#### Frontend (Bootstrap)
```bash
cd frontend
# Simply open index.html in browser or use live server
python -m http.server 3000  # Simple HTTP server
```

#### Python Service
```bash
cd backend/python-service
python app.py
# Service runs on http://localhost:5000
```

#### Spring Boot Service
```bash
cd backend/spring-boot-service
mvn spring-boot:run
# Service runs on http://localhost:8080
```

## Development Workflow

### 1. Feature Development
- Create feature branches: `git checkout -b feature/feature-name`
- Develop and test your feature
- Commit changes: `git commit -m "Add feature description"`
- Push to GitHub: `git push origin feature/feature-name`
- Create pull request

### 2. AI Model Training
- Place training data in `data/raw/`
- Run preprocessing: `python src/ai/preprocessing/preprocess.py`
- Train models: `python src/ai/training/train_model.py`
- Save trained models to `models/trained_models/`

### 3. Testing
```bash
# Run all tests
npm test

# Run Python tests
pytest tests/
```

## Project Structure Overview

### Frontend Components
- **Dashboard**: Main user interface (`src/frontend/components/Dashboard/`)
- **Symptom Tracker**: AI chatbot interface (`src/frontend/components/SymptomTracker/`)
- **Meal Planner**: Meal recommendations (`src/frontend/components/MealPlanner/`)

### Backend API
- **Routes**: API endpoints (`src/backend/routes/`)
- **Controllers**: Business logic (`src/backend/controllers/`)
- **Services**: External service integrations (`src/backend/services/`)

### AI Components
- **Models**: ML model definitions (`src/ai/models/`)
- **Training**: Model training scripts (`src/ai/training/`)
- **Preprocessing**: Data preparation (`src/ai/preprocessing/`)

## Next Steps

1. **Design Database Schema**: Define collections for users, symptoms, meals, etc.
2. **Create API Endpoints**: Build RESTful APIs for frontend communication
3. **Develop Frontend Components**: Create responsive UI components
4. **Implement AI Models**: Build and train symptom analysis models
5. **Add Authentication**: Implement user registration and login
6. **Create Chatbot Interface**: Develop conversational symptom tracker
7. **Build Meal Planner**: Implement personalized meal recommendations
8. **Add Notifications**: Create alert and reminder system
9. **Implement Gamification**: Add achievement and progress tracking
10. **Create Educational Content**: Build FAQ and learning resources

## Useful Commands

```bash
# Development
npm run dev          # Start development server
npm run build        # Build for production
npm run test         # Run tests
npm run lint         # Check code style

# Git workflow
git status           # Check repository status
git add .           # Stage all changes
git commit -m "msg"  # Commit changes
git push            # Push to GitHub

# Python/AI
python -m pytest    # Run Python tests
python train.py     # Train AI models
jupyter notebook    # Start Jupyter for data analysis
```

## Resources
- [Node.js Documentation](https://nodejs.org/docs/)
- [Express.js Guide](https://expressjs.com/)
- [MongoDB Documentation](https://docs.mongodb.com/)
- [TensorFlow Documentation](https://www.tensorflow.org/guide)
- [React Documentation](https://react.dev/) (if using React)

## Support
For questions or issues, please create an issue in the GitHub repository.
