
# 📧 Spam Email Classifier

This project builds a machine learning model to classify emails as **Spam** or **Ham (Non-Spam)** using Word2Vec embeddings and various ML algorithms. The goal is to help detect and filter spam emails automatically.

---

## 📂 Dataset Overview

- **Source**: [Kaggle - Spam Emails](https://www.kaggle.com/datasets/abdallahwagih/spam-emails)
- **Size**: 480 KB (CSV)
- **Features**:
  - `Message`: The email content (subject + body)
  - `Category`: The label — either `Spam` or `Ham`

📊 **Distribution**:
- Ham: 87%
- Spam: 13%
- Total Emails: 5157

---

## 🧠 Model Overview

- Text is vectorized using pre-trained **Google News Word2Vec** embeddings.
- Models used:
  - Naive Bayes
  - Random Forest
  - Support Vector Machine (SVM)
  - XGBoost

The best performing model is selected based on accuracy on a test split.

---

## 🧪 Accuracy Results

| Model         | Accuracy Score |
|---------------|----------------|
| Naive Bayes   | 0.8717         |
| Random Forest | 0.9713         |
| SVM (RBF)     | **0.9883**     |
| XGBoost       | 0.9776         |

✅ **Selected Model**: `SVC()`  
🏆 **Best Accuracy**: `0.9883`

---

## 🛠️ Dependencies

Make sure to install the following:

```bash
pip install pandas numpy nltk scikit-learn xgboost gensim
```

Also, download and place the **Google News Word2Vec** binary model (`word2vec-google-news.model`) into your working directory or Google Drive if using Colab.

---

## 📌 Usage

1. Mount Google Drive (for model file, if running in Colab)
2. Load dataset and preprocess
3. Train and evaluate models
4. Predict on new email samples

Example:

```python
text = "Subject: Confirm Your Email Now — Dear User, we’ve noticed unusual activity on your account..."
X_in_vec = np.array([_vectorizer(text)])
y_p = model.predict(X_in_vec)
print(le.inverse_transform(y_p))
```

---

## 🔒 License

This project uses the [Apache 2.0 License](https://www.apache.org/licenses/LICENSE-2.0). Dataset use may be subject to separate restrictions—verify with [Kaggle Terms](https://www.kaggle.com/terms).

---

## 🙌 Acknowledgements

- Dataset by Abdallah Wagih on Kaggle  
- Word2Vec pre-trained embeddings from Google  
- Developed in Google Colab
