---
layout: post
title:  "Inside Nested Cross Fold Validations"
description: The inside scoop of how nested cross validations work and when to use them
image: /assets/img/headernest.jpg
---


A good nest that is to hold a growing hatchling must be made from several layers. One layer is effective in providing soft coating for the baby bird while another may be totally designed to keep predetors away. Yet another layer can provide strength while there are sticks running through the layers to keep it one cohesive whole.

Nested cross fold validations can be thought of in this way with several layers each performing a unique and crutical aspect of the whole. So lets jump into it! Or should I say let's NESTle in?

## What are Nested Cross Fold Validations?

A nested cross fold validation is simply 2 cross fold validations compounded to give a optimal results all along the way. In order to understand the nested aspect of this tool, let's recall what a cross fold validation does on it's own. While there are several types of these validations, such as monte carlo, leave one out, k-fold, etc. we will focus on k-fold cross validations for simplicity

K-fold cross validations consist of several steps:
1. Divide your training data into K groups (usually around 5 or 10 but can be much larger)
2. Use all groups but one to train your model
3. Test or validate you model on the group that was left out of training
4. Repeat steps 2-3 iterating through each group as the validation set
5. Train final model across all training data with parameter(s) that performed the best

Here is this shown visually:

INSERT PICTURE OF CROSS FOLD VALIDATION HERE

A nested cross fold validation combines 2 nested cross validations to achieve optimal performance of both coefficients and hyperparameters. It works the same as k-fold cross validations with the following changes:

1. There is an outer and an inner cross fold validation
2. The training data is once again split into folds/groups
3. The first test set is withheld while the inner cross fold validation runs as explained above to find the best parameters over this training set
4. Once inner loop is complete, you test it's efficacy on the first test set withheld over some evaluation metric (precision, recall, acuraracy, f1, etc.) to evaluate hyperparameters
5. The test set is then rotated to the next group and the inner loop runs again over the new training data
6. Repeat across all groups 
7. Train final model on optimal hyperparameters over entire training set

It is a lot of information and many moving parts but here is another visual to show it another way:

INSERT PICTURE HERE OF NESTED CROSS FOLD VALIDATION

## Advantages of Nested Cross Fold Validations

1. Better Model Selection:
Nested cross fold validations provide a robust and reliable method of model selction over 1 layer cross validations because it seperates the hyperparameter tuning (inner loop) from the performance evaluation (outer loop). This helps prevent from overfitting and provides a model that is well trained but not overfit and not underfit.

2. No data leakage to training set:
One of the pitfalls of model fitting is training and testing on the same dataset leading to an overconfidence in the performance of a model. Nested cross fold validations protect against this issue by seperating hyperparameter tuning from model evaluation which is perhaps the biggest downside to using 1 layer cross fold validations.

3. Performance estimation:
Once a model is trained and tuned, it is difficult to evaluate the performance of this model without drawing on more data for validation. If no additional data is avialble, one might be overconfident in their results despite clear limitations in models. Nested cross fold validations protect against this issue by providing an effective evaluation metric on the model's ability to predict that is not skewed by data leakages.

## Limitations

1. Computing Power:
Any data scientist or rising statistician has likely sat at their computer waiting for a cross fold validation to run for longer then they'd want to admit. To run a nested cross fold validation one must mulitply the time to run a normal cross fold validation by the number of outer groups. Especially if one is training over many possible hyperparameters, this can take a long time but also be very financially taxing. 

2. Complex Interpretations:
After this point in the article, how well do you understand the concept and the need for a nested cross fold validation? Could you explain it to a 1st year college student in an intro statistics class? Now imagine you need to explain the interaction between the inner and outer folds over several metrics that are telling you different pieces of information. Most of the time this model selection criteria is complex enough that even the average data scientist would get lost in the logic of it all. Nested cross fold validations are complex and difficult to explain.


## Applications:

The better answer I hope you ask yourself at the end of the this article is when would I not want to use a nested cross fold validation? When computing power is availble, I hope you use it as often as your manager allows.

In a recent study of Congestive Heart Failure, nested cross fold validations were used to evaluate a logistic regression model and optimize its hyperparameters to obtain stunning results.

## Conclusion

Along your data science or statisitcal carrier, you may have run into a nested cross fold validation. There are often used to optimize a machine learning algorithm.