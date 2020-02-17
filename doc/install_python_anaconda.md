# Install Python for Machine Learning with Anaconda

**Prerequisites: a mac or a Linux computer.**

in this tutorial, you will learn how to install all the software you need on your own machine for machine learning and deep learning. 

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

## Install Anaconda

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

## A first test of python

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

## Installing packages in a conda environment

To install the packages we need, simply do:

```
conda install jupyter scikit-learn matplotlib
```

Here we installed:

* jupyter notebook: a web server that will allow us to run python and make plots in our web browser
* scikit-learn: the leading python machine learning library (apart from a few specific but important activitities like deep learning)
* matplotlib: an old but still relevant plotting library

as well as all the packages needed by these three. 

To list all the packages installed in the environment, do: 

```
conda list
```

```
# packages in environment at /Users/cbernet/anaconda2/envs/mlintro:
#
# Name                    Version                   Build  Channel
appnope                   0.1.0                    py37_0  
attrs                     19.3.0                     py_0  
backcall                  0.1.0                    py37_0  
blas                      1.0                         mkl  
bleach                    3.1.0                    py37_0  
ca-certificates           2019.11.27                    0  
certifi                   2019.11.28               py37_0  
cycler                    0.10.0                   py37_0  
dbus                      1.13.12              h90a0687_0  
decorator                 4.4.1                      py_0  
defusedxml                0.6.0                      py_0  
entrypoints               0.3                      py37_0  
expat                     2.2.6                h0a44026_0  
freetype                  2.9.1                hb4e5f40_0  
gettext                   0.19.8.1             h15daf44_3  
glib                      2.63.1               hd977a24_0  
icu                       58.2                 h4b95b61_1  
importlib_metadata        1.4.0                    py37_0  
intel-openmp              2019.4                      233  
ipykernel                 5.1.4            py37h39e3cac_0  
ipython                   7.11.1           py37h39e3cac_0  
...
```

## Using this repository locally

As stated already, we're going to run the following parts of this course on Google Colab and FloydHub. 

This part explains how you can run the tutorials of this course on your computer. 

Clone this repository:

```
git clone https://github.com/cbernet/introduction_machine_learning.git
```

Go to the course directory: 

```
cd introduction_machine_learning/notebooks
```

Start a jupyter notebook

```
jupyter notebook 01_outline.ipynb
```


