# Research Paper Vetting System

## 📌 Overview

The **Research Paper Vetting System** is an NLP-driven pipeline designed to **automatically evaluate scientific papers before the peer review stage**. The system analyzes research papers across multiple dimensions—such as citation support, argument quality, headline accuracy, readability, and reviewer concerns—and generates a **structured vetting report**.

This project uses a **hybrid approach combining multiple machine learning models and rule-based scoring**, enabling both statistical learning and logical reasoning for comprehensive evaluation.

---

## 🎯 Objective

* Detect unsupported or weakly supported claims
* Identify overstatements between title/abstract and results
* Evaluate logical consistency of arguments
* Measure readability and complexity
* Predict potential peer review concerns

---

## 🚀 Features

* 📑 Citation Worthiness Detection
* 🧠 Argument Quality Analysis (rule-based)
* 📰 Headline Accuracy Checker
* 📊 Cognitive Load Estimation (readability, jargon, complexity)
* 🧪 Peer Review Quality Predictor (rule-based)
* 📄 Unified Paper Quality Score (0–100)

---

## 🏗️ System Architecture

The system consists of five core modules:

### 1. Citation Worthiness Scorer

* Models used:

  * TF-IDF + Logistic Regression
  * SciBERT with feature fusion
* Task: Detect claims requiring citations

### 2. Argument Quality Scorer

* Fully **rule-based system** using:

  * Argument strength
  * Logical consistency
  * Overclaim detection

### 3. Headline Accuracy Checker

* Logistic Regression (classification)
* Ridge Regression / Random Forest (severity prediction)

### 4. Cognitive Load Estimator

* Models:

  * Ridge Regression
  * Random Forest
* Evaluates:

  * Readability
  * Jargon density
  * Structural complexity

### 5. Peer Review Quality Predictor

* Rule-based aggregation of all modules
* Simulates reviewer concerns and feedback

---

## 📊 Dataset

* 476 research papers (after preprocessing)

* Source: S2ORC (Semantic Scholar Open Research Corpus)

* Includes:

  * Title, abstract, results sections
  * 21 annotated features
  * Quality scores and flags

* Additional components:

  * Custom annotated dataset
  * Rule-based labels for argument and peer review modules

---

## ⚙️ Methodology

### 🔹 Preprocessing

* Text cleaning and normalization
* Section segmentation (title, abstract, results)
* Feature engineering:

  * Length features
  * Lexical cues (claims, hedges, evidence)
  * Structural indicators

### 🔹 Feature Extraction

* TF-IDF (unigrams + bigrams)
* SciBERT embeddings
* Handcrafted linguistic features

---

## 📈 Results

### ✅ Citation Worthiness

* TF-IDF + Logistic Regression (Best Model)

  * Test F1: **0.853**
* SciBERT showed lower generalization performance

### ✅ Headline Accuracy

* Logistic Regression:

  * Test Accuracy: **0.958**
  * Test F1: **0.929**

### ✅ Cognitive Load

* Ridge and Random Forest models used
* Observed overfitting due to dataset size

### ✅ Argument Quality

* Rule-based scoring using logical and linguistic signals

### ✅ Peer Review Prediction

* Rule-based aggregation
* Distribution:

  * 56.1% Low concern
  * 28.8% Moderate
  * 15.1% High

### 🏆 Unified Model

* Mean score: **72.4 / 100**
* Distribution:

  * 54.8% Excellent
  * 27.1% Good
  * 14.3% Fair
  * 3.8% Poor

---

## 🧠 Key Insights

* Classical ML (TF-IDF + LR) outperformed transformer models in low-data settings
* Argument quality, headline accuracy, and peer review signals are strongly correlated
* Citation quality and readability capture independent aspects of paper quality

---

## 👥 Team

Developed as part of a **team of 4**, with contributions including:

* Dataset creation and annotation
* Rule-based system design (argument & peer review)
* ML model development (multiple models evaluated)
* End-to-end pipeline integration

---

## ⚠️ Limitations

* Small dataset size
* Partial reliance on rule-based scoring
* Some labels generated using LLMs (silver labels)

---

## 🔮 Future Work

* Expand dataset and improve annotations
* Use advanced transformer models for all modules
* Section-level citation alignment
* Integration with real peer review workflows


---

## ⭐ Acknowledgements

* Semantic Scholar (S2ORC dataset)
* SciCite & PeerRead datasets
* NLP research community
