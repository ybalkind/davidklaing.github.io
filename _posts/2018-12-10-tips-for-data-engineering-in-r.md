---
layout: post
title: "Data engineering with R packages"
description: 
categories: "blog"
published: false
---

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

