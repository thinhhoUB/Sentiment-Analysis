# Sentiment-Analysis

## Introduction: 
For this project, I did my first exploration into **Sentiment Analysis**. It has two parts, where the first part is about **Binary Classification** with film reviews (either **positive** or **negative** and the second one is **Multiclass Classification** with the **newsgroup** where we have **eight** different groups of news.


## Method: 

Applying the equation of **Bayes Theorem**, I implement a NaΓ―ve Bayes Classifier that categorizes movie reviews as positive or negative based on words in it.

About the details:

> - Preprocessing the data: By working with text, in this step, I preprocess all the text data by eliminating handles and URL using **regex**, remove stop words like "and, is, a, on, etc." which are not provided any relevant information for the task but serve as noises, and converting all your words to lower case. 
>  - Building a frequency table: after splitting intro training and testing sets, from all the data on training set, I build a **frequency of appearance** of each works in both classes : **negative and positive**
>  - Main idea about Naive Bayes algorithm:

$$π(πππππ‘ππ£π/π‘ππ₯π‘)=π(π‘ππ₯π‘/πππππ‘ππ£π)π(πππππ‘ππ£π)$$

$$π(πππ ππ‘ππ£π/π‘ππ₯π‘)=π(π‘ππ₯π‘/πππ ππ‘ππ£π)π(πππ ππ‘ππ£π)$$

where  π(π‘ππ₯π‘/πππππ‘ππ£π)  will be likelihood function and  π(πππππ‘ππ£π)  is probability of being negative. Same for positive case.

Likelihood function and probability of positive/negative
In order to obtain likelihood function, we pretend each word in text is independent event. Therefore, the likelihood function can be written as following:

$$π(π‘ππ₯π‘/πππππ‘ππ£π)=π(π€πππ1/πππππ‘ππ£π)βπ(π€πππ2/πππππ‘ππ£π)β....βπ(π€ππππ.πππππ‘ππ£π)$$

For **multiclass classification**, we use the same idea.

## Conclusion:

For film reviews, our accuracy is 85.3%.

For newsgroup, our accuracy is up to 91.1%

As we can see, when a review is correctly classified, the difference between probability is much bigger than when a review is misclassified.

This can be explained grouping by each topic are much more significantly different and easier to predict than positive/negative.

For both classes: positive and negative, the recall accuracy equals to each other => no bias

While for newsgroup, there is one exception when the recall for talk.religion.misc class only 66.67%
