# Stroke Prediction Model from Coursera Independent Projects
This is the first time I am using Git independently. Honestly, it's not that hard but there are 
still ways to go before I learn the optimal ways of doing this stuff.

Coursera Project:
A logistic regression model built in R to predict stroke risk based on patient data.

## Files
- `stroke_prediction.R` - This is the Main code file that once run will generate plots and statistics {Template provided by Coursera}
- `stroke_prediction.Rmd` — This was supposed to be converted to an HTML document (but it kept showing a blank page)
- `stroke_prediction_via_R` - This is just a project file that I needed to open to access git on RStudio.
- `healthcare-dataset-stroke-data.csv` - This is the dataset used to carry out this analysis.

Findings and Conclusions
- The dataset contains both demographic and clinical features and the data distribution shows that stroke is a rare outcome. This fact suggests that there is a class imabalnce. 
- We did a 80/20 train/test data split based on stratification by stroke.
- I used logistic regression to estimate stroke probability. It was an arbitrary choice. Ideally we should test different models and decide based on evaluation metrics which one should be used. 
- Model performance was evaluated using the confusion matric and ROC-AUC. 
- By changing the parameters of the new patient data, once can get an estinate of teh risk of stroke to that person. 

**RESULTS: interpretation**
- AS we can see, the confusion matrix predicts that 31 cases were corretcly detected, 15 were missed, but there were 250 false positives which is a lot so we might need to do some more thresholds/weight adjustement. That said, 726 non-strokes were correctly identified. 
- A 67% sensitivity means I was able to catch 67% of the real stroke cases which is good from a medical screening perspective but it should be higher!
- The 74% specificity and accuracy are tradeoffs for higher sensitivity due to the weighted schemes used.
- An AUC of 80% reflects that if we randomly choose one stroke and one non-stroke patient, my model will rank the stroke patient higher 80% of the time. Looks solid enough!
- The ROC curve is clearly above the diagonal, no visible breaks. 
