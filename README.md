## Description
These codes are used for create TComQA dataset. We have used contexts from SAMsum and RealNews dataset to create it. Context are first used with all five types of temporal dimention/properties, duration, frequency, typical time, stationary, and event ordering to generate questions. Later, generated question are validated by Lexical validator. Then the valid questions are passed to the Question-Answering model to generate the questions.  \
 We only use a small portion of contexts to create a total of 7.9k Question -Answer pairs, that are given in the Dataset folder. 

## Folders
- Datasets:
  - TComQA_dataset_sample.json : A sample of TComQA; the generated dataset
  - mctaco_filtered_QA_train.json : MC-TACO data used for training the Question Answering model(directly loading from huggingface in the code)
  - qaContext_RealNews.txt : The RealNews contexts that were used to generate the questions(this is named as filtered_sentences.txt in the code)
  - qaContext_samsum.txt : The SAMSum data that were used to generate the questions(this data is directly loaded from huggingface instead of loading from this file)
  - train_df.tsv : MC-TACO data used to train Question generation model
  - mctaco_test.json :  MC-TACO data consisting of 150 question-answer pairs, 30 from each temporal type, used for evaluation of the answer-generation models
- Question Answering
  - Llama_2_TC.ipynb, Llama_2_TC_Train_McTACO+RealNews+SamSUM.ipynb, Llama_2_TC_Train_RealNews+SamSUM.ipynb : Training Llama using MC-TACO, (MC-TACO, RealNews and SAMSum) and (RealNews and SAMSum) respectively. The training code for Llama-2 model is from this [blog](https://deci.ai/blog/fine-tune-llama-2-with-lora-for-question-answering/)
  - QA_BERT.ipynb : Training BERT on MC-TACO using MLM for answer generation
  - numBERT_for_MLM.ipynb : Training NumBERT on MC-TACO using MLM for answer generation
  - similarity_scores.ipynb : Evaluation of answer-generation model tested on question-answer pairs from the MCTACO test dataset
- Question Generation
  - T5_Question_Generation.ipynb : Trained T5 model for question generation task. The code is from this [blog](https://towardsdatascience.com/asking-the-right-questions-training-a-t5-transformer-model-on-a-new-task-691ebba2d72c)
  - T5_Question_Generation__Various_Datasets.ipynb : Using the saved finetuned T5 model, question generation is done on SAMSum
- Validity Checker :
  - validity_checker.ipynb : Check whether the generated question is valid so as to pass it on to the QA Module
  - Crowdsource.ipynb : Find accuracy, recall etc from the results of crowdsourcing
- Miscellaneous :
  - stats.ipynb : Find average number of tokens in RealNews and SAMsum dataset
