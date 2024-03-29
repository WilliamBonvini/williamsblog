---
title: "Write better documentation with Sphinx"
subtitle: ""
excerpt: ""
date: 2022-11-12
author: "William Bonvini"
draft: true
images:
series:
tags:
categories: 
- documentation
layout: single
---

 

| topic                                                        | OS      | required modules |
| ------------------------------------------------------------ | ------- | ---------------- |
| Generate Sphinx documentation for a Python project with the *ReadTheDocs* theme. | Windows | venv             |

### High Level Overview

<div style="text-align:center">
  <figure>
    <img src="imgs/sphinxdoc.png" style="zoom:40%">
  </figure>
</div>



Suppose that you have written a Python library and you want to share it with your colleagues. One of the most important things to do is to write a clear documentation. This tutorial will help you in achieving just that.

Our sample project's structure will look like this

```
my_library
	|
	|---my_module.py
```

And `my_module.py` contains the following code:

```python
class MyFirstClass:
    def __init__(self, name: dict):
        """ class constructor """
        self.name = name
        
    def foo(self) -> None:
        """ This method prints a welcome message """
        print(f"Hello {self.name}")
        
    def bar(self) -> None:
        """ This method prints a goodbye message """
        print(f"Goodbye {self.name}")
```

in the end we will obtain an HTML page that documents all the methods we have written above.

Let's start!

### Create a virtual environment and install Sphinx

<div style="text-align: center">
  <figure>
    <img src="imgs/sphinx-installation.png" style="zoom:30%">
  </figure>
  <figcaption><i>A bunch of people installing a sphinx.</i></figcaption>
</div>

1. Open a shell (you'll be using this for all the next steps of this tutorial)

2. Go to the `my_project` folder

3. Find the path of your python executable

   ```bash
   python -c "import os, sys; print(os.path.dirname(sys.executable))"
   ```

   It will output a path (I'll refer to it as *MY_PATH*).   
   Copy it, you will need it in the next step.  

4. Create a virtual environment

   ```bash
   MY_PATH/python -m venv "venv-mylibrary"
   ```

5. activate your virtual environment by running

   ```bash
   venv-mylibrary/Scripts/activate
   ```

6. Run the following command to install Sphinx and some auxiliary libraries. 

   ```bash
   pip install sphinx==5.3.0 sphinxcontrib.applehelp==1.0.3 sphinx-rtd-theme==1.1.1
   ```

   Now you have added sphinx to the requirements of your virtual environment

### Sphinx Quickstart

<div style="text-align:center">
  <figure>
    <img src="imgs/sphinx-quickstart.png" style="zoom:35%">
  </figure>
</div>

1. Create a folder where you'll put your documentation files. I like to call it `docs`.

   ```bash
   mkdir docs
   ```

2. Navigate to the docs directory

3. Run the following command to create the necessary Sphinx files and directories:

```bash
sphinx-quickstart
```

This command will prompt you for some information about your project, let's see them  in detail:

```
> Separate source and build directories (y/n) [n]:
```

I suggest you to write `y`, It looks cleaner. 

```bash
> Project name:
```

I suggest you to use the name of the project's root folder.

```bash
> Author name(s):
```

Insert the author names in alphabetical order, separated by a `,`

```bash
> Project release []:
```

If you press enter, it will default to `0.0.0`, otherwise specify a different version.

```bash
> Project languge [en]: 
```

Press enter, it will default to `en`.

Finished: An initial directory structure has been created.

```
my_library
    |
    | - docs 
    |    |
    |    | ---------- source
    |    |				|
    |    |				| - conf.py
    |    |				| - index.rst
    |    | - make.bat
    |    | - Makefile
    |
    | - my_module.py
```

### Edit `conf.py`

The `conf.py` file let's you specify what extensions, themes and auxiliary information to create your Sphinx documentation. 
Modify it as shown below:

```python
# find the row where html_theme is set and modify it as follows (if it doesn't exist create it from scratch)
html_theme = 'sphinx_rtd_theme'

# find the row that contains extensions = [] and modify it as follows:
extensions = ['sphinx.ext.autodoc', 'sphinx.ext.napoleon']

# Add the path of the root directory of the library
sys.path.insert(0, os.path.abspath('../../my_library'))

```

### Create `my_module.rst`

At the same level of `index.rst` create a new file called  `my_module.rst` (give it the name of the module you want to document in Sphinx).

```
my_library
    |
    | - docs 
    |    |
    |    | ---------- source
    |    |				|
    |    |				| - conf.py
    |    |				| - index.rst
    |	 |				| - my_module.rst
    |    | - make.bat
    |    | - Makefile
    |
    | - my_module.py
```



And populate it as follows:



```rst
MyFirstClass
================

Description of MyClassName

.. autoclass:: my_module.MyFirstClass
   :members:
   :undoc-members:
   :show-inheritance:
```

This will generate the documentation for each public method of `MyClassName`.  

Repeat this process for all the classes/modules you have.

### Edit `index.rst`

Edit the file `docs/source/index.rst` to add to the table of content the link to the files you have just created.  
Mind the empty line before `my_module`, it is necessary!

```rst
Welcome to MY_LIBRARY's documentation!
=======================================

This is a high level description of MY_LIBRARY, modify it as you like.

.. toctree::
   :maxdepth: 2
   :caption: Contents:
   
   my_module


.. _my_module: my_module.rst



Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
```

### Generate HTML

Once you have populated all of the necessary files, you can generate the HTML documentation by running the following command from the `docs` directory:

```bash
make html
```

This will create the HTML documentation for your package in the `docs/_build/html` directory.   
You can view the documentation by opening the file `index.html` in a web browser.

### Conclusions

<div style="text-align:center">
  <figure>
    <img src="imgs/the_end.png" style="zoom:40%">
    <figcaption><br><i>A smiling anthropomorphic Sphinx in an elegant red jacket during a curtain call of a Broadway show in the style of Salvador Dalì.</i></figcaption>
  </figure>
</div>

That's it for this tutorial!   
You can now publish your repository to [readthedocs](https://readthedocs.org/) itself, or in any static website hosting platform (like GitHub Pages).

Suggested reads:

* [Read The Docs "How to"](https://sphinx-rtd-tutorial.readthedocs.io/en/latest/index.html) - ReadTheDocs itself has written a tutorial on how to generate documentation using Sphinx. Go to the *Populating Our Documentation* section.
* [Publishing the documentation to ReadTheDocs](
