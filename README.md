# Text Classification for Research Papers

## Problem Statement
Develop a text classification model to predict the relevant terms or labels associated with research papers based on their titles and summaries.

## Objective
The objective of this project is to accurately classify research papers into relevant categories or terms, enabling better organization and retrieval of information.

## Data Description
The dataset consists of research papers along with their titles, summaries, and associated terms. Each term represents a category or label relevant to the paper. The dataset is in tabular format, stored as a pandas DataFrame.

## Methodology
### Data Preprocessing
1. **Lowercasing:** Converted all text to lowercase to ensure uniformity.

2. **Tokenization:** Splitted the text into individual tokens (words) to facilitate further processing.

3. **Special Character Removal:** Removed special characters and non-alphanumeric characters from the text.

4. **Stopword Removal:** Eliminated common stopwords (e.g., "and," "the," "is") from the text as they do not contribute significantly to the classification task.

5. **Lemmatization:** Reduced words to their base or dictionary form to normalize the text and reduce dimensionality.

6. **Data Filtering:** Narrowed down the dataset to focus on a subset of labels with significant occurrences to address class imbalance.

7. **Data Visualization:** Visualized the distribution of label frequencies and label combination frequencies to gain insights into the dataset's characteristics.
   
8. **Text Embeddings:**  Text Eembedding using Word2Vec, and encoding the target variable using a MultiLabelBinarizer to handle multi-label classification.

9. **Saving Data:** Saved the preprocessed data for model training.
 
### Model Selection

1. **SVM-Label Powerset:** Utilized Support Vector Machine (SVM) with the Label Powerset approach to handle multilabel classification. This approach transforms the multilabel problem into multiple binary classification problems, where each combination of labels is treated as a separate class.

2. **Random Forest-MultiOutputClassifier::** Employed Random Forest with the MultiOutputClassifier wrapper to handle multilabel classification. Random Forest builds multiple decision trees and predicts multiple outputs (labels) simultaneously.

3. **KNN-Classifier Chains:** Applied k-Nearest Neighbors (KNN) with the Classifier Chains approach for multilabel classification. In this approach, multiple binary classifiers are trained in a chain, where each classifier predicts one label and uses the predictions of previous classifiers as additional features.

4. **LSTM and BiLSTM:** Implemented Long Short-Term Memory (LSTM) and Bidirectional LSTM (BiLSTM) neural network architectures for sequence modeling and text classification. These models are well-suited for processing sequential data like text and can capture long-range dependencies effectively.

### Training
Trained the model using the preprocessed data. Utilized techniques such as cross-validation and hyperparameter tuning to optimize model performance.

### Evaluation
Evaluate the trained model on a separate validation set using appropriate evaluation metrics for multilabel classification, such as F1-score, precision, recall, and accuracy, ROC curve. Analyze the model's performance and iteratively refined the models.

## Conclusion

**KNN with classifier chains was most promising as it trained fast and gave the highest overall performance.** 

The developed text classification model demonstrates promising performance in accurately categorizing research papers into relevant terms or labels based on their titles and summaries. By effectively organizing and classifying research papers, the model enhances the accessibility and retrieval of information, facilitating knowledge discovery and research exploration in the domain. Further enhancements and refinements can be explored to improve the model's robustness and applicability in real-world scenarios.
