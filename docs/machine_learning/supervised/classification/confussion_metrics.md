- A confusion matrix is a grid that breaks out the predictions against the actual out‐
comes showing the true positives, true negatives, false positives (type I error), and
false negatives (type II error). 

| --                        | Actually Quits True | Actually Stays False | --          |
| ------------------------- | ------------------- | -------------------- | ----------- |
| Predicted WIll True       | 0       [TP]        | 1   [FN]             | Sensitivity |
| Predicted Will Stay False | 1        [FP]       | 98       [TN]        | Specificity |
|                           | Precision           |                      | Accuracy    |
| F1 Score                  |                     |                      |             |

- From the confusion matrix, we can derive all sorts of useful metrics beyond just
accuracy. We can easily see that precision (how accurate positive predictions were)
and sensitivity (rate of identified positives) are 0, meaning this machine learning
model fails entirely at positive predictions.
- _precision_ : TP/(TP+FP)
- _Sensitivity_: TP/(TP+FN)
- _Specificity_: TN/(TN+FP)
- _Accuracy_: (TP+TN)/(TP+TN+FP+FN)
- _F1 Score_: (2 * Precision * Recall)/(Precision+Recall)
- 