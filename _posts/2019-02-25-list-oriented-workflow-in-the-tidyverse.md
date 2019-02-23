---
layout: post
title: "A list-oriented workflow in the tidyverse"
description:
categories: "blog"
published: false
---

Most of my R training involved operations on dataframes, usually with `dplyr` functions like `filter`, `select`, `mutate`, `group_by`, and `summarize`. These are wonderful tools that I continue to use every day. However, there is a second set of tools that have become equally important in my day-to-day data manipulation work: those for working with lists.

You may have been told on your first day learning R that a list is a special type of vector that can contain elements of different types, including lists. If you're like me, you promptly forgot this fact, and spent the next year working with dataframes. But if you spend enough time working with data professionally, it eventually becomes clear that most data isn't born as a tidy CSV. Instead, it's usually stored in a nested structure such as JSON or XML.

The reason lists are so useful is that they are R's most natural data type for representing data that starts out in a nested structure.