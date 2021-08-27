---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.10.3
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

+++ {"slideshow": {"slide_type": "slide"}}

# Setup

+++ {"tags": ["remove-cell"]}

CS1302 Introduction to Computer Programming
___

+++ {"slideshow": {"slide_type": "slide"}}

## JupyterHub

+++ {"slideshow": {"slide_type": "subslide"}}

### How to access the JupyterHub server?

+++ {"deletable": false, "editable": false, "nbgrader": {"cell_type": "markdown", "checksum": "5cd0a101a840f3eb47529428d2d1a17d", "grade": false, "grade_id": "Login", "locked": true, "schema_version": 3, "solution": false, "task": false}, "slideshow": {"slide_type": "fragment"}}

- Enter the url of the Jupyterhub server [divedeep.cs.cityu.edu.hk](https://divedeep.cs.cityu.edu.hk) in a web browser.
- Enter your [EID](https://www.cityu.edu.hk/esu/eid.htm) and Password in the fields `Username` and `Password` respectively.
- Click the `Sign in` button.  

![log in](images/login.dio.svg)

+++ {"slideshow": {"slide_type": "subslide"}}

- Choose `CS1302` as the server option and click `Start`.  

![server options](images/serveroptions.dio.svg)

+++

````{note}

`Minimal` is only for trouble-shooting and is insufficient for running the course materials.

````

+++ {"slideshow": {"slide_type": "subslide"}}

- The JupyterLab interface should appear.  

![jupyterlab](images/jupyterlab.dio.svg) 

+++ {"slideshow": {"slide_type": "fragment"}}

````{note}

To submit homework assignments, you will need to 

- `Help`$\to$`Launch Classic Notebook` will open the classic notebook interface, which is needed for submitting lab assignments. You may also
  - visit https://divedeep.cs.cityu.edu.hk/user-redirect/tree or 
  - replace `lab` in your browser url (indicated above in yellow) by `tree` can press `Enter`.
    
````

+++

````{tip}

**How to troubleshoot in case or error?**

- Refresh the page, re-login, or clear your browser cache to reset your browser.
- Restart your server using the `Hub Control Panel` under the `File` menu (shown above) or visit:  
    https://divedeep.cs.cityu.edu.hk/hub/home
- Contact your instructor using the contact information on the course website.

````

+++ {"slideshow": {"slide_type": "slide"}}

## Jupyter Notebook

+++ {"slideshow": {"slide_type": "slide"}}

### How to access course materials?

+++ {"slideshow": {"slide_type": "fragment"}, "tags": []}

The recommended way is to follow the links to the lecture/lab notebooks on the 
[course homepage](https://canvas.cityu.edu.hk/courses/42868).

![course homepage](images/canvas.dio.svg)

+++

The released notebooks are compiled into a

https://www.cs.cityu.edu.hk/~ccha23/cs1302book

which allows you to 
- preview the notebooks conveniently as webpages,
- download the notebooks in PDF or ipynb formats, and
- open the notebook on the jupyterhub server.

+++ {"slideshow": {"slide_type": "fragment"}, "tags": []}

````{important}

It is important to open to the notebooks using the links on the course homepage as it 
- [git-pull](https://git-scm.com/docs/git-pull) updates/corrections to the notebooks and 
- merge them with the notebooks stored under `cs1302` folder in your home directory but
- without overwriting your changes.

If you open the notebook directly on jupyterhub instead of following the git-pull link, updates will not be pulled, and your notebook may fail to have the updates needed for submission.

If you are interested in how [`nbgitpuller`](https://jupyterhub.github.io/nbgitpuller/index.html) works, the following is an example of a git-pull link:

[$
\begin{alignat*}{2}
&\text{https://divedeep.cs.cityu.edu.hk/hub/user-redirect/git-pull?} &\quad&\leftarrow \text{send request to nbgitpuller app}\\
&\text{repo=https://github.com/ccha23/cs1302&} &&\leftarrow \text{pull from the repository}\\
&\text{urlpath=lab/tree/cs1302/release/Lab0/Setup.ipynb} &&\leftarrow \text{follow the path to open the file}
\end{alignat*}
$](https://divedeep.cs.cityu.edu.hk/hub/user-redirect/git-pull?repo=https%3A%2F%2Fgithub.com%2Fccha23%2Fcs1302&urlpath=lab%2Ftree%2Fcs1302%2FLab0%2FSetup.ipynb)

````

+++ {"slideshow": {"slide_type": "subslide"}}

### How to complete a lab assignment?

+++ {"slideshow": {"slide_type": "fragment"}}

Learn how to edit a notebook:

+++ {"slideshow": {"slide_type": "-"}}

1. Click `Help`$\to$ `Welcome Tour` to learn the JupyterLab interface.  
2. Click `Help`$\to$ `Notebook Tour` to learn about the jupyter notebook.
3. Watch the official [video tutorial](https://youtu.be/A5YyoCKxEOU) to JupyterLab.?

+++ {"deletable": false, "editable": false, "nbgrader": {"cell_type": "markdown", "checksum": "6197853194877f5adcb146e250a2a7c9", "grade": false, "grade_id": "qHelloWorld", "locked": true, "schema_version": 3, "solution": false, "task": false}, "slideshow": {"slide_type": "subslide"}}

**Exercise** 

In learning a new programming language, the first program to write is often the ["Hello, World!"](https://en.wikipedia.org/wiki/%22Hello,_World!%22_program) program, which says Hello to the world.  

Type the program 
```Python
print('Hello, World!')
``` 
below and run it with `Shift+Enter`.

```{code-cell} ipython3
---
code_folding: []
deletable: false
nbgrader:
  cell_type: code
  checksum: 351047d00fd4cc7f037ee2059d332b39
  grade: false
  grade_id: helloworld
  locked: false
  schema_version: 3
  solution: true
  task: false
slideshow:
  slide_type: '-'
---
# YOUR CODE HERE
raise NotImplementedError()
```

+++ {"slideshow": {"slide_type": "subslide"}}

````{attention}

We often ask you to write your answer/code in a special cells with *unique but hidden id number*. 
- Make sure you provide your answers only to the answer cells that says `YOUR CODE HERE` or "YOUR ANSWER HERE". 
- For coding exercises, you should also remove `raise NotImplementedError()`.
- Do not clone or duplicate the answer cells.

````

+++ {"slideshow": {"slide_type": "fragment"}}

In order to check your work thoroughly, there will both *visible* and *hidden* test cases. The following is a visible test you can run to check your answer:

```{code-cell} ipython3
---
deletable: false
editable: false
nbgrader:
  cell_type: code
  checksum: 19f650921b4dcc627dfea1aa850b29cd
  grade: true
  grade_id: test-helloworld
  locked: true
  points: 1
  schema_version: 3
  solution: false
  task: false
slideshow:
  slide_type: '-'
---
# Run this test cell right after running your "Hello, World!" program.
import io
import sys

old_stdout, sys.stdout = sys.stdout, io.StringIO()
exec(In[-2])
printed = sys.stdout.getvalue()
sys.stdout = old_stdout
assert printed == "Hello, World!\n"
```

The test returns an assertion error only if your program does not print the correct message.

+++ {"slideshow": {"slide_type": "subslide"}}

````{tip}

1. You can repeatedly modify your solution and run the test cell until your solution passes the test. There is no mark penalty in failing the test before submission. 
1. The test cell often uses more tools that what you might have learned. You are not required to know how to write the test cell but you should try to understand the error messages from a failed test.
1. To assess your solution thoroughly, we will run new tests hidden from you after you have submitted your notebook. There is no partial credit for a partially correct solution that works for the visible test but fails for the hidden test. Therefore, *you should ensure your solution works in general rather than just the visible tests*.
1. If you open the same notebook multiple times in different browser windows, be careful in making changes in different windows as you may overwrite your own changes.
1. If your notebook fails to run any code, the Kernel might have died. You can restart the kernel with `Kernel`$\to$ `Restart`. If restarting fails, check your code cells to see if there is any code that breaks the kernel.

````

+++ {"slideshow": {"slide_type": "slide"}}

### How to submit a notebook

+++

Lecture notebooks under the subfolders `Lecture*\` need NOT be submitted. You only need to submit the lab notebooks under `Lab*\`. Although the first Lab (`Lab0`) does not count towards your final grade, you should still submit it, to get familiar with the procedure.

+++ {"deletable": false, "editable": false, "nbgrader": {"cell_type": "markdown", "checksum": "79e0b079764cade8af51905e2db631fe", "grade": false, "grade_id": "Check", "locked": true, "schema_version": 3, "solution": false, "task": false}, "slideshow": {"slide_type": "fragment"}}

````{attention}

Before you submit, make sure everything runs as expected:
1. **Git-pull the notebooks**: Follow any one of the link on the course homepage to a notebook, which will git-pull any updates/corrections to (all) your notebooks.
1. **Restart the kernel**: `Kernel`$\to$ `Restart Kernel...` 
1. **run all cells**: `Run`$\to$ `Run All Cells`

You may submit as many times as you wish before the due date as we collect your latest submission for grading. 
- *No late submission* will be collected without valid justifications.
- *Double check* that you have submitted the correct Lab assignment.
- You are responsible for *recording your submission attempt* with a valid timestamp in case of technical issues.

````

+++ {"deletable": false, "editable": false, "nbgrader": {"cell_type": "markdown", "checksum": "59999b495764c060fdc26b2ede6b288a", "grade": false, "grade_id": "Submit", "locked": true, "schema_version": 3, "solution": false, "task": false}, "slideshow": {"slide_type": "subslide"}}

To submit your notebook:
1. Start the classic notebook interface by choosing `Help`$\to$ `Launch Classic Notebook`.
1. Go to `Assignment` tab of JupyterHub where you fetched the Lab assignment. 
1. Expand the Lab folder and click the `validate` button next to the notebook(s) to check if all the visible tests pass.
1. Click `Submit` to submit your notebook.

+++

````{important}

Auto-grading often **FAIL** if:
1. The notebook files are renamed, e.g., `Setup.ipynb` changed to `Setup (Copy).ipynb`, or converted to a python script `Setup.py`.
2. An html file exists with the same name as a notebook, e.g., `Setup.html` is the default grading feedback file to be generated when grading `Setup.ipynb`.
3. The file size is too large, e.g, over `100MB`.
4. The notebook is shared from another student.Auto-grading often **FAIL** if:

````

+++ {"slideshow": {"slide_type": "subslide"}}

````{note}

You normally have at least 5 days to work on the lab after your lab session. 
1. You can check the due dates of all the labs from the course homepage. 
1. You may seek help from us or your classmates. However, you must write your own solution and indicate who your collaborators by including their EIDs:  
    ```Python
    COLLABORATORS = ["xfwong2", "mklee3"]
    ```
````

+++ {"slideshow": {"slide_type": "fragment"}}

````{tip}

In case of error: 
1. Download/backup your existing notebooks,
2. remove them from the `Lab*` folder,
3. click the git-pull links from the course homepage to re-pull the notebooks, and
4. copy your solutions to the new notebooks.

````

+++ {"slideshow": {"slide_type": "slide"}, "tags": []}

## Running notebook outside Jupyterhub (Optional)

+++

You may also run the course notebooks outside the jupyterhub server and locally on your computer. For details, see the github repo:  
https://github.com/ccha23/cs1302jupyter

+++

To submit the assignment, however, you still need to use the jupyterhub server.
