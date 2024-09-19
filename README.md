# Quantitative Text Analysis of the U.N. General Debates

This repository contains a quantitative text analysis of speeches from the U.N. General Debates. The analysis leverages several R packages to process and analyze large-scale text data, with a particular focus on the speeches related to Israel and Palestine. Various models, visualizations, and sentiment analyses are applied throughout the analysis.

## Contents

### Data Processing

- **Data Ingestion**: Text from the U.N. General Debates is read in from `.txt` files using the `readtext` package. Document variables such as `country`, `session`, and `year` are extracted from filenames.
- **Corpus Creation**: The text data is transformed into a quanteda corpus for further analysis.
- **Document Counts**: Tables and graphs are generated to display the number of documents (speeches) per country and year.
- **Keyword Searches**: A keyword-in-context (KWIC) search is performed to isolate speeches that mention specific keywords like "Israel," "Palestine," "Jerusalem," "Gaza," and "West Bank."

### Visualization

- **Document Distributions**: Various plots visualize the distribution of speeches across countries and years, including a breakdown of mentions of specific keywords over time.
- **Keyword Analysis by Country**: Plots are created to show which countries mentioned keywords like "Israel" and "Palestine" the most, over time and across various keywords.
- **World Map Visualization**: The average number of mentions of each keyword is plotted on a world map using the `tmap` package.

### Sentiment Analysis

- **Latent Semantic Scaling (LSS)**: 
  - LSS models are built to examine the sentiment surrounding Israel and Palestine over time.
  - Various models isolate and compare sentiment trends, including:
    - Sentiment with all speeches.
    - Sentiment excluding speeches from Israel.
    - Sentiment concerning only Israel and Jerusalem.
    - Sentiment concerning Palestine, Gaza, and the West Bank.
  - Smoothing and visualization of the LSS results are performed to highlight trends.
- **Dictionary-Based Sentiment Analysis**: 
  - Using the `data_dictionary_LSD2015`, a dictionary-based sentiment analysis is performed for mentions of Israel and Palestine.
  - Visualizations compare positive and negative sentiment over time.
  
### Model Validation

- **BERT-Based Natural Language Inference**: 
  - Sentiment analysis is validated using BERT-based Natural Language Inference (NLI), using labeled sentiment data processed through a Kaggle notebook based on Moritz Laurer's approach.
  - Visualizations and summaries of BERT predictions for sentiment toward Israel and Palestine are included.

## Libraries Used

The analysis relies on several R packages, including but not limited to:

- `quanteda`
- `dplyr`
- `ggplot2`
- `readtext`
- `quanteda.textmodels`
- `quanteda.textstats`
- `tmap`
- `countrycode`
- `LSX`
- `gridExtra`

## How to Run the Analysis

1. **Install Required Libraries**:
   Ensure the required R packages are installed:

   ```r
   install.packages(c("quanteda", "dplyr", "ggplot2", "readtext", "tmap", "quanteda.textmodels", "quanteda.textstats", "countrycode", "gridExtra", "sf", "LSX"))

2. Load Data: Place the U.N. General Debate .txt files in the TXT/ directory.

3. Run the RMarkdown File: Use RStudio or any R-compatible environment to knit the Quantitative Text Analysis of the U.N.qmd file. The file will process the data and generate the visualizations and outputs described above.