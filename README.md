# Cancer-Detection
**Business Problem:**<br/>
1. A molecular pathologist selects a list of genetic variations of interest that he/she want to analyze 2. The molecular pathologist searches for evidence in the medical literature that somehow are relevant to the genetic variations of interest 3. Finally this molecular pathologist spends a huge amount of time analyzing the evidence related to each of the variations to classify them Our goal here is to replace step 3 by a machine learning model.The molecular pathologist will still have to decide which variations are of interest, and also collect the relevant evidence for them. But the last step, which is also the most time consuming, will be fully automated.<br/>

**Business objectives and Constraints:**<br/>
1. No latency required <br/>
2. Probability of occurence is reuired,since the doctor had to interpret the cause of occurence 3. Errors can be very costly.<br/>

**Data:**<br/>
Training Variants consists of 4 columns: ID:the id of the row used to link the mutation to the clinical evidence Gene:the gene where this genetic mutation is located Variants:the aminoacid change for this mutations Class:1-9 the class this genetic mutation has been classified on Training Text consists of 2 columns:ID,Text Depending on the text related to each ID class label will be given.This mapping is done through an inner join between Training Variants and Training Text. Goal of machine learning is to detect class label depending on the text,gene,variation.Since class label is between [1 -9] it is multi-class classification.Metric used is multi-class log-loss and confusion matrix.<br/>

**Conclusion:**<br/>

|          Model          |     Train Loss     | Cross Validation Loss |     Test Loss      | 
|---|---|---|---|
|           K-NN          | 0.9582284186052225 |   1.1125636787444793  |  1.08911155067031  |
|       Naive Bayes       | 0.5176799623398368 |   1.2219297058574758  | 1.1679082869734096 | 
|   Logistic Regression   | 0.7088692795978287 |   1.0723810107015828  | 1.0041908224441571 | 
| Support Vector Machines | 0.4926686683306196 |   1.0799975073717587  | 1.0345586207144635 | 
|      Random Forest      | 0.8476740604468344 |   1.229275015767204   | 1.144385287527102  |
| Logistic Regression with Count vectorizer-Unigram + Bigram | 0.8522449793595871 |   1.2185638735846782  | 1.1701141141449427 |
|Logistic Regression with Tf-idf:Uni-gram and Bi-gram| 0.44009517292552414 |   1.024864596109853   | 0.9603419948632671|
