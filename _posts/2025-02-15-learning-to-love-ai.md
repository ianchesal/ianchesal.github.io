---
layout: post
title: Learning to Love AI
description: Where in an old dog tries to teach himself some new tricks
category: blog
tag: blog ai neovim vim technology
---

I've been mostly ignoring the use of generative AI technologies in my
day-to-day working life. I manage engineers for a living and aside from the
occasional draft of a hard email or slack message to write, I haven't found
many excellent ways to apply it to my work life.

I'm coming around though.

**I definitely believe that productive use of generative AI in an engineer's
day-to-day work is fast becoming the new "I know how to Google well" or "I
can find things on StackOverflow really well" type of skills.**

I like to understand the tools everyone is using around me even if I'm not
using the for my day-to-day. So I set out this morning to apply some generative
AI to a small problem I've been putting off solving in my own life: I wanted to
update [the Hugo theme](https://github.com/ianchesal/hugo-split-theme) I use
for [my band's website](https://crawlspacenh.com) to allow me to optionally
change the "background" picture the site is using on a per-page basis.

I like dipping my toes in to this type of tech doing more and more for me on
small projects. It makes evaluating the output easier; I don't have to be a
deep subject matter expert to know the results are correct. And it makes
managing the transitory state change as I work through the problem with the AI
engine easier; I'm not having to hold on to lot of context as I get from where
I started to where I want to be.

This old dog can't quit vim. Or more specifically:
[Neovim](https://neovim.io/). I've tried [VS
Code](https://code.visualstudio.com/) and [Cursor](https://cursor.com) seems
amazing. But my brain works in vim chords and I can't seem make VS Code's
vim-mode even close to functional enough for me to use it. So I've been focused
on using [avante.nvim](https://github.com/yetone/avante.nvim) with an API key
for [Anthropic's Claude 3.5 LLM](https://www.anthropic.com/claude) to do my
generative bidding on my project work.

I read [an article the other day about using Cursor more
effectively](https://ghuntley.com/stdlib/) and it really brought to light three
ways I've been approaching using AI wrong in my day-to-day:

1. The first is not treating it as an agent I can send off to do my bidding.
   I've been asking AI for small things, not big things. I should be asking it
for bigger things and then correcting it's output, refining it, through
additional prompting once it returns something. That makes it more productive
for me and helps me get what I want out of it without having to be all up front
about how I want it.
1. The second is not refining, refining, refining the output. I've been very
   all-or-nothing with my approach to what AI returns when I prompt it.
Abandoning it if the first answer isn't close enough to what I had in mind.
Refinement seems to be the key to getting what you need out of an LLM.

So with all that in mind, I opened up Neovim at the root of my checked out
theme and started giving avante prompts. The results were...surprisingly
excellent and very, very quick. With one prompt to get it going:

> i want to change this hugo theme so i can optionally display a different
> image on any page on the site

The LLM was able to absorb the files in the repo and understand pretty directly
what I wanted to do. It gave me an response that was detailed and clear;
restating my ask to be certain it was understanding what I wanted:

> I can see that the theme currently supports a site-wide background image
> through the site parameters. To allow page-specific images, we'll need to
> make a few changes. Here's what we'll do:
>
> 1. Modify the baseof.html template to support page-specific images
> 2. Update the SCSS to handle dynamic image paths
> 3. Add CSS to handle the background image styling

It listed the necessary changes for me to review.

I was then able to use avante's apply-all command to have it make the changes
on the various file. avante presents these changes as git diff blocks that you
can review, in-line in the files, and use git three-way-merge style
ours/theirs/all type syntax to either accept or discard each change hunk.
Perfect! This is a workflow I understand well!

A few file changes later and I had the theme updated along with the README so
that I had an example of the syntax I needed to remember to do a per-page
override of the background  image.

Remarkable, really. No refining prompts necessary.

Not a hard task by any means, but it's in a framework (Hugo themes) I don't
work in much at all. I could have spelunked documents and stitched all this
together, but the AI was able to take my prompt and turn it into output that
was correct and readily reviewed by me to make sure it was so.

I know I'm late to this GenAI party, but I'm getting there. This certainly
feels exciting and like something new I want to master.

Still not sure how I'm going to do more with AI day-to-day, but as an
enhancement to my programming productivity I'm pretty excited about the
technology.
