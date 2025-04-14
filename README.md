# Group 18:
- Sahithi (2101CS16)
- Shanmukha (2101CS40)
- Sampreety (2101CS71)

This is an emotion-cause prediction model based on the RECCON dataset. Given a conversation, it predicts the different clauses, classifies it as emotion and cause and predict which clause causes which emotion.

# Directories 
- Code: containes all the Jupyter files used for all the three tasks.
- Files: These contain training and testing data from the RECCON dataset. The output files contains the necessary auxilliary files generated.
- Results: Final emotion-cause predictions of the code are saved here.

# How to run
- ## Task 1:
  -- Using input data files(dailydialog_train.json and dailydilog_test.json) generate processed_train.csv and processed_test.csv using task1.ipynb. These break down the raw data into converstions with ids and their clauses.
- ## Task 2:
  -- Using the processed_train.csv and processed_test.csv generate annotated_output3.csv and annotated_output3_test.csv using task2.ipynb. These classify the clauses as emotion, clause, neither or both.
- ## Task 3:
  -- Using the processed_train.csv and processed_test.csv generate node_embeddings3.csv and node_embeddings_test3.csv using task3_embeddings.ipynb. These break down the clauses into numerical vector embeddings.
  --  


