# Integrated Analysis of Airbnb User Experience in Melbourne

This project explores the behavioral patterns and satisfaction signals of Airbnb guests in Melbourne, Australia. By leveraging both structured listing features and unstructured guest reviews, I developed two complementary pipelines: one for quantitative feature-based modeling and another for natural language processing of review text.

---

## 🗂 Dataset

- **Source**: [Kaggle - Melbourne Airbnb Open Data](https://www.kaggle.com/datasets/tylerx/melbourne-airbnb-open-data)
- **Scope**: Over 480,000 reviews and over 22,000 rows of listing data
- **Focus**: Guest review data and listing features for sentiment, pricing, and satisfaction analysis
- **Content**
  - [`01_listings_summary_dec18.csv`](https://github.com/zion-wu/Integrated-Analysis-of-Airbnb-User-Experience-in-Melbourne/blob/main/datasets/01_listings_summary_dec18.csv)
  - [`01_preprocessed_listings_summary.csv`](https://github.com/zion-wu/Integrated-Analysis-of-Airbnb-User-Experience-in-Melbourne/blob/main/datasets/01_preprocessed_listings_summary.csv) is preprocessed
  - `02_reviews_dec18.csv` can be found in public dataset [Kaggle - Melbourne Airbnb Open Data - reviews_dec18](https://www.kaggle.com/datasets/tylerx/melbourne-airbnb-open-data?select=reviews_dec18.csv)

---

## 📌 Project Structure

### 1. Structured Feature Analysis (ML)

**Objective**: Understand which structured attributes (price, amenities, location, etc.) influence listing performance and guest satisfaction.

**Key Components**:
- **Data Preprocessing**: Extensive EDA and cleaning of outliers, nulls, and categorical variables.
- **Feature Engineering**: Created interpretable factors such as availability rate, review frequency, pricing tiers, and derived distance proxies.
- **Modeling**: Applied ElasticNet, Random Forests and XGBoost to evaluate feature importance related to host rating and review behavior.
- **Insights**:
  - Availability, host responsiveness and superhost status were top predictors of guest satisfaction.
  - High-priced listings did not always translate to higher review scores.
  - Amenity variety and review volume played nuanced roles in guest engagement.

📎 Files:
- `datasets/01_listings_summary_dec18.csv`
- `datasets/01_preprocessed_listings_summary.csv`
- `notebooks/01_structured_feature_analysis.ipynb`
- `reports/01_structured_feature_analysis_report.pdf`
- `presentations/01_structured_feature_analysis_slides.pdf`
- `results/01_Heatmap_Tableau.png`

---

### 2. Unstructured Text Analysis (NLP)

**Objective**: Mine guest review text to extract fine-grained sentiment signals and aspect-level feedback using ABSA (Aspect-Based Sentiment Analysis).

**Key Components**:
- **Text Cleaning & Normalization**: Removed noise, lemmatized tokens, filtered stopwords and low-information content.
- **Aspect Extraction**:
  - Rule-based keyword matching
  - LDA topic modeling
  - BERTopic with embedding-based clustering
- **Sentiment Analysis**:
  - VADER (lexicon-based)
  - BERT (contextual classifier)
- **Cross Analysis**:
  - Identified consistently positive aspects: location, cleanliness, host communication
  - Outlier topics such as reservation procedure and cleaning fees exhibited higher non-positive polarity

📎 Files:
- `datasets/02_reviews_dec18.csv`
- `notebooks/02_review_text_analysis.ipynb`
- `reports/02_review_text_analysis_report.pdf`
- `presentations/02_review_text_analysis_slides.pdf`
- `results/02_bertopic_results.csv`

---

## 🔑 Key Insights

- **Top Structured features** such as availability, host responsiveness, and superhost status are stronger satisfaction drivers than price.
- **Textual feedback** uncovers latent dissatisfaction not reflected in numerical scores, especially around booking logistics and cleaning fees.
- **Combining structured and unstructured data** allows for a deeper, more holistic view of guest experience and operational bottlenecks. Integrating both modalities gives hosts and platform operators a more holistic understanding of service gaps and strengths.

---

## 💡 Applications

- Hosts can improve competitive edge by addressing frequently cited pain points in reviews.
- Platforms like Airbnb can integrate aspect-based review summarization into dashboards to support listing quality control.
- This hybrid approach—combining structured feature modeling with review text analysis—can be applied to other platforms with user-generated content (e.g., TripAdvisor, Yelp, Amazon) to uncover user experience patterns and product feedback at scale.

---

## 📁 Folder Overview
- Files starting with 01 are related to Structured Feature Analysis (ML), while 02 related to Unstructured Text Analysis (NLP).
```bash
Integrated-Analysis-of-Airbnb-User-Experience-in-Melbourne/
│
├── datasets/                         # Raw and preprocessed data files
│   ├── 01_listings_summary_dec18.csv
│   ├── 01_preprocessed_listings_summary.csv
│   └── 02_reviews_dec18.csv
│
├── notebooks/                        # Jupyter notebooks (code)
│   ├── 01_structured_feature_analysis.ipynb
│   └── 02_review_text_analysis.ipynb
│
├── reports/                          # PDF reports
│   ├── 01_structured_feature_analysis_report.pdf
│   └── 02_review_text_analysis_report.pdf
│
├── presentations/                    # Project presentation slides
│   ├── 01_structured_feature_analysis_slides.pdf
│   └── 02_review_text_analysis_slides.pdf
│
└── results/                          # Model outputs and visualizations
    ├── 01_Heatmap_Tableau.png
    ├── 01_Heatmap_Tableau.twb
    └── 02_bertopic_results.csv
```

---
