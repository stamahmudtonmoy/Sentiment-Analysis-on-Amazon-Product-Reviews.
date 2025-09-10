# Sentiment Analysis on Amazon Product Reviews

## Project Overview
This project implements a comprehensive sentiment analysis system to classify Amazon product reviews as positive or negative. The goal is to automatically analyze customer feedback and provide insights for product improvement and customer satisfaction monitoring.

## Dataset
- *Source*: Amazon product reviews dataset
- *Size*: Thousands of customer reviews
- *Target Variable*: Binary sentiment (1 = Positive, 0 = Negative)
- *Features*: Review text content only

## Project Workflow

### 1. Data Preprocessing
- *Missing Value Handling*: Removed rows with missing reviews
- *Text Cleaning*:
  - Converted to lowercase
  - Removed special characters, digits, and punctuation
  - Tokenized text into individual words
- *Stopword Removal*: Eliminated common English stopwords
- *Lemmatization*: Reduced words to their base forms using WordNet lemmatizer
- *Train-Test Split*: 80-20 stratified split to maintain class distribution

### 2. Feature Engineering
- *TF-IDF Vectorization*: Converted text to numerical features using Term Frequency-Inverse Document Frequency
- *Parameters*: Maximum 5000 features, unigrams and bigrams
- *Dimensionality Reduction*: Limited features to manage computational complexity

### 3. Model Selection & Training
*Models Implemented:*
1. *Logistic Regression*: Linear model with L2 regularization
2. *Random Forest*: Ensemble method with 100 trees
3. *Support Vector Machine*: With probability estimates enabled
4. *Naive Bayes*: Multinomial variant for text classification
5. *Gradient Boosting*: Sequential ensemble method

### 4. Model Evaluation
*Evaluation Metrics:*
- Accuracy: Overall correctness of predictions
- Precision: Ability to avoid false positives
- Recall: Ability to find all positive samples
- F1-Score: Harmonic mean of precision and recall
- Confusion Matrix: Detailed breakdown of predictions

### 5. Hyperparameter Tuning
- *Grid Search*: Exhaustive search over specified parameter values
- *Randomized Search*: Efficient sampling of parameter space
- *Tuned Models*: Logistic Regression and Random Forest showed best performance
- *Parameters Optimized*: Regularization strength, tree depth, number of estimators

### 6. Comparative Analysis
*Performance Findings:*
- Logistic Regression achieved best balance of performance and speed
- Random Forest provided highest accuracy with sufficient tuning
- All models achieved >80% accuracy, demonstrating text quality
- Trade-offs identified between interpretability and performance

### 7. Final Model Deployment
- *Best Model*: Tuned Logistic Regression selected for production
- *Feature Importance*: Identified most predictive words for sentiment
- *Prediction Examples*: Demonstrated model on sample reviews

## Technical Implementation
- *Programming Language*: Python
- *NLP Libraries*: NLTK for text preprocessing
- *ML Framework*: scikit-learn for model implementation
- *Visualization*: matplotlib and seaborn for results presentation

## Key Challenges & Solutions
1. *Text Variability*: Handled through comprehensive preprocessing pipeline
2. *Class Imbalance*: Used stratified sampling and appropriate metrics
3. *Computational Complexity*: Optimized through feature selection and efficient algorithms
4. *Model Interpretability*: Provided feature importance analysis

## Business Applications
- *Customer Feedback Analysis*: Automated review sentiment classification
- *Product Quality Monitoring*: Real-time sentiment tracking
- *Market Research*: Trend analysis of customer opinions
- *Customer Service*: Prioritizing negative reviews for follow-up

## Results
The system successfully:
- Achieved high accuracy (>85%) in sentiment classification
- Provided interpretable results with feature importance
- Demonstrated scalability through efficient preprocessing
- Offered practical business insights from customer feedback

## Future Enhancements
- Deep learning approaches (LSTM, BERT)
- Multi-class sentiment analysis (1-5 stars)
- Real-time processing capabilities
- Integration with business intelligence tools
