## Objectives

The objectives of this third assignment are to:

1.  Write a linear regression program using gradient descent
2.  Write linear classifiers using the perceptron algorithm and logistic regression.
3.  Experiment variations of the algorithms.
4.  Evaluate your classifier.
5.  Read a scientific article on optimization techniques and comment it.
5.  Present your code, results, and comments in a short dissertation.

## Overview

The gradient descent is a basic technique to estimate linear discriminant functions. You will first use the gradient descent method to implement linear regression. You will then program the perceptron algorithm. Finally, you will improve the threshold function with the logistic curve. You will try various configurations and study their influence on the learning speed and accuracy.

As programming language, you will use Python (strongly preferred) or, possibly, Java.

## Linear Regression

Implement the gradient descent method as explained in pages 719--720 in Russell-Norvig and in the slides to compute regression lines. You will implement stochastic and batch versions of the algorithm.

You will test your program on two data sets corresponding to letter counts in the 15 chapters of the French and English versions of _Salammbô_, where the first column is the total count of characters and the second one, the count of A's: [[French](https://github.com/pnugues/ilppp/blob/master/programs/ch04/salammbo/salammbo_a_fr.tsv)] [[English](https://github.com/pnugues/ilppp/blob/master/programs/ch04/salammbo/salammbo_a_en.tsv)]

Before you start the computation, scale the data so that they fit in the range [0, 1] on the x and y axes. Try different values for the learning rate.

Visualize the points as well as the regression lines you obtain using matplotlib or another similar program.

To help you start this assignment, two Python notebooks are available that solve this exercise on linear regression. You can find them here: https://github.com/pnugues/ilppp/tree/master/programs/ch04/python
The first notebook, gradient_descent.ipynb, only uses Python and vector operations such as the dot product that are in the vector.py file.
The second notebook, gradient_descent_numpy.ipynb, uses Numpy. It is more compact, but you need to know a bit of numpy.

To run these programs, download them on your computer as well as the other programs in the import list: datasets.py and vector.py
Then you need to have a complete python distribution such as Anaconda (https://www.anaconda.com/distribution/). This distribution is available on the student computers at the computer science department.
Finally, you start a notebook by typing:

`jupyter lab`

in a terminal window and you select the notebook by clicking on it in the left pane.
You run the pieces of code by typing shift+enter.

The programs are also available as simple python programs from
https://github.com/pnugues/ilppp/tree/master/programs/ch04/python

## The Perceptron

You will use the same data set as for linear regression, but this time to classify a chapter as French or English. 
1. You will encode the classes and the features using the LIBSVM format, also called SVMLight. This format is a standard way to encode data sets and you can find a description [here](https://github.com/cjlin1/libsvm/blob/master/README). You can also read details on the [sparse data format](http://www.csie.ntu.edu.tw/~cjlin/libsvm/faq.html#/Q3:_Data_preparation) as a complement. The complete LIBSVM program is available from this page: [http://www.csie.ntu.edu.tw/~cjlin/libsvm/](http://www.csie.ntu.edu.tw/~cjlin/libsvm/). You do not need this program in the assignment. You just need to read the description of the data format.
Should you find it difficult to understand the format from the description, you can have a look at dataset examples here: https://www.csie.ntu.edu.tw/~cjlin/libsvmtools/datasets/. The LIBSVM format (SVMLight format) is intuitive and straightforward. 

2. Write a reader function for the LIBSVM format and scale the data in your set. You can write a simplified reader that assumes that all the attributes, including zeros, will have an index, i.e. ignore the sparse format.

3. Write the perceptron program as explained in pages 723--725 in Russell-Norvig and in the slides and run it on your data set. As suggested program structure, use two functions: 
 * `fit(X, y)` that will return `w` (the model) and 
 * `predict(X, w)` that will return `y_hat`. You can encapsulate these functions in a class and, of course, add more parameters.

4. As a stop criterion, you will use the number of misclassified examples.

5. Report the results of the classification and the parameters you have used.

6. Evaluate your perceptron using the leave-one-out cross validation method. You will have to train and run 30 models. In each train/run session, you will train on 29 samples and evaluate on the remaining sample. You have a correct or wrong classification. You will sum these classifications, i.e. the number of correct or wrong classifications, to get your final evaluation.

## Logistic Regression

From your perceptron program, implement logistic regression. You can either follow the description from the textbook, S. Russell and R. Norvig, _Artificial Intelligence_, 2010, pages 725--727, or the slides. You can either implement the stochastic or the batch version of the algorithm, or both versions. As stop criterion, you will use either the norm of the gradient or the norm of the difference between two consecutive weight vectors. Run the resulting program on your data set.

Evaluate your logistic regression using the leave-one-out cross validation method as with the perceptron

## Reading
You will read the article *An overview of gradient descent optimization algorithms* by Ruder (2017) and you will outline the main characteristics of the optimization algorithms the author describes. This part should be of about one to two pages. Link to the article: https://arxiv.org/abs/1609.04747

If you understand French, or using Google translate, you may also want to read the original article on gradient descent by Cauchy here:  https://gallica.bnf.fr/ark:/12148/bpt6k2982c/f540.item.
## Remarks

### Deadline

Use Overleaf to write your report and send the Overleaf link as well as your programs and datasets before 23.59 on February 26, 2020\. The link should be e-mailed to edap01 @ cs.lth.se with the subject line Assignment 2 by username. For your programs, you can either send them as zipped files or as a link to them.

### Problems

In case of problems, send an e-mail to Pierre.Nugues@cs.lth.se.

### Report

The assignment must be documented in the report, which should contain the following:

*   The name of the author, the title of the assignment, and any relevant information on the front page.
*   A presentation of the assignment and the possible improvements you would have brought.
*   A presentation of your implementation and how to run the executable.
*   A print-out of the example set(s) and the resulting weight vectors.
*   Comments on the results you have obtained.
*   A short dissertation on the optimization algorithms from Ruder's paper.

Please, typeset and format your report consistently. You must use Latex. Documents written using MS Word or any similar formats will not be considered.

You may have a look to the code in the textbook code repository (or any other implementations), but the code you hand in must be your work. Do not include the code printout in the report -- the code is available in your solution directory anyway -- but only comments on its interesting parts.

## Programming Language and Environment

You can use one of these two languages: Python3 (strongly preferred, and ideally in the form of Jupyter notebooks) or Java. No other programming language is allowed. Be sure that your programs comply with the standard coding style. You can check this with programming environments like PyCharm or read the PEP: https://www.python.org/dev/peps/pep-0008/.

You must provide all the files and data needed to run the programs. To submit them, you can either:
* Attach them to your submission message as a zip archive (strongly preferred);
* Make them available on the Linux computers at the *.student.lth.se address (e.g. login.student.lth.se)

In the case you choose to submit your programs through the LTH Linux machines, make sure that they are available on these computers at the `*.student.lth.se` address (e.g. `login.student.lth.se`). Give their exact location (the exact PATH). Remember to make your programs and all the folders in their path readable and executable by 'others' (chmod 705 filename). Your programs should remain in your folder until you have been notified of the result, e.g. on the notice board and/or web or by e-mail. 

You may expect that your report and implementation will be examined within two weeks. If your report or implementation is unsatisfactory you will be given one chance to make the corrections and then to hand it in within a week after you have been notified (on the notice board and/or web or by e-mail).
