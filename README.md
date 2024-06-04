## Description
These codes are used for create TComQA dataset. We have used contexts from SAMsum and RealNews dataset to create it. Context are first used with all five types of temporal dimention/properties, duration, frequency, typical time, stationary, and event ordering to generate questions. Later, generated question are validated by Lexical validator. Then the valid questions are passed to the Question-Answering model to generate the questions.  \
 We only use a small portion of contexts to create a total of 7.9k Question -Answer pairs, that are given in the Dataset folder. 

## Folders
- Datasets:
  - TComQA_dataset_sample. : A sample of TComQA; the generated dataset
  - mctaco_filtered_QA_train.json : MC-TACO data used for training the Question Answering model
  - qaContext_RealNews.txt : The RealNews contexts that were used to generate the questions
  - qaContext_samsum.txt : The SAMSum data that were used to generate the questions
  - train_df.tsv : MC-TACO data used to train Question generation model