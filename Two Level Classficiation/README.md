# Sentiment Analysis for Mental Health Monitoring 🤯
---
NLP course homework, focusing on mental health text classification. Implements data preprocessing, POS filtering with Stanza, TF-IDF vectorization, and model training to detect mental health conditions.
---

#  What we do and Why .
___


---

### About Two-Level Classification

In a two-level classification approach, we break down a multi-class classification problem into two stages:

1. **Stage 1 - Binary Classification**:
   - This stage first classifies data into two  categories: **Normal** ans **Non-Normal**.
   - By creating this separation, we simplify the problem and reduce the initial complexity, allowing the model to focus on distinguishing between these high-level classes.
   - This binary classifier uses features from the full dataset, ensuring that it can accurately detect if a statement falls into the "Normal" or "Non-Normal" category.

2. **Stage 2 - Multi-Class Classification**:
   - In this stage, we take statements classified as **Non-Normal** from Stage 1 and further classify them into specific mental health categories such as **Depression**, **Suicidal**, **Anxiety**, **Stress**, **Bi-Polar**, and **Personality Disorder**.
   - This multi-class classifier uses data that has already been identified as "Non-Normal," focusing on differentiating among various mental health conditions.
   
### Why Two-Level Classification?

- 🌵**Improved Accuracy**: This approach allows each classifier to focus on a subset of the problem, potentially increasing accuracy by reducing the complexity each model has to handle.
- 🍀 **Efficient Use of Resources**: By filtering out "Normal" cases in Stage 1, Stage 2 can concentrate only on differentiating among the specific mental health conditions, making it more efficient.
- 🦠 **Handling Imbalance**: Many datasets are imbalanced, with "Normal" cases being more common. Splitting the classification into two levels allows us to address class imbalance in each level separately.

### How It Works in This Model

1. **Data Preparation**:
   - First, we preprocess the dataset by cleaning the text and extracting features (e.g., TF-IDF, POS tags, emojis).
   - Then, we split the data for training and testing each stage separately.

2. **Training**:
   - **Stage 1**: We train a binary classifier on the full training data to classify statements as **Normal** or **Non-Normal**.
   - **Stage 2**: We train a multi-class classifier on the subset of training data labeled as **Non-Normal**, focusing only on the six specific mental health conditions.

3. **Testing**:
   - For each test instance, we first use Stage 1 to determine if it’s "Normal" or "Non-Normal."
   - If classified as **Non-Normal**, the instance is passed to Stage 2, where it is classified into one of the specific mental health categories.

### Evaluation and Metrics

- **Stage-Specific Metrics**: Each stage is evaluated separately, with accuracy, recall, precision, and F1-score measured for both the binary and multi-class classifiers.
- **Combined Evaluation**: Finally, we combine predictions from both stages to evaluate the overall performance of the two-level classification system.

This two-level approach allows us to accurately identify both "Normal" and specific mental health conditions, leveraging targeted classification strategies to improve overall accuracy and interpretability.


---
# Text Processing Workflow

This document outlines the workflow for preprocessing text data by expanding slang terms and counting their occurrences.

## Workflow

```mermaid
graph TD;
    A[Start] --> B[Load Dataset]
    B --> C[Define Slang Dictionary]
    C --> D[Initialize Total Changes Counter]
    D --> E[Apply expand_slang Function to Each Row]
    E --> F{Check Each Word in Text}
    
    F -->|Slang Found| G[Replace with Expanded Form]
    F -->|No Slang Found| H[Keep Original Word]
    
    G --> I[Increment Total Changes Counter]
    H --> E
    
    I --> J[Join Expanded Words to Form New Text]
    J --> K[Store Expanded Text in New Column]
    
    K --> L[Calculate Total Number of Expansions]
    L --> M[Display Updated Dataset and Total Changes]
    M --> N[End]
