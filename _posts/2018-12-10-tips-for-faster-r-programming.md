---
layout: post
title: "Tips for faster R programming"
description: 
categories: "blog"
published: false
---

These are all things that I've learned over the past year that have sped up my ability to program in R:

## 1. Change the default RStudio pane layout.

Session history is below the source, and the console and terminal are on the top right. Collapse the history, and enjoy a full vertical screen for developing!

## 2. Add a margin line.

At 80 characters (or whatever), so you don't have to guess if your code is too wide to display in GitHub.

## 3. Use more specific `devtools` functions.


## 4. Use iTerm2 instead of Terminal. 

Set the default typing style  to Natural. This will allow you to use all your favourite keyboard shortcuts for text editing, e.g. option-LEFT for shifting to the beginning of the previous word.

## 5. Use `peek::pview()` and `peek::pprint()` to view or print an object and then return it unaltered.


## 6. Work backwards. 

When developing a new data manipulation feature, your first instinct is to start with your raw data, then build a data model, then write functions to compute the summaries you want from it. Don't! Start at the end: write your summary function, 

## 7. Document your systems like systems, and your tools like tools.

## 8. Use snippets.

## 9. Use git shortcuts.

## 10. Use lists.

Optimize screen space by changing the default layouts of the RStudio panes.

Use devtools to set up your package. Rather than using `check()`, which is slow, use `test()` to run all your tests, and `document()` to regenerate documentation. Once you've set up continuous integration, you can run `check()` in the cloud and get back to work.

90% of the documentation you read is for the tools you use. But 90% of the documentation you write is for the systems you build. Tools and systems require different types of documentation.

Tool documents need extensive examples, and can use short-cuts to save yourself typing.

Systems are often apprehended in GitHub itself (e.g. in pull requests), not on a desktop. This means that if you're passing a dataframe into a function, you should probably type out all of the columns that should be in that dataframe, every single time. I mean, copy-paste, sure.

Use a git branching model. Probably `git-flow`, although I'll note that there are surprisingly few options out there.

RStudio shortcuts:

CMD-OPT-i: create a code snippet.

Tab switching: CMD-OPT-LEFT

peek()

Multiple cursors: 

