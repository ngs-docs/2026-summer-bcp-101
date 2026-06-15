---
title: Day 1 - welcome and introduction!
layout: home
nav_order: 2
---

# Welcome and introduction!

## Introductions

Everyone introduce themselves and say why they're interested in
participating in this workshop!

## Scope & Goals

- See how certain kinds of modern open-source technology can support teaching data science in high school and college
- Understand, investigate, and exercise the opportunities of the technology we’ll be introducing
- Explore ways to connect technology to the needs of teachers
- Learn from teachers what they need
- Offer technological support to teachers
- Connect teachers by interest

## Structure & Schedule

Dates: Monday, June 15, to Thursday, June 18
Morning Session: 10:00 AM - 12:00 PM (PST)
Lunch: 12:00 PM - 1:00 PM (PST)
Afternoon Session: 1:00 PM - 3:00 PM (PST)

**Monday: Introductory material and the basic technology platform we are showing you.**
We will begin with an overview of the goals for the week, introduce the dataset and examples we will be working with, and make sure everyone is comfortable accessing the course materials. We will also introduce the basic technology platform, including how to open notebooks, run code, save work, and troubleshoot common setup issues.

**Tuesday: Basics of programming, plotting, and statistics in Python.**
We will focus on core Python skills for working with data, including variables, lists, tables, and simple calculations. We will then use these skills to make plots, summarize data, and interpret basic statistics. The goal is to build enough comfort with Python to explore a dataset and ask simple quantitative questions.

**Wednesday: Connecting specific skills to a general data analysis workflow.**
We will broaden from individual coding skills to the larger process of setting up and carrying out a data analysis project. This includes organizing files, choosing useful columns, cleaning or filtering data, deciding what questions can be asked, and connecting code, plots, and interpretation into a repeatable workflow.

**Thursday: Engaging with individual and group plans.**
We will spend time developing individual or group project ideas using the tools and concepts introduced earlier in the week. Participants will identify a question, choose relevant data, outline an analysis plan, and discuss possible outputs. This session will include time for feedback, troubleshooting, and planning next steps.

## Expectations

CTB: max expectations.

Show up; participate; engage!

Think about what you want out of this workshop and communicate it to us,
especially if and as it changes :).

## Technology

CTB: cassie presentation.

Over the next three days, we're going to be introducing you to a
particular set of data science technology. The technology we're using was
chosen based on our own experiences as well as our workshop last year;
in particular, it is not only free, but works on essentially any
computer with a modern Web browser and a keyboard - including Google
Chrome books - and needs no installation, no special permissions, and
no additional software.

The core piece of tech we'll be using is called
[JupyterLite](https://github.com/jupyterlite/jupyterlite), which is a
Web browser-based implementation of the
[JupyterLab](https://jupyter.org/) system. It is built around
[Python](https://www.python.org), which is the programming language
we'll be using. (We'll go over Python more thoroughly tomorrow.)

We'll also be using the [Pandas](https://pandas.pydata.org/) and
[matplotlib](https://matplotlib.org/) libraries in Python, to
work with data and plot data. This will be the bulk of what we do
tomorrow.  (We will also introduce various other Python packages
throughout!)

Last but not least, the other star players in our technology line up
will be [GitHub](https://github.com/) and
[Markdown](https://www.markdownguide.org/]). GitHub is a Web site that
we will use to create, edit, and customize collections of files, and
Markdown is a widely used way of formatting text for display that is
supported by GitHub and JupyterLab as well as many others.

These are all tools and approaches that we and millions of other people use
on a daily basis! We can show you how to begin using them, and there is
no real stopping point for them - they are fully powered and "deep". However,
that also means that they are not necessarily easy to use and configure!

Important things to mention:
* The only account or signup needed is GitHub, which is free to create.
* The main drawbacks of Jupyterlite are: limited by local compute; can't install many things; R is limited.

## Demo

CTB: max will teach..

Demo/overview of next two days to show you how all of these buzzwords
work together.

After lunch we will lead you through all of this so you can get a
top-down view of how it all fits together, and then tomorrow we will
give a more thorough introduction. On Wednesday we'll talk about how it
works underneath and where some of the challenges lie, and then show you
the approaches needed to build your own customized site.

<!-- source code: https://github.com/ngs-docs/2026-summer-bcp-101-jupyterlite-demo -->

Click on this link: [ngs-docs.github.io/2026-summer-bcp-101-jupyterlite-demo/](https://ngs-docs.github.io/2026-summer-bcp-101-jupyterlite-demo/)

Then open quick-demo.ipynb

# Hands-on introduction to technology

## JupyterLite

JupyterLite is a Web-based, entirely in-browser interface to running Python
code, visualizing outputs, and exploring files.

Points:
* Web-based: all interactions via a Web browser.
* entirely in-browser: after retrieving initial set of files, 100% local compute; no Web server needed.
* visualizing outputs: you can see graphs and graphics in the same interface as the code you're running.

To get started, go to this Web page:

<!-- source code: https://github.com/ngs-docs/2026-summer-bcp-101-jupyterlite-demo2 -->

[github.com/ngs-docs/2026-summer-bcp-101-jupyterlite-demo2/](https://ngs-docs.github.io/2026-summer-bcp-101-jupyterlite-demo2/)

This is a custom site that we built for you. On Wed, we'll show you how
to build one for yourself.

CTB TODO:
- put in some screenshots of the JupyterLite interface

### Exporing JupyterLite

You can browse files.

You can launch new notebooks.

### Python notebooks

Start a Python notebook.

**You can run Python code:** enter the following in a cell of your
notebook and click the "play" button to run it.

```
print('hello, world')
```

* you can do basic math
* you can load spreadsheets
* you can create plots and figures

More on this tomorrow.

The last value calculated will be displayed; try executing:
```
5+5
2+2
```
and see what is printed.

You can do:
```
print(5+5)
print(2+2)
```
if you want to see intermediate values printed.

### Manipulating notebook contents

You can curate your notebook cells.

* Edit, move, delete

### Prestaging notebooks

Click on the "markdown-examples.ipynb" file. This is a pre-existing notebook that we wrote for you. It's an example of a "pre-staged" notebook that can be prepared ahead of time and placed in the JupyterLite site.

### Writing text and explanations in Markdown

Basic formatting.

Math formatting.

Images.

### Storing, downloading, and uploading notebooks and figures.

Persistence.

Download.

Upload.

### JupyterLite gotchas.

Caching.

Where are files located.

CTB Maybe save for Wed:

* github, Browser local, clearing cache (chrome, firefox, safari, ??), incognito, updating files how and when

### CTB maybe to cover:

* Teaching strategies (look at instructor training notes!)
    * questions and answers
    * pre-staged data
    * faded examples

* Manipulating and working with Jupyter nb
    * downloading and uploading files/figures
    * printing and/or saving
    * saving/clearing data etc.
