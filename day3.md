---
title: Day 3 - Building your own JupyterLite Web site
layout: home
nav_order: 5
---

# Morning

# LUNCH BREAK

# Building and configuring your own custom site

Now we're going to use GitHub to create our own custom JupyterLite cite.

## Logging into GitHub.

First, let's make sure you have a GitHub account and are logged in!

Go to github.com. Do you see "Dashboard"? If so, that's all you need!
If not, please create an account ;).

## What is GitHub?

GitHub is a lot of things! It's where a lot of programming code is shared
and worked on, individually and collaboratively. It is also a great place
to host code and Web sites for your own use.

The two key concepts for this section are (1) a GitHub **repository**,
which is a collection of files, and (2) a GitHub pages **Web site**,
which is built from the collection of files in a repository and then
provided to everyone on the Internet.

Today we are going to make a copy of a repository by "forking" it, and then
we are going to customize the repository by adding and removing files.

Previously, we've shown you three different "custom" JupyterLite
deployments:

- quick demo on day 1 - [repository](https://github.com/ngs-docs/2026-summer-bcp-101-jupyterlite-demo) and [Web site](https://ngs-docs.github.io/2026-summer-bcp-101-jupyterlite-demo)
- full hands-on demo with just a pre-staged notebook - [repository](https://github.com/ngs-docs/2026-summer-bcp-101-jupyterlite-demo2) and [Web site](https://ngs-docs.github.io/2026-summer-bcp-101-jupyterlite-demo2/)
- the day 2 site with gapminder data pre-staged - [repository](https://github.com/ngs-docs/2026-summer-bcp-101-jupyterlite) and [Web site](https://ngs-docs.github.io/2026-summer-bcp-101-jupyterlite/)

These all varied mostly in terms of what data sets and notebooks were
"prepositioned" - readily available to people running that site. Next,
we're going to show you how to set up your own

(It is 100% possible to start with a "blank" site - just JupyterLite
and basic software installed - and then have students upload their own
data and notebooks. This just adds a lot of failure points the first
time through any lesson.)

## Building your own custom site

FIRST, Titus is going to demonstrate this process so you know what it looks
like.

THEN we are going to go through it together! This may involve some
troubleshooting!

### Step 1 - make your own copy of the repo.

Start by going to the repository you want to copy. We'll start
with the JupyterLite demo repository, which is here:

[https://github.com/jupyterlite/demo](https://github.com/jupyterlite/demo)

On the upper right, there should be a green button labeled "Use this
template." Click on it, and select "Create a new repository."

Now name it. You can name it anything you like. I have hundreds of
these so I tend to put the year in, but you can use something short,
like "bcp-101-demo". Note that spaces and "weird" symbols aren't
allowed - just letters, numbers, and dashes.

You can leave Description blank, if you like, or enter something to help you
and others know what it is - "Demo of jupyterlite", maybe?

Last but not least, choose the visibility of the new repository. **You have
to make this public for later steps to work.**

Now, click "Create Repository".

Wait a few seconds and click "Refresh".

Now you should have your very own copy under your own account!

### Step 2 - Enable GitHub Pages.

Go to "Settings", on the upper right.

Scroll down to Pages.

Under "Build and Deployment", "Branch" - select "main". Click "Save."

Now, go to "Actions" in the top middle. You should see an orange
"pages build and deployment" entry - it will turn green eventually
(you may have to reload the page). This means everything is working!
(The red entry on the bottom is because GitHub fails the first time it
tries to build a Web site, since Pages is not yet configured!)

### Step 3 - Make it easy to go to the Web site.

Go to your "Code" button (upper left) and click on it

On the right side, you'll see a little gear icon next to "About".
Select that, and check the box that says "Use your GitHub pages web site."

Then "Save Changes."

On the right side under About you should now see a blue link. If you 
click on this blue link, that is the JupyterLite Web site that you can
use yourself and also share with others! You can try opening it (maybe
in an incognito window...) if you like!

### Step 4 - customize your Web site!

In the GitHub repository, you will see a bunch of files. Anything in
"content" will end up in your deployed GitHub Pages Web site and hence
in your JupyterLite site.

You can upload any file you want here, as long as it's under ~50 MB.

Let's start by doing two things: first, deleting some files; and second,
adding our own file.

To delete a file, click on it to view it. Then go to the three dots on
the upper right, and select "Delete" from the menu. Then select
"commit changes", and then "commit changes" again.

Try deleting 'javascript.ipynb'!

To add a file, go to 'content' and click "Add file", and then select
"Upload files".  You can now select or drag/drop files to add to your site.

Let's try adding a notebook!

The question you might ask is ... where do I get a notebook??  The answer is,
anywhere! You can download one from your existing JupyterLite demo sites
from day 1 or day 2, OR you can find one on GitHub.

If you need one, try going to
[this link](https://github.com/ngs-docs/2026-summer-bcp-101-jupyterlite-demo2/tree/main/content)
and clicking on `markdown-examples.ipynb`. Now click the little
download link on the right side, and it will bring it to your computer (where
the file lands will differ by computer and browser, sorry...) Now go find it and select it to upload.

### Step 5 - test your site

Each time you change your repository, GitHub runs the "Actions" to build
the new Web site. This takes between 30 seconds and 5 minutes. You can
check on this by going to Actions and waiting for it to turn green.

Now, go to your "Code" view and select the blue link, and open it in
incognito mode. You should see your site with all your adjusted content!

### Step 6 - Celebrate!

OK, really, iterate :). You can keep on adjusting and editing your site
as you wish. Keep on testing it in incognito mode, tho!

### Post-workflow notes

#### Making your own template site!

It is possible to make your own template repository out of any
repository you own. This lets you develop your own "base" of files that
you use and then make copies of it.

To do so, go to "Settings" again and select "Template repository". 

Now go back to the "code" view and you will see "Use this template." Voila!

#### There is no limit to the number of repositories or sites in your GitHub account

...I have about 400 repos in my GitHub account :)
