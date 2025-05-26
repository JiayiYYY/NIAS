# Ecological Narrative Comparison between Pokémon and Endangered Mammals

Hi! This project compares the *narrative resemblance* between Pokémon descriptions and endangered mammal descriptions using NLP. I use semantic similarity and topic modeling to explore how fictional and real animal narratives overlap.

## 🧠 What the Code Does

Everything is organized in **`Final_Assignment.ipynb`**, which includes:

1. **Data Loading & Preprocessing**
   I import Pokémon and mammal descriptions, clean the text, and prepare the inputs for modeling.

2. **Semantic Similarity Matching (BERT)**
   I use Sentence-BERT (`all-MiniLM-L6-v2`) to find the most similar real mammal for each Pokémon, based on their description. Before that, there was a first try with basic TF-IDF method, which yielded less satisfying results. But feel free to try both!

3. **Topic Modeling (BERTopic)**
   I apply BERTopic *separately* to the two corpora (Pokémon and mammals) to discover ecological themes like "aquatic," "nocturnal," or "rodent-like."

4. **Topic–Topic Heatmap**
   I average BERT embeddings within each topic and compute cosine similarity between Pokémon and mammal topics to see which themes align.

5. **Visualization & Results**
   I plot the topic similarity heatmap and include code to summarize findings (e.g., highest-matching Pokémon, theme clusters, etc.).

## 🛠 Setup Instructions

To run the notebook, make sure you have the following installed:

```bash
pip install pandas numpy matplotlib seaborn \
    sentence-transformers bertopic scikit-learn \
    umap-learn hdbscan tqdm
```

Recommended Python version: **3.8+**

Run everything in order from top to bottom. Some BERTopic steps may take a few minutes depending on your machine.

## 📌 Notes

* BERTopic is **unsupervised**, so results may vary slightly between runs.
* I used the **elbow method** to help decide the number of topics for interpretability
* If embeddings or CSVs aren't pre-saved, the notebook will generate everything fresh.
