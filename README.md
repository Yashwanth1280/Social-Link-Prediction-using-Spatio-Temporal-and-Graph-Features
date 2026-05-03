# 🌐 Social Link Prediction using Spatio-Temporal and Graph Features

This project focuses on predicting social relationships between users by analyzing **spatio-temporal co-occurrence patterns** and **graph-based features** derived from Flickr datasets.

It combines **data preprocessing, graph modeling, and machine learning** to build a system capable of predicting social links and recommending potential connections.

---

## 🚀 Overview

- 📍 Uses **GPS + timestamp data** from Flickr photo uploads  
- 🔗 Builds a **user co-occurrence graph**  
- 🤖 Applies **machine learning techniques** for link prediction  
- 👥 Provides a **location-based friend recommendation system**  

---

## 📂 Dataset

The project uses three Flickr XML datasets:

- `photosCLEF.xml`
- `photosMIR.xml`
- `photosPASCAL.xml`

These datasets include:
- User IDs and usernames  
- Photo timestamps  
- GPS coordinates (latitude & longitude)  
- Titles and descriptions  

After preprocessing:
- Total records: **29,195**
- Valid geo-tagged records: **6,479** :contentReference[oaicite:0]{index=0}  

---

## ⚙️ Methodology

### 1. Data Preprocessing
- Parsed XML using Python (`ElementTree`, `pandas`)
- Cleaned missing values
- Converted timestamps from epoch format

### 2. Dataset Consolidation
- Merged datasets into a unified structure
- Generated:
  - `merged_photos.csv`
  - `df_all.pkl` :contentReference[oaicite:1]{index=1}  

### 3. Spatio-Temporal Co-Occurrence
Users are considered co-occurring if:
- ⏱ Within **1 hour**
- 📍 Within **0.1 – 100 km distance**

- Used **sliding window algorithm**
- Distance computed using **Haversine formula**
- Output: `user_cooccurrences.csv` :contentReference[oaicite:2]{index=2}  

### 4. Feature Engineering
- Co-occurrence frequency  
- Geographic proximity  
- Graph-based relationships  

### 5. Link Prediction
- Machine learning model trained on extracted features  
- Predicts likelihood of social connections  

---

## 📊 Results

- ✅ **F1 Score:** 1.0  
- ✅ **Precision:** 1.0  
- ✅ **Recall:** 1.0  

(Note: High scores due to filtered dataset with strong geo-temporal signals) :contentReference[oaicite:3]{index=3}  

---

## 🤝 Friend Recommendation System

- Suggests users based on:
  - High co-occurrence frequency  
  - Low average geographic distance  

This enables **location-aware social recommendations**.

---

## ▶️ Run the Project

Run the following command:

pip install pandas numpy && python main.py
