# 🧠 SentimentSense

**SentimentSense** is a lightweight, edge-AI web application that performs binary sentiment analysis (Positive/Negative) on text. Instead of relying on cloud APIs or backend servers, this project runs a pre-trained Machine Learning model directly in the browser using JavaScript.

🔗 **[Live Demo](https://sentiment-sense-nine.vercel.app/)** 

## 🚀 Overview

This project bridges the gap between traditional machine learning and modern web development. By training a model in Python and exporting its learned weights and vocabulary into a static JSON format, the React frontend can reconstruct the inference pipeline. This allows for instant, offline, and cost-free text classification.

* **Live Application:** [sentiment-sense-nine.vercel.app](https://sentiment-sense-nine.vercel.app/)
* **Dataset:** SST-2 (Stanford Sentiment Treebank), sourced from Hugging Face Datasets.
* **Accuracy:** ~78.47% on the held-out test split.
* **Architecture:** TF-IDF Vectorization (Unigrams & Bigrams) + Logistic Regression.

## ✨ Key Features

* **Zero-Latency Edge Inference:** No API calls, no loading spinners, and no backend hosting costs. The math runs entirely on the client's device.
* **Transparent AI:** The model uses a "white-box" Bag of Words approach. Users can see exactly which words contributed to the final probability score and by how much.
* **Interactive UI:** Built with React and Vite, featuring a responsive, modern design to test the model dynamically.

## ⚙️ How It Works (The Pipeline)

1. **Text Preprocessing:** The input text is lowercased, and punctuation is stripped using regex tokenization.
2. **Stop Word Removal:** Common, non-descriptive English words (like "the", "is", "at") are filtered out.
3. **TF-IDF Vectorization:** The remaining words (and word pairs) are mapped against a learned vocabulary of 2,500 terms. Their Term Frequency-Inverse Document Frequency (TF-IDF) is calculated.
4. **Logistic Regression:** The resulting mathematical vector is multiplied by the model's pre-trained coefficients (dot product).
5. **Sigmoid Activation:** The raw score is passed through a Sigmoid function to output a clean probability percentage (0% to 100%).

## 🛠️ Tech Stack

* **Frontend Framework:** React, Vite
* **Styling & Icons:** CSS (embedded), Lucide React
* **ML Training (Offline):** Python 3, scikit-learn, Hugging Face Datasets

## 🚧 Limitations & Future Scope

While highly optimized for speed and size, this linear "Bag of Words" approach has known linguistic limitations:
* **Context Blindness:** The model ignores sentence structure, meaning it struggles with sarcasm.
* **Long-Range Negation:** Modifiers placed far away from their target words (e.g., "I really cannot say it was good") can confuse the classifier.
* **Future Work:** Compare this baseline implementation against an in-browser Transformer model (like DistilBERT using ONNX Runtime Web) to evaluate the trade-off between semantic accuracy and computational payload.

## 💻 Local Setup

To run this project locally on your machine:

1. Clone the repository:
   ```bash
   git clone [https://github.com/yourusername/sentimentsense.git](https://github.com/yourusername/sentimentsense.git)
