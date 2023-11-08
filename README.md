# Sentiment Analyzer using Naive Bayes and TF-IDF

This repository contains an implementation of a sentiment analyzer using various strategies, including a base implementation using Naive Bayes and an advanced approach using TF-IDF with a Linear Support Vector Classifier (SVC). The goal of this project is to accurately predict the sentiment (positive or negative) of a given text.

## Naive Bayes Implementation

In this implementation, NLTK's Naive Bayes classifier is employed. The Naive Bayes algorithm assumes that each feature is independent of the others, allowing predictions based on individual feature probabilities. A Multimodal Naive Bayes classifier is used, which can incorporate data from multiple sources (modalities). The algorithm calculates probabilities for each word's occurrence in each class (positive/negative) and compares resulting probabilities to determine the sentiment.

### Pre-processing Strategies

Several pre-processing strategies are explored to enhance accuracy:

1. **No Pre-processing**: Without any pre-processing, an average accuracy of 80.75% is achieved.
2. **Tokenization**: Tokenizing the text improves accuracy to 81.3%, as it removes punctuation and aids in better word recognition.
3. **Stopwords Removal**: Removing stop words further improves accuracy, reducing noise and enhancing prediction quality.
4. **Alphabetic Filtering**: Focusing on strings containing only alphabets decreases accuracy due to the loss of informative features.
5. **Stemmatization**: Reducing words to base forms (stemming) decreases noise and increases accuracy.
6. **Lemmatization**: Lemmatization coupled with tokenization and stopword removal achieves the highest accuracy, outperforming other strategies.

### Evaluation and Analysis

The confusion matrix reveals interesting insights, including instances of sarcasm and irony in negative reviews. Some surprising words that contribute to sentiment are identified, indicating nuanced correlations. Fractional numbers as identifiers are recognized, but their importance diminishes when filtering alphabetic strings.

## TF-IDF Implementation

A second iteration utilizes the TF-IDF approach with a Linear SVC classifier. TF-IDF assigns importance scores to words based on their frequency and relevance to a specific document. The TfidfVectorizer converts text into numerical feature vectors, enabling the Linear SVC to classify sentiment based on these vectors.

### Results and Findings

Lemmatization coupled with tokenization continues to perform well with TF-IDF and Linear SVC. While Lemmatization performs equally with and without other pre-processing, it exhibits wider generalization. Linear SVC outperforms Naive Bayes with an improvement of 2.48% in accuracy. The confusion matrix indicates improved balance between false positives and false negatives.

## Parsing and Chunking

An attempt is made to improve the model by parsing and chunking using Parts of Speech (POS) tagging. Two variations are explored: focusing on adverbs, nouns, verbs, and adjectives, and focusing solely on adverbs and adjectives. However, these strategies do not significantly improve accuracy, emphasizing the importance of maintaining context in sentiment analysis.

## Conclusion

The project demonstrates the significance of pre-processing strategies in sentiment analysis, with substantial accuracy improvements achievable through careful text manipulation. While the explored parsing and chunking techniques do not yield substantial benefits, they emphasize the intricate nature of maintaining context in sentiment analysis. Future work could involve experimenting with recurrent neural networks and optimizing parsing and chunking techniques. The project provides valuable insights into the complexities of NLP tasks and the potential for further advancements in sentiment analysis.
