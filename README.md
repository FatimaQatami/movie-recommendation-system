# movie-recommendation-system
Hybrid movie recommender using ALS + content-based filtering on MovieLens 32M

# Movie Recommendation System

A hybrid movie recommender system built on the MovieLens 32M dataset (32 million ratings), combining collaborative filtering and content-based filtering to generate personalized top-10 movie recommendations.

## Overview

This project explores multiple recommendation approaches and evaluates them using standard recommender-system metrics, culminating in a hybrid model that blends the strengths of both collaborative and content-based methods.

## Dataset

- **Source:** MovieLens 32M (ml-32m)
- **Size:** ~32 million ratings across a large set of users and movies

## Approach

1. **Data Cleaning & Preprocessing**
   - Checked for missing values and duplicates
   - Remapped movie IDs to a contiguous range
   - Applied mean-centering normalization to ratings per user
   - Split data into train/test sets and converted to sparse matrices for memory efficiency

2. **Collaborative Filtering (ALS)**
   - Implemented Alternating Least Squares (ALS) using the `implicit` library
   - Tuned latent factors, iterations, and regularization

3. **Content-Based Filtering (CBF)**
   - Computed item similarity scores based on content features
   - Generated per-user recommendation scores from similar items

4. **Hybrid Model**
   - Blended normalized ALS and CBF scores using a weighted approach (alpha parameter)
   - Generated top-10 recommendations per user

## Evaluation

Model performance was assessed using:
- Precision@10, Recall@10, F1@10
- MAP@10 (Mean Average Precision)
- NDCG@10 (Normalized Discounted Cumulative Gain)
- Coverage
- Diversity

### Hybrid Model Results
| Metric | Score |
|--------|-------|
| Precision@10 | 0.2055 |
| Recall@10 | 0.1710 |
| F1@10 | 0.1446 |
| MAP@10 | 0.1788 |
| NDCG@10 | 0.2816 |
| Coverage | 0.0614 |
| Diversity | 0.8063 |

## Tools & Libraries

Python, pandas, NumPy, scikit-learn, scipy (sparse matrices), `implicit` (ALS), matplotlib

## Author

Fatima Qatami
