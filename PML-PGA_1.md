Practical Machine Learning Assignment
=====================================

Introduction
------------

After loading the file and looking at the summary of the training data
it was concluded that that there are 19622 rows with 160 varaibles, out
of which the the first 6 are user details ond around 100 columns have
more that 25% missing data.

### Cleaning the dataset

Column containing user timestamps are removed. All the other columns
containing NA are also deleted. This leaves us with 54 columns out of
which our dependent column is classe with 5 categories.

### Creating a cross validation set

The trainig set has been split into two different sets. 80 percent is
for building the model and 20 percent is for cross validation.

### Train the model using random forest

After testing various models random forest was selected for being the
most accurate and fast.

    ## Warning: package 'caret' was built under R version 3.3.3

    ## Loading required package: lattice

    ## Loading required package: ggplot2

    ## Warning: package 'ggplot2' was built under R version 3.3.3

    ## Warning: package 'randomForest' was built under R version 3.3.3

    ## randomForest 4.6-12

    ## Type rfNews() to see new features/changes/bug fixes.

    ## 
    ## Attaching package: 'randomForest'

    ## The following object is masked from 'package:ggplot2':
    ## 
    ##     margin

### Prediction on the cross validation set

As we can see from the confusion matrix the prediction for class A and E
is 100% and for the rest of the classes it is nearly equal to 100%

    ## Warning: package 'e1071' was built under R version 3.3.3

    ##     
    ## pred    A    B    C    D    E
    ##    A 1099    1    0    0    0
    ##    B    0  739    4    0    0
    ##    C    0    0  714    6    0
    ##    D    0    0    0  643    0
    ##    E    0    0    0    0  719

### Overall Accuray

Overall accuracy of the model on out of sample data is 0.99.

    ##  Accuracy 
    ## 0.9971975

### Recal and F1 fro all the classes

    ##          Sensitivity Specificity Pos Pred Value Neg Pred Value Precision
    ## Class: A   1.0000000   0.9996461      0.9990909      1.0000000 0.9990909
    ## Class: B   0.9986486   0.9987441      0.9946164      0.9996857 0.9946164
    ## Class: C   0.9944290   0.9981291      0.9916667      0.9987520 0.9916667
    ## Class: D   0.9907550   1.0000000      1.0000000      0.9981718 1.0000000
    ## Class: E   1.0000000   1.0000000      1.0000000      1.0000000 1.0000000
    ##             Recall        F1 Prevalence Detection Rate
    ## Class: A 1.0000000 0.9995452  0.2800000      0.2800000
    ## Class: B 0.9986486 0.9966285  0.1885350      0.1882803
    ## Class: C 0.9944290 0.9930459  0.1829299      0.1819108
    ## Class: D 0.9907550 0.9953560  0.1653503      0.1638217
    ## Class: E 1.0000000 1.0000000  0.1831847      0.1831847
    ##          Detection Prevalence Balanced Accuracy
    ## Class: A            0.2802548         0.9998231
    ## Class: B            0.1892994         0.9986964
    ## Class: C            0.1834395         0.9962790
    ## Class: D            0.1638217         0.9953775
    ## Class: E            0.1831847         1.0000000

Working on the test data set
----------------------------

Cleaning the test set is important before using the model for
prediction.

### Predicting on the test set

The prediction of the test set has given 100% accuracy.

    ## A B C D E 
    ## 7 8 1 1 3
