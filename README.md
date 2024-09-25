# Language-Detection-Project
 This project focuses on building a language detection system using the Naive Bayes classifier. It deals with identifying whether the input text is written in Slovak, Czech, or English. 

1: Exploratory Data Analysis + Visualization

2: Data Cleaning and Preprocessing

3: Naive Bayes implementation from scratch

4: The Naive Bayes Model

5: Simple Adjustments to the Naive Bayes Model

6: Using Advanced Techniques to Improve Performance


## Here’s a breakdown of the key parts:

1. Data Loading & Preprocessing:
Raw Data: Three languages (Slovak, Czech, English) are loaded from text files.
Preprocessing: This involves removing punctuation, digits, and converting text to lowercase. A key preprocessing step is the tokenization of text into words, followed by cleaning operations.

3. Zipf’s Law Visualization:
Zipf’s Law: The project visualizes the frequency distribution of words in each language, demonstrating that a small number of words occur very frequently while the majority are rare. This is shown via log-log plots.

4. Naive Bayes Model:
CountVectorizer: This step converts text into a format suitable for the Naive Bayes model (bag-of-words representation).
Naive Bayes: The model learns from the text data by computing conditional probabilities of words given the language. The training is performed using Multinomial Naive Bayes, which is suitable for text classification.
Confusion Matrix: The results of the model are visualized using a confusion matrix to identify how well the model distinguishes between the languages.

5. Evaluation and Improvement:
Initial evaluations showed that the model struggled to differentiate between Slovak and Czech, which are similar languages. Adjusting the alpha (smoothing parameter) and disabling the prior probabilities (fit_prior=False) significantly improved accuracy, pushing the F1-score from ~0.61 to 0.88.

6. Subword-Based Approach:
Subword Representation: An advanced method was applied by breaking words into subwords, which can help with cases where languages share many root words or inflections. The subwords were extracted using a technique inspired by Byte Pair Encoding (BPE), which is often used in neural machine translation models.
After incorporating subwords, the model was retrained and evaluated again, achieving reasonable accuracy (F1 score ~0.85).

7. Model Testing & Predictions:
A helper function, predict_language(), was created to classify the language of new text inputs. It preprocesses the input, splits it into subwords, and feeds it to the trained Naive Bayes model.

8. Challenges:
Confusion between Czech and Slovak: The model's performance improved but still struggled with the similarities between Czech and Slovak.
Experimenting with Subwords: Using subwords showed potential for improving model accuracy by capturing more nuanced differences between similar words.

## Conclusion:
This project demonstrates a classic Naive Bayes text classification pipeline applied to language detection. Through careful data preprocessing, model tuning, and leveraging subword information, the system becomes more robust at detecting similar languages.
