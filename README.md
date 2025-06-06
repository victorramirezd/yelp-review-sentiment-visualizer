# yelp-review-sentiment-visualizer

This repository contains a simple Python pipeline for sampling Yelp review data, merging it with precomputed sentiment‐analysis scores, and visualizing the relationship between user star ratings and sentiment polarity in a jittered scatter plot.

## Features

- **Data Sampling**  
  Loads a JSON file of Yelp reviews, takes a random sample (e.g. 200 records), and writes it back out as a smaller JSON for faster iteration.

- **Sentiment Merge**  
  Reads a CSV of sentiment-analysis results (indexed by `review_id`), renames and aligns the score column, then joins it to the sampled reviews on `review_id`.

- **Jittered Scatter Plot**  
  Uses NumPy to add a small Gaussian jitter to both the `stars` (x-axis) and `sentiment_score` (y-axis) values to prevent overplotting. Matplotlib then renders the plot, revealing the overall trend that higher star ratings tend to correspond with higher sentiment scores, while still showing the full distribution of individual points.

- **Visualization**  
  ![Stars vs. Sentiment Correlation](plot%20correlation%20v2.png)
  The output image clearly displays each review as an “×” marker, with axes labeled and gridlines for reference.
  We can see a clear correlation between the score given by the model and the stars given by the user (ground truth).

## Usage

1. Clone the repo:
   ```bash
   git clone https://github.com/your-username/yelp-review-sentiment-visualizer.git
   cd yelp-review-sentiment-visualizer
