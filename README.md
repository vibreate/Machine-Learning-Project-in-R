# A Machine Learning Approach to Evaluating Red Wine Quality

## Overview:

 * #### Applied machine learning algorithms including multiple linear regression, classification tree, and random forest in R to help wineries identify key physicochemical properties that influence red wine quality. 
 * #### Determined the optimal multiple linear regression model, which showed chloride concentration and pH level negatively affected red wine quality. 
 * #### Improved the classification tree model’s accuracy rate to 87% with a random forest model and found alcohol content, sulfate concentration, and volatile acidity to be the most impactful variables on red wine quality.
---


## Motivation for this Project:

 * The global red wine industry is growing rapdily, and the demand for great tasting wines continues to increase.
 * Wine tasting is an essential part of the wine certifcaiton process, but subjective factors are involved.


 * If the model of this project can forecast wine quality based on physicochemical properties to a high degree
     - it can potentialy be applied to the wine certification process to help oenologists make faster and more consistent assessments.
     - it can also allow wineries to optimize wine quality by focusing on key chemical variables
    
<br/><br/>
### Data Set Overview:

* [The red wine data set](https://archive.ics.uci.edu/ml/datasets/wine+quality) contains 12 columns and 1599 rows of data.
* Input variables:
   - fixed acidity  
   - volatile acidity  
   - citric acid  
   - residual sugar  
   - chlorides
   - free sulfur dioxide 
   - total sulfur dioxide
   - density
   - pH
   - sulphates
   - alcohol
* Output Variable
   - quality (scale of 0 to 10)

<br/><br/>
## Classification Tree Model:


### Method:
* Numerical quality scores were classified into 3 categories for tree-based classification
  - Low: (3, 4)
  - Medium (5, 6)
  - High: (7, 8)
* Randomly sampled ½ of the observations from the full data set
  - Training data set (799 rows)
  - Testing data set  (800 rows)
* Plotted the error rate a function of tree size to determine the optimal tree complexity (optimal size = 8)
* Pruned the initial classificaiton tree to improve model accuracy

### Results:

![](https://github.com/vibreate/Machine-Learning-Project-in-R/blob/main/Images/unpruned%20tree.png)

This is a rudimentary classification tree model with a tree size of 12 (terminal nodes).
<br/><br/>

![](https://github.com/vibreate/Machine-Learning-Project-in-R/blob/main/Images/error%20rate%20vs%20tree%20size.png)

The optimal tree size is 8 because it has the lowest classification error rate as shown by this plot.
<br/><br/>

![](https://github.com/vibreate/Machine-Learning-Project-in-R/blob/main/Images/pruned.JPG?raw=true)
<br/><br/>


<br/><br/>
## Random Forest Model:

### Method:
* The previous Low, Medium, High classification scheme was also used for classification with the random forest model
* Randomly sampled ½ of the observations from the full data set (same as above)
  - Training data set (799 rows)
  - Testing data set  (800 rows)
  

### Results:

![](https://github.com/vibreate/Machine-Learning-Project-in-R/blob/main/Images/importance%20plots.JPG) 
The two plots illustrate the relative importance in terms of each variable's effect on red wine quality. Overall, the two plots show that alcohol and volatile acidity have a heavy influence on red wine quality.
<br/><br/>
<br/><br/>
![](https://github.com/vibreate/Machine-Learning-Project-in-R/blob/main/Images/model%20performance.JPG)
As shown in this table, the accuracy rate of the random forest reached 86.75%, which is higher than the accuracy rate from the previous classification tree models. 

<br/><br/>
## Multiple Linear Regression:
### Method:
* Linear Regression Model (1) was obtained by regressing the output variable (quality) on all of the input variables.
* Linear Regression Model (5), which is the optimal model was obtained through backward selection (removing
   the variables that have the highest p-value one at a time until all the remaining variables are statistically significant)

### Results:

![](https://github.com/vibreate/Machine-Learning-Project-in-R/blob/main/Images/regression%20results.JPG)
<br/><br/>
Based on Linear Regression Model (5), the relatively large negative coefficients of chloride and volatile acidity suggest that an increase in chloride concentration and volatile acidity would negatively affect red wine quality while higher sulphates concentration is associated with positive effects on quality.
<br/><br/>


#### References

1. Cortez P, Cerdeira A, Almeida F, Matos T, Reis J. Modeling wine preferences by data mining from physicochemical properties. Elsevier. 2009;47(4):547-553.
doi:10.1016/j.dss.2009.05.016 

2. Hlavac M. Published May 30, 2018. https://cran.r-project.org/web/packages/stargazer/index.html.

3. Wine Quality Data Set. UCI Machine Learning Repository. https://archive.ics.uci.edu/ml/datasets/wine+quality 




 





   


