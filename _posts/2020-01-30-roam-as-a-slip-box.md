---
layout: post
title: "Roam as a slip-box"
description: How I'm using Roam to implement Niklas Luhmann's slip-box method of note-taking.
categories: "blog"
published: true
---

## The slip-box method

I’ve been experimenting with a new note-taking system. It’s called the “slip-box” method, so named because it originally comprised a literal box into which the notetaker would slip index cards.

The method excites me for two reasons. One: it’s a system for reflecting privately on the things I read—for checking my understanding, for improving retention of information, and for identifying questions to follow up on. Two: it’s a system for making connections between ideas. I pretty much buy the claim that creativity is mostly a matter of combining things in unusual ways, and the slip-box is a playground designed specifically for that.

So, what is it? Essentially, it is a repository and incubation chamber for two types of written documents. 

* *Literature notes* are paraphrases of ideas and arguments encountered during research, complete with references.
* *Permanent notes* are the notetaker’s ‘original’ thoughts. 

Both types of notes are written in publishable-quality prose, and each note is meant to include enough detail and context that it could be read and understood on its own. The magic starts once you’ve built up a handful of notes; that’s when you can start connecting them to each other, prompting the creation of even more notes. The inventor of the slip-box method, the German sociologist Niklas Luhmann, connected his notes manually with an intricate system of IDs. But now we have software that can manage connections for us.

Enter [Roam Research](https://roamresearch.com/), a new note-taking power-tool that early users are going absolutely bonkers over. I too have joined the [cult](https://twitter.com/search?q=%23roamcult). Roam is special for many reasons, one of which is that it’s a perfect platform for building a modern slip-box. (Roam’s founder, Conor White-Sullivan, was heavily influenced by Luhmann.)

Still, I haven't yet seen any accounts of how to use Roam as a slip-box. With the caveat that I’m still new to both Roam and the slip-box method, I thought I’d share my current system.

If you aren’t somewhat familiar with Roam, you should go read Nat Eliason's [Roam: Why I Love it and How I Use It](https://www.nateliason.com/blog/roam). If you want to read more about the slip-box method, read Sönke Ahrens' book [How to Take Smart Notes](https://www.goodreads.com/book/show/34507927-how-to-take-smart-notes).

## Roam as a slip-box

When I first started experimenting with the slip-box method in Roam, I had three big questions:

1. **Where should I write my notes?** Should each note be its own page, or its own block? How should I manage note metadata, if at all?
2. **How should I distinguish between types of notes?** How should literature notes differ from permanent notes, and how should both of them differ from other use of Roam that I might want to engage in separately from slip-box notetaking?
3. **How should I connect my notes to each other?** By inline page links, by sub-blocks, or something else?

My answers to these questions are in three Roam features:

* **Daily Notes pages.** I write all my literature notes and permanent notes as individual blocks in my daily notes. This makes it easy to track when I wrote each note, and means that other notes or thoughts can be conveniently added in parallel.

* **Tags**: I have a tag for literature notes (`#litnote`) and a tag for permanent notes (`#permnote`). I include these tags, as well as any relevant reference material, at the end of the relevant blocks. When I want to see all my literature notes or permanent notes together, I can go to the `litnote` or `permnote` pages and see them in the linked references.

* **Block references**: One of the keys to the slip-box is that you need to be able to connect your notes to each other. Roam allows inline links to other pages, but sometimes you don't want to link a block to a whole page, but simply to another block. One way to do this would be to create and indent a new block that nested under the one you are "replying" to, but since I write all my notes in my daily notes, this method would prevent me from knowing when I wrote the reply unless it was on the same day as the original. So instead I use block references: by typing double parentheses and searching for the original block of interest, I can insert that block into my current block at any point and fill out the rest of my block with whatever information I want to include in my new note.

You can see me using all three of these features in my daily notes page from January 18th:

![](../../assets/img/roam_slipbox/roam_daily_note.png)

I like this system because it makes many things easy. I can compose, categorize, connect, and track my notes all at the speed of thought, without being prevented from using Roam for other purposes.

Still, my system will surely keep evolving. I don't consider myself a Roam poweruser, so if you are one and you have suggestions, please do send them my way.