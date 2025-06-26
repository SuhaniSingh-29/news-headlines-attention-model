# 🗞️ News Headline Generator using Seq2Seq + Attention

This project builds a deep learning model that **generates headlines** from news article descriptions. Currently, the model achieves around **78% accuracy** and will be improved further with better training strategies and data augmentation.

---

## 📂 Dataset

We use the **HuffPost News Category Dataset** (`News_Category_Dataset_v3.json`), which contains:

* Total rows and columns: (209527, 6)
* Fields like `headline`, `short_description`, `category`, `authors`, `links` and 'date'.

For this project, we sample **7,500** examples for training and validation.

---

## 🧼 Data Cleaning & Preprocessing

Preprocessing includes:

* Lowercasing and punctuation removal
* Removing links, stopwords, and short tokens
* Tokenization and lemmatization
* Padding sequences to fixed length

> Check out the notebook for detailed steps on data cleaning and tokenizer configuration.

---

## 🏗️ Model Architecture

We use a **Seq2Seq model with Bahdanau Attention**, consisting of:

* 🧠 **Encoder**: 3 stacked LSTM layers that process the news descriptions
* 📘 **Decoder**: LSTM-based decoder that generates headlines
* 🎯 **Attention Layer**: Helps the decoder focus on relevant words in the input at each step

> This approach is inspired by the human tendency to pay attention to relevant parts of an input when generating output — just like we do when reading and summarizing.

### 🔀 Attention Intuition (Example)

For the input:

> "Which sport do you like the most?"

The generated headline:

> "I love cricket"

Here:

* "I" aligns with "you"
* "love" aligns with "like"

The model learns these alignments using the **attention mechanism**.

---

## ⚙️ Training Details

* Loss Function: `SparseCategoricalCrossentropy`
* Optimizer: `Adam`
* Metrics: Accuracy
* Callbacks:

  * `EarlyStopping` (patience=40)
  * `ReduceLROnPlateau`
  * `ModelCheckpoint` (to save the best model)

### 📉 Training Performance


---

## 🛃️ Future Plans

While the model works reasonably well, there’s room for improvement:

* 📈 Increase training data size
* 🧪 Hyperparameter tuning
* 🔀 Try different encoder structures (e.g., bidirectional LSTMs or GRUs)
* 🧠 Experiment with transformer-based architectures like BART/T5
* 🕒 Train longer with better learning rate schedules

---

## 🧑‍💻 Author

**Suhani Singh**
Feel free to reach out or fork the project for your own experiments!!!
