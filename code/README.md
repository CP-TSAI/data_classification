## How to run the program? 

### Bayes.m

- the program is for multiclass-classification. 

- to play with the data, change the variables in this following section

```
%%%%%%%%%%% Setting Up Variable %%%%%%%%%
% Divide Data with Different Method
% Choose the "training data" and "processing method".
% TRAIN_IDX is implemented to do LOOCV, 
% use 2/3 data for training, and 1/3 data for testing
%
% function_divide_data(data, TRAIN_IDX1, TRAIN_IDX2, METHOD)
% TRAIN_IDX: 1, 2, 3
% METHOD: 'NONE', 'LDA', 'PCA'

[train_data_set, train_label, test_data_set, test_label] = function_divide_data(data, 1, 2, 'NONE');
% [train_data_set, train_label, test_data_set, test_label] = function_divide_data(data, 2, 3, 'LDA');
% [train_data_set, train_label, test_data_set, test_label] = function_divide_data(data, 1, 2, 'PCA');
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
```

- for example, the following command use **(1) neutral face** and **(2) facial expression** as training data, in the same time, **(3) illumination variations** would be used as testing data. No processing method is applied to the data. 

```
[train_data_set, train_label, test_data_set, test_label] = function_divide_data(data, 1, 2, 'NONE');
```

- another example, **(2)** and **(3)** is used for training (so **(1)** would be applied for testing). **LDA** (you can also use **PCA**) is appied to the data. 

```
[train_data_set, train_label, test_data_set, test_label] = function_divide_data(data, 2, 3, 'LDA');
```




### Bayes_binary.m


- the program is for binary-classification.

- to play with the data, change the variables in the following section

```
%%%%%%%%%%% Setting Up Variable %%%%%%%%%
isPCA = 0; % execute PCA or not (0/1)
isLDA = 1; % execute LDA or not (0/1)
LOWER_DIM = 200; % for PCA/LDA
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
```

- Change the boolean variable **isPCA** and **isLDA** to 0/1 to decide use them or not. 

- The variable **LOWER_DIM** is how small of dimension you want the data to be.


### knn.m

- the program is for multiclass-classification. 

- to play with the data, refer the description in **Bayes.m**

- if you want to change k-value for kNN, change the parameter in **function_NN()**.

- For example, if you want **k = 3**, use the following command.

```
y_predict = function_NN(test_data_set, train_data_set, train_label, 3)
```



### knn_binary.m

- the program is for binary-classification.


- to play with the data, change the variables in the following section

```
%%%%%%%%%%% Setting Up Variable %%%%%%%%%
isPCA = 0; % execute PCA or not (0/1)
isLDA = 1; % execute LDA or not (0/1)
LOWER_DIM = 200; % for PCA/LDA
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
```





### kernel_svm_binary.m

- the program is for binary-classification.

- A **Polynomial kernel** and **RBF kernel** is applied to SVM to do the binary  classification. 

- To play with the program, you can change the variables in the section **Setting Up Variable** in the program. 

```
%%%%%%%%%%% Setting Up Variable %%%%%%%%%
isPCA = 0; % execute PCA or not (0/1)
isLDA = 1; % execute LDA or not (0/1)
LOWER_DIM = 200; % for PCA/LDA
kernel_type = 1; % 1: POLY, 2: RBF
degree = 1.6; % for POLY kernel
sigma = 7; % for RBF kernel
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
```

- You can change the kernel with **kernel_type**. (1: POLY, 2: RBF)

- The **degree** and **sigma** is the variable in "POLY" and "RBF" respectively. 

- A cross-validation is applied to get the optimal value.  


### boosted_svm_binary.m

- the program is for binary-classification.

- to play with the data, change the variables in the following section

```
%%%%%%%%%%% Setting Up Variable %%%%%%%%%
isPCA = 0; % execute PCA or not (0/1)
isLDA = 1; % execute LDA or not (0/1)
LOWER_DIM = 200; % for PCA/LDA
WEAK_LEARNER_NUMBER = 5;
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
```

- You can change the **WEAK_LEARNER_NUMBER** to see how many weak-learner it needs to have a good performance. 



### multiclassifier_fitcecoc.m

- the program is for multiclass-classification with the Matlab built-in function **fitcecoc()**.

- one-vs-one is applied in the built-in function.

- no change for the variables, just run the program and see the result. 

- the training time takes 2 min in my laptop. 


### kernel_svm.m

- the program is for multiclass-classification

- one-vs-all is implemented, we can compare the result with one-vs-one.

- to play with the data, refer to the description in **Bayes.m**.