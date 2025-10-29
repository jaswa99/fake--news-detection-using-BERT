project builds and evaluates several machine learning models to classify news articles as "Fake" or "True". The models are trained on a dataset of news headlines and text, using NLP (Natural Language Processing) techniques for feature extraction.

The project demonstrates a comparative analysis of four different classification algorithms, with the Decision Tree Classifier achieving the highest accuracy at 99.53%.

📋 Dataset
The dataset consists of two separate CSV files:

Fake.csv: Contains news articles that are classified as "fake".

True.csv: Contains news articles that are classified as "true" (originating from sources like Reuters).

These datasets are loaded, assigned a binary class label (0 for Fake, 1 for True), and then merged into a single, shuffled DataFrame for processing.

⚙️ Project Workflow
The project follows a standard NLP and machine learning pipeline:

Data Loading & Merging:

Load Fake.csv and True.csv into pandas DataFrames.

Assign a class label: 0 for fake, 1 for true.

Merge the two DataFrames.

Drop irrelevant columns (title, subject, date).

Text Preprocessing:

A custom function (wordopt) is defined to clean the news text. This includes:

Converting text to lowercase.

Removing URLs and HTML tags.

Removing punctuation and special characters.

Removing digits.

This cleaning function is applied to the text column.

Feature Engineering (TF-IDF):

The cleaned text data is converted into a numerical feature matrix using TfidfVectorizer from scikit-learn.

This method weighs words based on their frequency in a document (Term Frequency) and their rarity across the entire corpus (Inverse Document Frequency).

English stop words are removed during vectorization.

Train-Test Split:

The dataset is split into training and testing sets, with 80% of the data used for training and 20% reserved for testing.

Model Training & Comparison:

Four different machine learning models are trained and evaluated to find the best performer:

Logistic Regression

Decision Tree Classifier

Gradient Boosting Classifier

Random Forest Classifier

📊 Model Performance
All models performed exceptionally well, indicating that the TF-IDF features are highly effective for this classification task. The Decision Tree Classifier achieved the highest accuracy on the test set.

Overall Accuracy
Model	Test Accuracy
Logistic Regression	98.66%
Decision Tree Classifier	99.53%
Gradient Boosting	99.51%
Random Forest	99.51%

Export to Sheets

Classification Report (Best Model: Decision Tree)
The classification report for the Decision Tree shows near-perfect precision, recall, and f1-scores for both classes.

              precision    recall  f1-score   support

           0       1.00      0.99      0.99      4681
           1       0.99      1.00      0.99      4807

    accuracy                           1.00      9488
   macro avg       1.00      1.00      1.00      9488
weighted avg       1.00      1.00      1.00      9488

Confusion Matrix
The confusion matrix for the models (example below from Random Forest) visually confirms the low number of misclassifications.

(Placeholder: Insert your confusion matrix plot here) ``

🧪 Manual Testing
The notebook includes a final section that allows you to input a custom news headline or text. This text is then processed through the same pipeline and classified by all four trained models, providing an immediate prediction.

🚀 How to Run
Clone the repository:

Bash

git clone <your-repo-url>
Install dependencies: It is recommended to use a virtual environment.

Bash

pip install pandas numpy scikit-learn seaborn matplotlib jupyter
(You can also generate a requirements.txt file from your environment.)

Get the Data:

Download the Fake.csv and True.csv files.

Place them in the same directory as the notebook.

Run the Notebook:

Start the Jupyter Notebook server:

Bash

jupyter notebook
Open fake-vs-real-news-detection-2.ipynb and run the cells sequentially.
