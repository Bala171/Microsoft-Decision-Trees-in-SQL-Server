# Microsoft-Decision-Trees-in-SQL-Server
 In our Data Mining series, we dive into decision trees, a popular algorithm. "Introduction to SQL Server Data Mining" covers setup and fundamentals. Microsoft Decision Trees excel in classification and regression, predicting discrete and continuous attributes.


**What is Decision Trees

Decision Trees are one of the most common data mining algorithm. When you make a decision, you always tend to divide your problem. Let us say you want to go to one place from another place. To decide what time you should leave, you will have a lot of parameters in your mind. Depending on the day (weekend or weekday), type of mode of transport, time of traveling, and if there any special events, type of weather will decide the time. So when you decide on the time, there can combinations. For example, if it is raining, on a weekday, at a peak time, traveling time would be different for different combinations. All these combinations can be visualized into a tree format.

![sample-of-a-decision-tree](https://github.com/Bala171/Microsoft-Decision-Trees-in-SQL-Server/assets/69398534/7b90d73a-7b33-4a91-935d-08832885c2c4)



**Microsoft Decision Trees in SSAS

In SQL Server, using data sets model can be built with Decision Tree algorithms and then predictions can be done from the built decision tree.

We will be using the same dataset vTargetMail view in the AdventureWorksDW database. As we discussed in the previous article, create a SSAS project in the Visual Studio. Then create a data source which will point to the AdventureworksDW database and DataSourceView in which vTargetMail is selected.


**Decision Trees for Classification Problem

After choosing the correct content types, next is to provide the train and test data set parameters. After naming the model, next is to process and view the results.

Following is the Full graph view of the decision. Though the graph is not fully readable in this article, this is to understand how different attributes are contributed to the tree view.


**Depedency Netwok



![dependency-net-work-of-the-decision-tree-model-1](https://github.com/Bala171/Microsoft-Decision-Trees-in-SQL-Server/assets/69398534/e8253d75-8f11-4afa-9593-a3f90ddd5c0a)



**Decision Trees for Regression Problem

![adding-a-regression-model-for-decision-tree-from-t](https://github.com/Bala171/Microsoft-Decision-Trees-in-SQL-Server/assets/69398534/3157885b-6e76-48e5-be95-f80f592fecdc)


**Full Graph of Decision Tree




![full-graph-of-the-decision-tree](https://github.com/Bala171/Microsoft-Decision-Trees-in-SQL-Server/assets/69398534/4a1065b5-e54b-467f-aa22-85c320d764b7)






**Final output


![WhatsApp Image 2024-01-12 at 5 47 29 PM (1)](https://github.com/Bala171/Microsoft-Decision-Trees-in-SQL-Server/assets/69398534/47bcef33-6ed7-4fb8-95b4-d585f35c64dc)


**Model Parameters
As discussed in the previous article, model parameters can be changed so that the model can be further improved to better results.

Model attributes, default value, range are shown in the Model Parameter dialog box.

**Setting up model parameters in decision trees. 


![setting-up-model-parameters-in-decision-trees-](https://github.com/Bala171/Microsoft-Decision-Trees-in-SQL-Server/assets/69398534/1c8f89e4-6785-4bf1-bfe0-63416f3941d5)

**Complexity Penalty
Decreasing the value increases the likelihood of a split while increasing the value decreases the likelihood. The default value is based on the number of attributes for a given model. If there is 1 to 9 attributes default is 0.5 and it will be 0.9 if there are 10 to 99 attributes, and the default is 0.99 if there are 100 or more attributes.

**Force Regressor
This parameter forces the algorithm to use the indicated columns as regressors in the regression formula regardless of their importance as calculated by the algorithm. This parameter is only used for regression trees. This parameter is only available in the Enterprise Edition of the SQL Server.

**Maximum Input Attributes
This parameter specifies the maximum number of input attributes that the algorithm can handle before invoking feature selection. Setting this value to 0 disables feature selection for input attributes. This parameter is only available in the Enterprise Edition of the SQL Server.

**Maximum Output Attributes
This parameter the maximum number of output attributes that the algorithm can handle before invoking feature selection. Setting this value to 0 disables feature selection for output attributes. This parameter is only available in the Enterprise Edition of the SQL Server.

**Minimum Support
This parameter specifies the minimum number of cases that a leaf node must contain. Setting this value to less than 1 specifies the minimum number of cases as a percentage of the total cases. Setting this value to a whole number greater than 1 specifies the minimum number of cases as the absolute number of cases.

**Score Method
This Specifies the method used to calculate the split score. The available methods are Entropy (1), Bayesian with K2 Prior (3), or Bayesian Dirichlet Equivalent with Uniform prior (4).

**Split Method
Specifies the method used to split the node. The available methods are Binary (1), Complete (2), or Both (3).


