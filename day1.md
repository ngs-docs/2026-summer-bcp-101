---
title: Day 1 - welcome and introduction!
layout: home
nav_order: 2
---

# Welcome and introduction!

## Introductions

Everyone introduce themselves and say why they're interested in
participating in this workshop!

## Scope & goals

- see how certain kinds of modern open source tech can support teaching legit data science in high school and college
- understand, investigate, and exercises the affordances of the technology we’ll be iintroducing
- explore ways to connect technology to needs of teachers
- learn from teachers what they need
- offer technology support to teachers
- connect teachers by interest

## Structure & schedule

## Expectations

Show up; participate; engage!

## Technology

Over the next three days, we're going to be introducing you to a
particular set of data science technology. The tech we're using was
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

## Demo

Demo/overview of next two days to show you how all of these buzzwords
work together.

After lunch we will lead you through all of this so you can get a
top-down view of how it all fits together, and then tomorrow we will
give a more thorough introduction. On Wednesday we'll talk about how it
works underneath and where some of the challenges lie, and then show you
the approaches needed to build your own customized site.

- start up jupyterlite from a customized site
- load in data set from spreadsheet
- plot relationships present in data set
- provide a faded example of some kind

# Hands-on introduction to technology

## JupyterLite

JupyterLite is a Web-based, entirely in-browser interface to running Python
code, visualizing outputs, and exploring files.

Points:
* Web-based: all interactions via a Web browser.
* entirely in-browser: after retrieving initial set of files, 100% local compute; no Web server needed.
* visualizing outputs: you can see graphs and graphics in the same interface as the code you're running.

To get started, go to this Web page:

[ngs-docs/2026-summer-bcp101-jupyterlite](https://github.com/ngs-docs/2026-summer-bcp-101-jupyterlite)

This is a custom site that we built for you. On Wed, we'll show you how
to build one for yourself.

CTB TODO:
- replace jupylite site above with custom site
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

### Manipulating notebook contents

You can curate your notebook cells.

* Edit, move, delete

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

* Teaching strategies
    * questions and answers
    * pre-staged data
    * faded examples

* Manipulating and working with Jupyter nb
    * downloading and uploading files/figures
    * printing and/or saving
    * saving/clearing data etc.
