# Algorithmic Accountability in Media: Delineating Political Bias through TFIDF and Logistic Regression

**Author**: Ji Noh - eun.ji.noh@vanderbilt.edu

This repository contains the code and dataset used in the research paper titled "Dissecting Political Orientation in Media Content Through TFIDF and NLP Techniques." The study investigates the application of Term Frequency-Inverse Document Frequency (TFIDF) analysis, coupled with logistic regression, to classify news articles into conservative or liberal categories based on their content.


## 1. Repository Structure
- [code/](https://github.com/jinoh0731/NLP-Algorithmic-Accountability-in-Media/tree/main/code): This directory contains all Python scripts and Jupyter notebooks used in the analysis.
- [data/](https://github.com/jinoh0731/NLP-Algorithmic-Accountability-in-Media/tree/main/data): Due to size constraints, this directory contains a text file showing a link to the [Box folder](https://vanderbilt.box.com/s/xdd2aumtcliwqb8gnr8buh8pzujtkupm). This Box contains 3 subset of the data, which was then combined to do the analysis.
- [docs/](https://github.com/jinoh0731/NLP-Algorithmic-Accountability-in-Media/tree/main/docs): Documentation related to the project, including the paper.
- [figures/](https://github.com/jinoh0731/NLP-Algorithmic-Accountability-in-Media/tree/main/figures): Any figures or images, such as charts or diagrams used in the research paper.


## 2. About the Research
In an era of polarized political discourse, understanding media bias is more critical than ever. This project applies machine learning and natural language processing to a large corpus of news articles to discern linguistic patterns that correlate with political biases. We leverage the TFIDF statistical measure to highlight the importance of words within articles and use logistic regression to classify these texts according to the inferred political orientation of their source publications.

### 2-1. Research Question:
Can Term Frequency-Inverse Document Frequency (TFIDF) analysis distinguish between liberal and conservative news companies in the United States based on the content of their articles?

### 2-2. Hypothesis
TFIDF analysis of news articles will reveal distinct lexical patterns that correlate with the political bias of the news source. Specifically, conservative news outlets are expected to exhibit a unique set of frequently used terms and narratives that differ significantly from those employed by liberal news organizations.

## 3. Dataset
The dataset, titled "All the News," was sourced from Kaggle and compiled by Andrew Thompson. It consists of 142,570 articles from various U.S. news outlets spanning from 2000 to 2016. The dataset is uploaded in the data folder in the repository, also can be accessed directly from Kaggle at the following link: [Kaggle Dataset](https://www.kaggle.com/datasets/snapcrack/all-the-news/data)

### 3-1. Type of Publications
The dataset contains articles from a diverse array of 15 news outlets, including the New York Times, Breitbart, CNN, Business Insider, the Atlantic, Fox News, Talking Points Memo, Buzzfeed News, National Review, New York Post, the Guardian, NPR, Reuters, Vox, and the Washington Post. These 15 news sources span a broad spectrum of political alignments, ranging from conservative to liberal, with some positioned as neutral.

### 3-2. Categorization of Data
The dataset used in this analysis categorizes news outlets into "Conservative" and "Liberal" groups. This classification is based on the AllSides [Media Bias Chart](https://www.allsides.com/media-bias/media-bias-chart), a respected resource that assesses media sources on their political bias.

#### <ins>Conservative Outlets</ins>
- **Right**: Breitbart, Fox News, 
- **Lean Righ**t: New York Post, National Review

Breitbart and Fox News are categorized as Right by the AllSides Media Bias Chart, reflecting a conservative editorial stance. The New York Post and National Review, while still leaning conservative, are positioned closer to a neutral point of view on the spectrum. These outlets typically feature narratives that resonate with conservative principles, including limited government, individual liberties, and free markets.

#### <ins>Liberal</ins>
- **Left**: Atlantic, Vox
- **Lean Left**: CNN, Guardian, NPR, New York Times, Washington Post, Business Insider

Conversely, The Atlantic and Vox are classified as Left, exhibiting a liberal editorial focus. CNN, The Guardian, NPR, The New York Times, The Washington Post, and Business Insider are categorized as Lean Left, reflecting a preference for liberal perspectives. The content from these sources often highlights social justice, environmental concerns, and progressive policy discussions.

####  <ins>Moderate and Unknown</ins>
- **Moderate**: Reuters
- **Unknown**: Buzzfeed News, Talking Points Memo

Reuters is recognized for its neutral reporting and is thus categorized as Moderate. Buzzfeed News and Talking Points Memo are excluded from this study due to a lack of clear classification on the AllSides Media Bias Chart.

#### Data Division

To ensure an equitable analysis, the dataset was bifurcated into "Conservative" and "Liberal" sets. Two sources from the Right and two from the Lean Right were selected to compose the Conservative set, and similarly, two from the Left and two from the Lean Left formed the Liberal set. We then randomly sampled 250 articles from each of these publications, aiming for a balanced yet diverse representation for each political category.

```
conservative = ['Breitbart', 'Fox News', 'New York Post', 'National Review']
liberal = ['Atlantic', 'Vox', 'CNN', 'New York Times']
```

## 4. Method

### Logistic Regression for Classification
To discern the political bias in media content, logistic regression was employed as a classification algorithm. This method is commonly used for binary classification tasks and was chosen for its ability to estimate the probability that a given input belongs to one of two possible categories—conservative or liberal in our case. Logistic regression operates on the principle of the logistic function, also known as the sigmoid function, which maps any real-valued number into a value between 0 and 1, suitable for binary classification.

In our study, we used logistic regression in conjunction with Term Frequency-Inverse Document Frequency (TFIDF) scores to classify articles. After the preprocessing of data, which included data cleaning for removing potential bias, tokenization and removal of irrelevant characters, we transformed the corpus into a numerical format using TFIDF vectorization. This numerical representation was then fed into the logistic regression model.

### Model Output
The model was trained using a subset of our dataset (80% of data for training set), and evaluated on a separate test set to ensure the robustness and validity of the results. By utilizing logistic regression, we were able to predict with an accuracy of 72% whether an article was more likely to come from a conservative or liberal news source. 


