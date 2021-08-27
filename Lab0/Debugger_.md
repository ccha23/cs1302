---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.10.3
kernelspec:
  display_name: Python 3.8 (XPython)
  language: python
  name: xpython
---

+++ {"slideshow": {"slide_type": "slide"}, "tags": []}

# Debugger

+++ {"tags": ["remove-cell"]}

CS1302 Introduction to Computer Programming
___

+++ {"slideshow": {"slide_type": "slide"}, "tags": []}

## Why debuggers?

+++ {"slideshow": {"slide_type": "fragment"}, "tags": []}

As a computer programmer, your goal is to write programs which solves some tasks. But sometimes computer programs behaves in an unexpected way due to *Errors* or *Bugs*. For simple programs, finding errors might be easy. However, for programs consisting many lines of code, finding errors can be very hard.

+++ {"slideshow": {"slide_type": "fragment"}, "tags": []}

A *Debugger* allows us to pause/break the execution of a program at a line, called a *breakpoint*, we specify. This allows us to find errors more easily.

+++ {"slideshow": {"slide_type": "fragment"}, "tags": []}

 In this lab, we will learn to use a visual debugger in JupyterLab. 

+++ {"slideshow": {"slide_type": "slide"}, "tags": []}

## Set breakpoints

+++ {"slideshow": {"slide_type": "subslide"}, "tags": []}

To use the Jupyterlab visual debugger, ensure XPython kernel is running:

+++

![xpython](images/xpython.dio.svg)

If you do not see XPython or a circle next to it on the top-right-hand corner, switch to the XPython kernel by clicking the name of the current kernel on the top-right-hand corner.

+++ {"slideshow": {"slide_type": "subslide"}, "tags": []}

We will use the following code as an example to set a breakpoint. First, execute the code to see the effect.

```{code-cell}
msg = "Hello, World!"
print(msg)
```

+++ {"slideshow": {"slide_type": "subslide"}, "tags": []}

To enter the debug mode, turn on the switch near on top right-hand corner: 

![jupyterlab debugger switch](images/jupyterlab-debug.dio.svg) 

+++ {"slideshow": {"slide_type": "fragment"}, "tags": []}

The debugging sidebar should slide open. You can also open/close the sidebar by clicking bug icon on the right. 

+++ {"slideshow": {"slide_type": "subslide"}, "tags": []}

**Exercise** 

Code cells also looks different in debug mode. What is the difference?

![code cell](images/codecell.dio.svg)

+++ {"deletable": false, "nbgrader": {"cell_type": "markdown", "checksum": "723be0a25c4e145cdd163aa7318f3629", "grade": true, "grade_id": "line-number", "locked": false, "points": 1, "schema_version": 3, "solution": true, "task": false}, "tags": []}

YOUR ANSWER HERE

+++ {"slideshow": {"slide_type": "subslide"}, "tags": []}

To set a breakpoint, press the dot that appears as you hover to the left of line number 2. Run the cell to see what happens.

```{code-cell}
msg = "Hello, World!"
print(msg)
```

The debugger provides quite a bit of information, organized as follows:

+++

* **Orange line** is the line where the execution is paused.  
![paused](images/paused.dio.svg)

+++

* **Variables panel** shows the current values of different variables.  
![variables](images/variables.dio.svg)

+++

* **Callstack panel** provides a more detailed context of where the execution is paused. It also provides the flow control buttons to resume/stop the execution.  
![callstack](images/callstack.dio.svg)

+++

* **Breakpoints panel** shows all the breakpoints of the current debug session.  
![breakpoints](images/breakpoints.dio.svg)

+++

* **Source panel** highlights the source of the breakpoint at which the execution is currently paused.  
![source](images/source.dio.svg)

+++ {"slideshow": {"slide_type": "subslide"}}

**Exercise** Explain whether line 1 and 2 are executed. Use the information from the debugger to support your answer.

+++ {"deletable": false, "nbgrader": {"cell_type": "markdown", "checksum": "060b14b2b8a2628bca885fc8273395c3", "grade": true, "grade_id": "executed", "locked": false, "points": 1, "schema_version": 3, "solution": true, "task": false}}

YOUR ANSWER HERE

+++ {"slideshow": {"slide_type": "slide"}}

## Resume execution

+++

To resume/terminate the execute, use the following control flow buttons at the top of the callstack panel:  
![callstack](images/flowcontrol.dio.svg)
- **Continue** button continues the execution and pause again if it hits a breakpoint.
- **Terminate** button stops the execution.
- **Next/Step-over** button continues the execution of program to the next statement without entering function.

+++ {"slideshow": {"slide_type": "subslide"}}

**Exercise** 

What does the following function `f(n)` computes? Try to set a breakpoint and use the control flow to understand how the program works.

```{code-cell}
def f(n): # definition of a function
    return n * f(n - 1) if n > 0 else 1


f(3)
```

````{hint}

Set the breakpoint one at a time but at different locations. If you set your breakpoint at line 5, you should use the **Step In** button to step into the execution of the function.

````

+++ {"deletable": false, "nbgrader": {"cell_type": "markdown", "checksum": "4977f55aff95e93021c125fe6ec165b6", "grade": true, "grade_id": "factorial", "locked": false, "points": 1, "schema_version": 3, "solution": true, "task": false}}

YOUR ANSWER HERE

+++ {"slideshow": {"slide_type": "slide"}}

## Run temporary code

+++ {"slideshow": {"slide_type": "-"}}

Sometimes, we want to run temporary code without modifying the current notebook. To do so:

+++ {"slideshow": {"slide_type": "-"}}

- Right click anywhere on a notebook and choose `New Console for Notebook`:

![new console](images/newconsole.dio.svg) 

+++ {"slideshow": {"slide_type": "subslide"}}

- Type some code such as `msg` into the console input and run it with `Shift-Enter`:

![console](images/console.dio.svg) 

+++ {"slideshow": {"slide_type": "subslide"}}

````{tip}

- You can run `f(n)` for different values of `n` in the console to understand how the function works. 
- You can set a breakpoint in line 2 of the previous code cell containing `def f(n): ...` and run `f(3)` in the console to pause at the breakpoint. The source code containing the breakpoint will also be shown in the **Source panel**. 
- You can also set a breakpoint in the console input, say `f(3)`, and then step into it.
- While the execution is paused, you can enter a new line of code such as `print(msg)` below `f(3)` in the console and then continue the execution to run the new line of code.

````

+++ {"slideshow": {"slide_type": "slide"}, "tags": []}

## VS Code interface (Optional)

+++

There are other debuggers in different interfaces. A powerful GUI debugger is available in the vscode interface:  
- `File`$\to$ `New Launcher`$\to$ `VS Code`

+++ {"slideshow": {"slide_type": "fragment"}, "tags": []}

Follow the [official guide](https://code.visualstudio.com/docs/datascience/jupyter-notebooks) to install the python/jupyter extension and debug a jupyter notebook.
