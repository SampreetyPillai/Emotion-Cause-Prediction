# Group 18:
- Sahithi (2101CS16)
- Shanmukha (2101CS40)
- Sampreety (2101CS71)

This is an emotion-cause prediction model based on the [RECCON](https://github.com/declare-lab/RECCON) dataset. Given a conversation, it predicts the different clauses, classifies it as emotion and cause and predict which clause causes which emotion.
[Code explanation and work distribution](https://docs.google.com/document/d/1Bl2ZmMzaWTTJcmmgHuHSRPaB1WfIAHjRFZ-xuo3cjEM/edit?usp=sharing)


# Directories 
- Code: containes all the Jupyter files used for all the three tasks.
- Files: These contain training and testing data from the RECCON dataset. The output files contains the necessary auxilliary files generated.
- Results: Final emotion-cause predictions of the code are saved here.

# How to run
- ## Task 1:
  - Using input data files(dailydialog_train.json and dailydilog_test.json) generate processed_train.csv and processed_test.csv using task1.ipynb. These break down the raw data into converstions with ids and their clauses.
- ## Task 2:
  - Using the processed_train.csv and processed_test.csv generate annotated_output3.csv and annotated_output3_test.csv using task2.ipynb. These classify the clauses as emotion, clause, neither or both.
- ## Task 3:
  -   Using the annotated_output3.csv and annotated_output3_test.csv run task3_embeddings.ipynb, task3_train.ipynb and task3_predictions.ipynb one after the other in order. node_embeddings3.csv, node_embeddings_test3.csv and test_prediction.csv would be generated which have to be used as input in the subsequent files. Here, the code generates embeddings from the given clauses and then uses it to produce a graph that can be trained by DyGCN. The final output file is stored in the results folder calles emotion_cause_predictions.csv.

