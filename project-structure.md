# GastroSphere Project Structure

```
GastroSphere/
├── src/
│   ├── frontend/
│   │   ├── components/
│   │   │   ├── Dashboard/
│   │   │   ├── SymptomTracker/
│   │   │   ├── MealPlanner/
│   │   │   ├── EducationalHub/
│   │   │   └── CommunityForum/
│   │   ├── assets/
│   │   │   ├── css/
│   │   │   ├── js/
│   │   │   └── images/
│   │   └── pages/
│   ├── backend/
│   │   ├── api/
│   │   ├── controllers/
│   │   ├── middleware/
│   │   ├── routes/
│   │   └── services/
│   └── ai/
│       ├── models/
│       ├── training/
│       └── preprocessing/
├── data/
│   ├── raw/
│   ├── processed/
│   └── gastrosphere_100k_enhanced_dataset.csv
├── models/
│   ├── trained_models/
│   └── model_configs/
├── docs/
│   ├── api-documentation.md
│   ├── user-guide.md
│   └── project-documentation.md
├── tests/
│   ├── unit/
│   ├── integration/
│   └── e2e/
├── config/
│   ├── database.config.js
│   ├── ai.config.js
│   └── app.config.js
├── scripts/
│   ├── setup.sh
│   ├── deploy.sh
│   └── data-preprocessing.py
├── .gitignore
├── package.json
├── requirements.txt
└── README.md
```

## Key Directories Explained

### `/src`
Main source code directory containing frontend, backend, and AI components

### `/data`
Contains all datasets including the main 100k enhanced dataset

### `/models`
Stores trained AI models and configurations

### `/docs`
Project documentation and user guides

### `/tests`
Testing files for different testing levels

### `/config`
Configuration files for different environments

### `/scripts`
Utility scripts for setup, deployment, and data processing
