# Classification

Classification is a supervised technique of machine learning, this one has the objective of predicting in which class or category something belongs to. A classification model mostly has:

- Training set: This is the data used to teach the model how to diffirentiate.
- Test set: This is the data you use to see if your model was well trained.

Remember the more data you have the merrier. Another thing remember that computationally you need to have the few features, so you should clean your data and only have the features that are actually important in terms of what you want to predict.

Another thing is remember features can be called **predictors, covariates, explanatory variables or independent variables** __x__ and you have also the labels __(y)__. So formally, given a training set (**xi,yi**) for i=1........n, we want to create a classification model **f** that can predict label **y** for a new **x**. This is where ML comes up, because it will be the one responsible of creating the function **f** to help you with the prediction of its category. In few words a binary classification is the perfect example of this, it is something or it isn't.

## Common Algorithms

This ones are the most common classification algorithms:

- Logistic Regression(with L1 or L2 regularization)
- Decision Trees/Classification Trees/CART/C4.5/C5.0
- AdaBoost(Boosted Decision Trees)
- Support Vector Machines
- Random Forests
- Neural Networks

## Loss Functions
How do you measure classification error?

Well you can use loss functions, this ones are functions that evaluate you model decisions and penalize the model if it was wrong. This first function is not bad but it doesn't give any chance of little mistakes, it is totally binary, you are worng or you are right there isn't any middle ground. And this is the function:

- yf(x)<0

Second one which is a little better because you can have in mind that you can be **very wrong** , **sort of wrong**, **sort of correct** or **very correct** which gives you a bigger margin of being wrong or right. This is by using this function:

- l(yf(x))

But I would recommend to continue reading this so you can see what are the other options you have.