# MNIST-handwriting-recognition

I performed a drill-down on the MNIST database to train a handwriting recognition algorithm. 

Here, I experimented with two different approaches. First, I went with a bare-bones Naive Bayes approach. While the results are satisfactory, the drawbacks of Naive Bayes are evident in the error analysis. The model tends to get confused when it sees data points that have very little similarity to anything it has seen in the training set. 

My findings corroborate the fact that Naive Bayes would only perform well when the predictors are independent. We learn that this may not be the case for the MNIST dataset because of the inherent nature of how the dataset is generated. Handwriting strokes generate vectors which have a dependency on one another. For example, it is much more likely for pixels that are next to a stroke to be active than those which are farther away. 

This drawback is overcome when I used logistic regression to predict the values instead. While this is not the best approach to use logistic regression (our output class is non-binary), a cascaded prediction does lead to decent results and a great improvement over plain old Naive Bayes. 