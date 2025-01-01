# Classifying Refugee Needs from Arabic Social Media Comments

## Project Overview
This project was developed during my internship with UNHCR to predict refugee needs by analyzing Arabic comments collected from social media. The goal is to classify comments into specific categories such as **Health**, **Registration**, **Resettlement**, and others, providing actionable insights into the concerns and needs of refugees.

## Dataset
The dataset was collected using the **ExportComments** tool, extracting comments from the UNHCR Jordan Facebook page.

### Data Collection and Cleaning
- **Initial Data**: Over 5,000 comments were collected.
- **Cleaning Process**:
  - Removed duplicates, irrelevant content, and noise.
  - Final dataset reduced to 2,000 records.
  - Each record was manually categorized into one of the following nine categories:

    - **Others**: 34.72%
    - **Resettlement**: 29.84%
    - **Cash Assistance**: 13.68%
    - **Registration**: 11.29%
    - **Health**: 6.72%
    - **Education**: 6.08%
    - **Helpline**: 2.00%
    - **Protection**: 1.44%
    - **Employment**: 1.44%
## Arabic Text Preprocessing
Preprocessing Arabic text is crucial to ensure clean and meaningful input for the model. The following steps were applied:

1. **Stopword Removal**
   - Removed common Arabic stopwords, including custom frequently used phrases.

2. **Phrase Removal**
   - Filtered out common religious phrases and general expressions (e.g., “اللهم صل على النبي”, “حسبنا الله ونعم الوكيل”).

3. **Emoji and Symbol Removal**
   - Removed non-text symbols, emojis, and non-Arabic characters.

4. **Text Normalization**
   - Normalized different forms of Arabic letters (e.g., replaced "إأآا" with "ا").

5. **Duplicate Word Removal**
   - Removed duplicate words within comments to retain conciseness.

6. **Final Cleaning**
   - Cleaned URLs, repetitive patterns, and unnecessary words.

## Text Classification Using AraBERT
The model used for this task is **AraBERT**, a pre-trained BERT model optimized for Arabic text. Below are the implementation details:

### Process Steps

1. **Text Preprocessing**
   - Applied cleaning steps (stopword removal, phrase filtering, emoji cleaning, and normalization).

2. **Label Encoding**
   - Encoded target labels using `LabelEncoder` for model training.

3. **Dataset Splitting**
   - Split dataset into 80% training and 20% testing subsets.

4. **Custom Dataset Class**
   - Implemented a PyTorch `Dataset` class to tokenize input text and generate input IDs and attention masks suitable for AraBERT.

5. **Model Training**
   - Fine-tuned AraBERT using Hugging Face's `Trainer` API.
   - Configurations: Custom batch size, number of epochs, and learning rate.
   - Used a `compute_metrics` function to evaluate training accuracy.

6. **Model Evaluation**
   - Achieved a classification accuracy of **83.58%** on the test set.

7. **Model Saving**
   - Saved the trained model, tokenizer, and label encoder as a pickle file for deployment.

## User Interface
An interactive **Streamlit** application was built to make the model accessible to users. The UI provides the following features:

### Features
- **Upload CSV File**: Upload a file containing social media comments.
- **Predict Categories**: Predict categories for comments using the trained AraBERT model.
- **Download Results**: Download the updated CSV file with predicted labels.
- **Basic Analytics**:
  - Total number of comments.
  - Period covered by the data.
  - Number of unique users.
  - Graphical distribution of predicted categories.

### How to Use
1. Export comments from Facebook using **ExportComments**.
2. Upload the exported CSV file to the Streamlit application.
3. View predictions and analyze results.
4. Download the updated file with predictions for further use.

## Video Demonstration
Watch the step-by-step tutorial to learn how to use the application effectively.







https://github.com/user-attachments/assets/47c60c63-5e89-4532-9132-c28b99ea397b







## Project Highlights
- Developed an Arabic sentiment analysis model using **AraBERT**.
- Processed and normalized 2,000 Arabic comments for text classification.
- Built an interactive UI with **Streamlit** for real-time predictions and analysis.
- Achieved a classification accuracy of **83.58%**.
- Enabled actionable insights to understand refugee needs and improve services.

## Tools and Technologies Used
- **Python**: Data preprocessing, model training.
- **Hugging Face Transformers**: AraBERT fine-tuning.
- **Streamlit**: User interface for predictions and analytics.
- **ExportComments**: Data collection.
- **Matplotlib/Seaborn**: Visualizations.

---


