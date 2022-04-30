# Depression-Analysis-and-Modeling
## Team-Data Pirates  
**Cheng Chun Ling**  
**Guo Siyi**  
**Lei Yu**  
**Sia Pei Ying**  
**Wang Yuqi**  
## Introduction  
Depression is a common mental illness. With the rapid development of social media platforms, people are more willing to express their feelings on social media platforms than to talk to friends and family. It is feasible and practical to study depression based on social media data. Based on the data from **Twitter**, this project used **topic modeling** and **sentiment analysis** using text classification to compare the classifiers used to predict depression tendency and analyze the influencing factors of depression.  
## Brief description of the project  
The project follows the steps below:  

**1. Data Extraction**  
We registered a developer account and crawl the data via the Twitter API to obtain tweets related to depression with keywords. We chose: depression, sad, suicide and stress. But due to the limitation access of the developer account, it only allowed us to retrieve up to 7 days tweets. For this research, the data was extracted from 4/3-4/8 period. After crawling down the data from Twitter, we got a data source named **df_data_global_v2**.  

**2. Text Preprocessing**
We mainly used **Texthero** to clean text information:  
**•	Fillna:** Replacing unassigned values with empty spaces, so we can avoid some unreadable characters.  
**•	Lowercase:** Changing all the text to lowercase to improve the efficiency of further data mining.  
**•	Remove URLs:** Removing all the links, which are commonly seen in tweets as users usually share some video or message from other websites.  
**•	Remove Punctuation:** Removing punctuation from the tweets data.   
**•	Remove Stop words:** Removing the stop words to improve the accuracy of the testing models and make the result more reliable and more efficient.  

**3. Data Annotation**  
We started by labelling the dataset with the help of existing sentiment analysis packages including **Flair**, **VADER** and **SentiWordNet**. In order to have a higher degree of accuracy, we first used three labelling techniques to label the first 100 tweets in the data set, and then manually labelled these 100 tweets to compare the results of each model with those of the manual labelling, and to come up with the most accurate model for final use. Flair has the highest accuracy and is the closest to the results of the manual labelling. Therefore, we finally used **Flair** for the annotation.  
  
**4. Exploratory Data Analysis**  
We explore few common questions on EDA analysis:  
① Top words comparison before and after text cleaning.  
② Summary of sentiment result after analysis.  
③ Top 10 countries that contribute the raw data and sentiment analysis comparison.  
④	Negative and Positive Sentiment results.  

**5. Topic Modeling**  
K-Means clustering was applied to our tweet clustering process. As for LDA, several parameters should be set well before processing, and an important one is the parameter num_topic which is the K for K clustering. Once the number of topics is determined and provided to the algorithm, the algorithm will help us to reprogram the distribution of topics in these texts and finally obtain an optimal topic-keyword distribution. For this study, the num_topic is set to 3.  

**6. Supervised Learning Classification**  
Seven supervised learning classifier models are built in this study by using different machine learning techniques to predict and classify depression and non-depression categories for the input tweets raw data. Tuning the parameter values for each machine learning algorithm effectively help to optimize each classifier model performances. The seven supervised learning classifiers are listed as below.  
•	Logistic Regression  
•	Support Vector Machine  
•	Naïve Bayes   
•	Decision Tree  
•	Random Forest  
•	AdaBoost  
•	Neural Network  

## Results  
**Topic Modeling**  
The result of clustering reminds us that the top cause behind the depression is stress and imbalance between work and life.
  
**Machine Learning Models**    

**① ACCURACY**  
•	Logistic Regression: 75.97%  
•	Support Vector Machine: 79.12%  
•	Naïve Bayes: 74.32%   
•	Decision Tree: 76.15%  
•	Random Forest: 80.68%  
•	AdaBoost: 80.98%  
•	Neural Network: 78.83%
  
**② PRECISION SCORE**  
•	Logistic Regression: 74.37%  
•	Support Vector Machine: 77.22%  
•	Naïve Bayes: 77.22%   
•	Decision Tree: 65.63%  
•	Random Forest: 79.27%  
•	AdaBoost: 79.33%  
•	Neural Network: 70.11%  

**③ RECALL SCORE**   
•	Logistic Regression: 46.72%  
•	Support Vector Machine: 48.81%  
•	Naïve Bayes: 36.44%   
•	Decision Tree: 64.22%  
•	Random Forest: 59.71%  
•	AdaBoost: 60.80%  
•	Neural Network: 67.51%  

**④ F1 SCORE**   
•	Logistic Regression: 57.33%  
•	Support Vector Machine: 64.02%  
•	Naïve Bayes: 49.52%   
•	Decision Tree: 64.98%  
•	Random Forest: 68.11%  
•	AdaBoost: 68.84%  
•	Neural Network: 68.78%  

**⑤ TIME IN SEC OF TRAINING**   
•	Logistic Regression: 0.181seconds  
•	Support Vector Machine: 72.0seconds  
•	Naïve Bayes: 0.006seconds  
•	Decision Tree: 3.88seconds  
•	Random Forest: 17.6seconds  
•	AdaBoost: 143.0seconds  
•	Neural Network: 177.0seconds  

