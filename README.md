# Sentiment-Analysis

## Introduction: 
For this project, I did my first exploration into **Sentiment Analysis**. It has two parts, where the first part is about **Binary Classification** with film reviews (either **positive** or **negative** and the second one is **Multiclass Classification** with the **newsgroup** where we have **eight** different groups of news.


## Method: 

Applying the equation of **Bayes Theorem**, I implement a Naïve Bayes Classifier that categorizes movie reviews as positive or negative based on words in it.

About the details:

> - Preprocessing the data: By working with text, in this step, I preprocess all the text data by eliminating handles and URL using **regex**, remove stop words like "and, is, a, on, etc." which are not provided any relevant information for the task but serve as noises, and converting all your words to lower case. 
>  - Building a frequency table: after splitting intro training and testing sets, from all the data on training set, I build a **frequency of appearance** of each works in both classes : **negative and positive**
>  - Main idea about Naive Bayes algorithm:

$$𝑝(𝑛𝑒𝑔𝑎𝑡𝑖𝑣𝑒/𝑡𝑒𝑥𝑡)=𝑝(𝑡𝑒𝑥𝑡/𝑛𝑒𝑔𝑎𝑡𝑖𝑣𝑒)𝑝(𝑛𝑒𝑔𝑎𝑡𝑖𝑣𝑒)$$

$$𝑝(𝑝𝑜𝑠𝑖𝑡𝑖𝑣𝑒/𝑡𝑒𝑥𝑡)=𝑝(𝑡𝑒𝑥𝑡/𝑝𝑜𝑠𝑖𝑡𝑖𝑣𝑒)𝑝(𝑝𝑜𝑠𝑖𝑡𝑖𝑣𝑒)$$

where  𝑝(𝑡𝑒𝑥𝑡/𝑛𝑒𝑔𝑎𝑡𝑖𝑣𝑒)  will be likelihood function and  𝑝(𝑛𝑒𝑔𝑎𝑡𝑖𝑣𝑒)  is probability of being negative. Same for positive case.

Likelihood function and probability of positive/negative
In order to obtain likelihood function, we pretend each word in text is independent event. Therefore, the likelihood function can be written as following:

$$𝑝(𝑡𝑒𝑥𝑡/𝑛𝑒𝑔𝑎𝑡𝑖𝑣𝑒)=𝑝(𝑤𝑜𝑟𝑑1/𝑛𝑒𝑔𝑎𝑡𝑖𝑣𝑒)∗𝑝(𝑤𝑜𝑟𝑑2/𝑛𝑒𝑔𝑎𝑡𝑖𝑣𝑒)∗....∗𝑝(𝑤𝑜𝑟𝑑𝑛.𝑛𝑒𝑔𝑎𝑡𝑖𝑣𝑒)$$

For **multiclass classification**, we use the same idea.

## Conclusion:

For film reviews, our accuracy is 85.3%.

For newsgroup, our accuracy is up to 91.1%

As we can see, when a review is correctly classified, the difference between probability is much bigger than when a review is misclassified.

This can be explained grouping by each topic are much more significantly different and easier to predict than positive/negative.

For both classes: positive and negative, the recall accuracy equals to each other => no bias

While for newsgroup, there is one exception when the recall for talk.religion.misc class only 66.67%
