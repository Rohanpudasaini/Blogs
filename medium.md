What Happens When You Run `python main.py`? A High-Level Overview
=================================================================

![captionless image](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*hpkABTZZ_HFLrvkcKFiDWQ.png)

If you’re a Python developer, you’ve probably run `python main.py` hundreds, if not thousands, of times. It’s as simple as typing a command and watching your code come to life. But have you ever wondered what _really_ happens under the hood when you hit Enter? What magic transforms your human-readable Python code into something your computer can execute?

Interesting, right? Well, a few days ago, I found myself asking the same question. I decided to dive deep into Python’s internals and explore its source code (which, by the way, is written in C). What I discovered was fascinating, and I thought, why not share this journey with all of you?

In this series, **Deep Diving into How Python Really Works**, I’ll take you through everything I’ve learned. We’ll get our hands dirty, explore the CPython source code, and even use a debugger to step through the C code that makes Python, well, _Python_. By the end of this series, you’ll have a solid understanding of what happens when you run `python main.py`—right from the moment you hit Enter to the execution of your code.

So, buckle up! In this first part, we’ll start with a high-level overview of the process and set up our environment for the deep dive. From the next part onward, we’ll get into the actual source code and see how Python is _Pythoning_.

A Quick Disclaimer
==================

Before we dive in, I want to be upfront about something: I’m not a C expert. My knowledge of C comes mostly from reading about it during my Bachelor’s degree in BSc CSIT, and I’ve never worked on large-scale C projects professionally. This means I might make mistakes or misinterpret things as I explore the CPython source code. But that’s part of the learning process, right?

Everything I share in this series is based on my own exploration and experimentation. I’ll be diving deep into the C code, using a debugger to trace execution, and sharing my findings as I go. If you spot any errors or have additional insights, please feel free to point them out in the comments — I’d love to learn from you too!

With that said, let’s roll up our sleeves and start this exciting journey into the heart of Python.

The Journey of a Python Script
==============================

When you run `python main.py`, your code goes through a series of transformations before it’s executed. Here’s a simplified breakdown of what happens:

1.  **The Python Interpreter**:
    The `python` command invokes the Python interpreter, which is the core of Python’s execution model. It reads your script, processes it, and executes it.
2.  **Tokenization and Parsing**:
    The interpreter first breaks your code into smaller pieces called _tokens_. These tokens represent the basic elements of your code, like keywords, variables, and operators.
    These tokens are then parsed into an _Abstract Syntax Tree (AST)_, a tree-like structure that represents the syntactic structure of your code.
3.  **Compilation to Bytecode**:
    The AST is compiled into _bytecode_, a low-level, platform-independent representation of your code. Bytecode is not machine code but an intermediate form that the Python Virtual Machine (PVM) can execute.
4.  **Execution by the Python Virtual Machine (PVM)**:
    The bytecode is executed by the PVM, which is Python’s runtime engine. The PVM reads the bytecode instructions and performs the corresponding operations.

![Flow of python code](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*Ae2Z7xMVk4_UDyhGm2k0Nw.png)

The Role of CPython
===================

Python is implemented in C, and the most widely used implementation is called **CPython**. When you run `python main.py`, you’re actually running the CPython interpreter. CPython handles everything from tokenization and parsing to bytecode compilation and execution.

But CPython is more than just an interpreter. It’s a complex piece of software that includes:

*   A **lexer** and **parser** to process your code.
*   A **compiler** to generate bytecode.
*   A **virtual machine** to execute the bytecode.
*   A **memory manager** to handle object allocation and deallocation.
*   A **standard library** that provides built-in modules and functions.

As mentioned earlier, to truly understand how the Python interpreter works, we’ll set up our own Python environment in the upcoming article. This will allow us to dive deep into its internals and explore the magic behind the scenes.

Conclusion
==========

Running `python main.py` might seem like a simple command, but as we’ve seen, it sets off a fascinating chain of events under the hood. From tokenization and parsing to bytecode compilation and execution, Python’s interpreter works tirelessly to transform your human-readable code into something your computer can understand.

This is just the beginning of our journey. In the next article, we’ll roll up our sleeves and dive deeper. We’ll set up a debugging environment, explore the CPython source code, and use tools like LLDB or GDB to trace how Python processes your script step by step. By the end of this series, you’ll have a solid understanding of what makes Python tick — right down to its C code.

**Join Me on This Journey!**
============================

If you’re as excited as I am to explore Python’s internals, make sure to **follow along**! In the next article, we’ll set up our debugging environment and start diving into the CPython source code. If you have any questions or thoughts about what we’ve covered so far, drop a comment below — I’d love to hear from you.

And if you don’t want to miss the next part of this series, **subscribe** or **follow** to get notified when it’s out. Let’s uncover the magic behind Python together!

**What’s in Store for Part 2?**
===============================

In **Part 2**, we’ll set up our debugging environment by cloning the CPython repository, building Python in debug mode, and configuring LLDB. This will prepare us to dive into the source code and explore how Python processes your script. Get ready to get your hands dirty!