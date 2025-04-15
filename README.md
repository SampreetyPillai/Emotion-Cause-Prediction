# Group 18:
- Sahithi (2101CS16)
- Shanmukha (2101CS40)
- Sampreety (2101CS71)

This is an emotion-cause prediction model based on the [RECCON](https://github.com/declare-lab/RECCON) dataset. Given a conversation, it predicts the different clauses, classifies it as emotion and cause and predict which clause causes which emotion.
[Code explanation and work distribution](https://docs.google.com/document/d/1Bl2ZmMzaWTTJcmmgHuHSRPaB1WfIAHjRFZ-xuo3cjEM/edit?usp=sharing)


[Code demo video](https://drive.google.com/file/d/1svsmUIYMq_lnDu5i3iYNbQJemY70MoPP/view?usp=sharing)


# Directories 
- Code: containes all the Jupyter files used for all the three tasks.
- Files: These contain training and testing data from the RECCON dataset. The output files contains the necessary auxilliary files generated.
- Results: Final emotion-cause predictions of the code are saved here.

# How to run
- ## Task 1:
  - Using input data files(dailydialog_train.json and dailydilog_test.json) generate processed_train.csv and processed_test.csv using task1.ipynb. These **break down the raw data into converstions with ids** and their clauses.
- ## Task 2:
  - Using the processed_train.csv and processed_test.csv generate annotated_output3.csv and annotated_output3_test.csv using task2.ipynb. These **classify the clauses as emotion, clause, neither or both**.
- ## Task 3:
  -   Using the annotated_output3.csv and annotated_output3_test.csv run task3_embeddings.ipynb, task3_train.ipynb and task3_predictions.ipynb one after the other in order. node_embeddings3.csv, node_embeddings_test3.csv and test_prediction.csv would be generated which have to be used as input in the subsequent files. Here, the code **generates embeddings from the given clauses** and then **uses it to produce a graph that can be trained by DyGCN**. The final output file is stored in the results folder calles emotion_cause_predictions.csv.

# Contributions

## Task 1

### Sahithi
- Designed and implemented the clause segmentation logic using spaCy.
- Ensured accurate sentence separation, considering delimiters and conjunctions.

### Sampreety
- Handled dataset preprocessing, including JSON parsing and text cleaning.
- Ensured data integrity while processing different text structures.

### Shanmukha
- Developed the end-to-end automation script for dataset processing.
- Integrated sentence segmentation, emotion-cause mapping, and CSV export.

## Task 2

### Sahithi
- Loaded and parsed the dataset.
- Extracted cause spans and tagged each clause as “emotion”, “cause”, “both”, or “neither”.
- Added these labels in a new “annotation” column.

### Sampreety
- Created TF-IDF features from clause text (up to bigrams).
- Built meta features like clause length, turn, speaker, emotion, and presence of emotion.
- Normalized and combined all features into a single model input.

### Shanmukha
- Encoded labels and split data into train/test sets.
- Trained an XGBoost model with early stopping and optimized hyperparameters.
- Evaluated model performance and saved annotated predictions to CSV.

## Task 3

### Sahithi
- SVO Extraction & Embedding Preparation: Clauses are processed using spaCy to extract Subject-Verb-Object (SVO) triplets (during training).
- Identified emotion-cause pairs by tracking the sequence of cause and emotion clauses within the same conversation and saved the predictions (`emotion_cause_predictions.csv`).

### Sampreety
- Creates structured nodes from annotated conversation data, uniquely identifying each clause with conversation ID, turn, and clause number.
- Generates sentence embeddings for each clause using the all-MiniLM-L6-v2 model from Sentence Transformers and saved the node details and embeddings (`node_embeddings3.csv`).

### Shanmukha
- Graph Construction & DyGCN Training: Graph edges are created based on shared verbs or object-subject pairs. A two-layer GCN model is trained using node embeddings and class-weighted loss to classify each node as 'emotion', 'cause', 'neither', or 'both'.
- Evaluation & Visualization: The trained model predicts on test data, saves results with predicted and true labels, and visualizes classification metrics (precision, recall, F1-score) for each class in a bar chart.


