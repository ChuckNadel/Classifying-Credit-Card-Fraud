# Classifying Credit Card Fraud

### The Business Problem

American Express wants to do a better job protecting their customers by catching fraudulent purchases more efficiently than before. We've been hired to create a screener to flag potentially fradulent purchases.


### The Dataset

Due to privacy concerns, we used a synthetically created dataset found on Kaggle [here](https://www.kaggle.com/datasets/kartik2112/fraud-detection). This dataset containis legitimate and fraudulent transactions simulated from the beginning of 2019 to the end of 2020. It covers credit cards of 1000 customers doing transactions with a pool of 800 merchants.

### My Methods

Due to the size of this dataset, I was only able to create and run 2 models. Our baseline model was a linear regression model, which I thought would be a great place to start for this business problem due to its ability to assign probabilities to whether or not a purchase was fraudulent. I also used a decision tree classifier, as I was unhappy with the results I got from our baseline model, and wanted to choose a model that would not take forever to fit and tune.

### The Results

I optmized my two models for recall score, as we were tasked with catching as many fraudelent purchases as possible, with less regard for false positives. Our optimized logistic regression gave us a recall score of 0.865, with a false positive rate of 0.31, as shown by the following confusion matrix. 
<p align="center">
  <img src = images/ConfusionMatrixLogReg.png width="750" height="250">
</p>
While I mentioned before that we did not care too much about false positives, this screener is quite bad, as we do not want to mark over 30% of purchases as potentially fraudelent, unnesesarily bothering our customers.

On the other hand, our decision tree classifier did a great job classifying fraudulent vs non-fradulent purchases, with a recall score of 0.932, and a false positive rate of 0.03, as shown by this confusion matrix. 

<p align="center">
  <img src = images/ConfusionMatrixDT.png width="750" height="250">
</p>

It is clear that our decision tree classifier would be a much more effective screener for fraud, as it was able to acheive a 7% higher recall score, with a false postive rate 27% lower.

Lastly, the decision tree classifier was able to catch 98.6% of fraudenlent money spent, meaning the 8% of fraudulent purchases it missed were for relatively small amounts.

### Next Steps

Create a new feature that finds the distance travelled between each purchase, possibly taking into account the time as well.

Test out more classification models.

Create a custom score to optimize on that takes into account both recall score and false positive rate.