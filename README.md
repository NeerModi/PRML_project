# Leaf Classification System

A machine learning project that classifies leaf images into different species using multiple classification models.

## Project Overview

This project implements a leaf classification system with both backend machine learning models and a frontend web interface. Users can upload images of leaves, and the system will identify the species using one of several machine learning models.

## Features

- Multiple machine learning models for leaf classification (KNN, SVM, Decision Tree, Random Forest, ANN)
- Image feature extraction for shape, texture, and margin characteristics
- Web interface for easy leaf image upload and analysis
- Real-time prediction and species identification

## Directory Structure


```yaml
leaf-classification:
  backend:
    # Flask API server
    app.py:                         # Main API implementation
    requirements.txt:               # Backend dependencies
    uploads: {}                     # Temporary storage for uploaded images

  frontend:
    # React frontend application
    src:
      components:
        ImageUpload.jsx:            # Image upload component
        ResultsDisplay.jsx:         # Results display component
        ModelSelection.jsx:         # Model selection component
      App.jsx:                      # Main application component
    other-files: ...                # Other frontend files/configs

  data:
    # Data directory
    raw:
      train.csv:                    # Training data with features
      test.csv:                     # Test data with features
    processed: {}                   # Processed data files

  models:
    # Trained model storage
    knn: {}
    svm: {}
    decision_tree: {}
    random_forest: {}
    ann: {}
    scaler.pkl:                    # Feature scaler
    label_encoder.pkl:             # Label encoder
    pca_reducer.pkl:               # PCA model
    lda_reducer.pkl:               # LDA model

  src:
    # Source code for model training
    data_preprocessing.py:          # Data preprocessing functions
    feature_extraction.py:          # Feature extraction utilities
    model_training.py:              # Model training functions
    evaluation.py:                  # Model evaluation metrics
    main.py:                        # Main script for training models

  requirements.txt:                 # Project dependencies
  README.md:                        # Project documentation
```



## Setup Instructions

### Prerequisites

- Python 3.8+
- Node.js and npm
- Git

### Backend Setup

1. Clone the repository:
   bash
   git clone https://github.com/yourusername/leaf-classification.git
   cd leaf-classification
   

2. Create a virtual environment and activate it:
   bash
   python -m venv venv
   
   # On Windows:
   venv\Scripts\activate
   
   # On Unix/macOS:
   source venv/bin/activate
   

3. Install backend dependencies:
   bash
   cd backend
   pip install -r requirements.txt
   

4. Run the Flask API server:
   bash
   python app.py
   

   The server will start on http://localhost:5000

### Frontend Setup

1. Navigate to the frontend directory:
   bash
   cd ../frontend
   

2. Install frontend dependencies:
   bash
   npm install
   

3. Start the development server:
   bash
   npm start
   

   The frontend will be available at http://localhost:3000

## Dataset

The project uses the Leaf Classification dataset from Kaggle ([https://www.kaggle.com/competitions/leaf-classification](https://www.kaggle.com/competitions/leaf-classification)). The dataset contains:

- Margin, shape, and texture features for various leaf species
- Images of leaf samples
- 99 species of plants represented

## Models Implemented

1. *K-Nearest Neighbors (KNN)*
   - Fast classification based on similarity metrics

2. *Support Vector Machine (SVM)*
   - High accuracy with good generalization capability
   - Optimal hyperplane for classification in high-dimensional space

3. *Decision Tree (DT)*
   - Simple interpretable model for leaf classification

4. *Random Forest (RF)*
   - Ensemble method with improved robustness and accuracy

5. *Artificial Neural Network (ANN)*
   - Deep learning approach for complex feature relationships

## Feature Extraction

The system extracts three types of features from leaf images:

1. *Shape Features*: Using elliptic Fourier descriptors
2. *Texture Features*: Using Local Binary Patterns (LBP)
3. *Margin Features*: Based on distance from centroid along the contour

## Usage

1. Open the web interface at http://localhost:3000
2. Upload a leaf image through the interface
3. The system will process the image and extract relevant features
4. The selected model will classify the leaf species
5. Results will display the predicted species name and confidence level

## Troubleshooting

- If models return consistent class numbers (e.g., always class 19 or 64), check the label encoding between training and inference
- Verify that the feature extraction process matches between training and inference
- Ensure all preprocessing tools (scaler, reducer) are properly loaded

## Technologies Used

- *Backend*: Flask, TensorFlow, scikit-learn, OpenCV
- *Frontend*: React, TailwindCSS
- *Data Processing*: NumPy, Pandas, scikit-image

## License

This project is licensed under the MIT License - see the LICENSE file for details.
