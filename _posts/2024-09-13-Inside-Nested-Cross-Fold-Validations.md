---
layout: post
title:  "Inside Nested Cross Fold Validations"
description: The inside scoop of how nested cross validations work and when to use them
image: /assets/img/headernest.jpg
---


A nest that is to hold a growing hatchling must be made from several layers. One layer must be effective in providing a soft coating for the baby bird while another may be designed to keep predators away. Yet another layer can provide strength. In addition, there are likely larger sticks running through the many layers to keep it in one piece.

Nested cross-fold validations can be thought of in this way with several layers each performing a unique and critical aspect of the whole process. So, let’s jump into it! Or should I say let's NESTle in?

## What are Nested Cross-Fold Validations?

A nested cross-fold validation is simply 2 cross-fold validations compounded to give an optimal result while preventing data leakage. To understand the nested aspect of this tool, let's recall what a cross-fold validation does on its own. While there are several types of these validations, such as Monte Carlo, leave one out, K-fold, etc. we will focus on K-fold cross-validations for simplicity

K-fold cross-validations consist of several steps:
1. Divide your training data into K groups (usually around 5 or 10 but can be much larger)
2. Use all groups but one to train your model
3. Test or validate you model on the group that was left out of training
4. Repeat steps 2-3 iterating through each group as the validation set
5. Train final model across all training data with parameter(s) that performed the best

Here is a visual example:

![cross-validation]({{site.url}}/{{site.baseurl}}/assets/img/cross-validation.png)

A nested cross-fold validation combines 2 cross-validations to achieve optimal performance of both coefficients and hyperparameters. It works the same as k-fold cross-validations with some changes:

1. There is an outer and an inner cross-fold validation
2. The training data is once again split into folds/groups
3. The first test set is withheld while the inner cross-fold validation runs as explained above to find the best parameters over this training set
4. Once inner loop is complete, you test its efficacy on the first test set withheld over some evaluation metric (precision, recall, accuracy, f1, etc.) to evaluate hyperparameters
5. The test set is then rotated to the next group and the inner loop runs again over the new training data
6. Repeat across all groups 
7. Train final model on optimal hyperparameters over entire training set

It is a lot of information and many moving parts but here is another visual to show it another way:

![nested_cv]({{site.url}}/{{site.baseurl}}/assets/img/nested_cv.png)

## Advantages of Nested Cross-fold Validations

1. Better Model Selection:
Nested cross-fold validations provide a robust and reliable method of model selection over 1 layer cross-validations because it separates the hyperparameter tuning (inner loop) from the performance evaluation (outer loop). This helps prevent from overfitting and provides a model that is well trained but not overfit nor underfit.

2. No data leakage to training set:
One of the pitfalls of model fitting is training and testing on the same dataset leading to an overconfidence in the performance of a model. Nested cross-fold validations protect against this issue by separating hyperparameter tuning from model evaluation which is perhaps the biggest downside to using 1 layer cross-fold validations.

3. Performance estimation:
Once a model is trained and tuned, it is difficult to evaluate the performance of this model without drawing on more data for validation. If no additional data is available, one might be overconfident in their results despite clear limitations in models. Nested cross-fold validations protect against this issue by providing an effective evaluation metric on the model's ability to predict that is not skewed by data leakages.

## Limitations

1. Computing Power:
Any data scientist or rising statistician has likely sat at their computer waiting for a cross-fold validation to run for longer than they'd want to admit. To run a nested cross-fold validation one must multiply the time to run a normal cross-fold validation by the number of outer groups. Especially if one is training over many possible hyperparameters, this can take a long time but also be a financial burden. 

2. Complex Interpretations:
After this point in the article, how well do you understand the concept and the need for a nested cross-fold validation? Could you explain it to a 1st year college student in an intro statistics class? Now imagine you need to explain the interaction between the inner and outer folds over several metrics that are telling you different pieces of information. Most of the time this model selection criteria is complex enough that even the average data scientist would get lost in the process of it all. Nested cross-fold validations are complex and difficult to explain.

## Conclusion

Along your data science or statistical carrier, you may have run into a nested cross-fold validation and wondered its purpose or have yet to have the opportunity to hear of their existence. Wherever you are on your data journey, I hope you see just how effective a nested cross-fold validation can be when used in the right context. They near perfect in choosing an accurate model, no data leakage occurs, and one can have an accurate performance estimation as they finish.

Whatever size your data science nest is, I hope you fit in a nested cross-fold validation.

![birds]({{site.url}}/{{site.baseurl}}/assets/img/nest1.jpg)