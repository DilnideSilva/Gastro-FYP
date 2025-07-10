# GastroSphere - Getting Started Guide

## Prerequisites
- Node.js (v14 or higher)
- Python (v3.8 or higher)
- Git
- A modern web browser

## Initial Setup

### 1. Clone the Repository
```bash
git clone <your-repository-url>
cd Gastro-FYP
```

### 2. Install Dependencies

#### Frontend/Backend Dependencies
```bash
npm install
```

#### AI/ML Dependencies
```bash
pip install -r requirements.txt
```

### 3. Environment Configuration
Create a `.env` file in the root directory:
```
# Database Configuration
DB_HOST=localhost
DB_PORT=27017
DB_NAME=gastrosphere

# AI Model Configuration
AI_MODEL_PATH=./models/trained_models/
OPENAI_API_KEY=your_openai_api_key

# Application Configuration
PORT=3000
NODE_ENV=development
JWT_SECRET=your_jwt_secret_key

# Email Configuration
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your_email@gmail.com
EMAIL_PASS=your_app_password
```

### 4. Database Setup
```bash
# Install MongoDB if not already installed
# Start MongoDB service
mongod

# Create database and collections (run in MongoDB shell)
use gastrosphere
```

### 5. Data Preprocessing
```bash
# Run data preprocessing script
python scripts/data-preprocessing.py
```

### 6. Start Development Server
```bash
# Start backend server
npm run dev

# In another terminal, start frontend (if separate)
# cd frontend && npm start
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
