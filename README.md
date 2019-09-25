# MulticlassClassification
Multiclass classifiers (also called multinomial classifiers) can distinguish between more than two classes.

Random Forest classifiers or naive Bayes classifiers are multi class classifiers.

(Support Vector Machine classifiers or Linear classifiers) are strictly binary classifiers. However, there are various strategies that you
can use to perform multiclass classification using multiple binary classifiers.

For example, one way to create a system that can classify the digit images into 10 classes (from 0 to 9) is to train 10 binary classifiers,
one for each digit (a 0-detector, a 1-detector, a 2-detector, and so on). Then when you want to classify an image, you get the decision
score from each classifier for that image and you select the class whose classifier outputs the highest score. This is called the
one-versus-all (OvA) strategy (also called one-versus-the-rest). 

Another strategy is to train a binary classifier for every pair of digits: one to distinguish 0s and 1s, another to distinguish 0s and 2s,
another for 1s and 2s, and so on.This is called the one-versus-one (OvO) strategy. If there are N classes, you need to train 
N × (N – 1) / 2 classifiers. For the MNIST problem, this means training 45 binary classifiers! When you want to classify an image,
you have to run the image through all 45 classifiers and see which class wins the most duels. The main advantage of OvO is that each
classifier only needs to be trained on the part of the training set for the two classes that it must distinguish.

Some algorithms (such as Support Vector Machine classifiers) scale poorly with the size of the training set, so for these algorithms
OvO is preferred since it is faster to train many classifiers on small training sets than training few classifiers on large training sets.
For most binary classification algorithms, however, OvA is preferred.
