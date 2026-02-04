# 📁 Requirement for Executing Code in Google Colab
The following file structure is required in **Google Drive**:
```plaintext
└── drive/                       
      └── MyDrive/                
            └── COMP90042_2025/    
                    └── data/          
                         ├── evidence.json            # all evidences
                         ├── train-claims.json        
                         ├── dev-claims.json    
                         ├── test-claims-unlabelled.json 
                         └── dev-claims-baseline.json   

```

##  Project Overview

In this project, we divide the task into two parts:
1. **Retrieval Task**  
   Retrieve the most relevant evidences for each claim using three different methods.

2. **Classification Task**  
   Classify and predict the semantic relationship between each claim and its corresponding evidences using three different models.

##  Approach 1 – Code Execution Steps
###  Retrieval Task
1. **DataSet Processing**
   Run code in the section: 
   _"TF-IDF Retrieval task for data preprocess"_
2. **Model Implementation**  
   _"Run code in the section: TF-IDF Retrieval model"_
3. **Testing and Evaluation**  
   _"Run code in the section: TF-IDF Retrieval test and evaluate"_

After running the Task 1 second part, there will be 2 more document named "train_lstm_input" and "dev_lstm_input". And following, those 2 documents will be read.

### Classification Task
1. **DataSet Processing**  
   Run code in the section:  
   _"LSTM data preprocess"_
2. **Model Implementation**  
   Run code in the section:  
   _"LSTM Classification model with TF-IDF retrieval"_
3. **Testing and Evaluation**  
   Run code in the section:  
   _"LSTM model test and evaluate"_

When running the last part of Classification task, "test-output.json" will be created for test on the leaderboard.
 
##  Approach 2 – Code Execution Steps
###  Retrieval Task
1. **DataSet Processing**  
   Run code in the section:  
   _"Retrieval task dataset for Word2Vec model"_
2. **Model Implementation**  
   Run code in the section:  
   _"Retrieval model implementation (Word2Vec model+ average pooling + cosine similarity for retrieving evidence)"_
3. **Testing and Evaluation**  
   run $ python eval.py --predictions test-claims-prediction.json --groundtruth dev-claims.json in the terminal to get the evaluate result

After completing the above steps, the retrieved evidences will be saved in:test-claims-predictions.json

### Classification Task
1. **DataSet Processing**  
   Run code in the section:  
   _"load necessarily data for LLMs"_
2. **Model Implementation**  
   Run code in the section:  
   _"Classification model implementation (a list of LLMs including: distilgpt2, tiny-llama, or flan-t5-small)"_
3. **Testing and Evaluation**  
   run $ python eval.py --predictions dev-output.json --groundtruth dev-claims.json in the terminal to get the evaluate result

After completing the above steps, the predicted labels will be saved in:test-output.json


##  Approach 3 – Code Execution Steps
###  Retrieval Task
1. **DataSet Processing**  
   Run code in the section:  
   _"Retrieval task dataset for sentence embedding model"_
2. **Model Implementation**  
   Run code in the section:  
   _"Retrieval model implementation (fine-tuned sentence embedding model + cosine similarity for retrieving evidence)"_
3. **Testing and Evaluation**  
   Run code in the section:  
   _"Retrieval model evaluation and testing (fine-tuned sentence embedding model + cosine similarity for retrieving evidence)"_

After completing the above steps, the retrieved evidences will be saved in:test-claims-with-retrieved-evidences.json

### Classification Task
1. **DataSet Processing**  
   Run code in the section:  
   _"Classification model implementation (fine-tuned BERT with customized classifier head)"_
2. **Model Implementation**  
   Run code in the section:  
   _"Classification model implementation (fine-tuned BERT with customized classifier head)"_
3. **Testing and Evaluation**  
   Run code in the section:  
   _"Classification model evaluation and testing (fine-tuned BERT with customized classifier head)"_

After completing the above steps, the predicted labels will be saved in:test-output.json
