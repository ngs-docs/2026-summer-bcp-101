---
title: Day 3 - Building your own JupyterLite Web site
layout: home
nav_order: 5
---

# Revisiting JupyterLite and notebooks

Schematic: how JupyterLite works.

Caching and local copies.

Implications: data and notebooks need to be prestaged. Libraries need
to be provided.

Alternatives to discuss/demo:
- Google Colab
- mybinder
- local install of JupyterLab; JupyterHub

# Building and configuring your own custom site

We've shown you three different "custom" JupyterLite deployments.

- quick demo
- full hands-on demo
- day 2

These all varied mostly in terms of what data sets and notebooks) were
"prepositioned" - readily available to people running that site. In this
section we're going to show you how to set up your own

(It is 100% possible to start with a "blank" site - just JupyterLite and
basic software installed - and then have students upload their own data
and notebooks. This just adds a lot of failure points the first time through.)

## Building your own custom site

Full docs here:

https://jupyterlite.readthedocs.io/en/stable/quickstart/deploy.html

- naming repos, guidelines.
- organizations vs accounts.

- creating your own github sandbox
    - log into github
    - fork repo: https://github.com/jupyterlite/demo
    - enable github pages; record URL of new site
    - check actions
- prestage data files and notebooks
    - upload/etc files; commit
    - wait for actions
    - (how to find URL of new site)
- details:
    - what is done automatically by github/github actions
    - issues and problems revisited: caching and testing.

# How can we support you?

Some of the things we hope to work with you on:

- designing and setting up your own lessons;
- trying things out with us as a "foil";
- digesting custom data sets and helping figure out how to deploy them in a JupyterLite environment;
- helping you figure out what packages to use and how to install them;
- helping with technical problems and debugging;
