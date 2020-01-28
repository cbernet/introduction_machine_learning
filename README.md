# An Introduction To Machine Learning

**Illustration here**

Welcome to this practical introduction to machine learning! 

The goal of this series of tutorials is to get you started with machine learning fast and easy, so that you can then feel comfortable using it at work. 

If you'd like to try machine learning for the first time, you're at the right place. The only prerequisite is a vague knowledge of any programming language. Here, we're going to use python, which is ruling the field at the moment.

We're not going to bother much about theory, mathematics, statistics. Instead, we'll focus on practical exercises. You'll get your feets wet for the tools commonly used in research and the industry, and you'll build a real feeling for machine learning.  

So here's a brief outline of the material that we will cover. 

1. Install python for machine learning with Anaconda
* Minimal python for machine learning: 
  * Python basics : variables, loops, functions, data structures
  * Numpy arrays : efficient data manipulation in python
  * Plotting with matplotlib
  * Tips : most useful python packages, notebooks & IDEs.
* Basic machine learning 1: Classification: 
* Basic machine learning 2: regression and unsupervised learning
* Deep learning 1: convolutional neural networks, transfer learning
* Deep learning 2: u-nets, GANs, auto-encoders

Without much ado, let's get started! 


## Install python for machine learning with Anaconda

**Prerequisite:** A linux or mac computer. 

In most tutorials, we will run our code on remote platform, in which everything we need is preinstalled: 

* For sections 2. to 5., we will use Google Colab, which is great for short tests and small datasets. 
* For section 5., we will use FloydHub, which is more adapted to real-life deep learning problems, as it can handle large datasets and store them for a long time.

We'll come back to that. 

These remote platforms are great for lectures such as this one, but you will often need to run on your own machine, on local datasets. 

So in this section, you will learn how to install everything you need on your own machine. 

Python is certainly installed on your machine already. Open a terminal, and type the following command to find it: 

```
which python
```

You should get the path of the python executable: 

```
/usr/bin/python
```

If not, don't worry :-) 

**You do not want to mess up with the python version installed on your computer**, as it could perturbate other programs based on this version. So if it exists, we're not going to use it at all.

**Instead, we will use a tool called Anaconda to install a specific version of python** for a specific task.

### Install Anaconda

As stated on Anaconda's website:

*With over 6 million users, the open source Anaconda Distribution is the fastest and easiest way to do Python and R data science and machine learning on Linux, Windows, and Mac OS X. It's the industry standard for developing, testing, and training on a single machine.*

In a nutshell, the anaconda team maintains a repository of more than 1400 data science python packages, all compatible, and provides tools to install a version of python and these packages at the push of a button, and under five minutes.

To install Anaconda on your computer, [download Miniconda](https://docs.conda.io/en/latest/miniconda.html) for your system. 

* Choose the python 3.7 version
* If you're using Linux, make sure to download the 64 bit version if you have a 64 bit system. Check this by doing: 

```
cat /proc/version
```

```
Linux version 2.6.32-754.23.1.el6.x86_64 (mockbuild@sl6.fnal.gov) (gcc version 4.4.7 20120313 (Red Hat 4.4.7-23) (GCC) ) #1 SMP Mon Sep 23 04:00:04 CDT 2019
```

The `x86_64` string means that this system is 64 bits. If you're unsure, ask us. 

On Linux, you can download the bash installer from the command line with wget like this (replace with the link you need from the Miniconda page):

```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
```

On the mac, you can download it with curl:

```
curl -O https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh
```

After this is done, open a bash terminal and type the following (use the name of the installer that you have just downloaded)

```
bash Miniconda3-latest-MacOSX-x86_64.sh
```

Answer all questions, and make sure you agree to the modification of your `.bashrc` at the end.

### Conda environment creation

Now that Anaconda is installed, we can use it to create a new environment: 

```
conda create -n mlintro python=3.7
```

Activate your new environment by doing: 

```
conda activate mlintro
```

In this environment, python is indeed the python 3.7 of Anaconda. Type the following commands to be sure: 

```
which python
python --version
```

When you want to leave the environment (don't do it know), you can do: 

```
conda deactivate
```

You can always activate the environment again when you need it. 

Typically, people create an environment for each specific task. 
For example, at the moment, I have the following ones, and I switch between them on a regular basis depending on what I have to do: 

```
 conda info --envs
# conda environments:
#
base                     /Users/cbernet/anaconda2
cynapps_web              /Users/cbernet/anaconda2/envs/cynapps_web
dask                     /Users/cbernet/anaconda2/envs/dask
geovis                   /Users/cbernet/anaconda2/envs/geovis
keras                    /Users/cbernet/anaconda2/envs/keras
keras_dev                /Users/cbernet/anaconda2/envs/keras_dev
keras_dev_2x             /Users/cbernet/anaconda2/envs/keras_dev_2x
maldives3                /Users/cbernet/anaconda2/envs/maldives3
mlintro               *  /Users/cbernet/anaconda2/envs/mlintro
mupython                 /Users/cbernet/anaconda2/envs/mupython
opencv                   /Users/cbernet/anaconda2/envs/opencv
source                   /Users/cbernet/anaconda2/envs/source
web2                     /Users/cbernet/anaconda2/envs/web2
```

### A first test of python

First of all, let's try the python we've just installed, by lauching the python prompt: 

```
python
```
Python is an interpreted language, so python code does not need to be compiled before it can be executed (in fact, the code is compiled under the hood only when it's needed). This means we can use python by just typing lines of code on the prompt. Try the following: 

```
>>> a = 1
>>> a
1
>>> a*2
2
>>> b = a*2
>>> b
2
```

We did the following: 

* create variable `a` and set its value to 1
* evaluate `a`
* evaluate `b*2`
* create `b` and set its value to `a*2`
* evaluate `b`

Pretty easy, right? 

We'll explain python variables later on. For now, just note that we don't need to use any special keyword to specify that we're declaring a variable.

Now what if you want to exponentiate `a`? 

```
>>> exp(a)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'exp' is not defined
```

Python tells us that `exp` does not exist. Actually it does, but it's not one of the built-in python functions. It's in fact defined in the `math` **package**. A package is some kind of extension, and can be imported like this: 

```
>>> import math
>>> math.exp(a)
2.718281828459045
``` 

Some packages are included in the [standard python library](https://docs.python.org/3.7/library/) and can be imported right away, like `math`. The standard library contains a lot of packages already! But most of the ones we need for machine learning are not there. 

Fortunately, conda makes it extremely easy to install new packages. 

### Installing packages in a conda environment



