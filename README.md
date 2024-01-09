# link-prediction-yelp
Testing link prediction techniques on a Yelp dataset. It can be used as part of a recommender system on graph data.

## Data

Extracted from [this](https://www.kaggle.com/competitions/predicao-de-links-utfpr-2023-2/data) kaggle challenge.

## Overview

The first technique applied was using a boosted tree classifier ([CatBoost](https://catboost.ai/)) on edge data extracted from the graph. To add information about the links, I used a Node2Vec model to generate embeddings for the specific graph. The node features were also used.

For the second technique, I used a Graph Auto-Encoder (GAE), with a graph convolutional network as the Encoding layer and the a inner product Decoder. The library used was [PyTorch Geometric](https://github.com/pyg-team/pytorch_geometric).

## General results

Results are shown in the notebook, but as a general result the CatBoost performed better. The features used in the first technique were much more refined. The only metric avaliable in the kaggle challenge was the F1 score. Here are the best results for each technique:

| Technique | Best F1 score |
|-----------|---------------|
| CatBoost  | **0.81794**   |
| GAE       | 0.76727       |
