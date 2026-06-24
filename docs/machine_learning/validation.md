# Validation

## Cross Validation
- the testing dataset across each 1/3 fold
- This is known as cross-validation and is often considered the gold standard of validation techniques.
- Leave-one-out cross-validation (LOOCV) will alternate each individual data record as the only sample in the testing dataset, and this can be helpful when the whole dataset is small.

## K-Fold Validation 
- similar to [[Cross Validation]] which folds dataset in 1/3, if we fold the dataset in any fold like 1/3, 1/4, 1/6 is called k-fold validation

## Random Fold Validation
When you get concerned about variance in your model, one thing you can do, rather than a simple train/test split or cross-validation, is use random-fold validation to repeatedly shuffle and train/test split your data an unlimited number of times and aggregate the testing results