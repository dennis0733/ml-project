# Student Performance Analysis

## Project Purpose
This project serves two main purposes:
1. To analyze student performance across various subjects and factors
2. To demonstrate best practices in creating modular, production-ready data science projects

## Modular Code Implementation Guide
This project follows industry best practices for structuring machine learning projects:

### 1. Modular Code Structure
- **Components-based Architecture**: Each step of the ML pipeline is implemented as a separate component (ingestion, transformation, training)
- **Separation of Concerns**: Clear separation between data processing, model training, and prediction logic
- **Pipeline Architecture**: Orchestration of components through pipeline modules
- **Utils and Common Functions**: Shared functionality extracted into utility modules

### 2. Project Organization Best Practices
```
project_root/
├── artifacts/              # Generated files during training
├── logs/                   # Logging and monitoring
├── notebook/              # Experimental notebooks and raw data
├── src/                   # Source code
│   ├── components/       # Core ML pipeline components
│   ├── pipeline/        # Orchestration pipelines
└── └── utils/          # Shared utilities
```

### 3. Code Organization Principles
- **Components**: Each component is a self-contained module with clear inputs and outputs
- **Configuration**: External configuration for easy modification
- **Error Handling**: Centralized exception handling
- **Logging**: Comprehensive logging for monitoring and debugging
- **Testing**: Organized structure supporting unit and integration tests

### 4. Benefits of This Structure
- **Maintainability**: Easy to understand and modify
- **Scalability**: New components can be added without changing existing ones
- **Reusability**: Components can be reused across projects
- **Testing**: Modular structure facilitates unit testing
- **Deployment**: Clear separation makes deployment easier

## Overview
This project analyzes student performance across various subjects (Mathematics, Reading, and Writing) to understand the influence of different factors such as parental education, test preparation, and demographic variables. The analysis aims to help educators and institutions make data-driven decisions to improve student outcomes.

## Project Structure Details
```
├── artifacts/                     # Generated during training
│   ├── data.csv                  # Processed data
│   ├── train.csv                 # Training split
│   ├── test.csv                  # Testing split
│   ├── preprocessor.pkl          # Saved preprocessor
│   └── model.pkl                 # Trained model
├── logs/                         # Application logs
│   └── (log files)              # Timestamped log files
├── notebook/                     # Experimentation
│   └── data/
│       └── StudentsPerformance.csv  # Raw data
├── src/                         # Source code
│   ├── components/              # Core ML components
│   │   ├── data_ingestion.py   # Data loading
│   │   ├── data_transformation.py  # Feature engineering
│   │   └── model_trainer.py    # Model training
│   ├── pipeline/               # Orchestration
│   │   ├── predict_pipeline.py # Prediction pipeline
│   │   └── train_pipeline.py   # Training pipeline
│   ├── exception.py            # Custom exceptions
│   ├── logger.py              # Logging setup
│   └── utils.py               # Utility functions
├── requirements.txt            # Dependencies
├── README.md                  # Project documentation
├── setup.py                   # Package setup
└── .gitignore                # Git ignore rules
```

## Component Details

### 1. Data Pipeline Components
Each component is designed to be independent and reusable:

#### Data Ingestion (`src/components/data_ingestion.py`)
- Handles data loading and validation
- Implements train-test splitting
- Returns DataFrames ready for transformation

#### Data Transformation (`src/components/data_transformation.py`)
- Preprocesses features
- Handles categorical encoding
- Implements feature scaling
- Saves preprocessing pipeline

#### Model Training (`src/components/model_trainer.py`)
- Trains the model
- Performs hyperparameter tuning
- Evaluates model performance
- Saves the final model

### 2. Pipeline Implementation

#### Predict Pipeline (`src/pipeline/predict_pipeline.py`)
- Loads preprocessor and model
- Processes new data
- Generates predictions

### 3. Support Modules
#### Exception Handling (`src/exception.py`)
- Custom exception classes
- Detailed error tracking

#### Logging (`src/logger.py`)
- Configures logging
- Manages log files

#### Utilities (`src/utils.py`)
- Common functions
- File operations
- Configuration management

## Dataset Description
The dataset contains the following features:
- `gender`: Male/Female
- `race/ethnicity`: Group division from A to E
- `parental level of education`: Various levels from high school to master's degree
- `lunch`: Type of lunch selected
- `test preparation course`: Course details
- `math score`: Marks secured in Mathematics
- `reading score`: Marks secured in Reading
- `writing score`: Marks secured in Writing

## Setup and Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd student-performance-analysis
```

2. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # For Linux/Mac
# or
venv\Scripts\activate  # For Windows
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```


### Prediction
To make predictions:
```bash
python src/pipeline/predict_pipeline.py
```

## Model Artifacts
The following artifacts are generated during training:
- `preprocessor.pkl`: Saved preprocessor pipeline
- `model.pkl`: Trained model
- `train.csv`: Training dataset
- `test.csv`: Testing dataset

## Logging
Logs are maintained in the `logs` directory for monitoring and debugging purposes.

## Contributing
1. Fork the repository
2. Create a new branch (`git checkout -b feature/improvement`)
3. Make changes and commit (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/improvement`)
5. Create a Pull Request
