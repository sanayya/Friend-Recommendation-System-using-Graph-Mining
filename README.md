# Friend-Recommendation-System-using-Graph-Mining
**Problem statement**
Given a directed social graph, we want to predict missing links to recommend friends/connections and followers.

**Mapping the problem**
Let us say that we have vertex Ui and Uj. If Ui is following Uj or there is a directed edge between Ui and Uj: it will be labeled as “1”. If Ui is not following Uj or there is no edge between Ui and Uj: it will be labeled as “0”. So, the problem automatically gets mapped to a binary classification problem.

**Performance Metrics**
•	No low-latency requirements- We can precompute the top 5 or 10 friends Ui should follow once in 2 days or weekly or every night and store it in a hash table-like structure and show it whenever Ui logs in. As we can precompute, so there’s no strong latency requirement
•	We will recommend the highest probability links to a user, so we need to predict the probabilities of the links which are useful- We could have 100 such users which Ui could follow, and we can have the probability values. We might have 5 slots or 10 slots, where we want to show the most probable top 5 friends the user Ui may want to follow.
•	Both precision and recall are important, hence F1 score is a good choice here. We will also plot Confusion matrix.

**Dataset:**
We will be using the dataset provided by Facebook: https://www.kaggle.com/c/FacebookRecruiting 
Exploratory Data Analysis:
•	We will be using the networkx library as it is very helpful for graph related features.
•	We will perform EDA to find out patterns in the data and visualize the graph data.
Posing a problem as a classification problem
•	As discussed before, we want to convert this into a binary classification problem such that existing edges are labelled as “1” and non-existing edges or absent edges are labelled as “0”.
•	In the original dataset, non-existing edges are not labelled as “0”. Therefore, we will generate data for the label “0”. We will randomly sample edges from total number of edges to make our data a balanced dataset for binary classification. We will only consider those nodes where edges from one node to another are greater than 2 as “0”.
•	We will perform train test splitting in 80:20 ratio.

**Feature Engineering:**
•	We will create new features in the dataset from existing features. 
•	We will calculate similarity measures such as Jaccard distance and Cosine distance (Otsuka-Ochiai coefficient).  
•	We will also create graph features such as shortest path, Adar index, Katz centrality, HITS score, SVD.

**Modelling:**
•	After feature engineering, we will perform hyperparameter tuning and create models using Random Forest and XGBoost to compare the performance.
•	We will also plot Confusion Matrix, ROC curve, and find out the importance of different parameters to analyse which parameters are the most important for the problem we are trying to solve.

