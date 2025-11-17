# Sentiment Analysis System

## Overview
This project implements sentiment analysis for product reviews using Natural Language Processing (NLP) techniques from Chapter 23.

## Features
- **Two Analysis Methods:**
  - Simple: Word counting based on positive/negative word lists
  - Advanced: Machine learning using TextBlob
- **REST API** for easy integration
- **Visualization** of sentiment distributions
- **Text preprocessing** including tokenization and stop word removal

## How to Run

### 1. Install Requirements
```bash
pip install -r requirements.txt
```

### 2. Test the Analyzer
```bash
python test_sentiment.py
```

### 3. Start the API Server
```bash
python api_server.py
```
Then visit http://localhost:5000

## API Usage Example

```python
import requests
response = requests.post('http://localhost:5000/analyze',
    json={'text': 'This product is amazing!'})
print(response.json())
```

## Understanding NLP Concepts

### Tokenization
Breaking text into words: "I love this" → ["I", "love", "this"]

### Stop Words
Common words we filter out: "the", "is", "at", "which"

### Sentiment Analysis
Determining if text is positive, negative, or neutral

## Challenges Encountered
[Write 2-3 challenges you faced and how you solved them]

## Real-World Applications
[List 3 ways companies use sentiment analysis]

## What I Learned
[Write 3-4 sentences about NLP concepts you now understand]
