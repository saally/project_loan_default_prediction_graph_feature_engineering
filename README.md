# Loan Default Prediction with Feature Extraction from Social Network Graphs

Date: 2021-03-18

## Business Scenario:

Rong360 is a fintech company in China that matches lenders with borrowers seeking small loans. It disrupts the lending market by making it easier for people to borrow money from other people. However, the business model also comes with a high risk of loan default. Rong360 collects additional data on borrower’s social network and digital footprints. The business question is to utilize these data to predict loan default. 

## Data Description:

The data came in 5 tables: borrower social interaction data, borrower risky behavior data, borrower app installation data, lender type data, and label data. The social interaction data contains 31,255,329 interaction records, including from_id, to_id, and an info column containing time and numbers. Additional details of the other tables will be updated in my project report. 

## Feature Engineering:

I took three approaches to extract features from graph. 
1. Embedding: I used DeepWalk to generate embedding for each node. 
2. Generate other graph features, including pagerank, centrality, hits (hub and authority), and indegree & outdegree. 
3. Based on contact information, I also summarized 1-degree contact’s features for each node. Because the last task was repetitive, I wrote a helper function to automate it.

## Dealing with Imbalanced Data (currently working on):

I noticed that the data is imbalanced, with only 15% default rate. For my next iteration, I will try over-sampling the minority cases and probability calibration. 

## Challenge:

The biggest challenge is to understand the algorithm of DeepWalk. My objective is to understand the details of this embedding technique, instead of just using the package. I find it helpful to go back to the classic work2vec algorithm in order to understand DeepWalk.
