# Linear_Regressions

## Exploring Boston Housing Data Set

- The first step is to import the required Python libraries into Ipython Notebook.

![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Explore-1.png)

- This data set is available in sklearn Python module, so I will access it using scikitlearn. I am going to import Boston data set into Ipython notebook and store it in a variable called boston.

![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/sklearn.png)

The object boston is a dictionary, so you can explore the keys of this dictionary.

![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/boston-keys.png)

![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/boston-data-shape1.png)

I am going to print the feature names of boston data set.


![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/boston-features.png)

* I will see the description of this data set to know more about it. In this data set I have 506 instances(rows) and 13 attributes or parameters(columns). The goal of this exercise is to predict the housing prices in boston region using the features given.


![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/boston-description.png)


![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Attribution.png)

I am going to convert boston.data into a pandas data frame.

![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Pandas-DataFrame.png)

As you can see the column names are just numbers, so I am going to replace those numbers with the feature names.

![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/bos-columns.png)

boston.target contains the housing prices.

![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Boston-target.png)

I am going to add these target prices to the bos data frame.


![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Bos-Price.png)

![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/RAD.png)

## Scikit Learn


In this section I am going to fit a linear regression model and predict the Boston housing prices. I will use the least squares method as the way to estimate the coefficients.

Y = boston housing price(also called “target” data in Python)

and

X = all the other features (or independent variables)

First, I am going to import linear regression from sci-kit learn module. Then I am going to drop the price column as I want only the parameters as my X values. I am going to store linear regression object in a variable called lm.

![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Skitlearn-linear-model1.png)

- If you want to look inside the linear regression object, you can do so by typing LinearRegression. and the press <tab> key. This will give a list of functions available inside linear regression object.

![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/linear-regression.png)

**to learn more visit [this link](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html)**