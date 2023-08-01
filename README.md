# Exploring the variety of phrasing in baroque music performance: Project Overview
### Introduction
Many people have the impression that Bach should be played in a stiff and mechanical way since this is how people are often taught to play Bach at a young age. The reality is that baroque performance practice is a highly varied and nuanced art form. In this project I explore the phrasing attributes of three distinct performance styles of historical Baroque music.

This project showcases:
- **Visualization of high dimensional data:** Using t-squared stochastic neighbor embedding (t-SNE), I show how high-dimensional data can be effectively visualized.
- **Input feature comparison:** I compare two sets of input features by using them to train a machine learning classifier and comparing the resulting accuracies.
- **Importance of domain knowledge:** By leveraging knowledge of music performance I was able to improve the ability of a classifier to predict performance style by 20% through improved feature engineering.

### Code and Resources Used
**Python Version**: 3.11.4
**Packages**: pandas, numpy, matplotlib, scikit-learn

### Website blog post
https://www.nolaneley.com/baroque-phrasing

### Data sources and cleaning
The data was manually calculated from raw audio recordings of three compositions by three different artists (representing three distinct performance styles) below:
- Yehudi Menuhin, 1934, Philips 438 736-2
- Arthur Grumiaux, 1967, Nonesuch 7559 73030-2
- Sergiù Luca, 1977, EMI CHS 7 63035 2

For complete information on how the tempo and loudness information were extracted from the audio, you can read chapters 5 and 6 of my PhD Manuscript: https://www.theses.fr/2023CYUN1166

All data were manually verified before any analysis.

### EDA
In order to visualize high-dimensional data, t-squared stochastic neighbor embedding (t-SNE) was used.

![tsnePerformer](/images/tsne_performer.png)

### Classification
I trained support vector machines with radial basis function kernels and 5-fold cross validation to predict the performer based on two sets of features: the raw note-level tempo and loudness, and the engineered features (summary statistics of tempo and loudness of musically meaningful durations). I measured the performance of these two sets of features by taking the mean accuracy across these 5 folds.

| Input features | Mean Accuracy |
|----------|----|
| Raw features |  47.19% |
| Engineered features |  **68.32%** |  
