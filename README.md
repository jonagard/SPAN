# Introduction

SPAN (SELinux Policy Analysis Notebook) is a small library designed to make using SETools 4 simple in a Jupyter notebook.

Using SETools within Jupyter notebook is an amazingly productive way to do policy analysis. It becomes simple to keep
notes alongside any queries you do or, almost more importantly, write simple scripts that allow you to do more powerful
policy analysis.

![SPAN Screenshot](/images/screenshot.png?raw=true "SPAN Screenshot")

Jupyter notebooks are an interactive environment that lets you write text (in Markdown) and code together. What's
powerful is that the code is executable within the document itself. That let's you
write queries and text together at the same time. You can get a feel for what's possible in this awesome notebook on
[Regex Golf from XKCD](http://nbviewer.jupyter.org/url/norvig.com/ipython/xkcd1313.ipynb). There is also the more
official (and boring) [introduction](https://jupyter-notebook-beginner-guide.readthedocs.io/en/latest/).

# Installation

setools is required but no longer in PyPi.  You'll have to download https://github.com/SELinuxProject/setools and install it.
Note that libsepol has to be at least at 2.7 to work with newer setools (4.2 as of this writing).  If your OS repo
does not offer this version, you can get it from https://github.com/SELinuxProject/selinux/tree/master/libsepol and build
it yourself.  After you build it, do the following:

```
sudo cp selinux/libsepol/src/libsepol.a /usr/lib64/
sudo cp selinux/libsepol/src/libsepol.so.1 /usr/lib64/
sudo rm /usr/include/sepol/*
cd selinux/libsepol/include/sepol
sudo cp -r * /usr/include/sepol
cd ../..
sudo cp -r cil /usr/include/sepol
```

Confirm it works with "import setools" before moving on.  You may have to install some other modules with pip3.

Note that https://github.com/TresysTechnology/setools and https://github.com/TresysTechnology/setools/wiki, although
deprecated, might have some more OS-specific install notes regarding dependencies.

SPAN is pure Python and supports Python 3 only. You can install with:

```
$ pip3 install -r python_requirements.txt
$ python3 setup.py install
```

## MacOS Support

Also note, that this all installs and works on MacOS as well. You will have to install libsepol and SETools from
source, but if you have a working development environment that is not difficult. Just make certain that you
use master from SELinux userspace (https://github.com/SELinuxProject/selinux) and SETools.

# Getting Started

Go to examples and start Jupyter notebook: e.g., jupyter-notebook. This will open a browser window listing the
 contents of the directory. From there you can explore the example notebooks (start with SPAN Example).
