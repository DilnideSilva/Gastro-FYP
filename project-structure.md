# GastroSphere Project Structure

```
GastroSphere/
├── frontend/
│   ├── assets/
│   │   ├── css/
│   │   │   ├── bootstrap.min.css
│   │   │   └── custom-styles.css
│   │   ├── js/
│   │   │   ├── bootstrap.bundle.min.js
│   │   │   └── app.js
│   │   └── images/
│   ├── components/
│   │   ├── dashboard.html
│   │   ├── symptom-tracker.html
│   │   ├── meal-planner.html
│   │   ├── educational-hub.html
│   │   └── community-forum.html
│   ├── pages/
│   │   ├── index.html
│   │   ├── login.html
│   │   └── register.html
│   └── partials/
│       ├── header.html
│       ├── footer.html
│       └── navbar.html
├── backend/
│   ├── python-service/
│   │   ├── app.py
│   │   ├── requirements.txt
│   │   ├── models/
│   │   │   ├── __init__.py
│   │   │   ├── symptom_classifier.py
│   │   │   └── recommendation_engine.py
│   │   ├── services/
│   │   │   ├── __init__.py
│   │   │   ├── ai_service.py
│   │   │   ├── data_processor.py
│   │   │   └── vertex_ai_client.py
│   │   ├── routes/
│   │   │   ├── __init__.py
│   │   │   ├── ai_routes.py
│   │   │   └── data_routes.py
│   │   └── config/
│   │       ├── __init__.py
│   │       ├── settings.py
│   │       └── vertex_ai_config.py
│   └── spring-boot-service/
│       ├── src/
│       │   └── main/
│       │       ├── java/
│       │       │   └── com/
│       │       │       └── gastrosphere/
│       │       │           ├── GastrosphereApplication.java
│       │       │           ├── controller/
│       │       │           │   ├── UserController.java
│       │       │           │   ├── SymptomController.java
│       │       │           │   └── MealController.java
│       │       │           ├── service/
│       │       │           │   ├── UserService.java
│       │       │           │   ├── SymptomService.java
│       │       │           │   └── FirestoreService.java
│       │       │           ├── model/
│       │       │           │   ├── User.java
│       │       │           │   ├── Symptom.java
│       │       │           │   └── Meal.java
│       │       │           ├── repository/
│       │       │           │   ├── UserRepository.java
│       │       │           │   └── SymptomRepository.java
│       │       │           └── config/
│       │       │               ├── FirestoreConfig.java
│       │       │               └── SecurityConfig.java
│       │       └── resources/
│       │           ├── application.properties
│       │           └── firebase-service-account.json
│       ├── pom.xml
│       └── Dockerfile
├── data/
│   ├── raw/
│   ├── processed/
│   └── gastrosphere_100k_enhanced_dataset.csv
├── ml-models/
│   ├── vertex-ai-configs/
│   │   ├── training-config.yaml
│   │   └── deployment-config.yaml
│   ├── notebooks/
│   │   ├── data-exploration.ipynb
│   │   ├── model-training.ipynb
│   │   └── model-evaluation.ipynb
│   └── scripts/
│       ├── train_model.py
│       ├── deploy_model.py
│       └── batch_predict.py
├── docs/
│   ├── api-documentation.md
│   ├── user-guide.md
│   ├── deployment-guide.md
│   └── project-documentation.md
├── tests/
│   ├── frontend/
│   ├── python-service/
│   └── spring-boot-service/
├── config/
│   ├── docker-compose.yaml
│   ├── firestore-rules.txt
│   └── vertex-ai-setup.sh
├── scripts/
│   ├── setup.sh
│   ├── deploy.sh
│   └── data-preprocessing.py
├── .gitignore
├── README.md
└── GETTING-STARTED.md
```

## Key Directories Explained

### `/frontend`
Bootstrap-based responsive frontend with HTML, CSS, and JavaScript

### `/backend`
Dual backend architecture:
- **Python Service**: AI/ML processing with Vertex AI integration
- **Spring Boot Service**: Main application logic and Firestore integration

### `/data`
Contains datasets including the main 100k enhanced dataset

### `/ml-models`
Vertex AI configurations, Jupyter notebooks, and ML scripts

### `/docs`
Project documentation and API guides

### `/tests`
Testing files for frontend, Python service, and Spring Boot service

### `/config`
Configuration files for Docker, Firestore, and Vertex AI
