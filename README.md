# An Introduction To Machine Learning


![](doc/images/transfer_learning.jpg)


Welcome to this practical introduction to machine learning! 

It was given for the first time at the University of Lyon  between October 13 and 22, 2020. 

The goal of these lectures is to get you started with machine learning fast and easy, so that you can then feel comfortable using it at work (or just for fun).

If you want to try machine learning for the first time, you're at the right place. The only prerequisite is a vague knowledge of any programming language. Here, we're going to use python, which is ruling the field at the moment.

We're not going to bother too much about theory, mathematics, statistics. 

Instead, we'll focus on practical exercises. You'll get your feets wet for the tools commonly used in research and the industry, and you'll build a real feeling for machine learning.  


## How to follow this course? 

The lectures are organized as a series of modules, featuring a set of introductory slides and / or practical jupyter notebooks. 

You can run the notebooks on Google Colab by just clicking on their link. 

*In the notebooks, at the first code cell, Google Colab will ask you if you really want to execute it. Just say yes.*

In the Runtime menu, you can choose a runtime type. For most notebooks, you don't have to care about this. 

**For deep learning notebooks, choose GPU to benefit from hardware acceleration.**
 
**Just after opening a notebook in Colab, make sure to unwrap all the code by doing View -> Expand sections.** so that you don't miss anything. You can also unwrap by simply clicking on collapsed sections when you reach them. 
 
## Ouline

### Basics of scientific python for machine learning (Oct 13)

No slides here, just the notebooks: 

* [python crash course](https://colab.research.google.com/github/cbernet/introduction_machine_learning/blob/master/notebooks/python_crash_course/01_python_crash_course_for_machine_learning.ipynb) 
* [introduction to numpy](https://colab.research.google.com/github/cbernet/introduction_machine_learning/blob/master/notebooks/python_crash_course/02_numpy_for_machine_learning.ipynb)
* [first plots with matplotlib](https://colab.research.google.com/github/cbernet/introduction_machine_learning/blob/master/notebooks/python_crash_course/03_plotting_for_machine_learning.ipynb) 
* Installing Anaconda and scientific python packages (live)
   
### Supervised learning (Oct 14 am)

[slides](https://docs.google.com/presentation/d/1WTeOmpcj3Fr4KU2-ZASnBPjyNd5OddY6Bmr9YYZaXDs/edit?usp=sharing)

* [The 1-neuron network (Logistic regression)](https://colab.research.google.com/github/cbernet/introduction_machine_learning/blob/master/notebooks/supervised_learning/logistic_regression_1d.ipynb)
* [Non-linearities](https://colab.research.google.com/github/cbernet/introduction_machine_learning/blob/master/notebooks/supervised_learning/logistic_regression_2d.ipynb)
* [Overfitting illustrated](https://colab.research.google.com/github/cbernet/introduction_machine_learning/blob/master/notebooks/supervised_learning/overfitting.ipynb)
* [Predicting housing prices in California with XGBoost](https://colab.research.google.com/github/cbernet/introduction_machine_learning/blob/master/notebooks/supervised_learning/xgboost_housing.ipynb)
* [The universal approximation theorem](https://colab.research.google.com/github/cbernet/introduction_machine_learning/blob/master/notebooks/supervised_learning/universal_approx.ipynb)

### Unsupervised learning (Oct 14 pm)


* Visualizing datasets and dimensionality reduction: 
  * [slides](https://drive.google.com/file/d/1NkmNR3EH2Y9G4mGufoYxgvNpigFIaEAi/view?usp=sharing) 
  * [notebook](https://colab.research.google.com/github/cbernet/introduction_machine_learning/blob/master/notebooks/unsupervised_learning/visualizing_datasets.ipynb)
* Clustering: 
  * [slides](https://drive.google.com/file/d/1NkRtXN9mPscZaE6CMqeJ4l4uNCPvtK9z/view?usp=sharing) 
  * [notebook](https://colab.research.google.com/github/cbernet/introduction_machine_learning/blob/master/notebooks/unsupervised_learning/clustering.ipynb)

### Introduction to deep learning (Oct 20 am)
   
* Get started with Keras and Tensorflow
* Convolutional neural networks 
* Embedding
* Transfer learning

### Long Short Term Memory networks (Oct 20 pm)
   
* [slides](ftp://lyoftp.in2p3.fr/baulieu/nn_data/lstm.pdf)
* [Signals classification with MLP and LSTM networks](https://colab.research.google.com/github/cbernet/introduction_machine_learning/blob/master/notebooks/lstm/01_Neda-lstm.ipynb)
* [Anomaly detection on time series data with LSTM network](https://colab.research.google.com/github/cbernet/introduction_machine_learning/blob/master/notebooks/lstm/02_lstm_prediction.ipynb)
