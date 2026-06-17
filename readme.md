# Album Recommendation System

A Python-based music recommendation engine that analyzes the acoustic profile of full-length albums using Spotify audio features. The system computes mathematical similarities between albums using metadata filtering and cosine similarity, ensuring recommendations stay structurally and culturally relevant.

## 🚀 Features

* **Single/EP Filtering:** Uses track-counting logic grouped by artist to automatically exclude singles and short EPs (less than 5 tracks) from recommendations.
* **Smart Metadata Handling:** Prevents data collisions by grouping unique artist-album combinations, cleanly handling identical album titles across different artists.
* **Genre Guardrails:** Employs a text-intersection keyword filter to prevent purely acoustic matches across completely unrelated musical genres.
* **Data Normalization:** Utilizes `StandardScaler` to bring distinct audio ranges (e.g., loudness decibels vs. danceability percentages) onto a uniform scale for fair mathematical scoring.

---

## 🛠️ How It Works

1. **Aggregation:** Aggregates track-level features (danceability, energy, tempo, etc.) into an averaged, distinct album-level profile.
2. **Vector Space Mapping:** Projects each album into a multidimensional vector space based on its acoustic properties.
3. **Similarity Calculation:** Uses Cosine Similarity to score the geometric distance between the target album's vector and the rest of the catalog.
4. **Output Filtering:** Iterates through the top mathematical matches, dropping items that fail track length requirements or genre keyword overlaps before displaying the top 10 results.

---
