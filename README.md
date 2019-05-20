# Microchip-Quality-Assurance

Suppose you are the product manager of a microchip factory, and you are in charge of the quality assurance (QA). During QA, each microchip goes through two tests. From the two test results, you would like to determine whether the microchips should be accepted, rejected or undecided (require more tests). To help you make the decision, you have a dataset of test results on past microchips, from which you can build classifiers for your future decisions. Test results from past microchips are scatter plotted as below.

![Pic1](pic1.png)


### Two class Classification 
<b>*1. Logistic Regression Classifier for the first two classes rejected and accepted (C = 10)*</b>
- *Accuracy for training data: 52%*
- *Accuracy for test data: <b>31%</b>*

<table style="width:100%">
  <caption><b>Confusion Matrix</b></caption>
  <tr>
    <th></th>
    <th>Predicted Class = 0</th>
    <th>Predicted Class = 1</th>
  </tr>
  <tr>
    <td><b>Actual Class = 0</b></td>
    <td>11</td>
    <td>7</td>
  </tr>
  <tr>
    <td><b>Actual Class = 1</b></td>
    <td>24</td>
    <td>3</td>
  </tr>
</table>

<b>Precision: *30%*</b><br>
<b>Recall: *11%*</b><br>
<b>F1-Score: *16%*</b>

![Pic1](Log_Reg1.png)

<b>Result</b>:Logistic Regression classifier performed poor, because data was not scattered in a linearly separable way, hence, the hyperplane of logistic regression model was not be able properly separate two classes.
<br><br><br><br>
<b>*2. Gaussian naïve Bayes classifier for the first two classes rejected and accepted*</b>
- *Accuracy for training data: 75%*
- *Accuracy for test data: <b>69%</b>*

<table style="width:100%">
  <caption><b>Confusion Matrix</b></caption>
  <tr>
    <th></th>
    <th>Predicted Class = 0</th>
    <th>Predicted Class = 1</th>
  </tr>
  <tr>
    <td><b>Actual Class = 0</b></td>
    <td>14</td>
    <td>4</td>
  </tr>
  <tr>
    <td><b>Actual Class = 1</b></td>
    <td>10</td>
    <td>17</td>
  </tr>
</table>

<b>Precision: *81%*</b><br>
<b>Recall: *63%*</b><br>
<b>F1-Score: *71%*</b>

![Pic1](Gaussian1.png)

<b>Result</b>:Gaussian Naive Bayes model outperformed Logistic Regression model, because Gaussian Naive Bayes:
- working well with small data
- decision boundary is presented by piecewise quadratic function which better match given data
- assumes the features to be conditionally independent (correlation between data variables: -0.13)
<br><br><br><br>

<b>*3. Applying SVM kernel idea to Logistic Regression model</b>*

In order to improve the performance of Logisitic Regression model, polynomial degrees were introduced that maps the data to higher dimensional space where the hyperplane of the Logistic regression can separate classes better.

<table style="width:100%">
  <caption><b>4-degree Polynomial degree Confusion Matrix</b></caption>
  <tr>
    <th></th>
    <th>Predicted Class = 0</th>
    <th>Predicted Class = 1</th>
  </tr>
  <tr>
    <td><b>Actual Class = 0</b></td>
    <td>16</td>
    <td>2</td>
  </tr>
  <tr>
    <td><b>Actual Class = 1</b></td>
    <td>6</td>
    <td>21</td>
  </tr>
</table>



### Three class Classification 
4. Report the precision score, recall score and F1 score of the logistic regression classifier from part 1. You need to build a multi-class logistic regression model using softmax function, which can be implemented by multi_class = 'multinomial' and solver='newton-cg'. Please report the precision score, recall score and F1 score again with average='weighted' (the other options are 'micro' and 'macro', we ignore them here). Is it true that all three scores have improved from binary classification to 3-class classification? Why do the three scores improve or decline? Intuitively, with more classes, both precision and recall decrease as the classification task is deemed harder. F1 score is the harmonic mean of precision and recall, so F1 score should fall between the precision score and recall score. Is this what you observed? Why is it so?
