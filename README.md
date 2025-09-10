# Amazon Reviews Sentiment Classifier

A full pipeline that reads Amazon product reviews and decides if each one is positive or negative. The aim is simple: turn raw customer text into signals a team can act on.

---

## What it does
- Ingests thousands of Amazon reviews
- Learns from the review text only
- Predicts a binary label  
  1 means positive  
  0 means negative

---

## Data at a glance
- **Source** Amazon product review corpus  
- **Scale** Thousands of rows  
- **Target** Binary sentiment  
- **Input** Free-form review text

---

## Pipeline

### Preprocessing
Here’s the cleaning pass before any modeling:
- Drop rows with missing text
- Lowercase everything
- Strip punctuation, digits, and stray symbols
- Tokenize into words
- Remove English stopwords
- Lemmatize with WordNet
- Split with an **80–20 stratified** train test split to keep class balance stable

### Feature building
- TF-IDF vectorization on unigrams and bigrams
- Cap vocabulary at **5,000** terms to keep memory and speed in check

---

## Models trained
Let’s break it down by family:
- **Logistic Regression** with L2 penalty
- **Random Forest** with 100 trees
- **Linear SVM** with probability estimates
- **Multinomial Naive Bayes**
- **Gradient Boosting**

---

## How we score models
- **Accuracy** overall hit rate  
- **Precision** avoiding false positives  
- **Recall** catching positives  
- **F1** balance of precision and recall  
- **Confusion Matrix** where predictions land

---

## Hyperparameter search
Two strategies, used where they shine:
- **Grid Search** for tight, interpretable sweeps  
- **Randomized Search** for broader coverage faster

**Tuned models** Logistic Regression and Random Forest  
**Typical knobs** C for regularization, tree depth, number of estimators

---

## What performed best
What this really means for choices:
- **Logistic Regression** offered the best mix of accuracy, speed, and simplicity
- **Random Forest** could edge accuracy higher with tuning, at a compute cost
- Every model cleared **80 percent** accuracy, which tells us the text signal is strong
- Clear trade-off interpretability vs raw performance

---

## Final pick and deployment
- **Production model** tuned Logistic Regression
- **Interpretation** top TF-IDF terms highlight which words push predictions up or down
- **Demos** include quick passes on sample reviews to show behavior

---

## Tech stack
- **Language** Python  
- **NLP** NLTK for tokenization, stopwords, lemmatization  
- **ML** scikit-learn for vectorizers, models, and tuning  
- **Viz** matplotlib and seaborn for charts

---

## Headaches I have solved
- **Messy language** handled by a careful cleaning + lemmatization pipeline
- **Class imbalance** protected via stratified split and metric choice
- **Runtime** controlled through TF-IDF limits and efficient models
- **Explainability** delivered via word-level feature importance

---

## Where it helps the business
- **Feedback triage** auto-label reviews for sentiment
- **Quality monitoring** track shifts in sentiment over time
- **Market signals** mine themes and trends from language
- **Support workflows** surface negative reviews for quick follow-up

---

## Results
- **Accuracy** consistently above **85 percent**
- **Readable insights** via top positive and negative terms
- **Scalable** preprocessing and compact feature space
- **Actionable** dashboards and examples that connect to real cases

---

## What’s next
- Try **LSTM or BERT** for richer language understanding
- Expand to **multi-class** prediction across 1–5 stars
- Add **streaming** inference for near real-time updates
- Plug into **BI tools** for team-friendly monitoring and drill-downs
