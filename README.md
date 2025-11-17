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

### 1. **Handling Sarcasm and Context**
**Challenge:** The simple word-counting method couldn't understand sarcasm. For example, "Oh great, it broke on the first day. Just wonderful!" contains positive words like "great" and "wonderful" but expresses negative sentiment through sarcasm.

**Solution:** Implemented the advanced TextBlob method which uses machine learning to understand context and polarity scores better than simple word matching. I also added both analysis methods so users can compare results and see where simple methods fail.

### 2. **Stop Words and Text Preprocessing**
**Challenge:** Common words like "the", "is", "and" don't contribute to sentiment analysis but appeared frequently in reviews, potentially skewing results and making analysis slower.

**Solution:** Integrated NLTK's built-in stop word list to filter out 179 common English words. This improved analysis accuracy by focusing on meaningful words while reducing noise and processing time.

### 3. **Balancing Accuracy vs. Simplicity**
**Challenge:** A pure machine learning approach required significant computational resources and external dependencies, while a rule-based approach lacked accuracy for complex reviews.

**Solution:** Created a hybrid system with both simple (rule-based) and advanced (TextBlob ML) methods. This allows users to choose based on their needs: simple method for speed, advanced for accuracy. The comparison also provides educational value about NLP techniques.

## Real-World Applications

1. **Customer Service & Product Feedback**: Companies like Amazon and Walmart use sentiment analysis to automatically categorize customer reviews, identify issues, and prioritize complaints for response teams.

2. **Social Media Monitoring**: Brands monitor Twitter, Facebook, and Instagram sentiment to track brand reputation, detect crisis situations early, and identify trending customer concerns in real-time.

3. **Market Research & Investment Analysis**: Financial firms analyze sentiment in earnings calls, news articles, and social media to predict stock movements and identify emerging market trends before they become mainstream.

## What I Learned

Through building this sentiment analyzer, I gained practical understanding of Natural Language Processing fundamentals. I learned that tokenization breaks text into meaningful units, allowing computers to process language systematically. Stop word removal helped me understand that not all words carry sentiment—common words need filtering to focus analysis. Most importantly, I realized that sentiment analysis requires both simple rule-based methods and machine learning approaches; no single technique works perfectly because language is complex, contextual, and often uses sarcasm or idioms that challenge even advanced algorithms. This project demonstrated that effective NLP solutions often combine multiple techniques and require continuous refinement based on real-world test cases.
