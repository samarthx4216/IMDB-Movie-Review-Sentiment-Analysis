# 🎬 IMDB Movie Review Sentiment Analysis

A deep learning web app that classifies movie reviews as **Positive** or **Negative** using a Simple RNN trained on the IMDB dataset — deployed with Streamlit.

---

## 📌 Project Overview

This project builds a binary sentiment classifier using a Simple Recurrent Neural Network (RNN). Users can enter any movie review and instantly receive a sentiment prediction along with a confidence score.

---

## 🧠 Model Architecture

| Layer        | Type        | Output Shape  | Parameters |
|--------------|-------------|---------------|------------|
| Embedding    | Embedding   | (None, 500, 128) | 1,280,000 |
| SimpleRNN    | SimpleRNN   | (None, 128)   | 32,896     |
| Dense        | Dense       | (None, 1)     | 129        |

- **Total Parameters:** ~1.3 Million  
- **Activation:** Sigmoid (output layer)  
- **Loss Function:** Binary Crossentropy  
- **Saved Model:** `simple_rnn_imdb.h5`

---

## 📂 Project Structure

```
├── simple_rnn_imdb.h5     # Pre-trained RNN model
├── main.py                # Streamlit web application
├── prediction.ipynb       # Prediction & testing notebook
├── simplernn.ipynb        # Model training notebook
└── README.md
```

---

## ⚙️ Installation

**1. Clone the repository**
```bash
git clone https://github.com/your-username/imdb-sentiment-rnn.git
cd imdb-sentiment-rnn
```

**2. Install dependencies**
```bash
pip install tensorflow streamlit numpy
```

---

## 🚀 Run the App

```bash
streamlit run main.py
```

Then open your browser at `http://localhost:8501`

---

## 🔍 How It Works

1. **Input** — User enters a movie review as plain text
2. **Tokenization** — Words are lowercased and mapped to IMDB word indices
3. **Padding** — Sequence is padded/truncated to 500 tokens
4. **Prediction** — Model outputs a score between 0 and 1
5. **Result** — Score > 0.5 → ✅ Positive | Score ≤ 0.5 → ❌ Negative

---

## 🧪 Example

| Review | Sentiment | Score |
|--------|-----------|-------|
| *"This movie was fantastic! The acting was great and the plot was thrilling."* | ✅ Positive | 0.81 |

---

## 🛠️ Tech Stack

- **Python 3.11**
- **TensorFlow / Keras**
- **NumPy**
- **Streamlit**

---

## 📊 Dataset

- **Source:** Keras built-in IMDB Dataset
- **Size:** 50,000 reviews (25k train / 25k test)
- **Labels:** Binary — Positive / Negative
- **Vocabulary:** Top 10,000 words
- **Max Sequence Length:** 500 tokens
