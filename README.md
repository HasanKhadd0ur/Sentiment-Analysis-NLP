# Sentiment Analysis for Mental Health Monitoring 🤯
---
NLP course homework, focusing on mental health text classification. Implements data preprocessing, POS filtering with Stanza, TF-IDF vectorization, and model training to detect mental health conditions.
---

___

> [dataset source](https://www.kaggle.com/datasets/suchintikasarkar/sentiment-analysis-for-mental-health) 🔗

---

## **About The Datset** 🧷
This comprehensive dataset is a meticulously curated collection of mental health statuses tagged from various statements. The dataset amalgamates raw data from multiple sources, cleaned and compiled to create a robust resource for developing chatbots and performing sentiment analysis.

---
## **Data Souce** 🌍
The dataset integrates information from the following Kaggle datasets:

 - 3k Conversations Dataset for Chatbot
 - Depression Reddit Cleaned
 - Human Stress Prediction
 - Predicting Anxiety in Mental Health Data
 - Mental Health Dataset Bipolar
 - Reddit Mental Health Data
 - Students Anxiety and Depression Dataset
 - Suicidal Mental Health Dataset
 - Suicidal Tweet Detection Dataset
---

###  **Datset Over View**  :

* **Description:**

    This dataset is a comprehensive collection of 50,000 text statements related to mental health, each tagged with one of seven mental health statuses. The primary purpose of this dataset is to assist in building machine learning models for classifying mental health conditions based on textual data, such as social media posts or other user-generated content.

* **Columns:**
  1. **unique_id**: A unique identifier for each entry.
  2. **statement**: A piece of text, typically a statement or comment, associated with a particular mental health status.
  3. **status**: The mental health status assigned to the statement. The possible categories are:
    - Normal
    - Depression
    - Suicidal
    - Anxiety
    - Stress
    - Bi-Polar
    - Personality Disorder

---
### **Usage** :
This dataset is ideal for training machine learning models aimed at understanding and predicting mental health conditions based on textual data.
It can be used in various applications such as:

- Chatbot development for mental health support.
- Sentiment analysis to gauge mental health trends.
-
---

### **How we use NLP Concepts**


  In our text processing methodology, we begin by removing punctuation, URLs, and hyperlinks from the statements. Additionally, we eliminate stop words, such as "is," "are," and "the," to enhance the focus on more informative terms.


  In the realm of morphological analysis, we extract the stems of the words. Subsequently, we employ a TF-IDF (Term Frequency-Inverse Document Frequency) vectorizer to transform the processed text into a vector representation. This vector is then utilized to fit the mode

  In the realm of POS, we split the statemetn to three field ,for verbs, nouns, adjectvies column , and the we make a four TF-IDF Vectors as the folowing :
    1. Verb TF-IDF Vector
    2. Nouns TF-IDF Vector
    3. Adjective TF-IDF Vector 
    4. Weighted TF-IDF Vector
    
---
### 
### **Conlusion**
 *  in the conclusion  for the moph part 1, we train and tune  a four model wich is :
    * SVM  
    * Logistic Regression
    * Neural Ntwork
    * KNN
  the first three give a Convergent results with accuracy near to 76 % , and the last one give  a 65 % acc .
*  in the pos part 2 , we train the model on each vector from the vectors that mentioned above, and the results was as the following:

| Model                  | Vectorizing Approach         | Accuracy |
|------------------------|------------------------------|----------|
| Logistic Regression    | TF-IDF Based on Verbs        | 66%      |
| Logistic Regression    | TF-IDF Based on Nouns        | 66%      |
| Logistic Regression    | TF-IDF Based on Adjective    | 60%      |
| Logistic Regression    | TF-IDF Based on Weightes     | 75%      |
| Neural Network         | TF-IDF Based on Verbs        | 64%      |
| Neural Network         | TF-IDF Based on Nouns        | 68%      |
| Neural Network         | TF-IDF Based on Adjective    | 46%      |
| Neural Network         | TF-IDF Based on Weightes     | 72%      |

*  
---
---
<img src="https://img.freepik.com/free-vector/mental-health-awareness-concept_23-2148531011.jpg" alt="Sample Image" >




---
```


```
---



