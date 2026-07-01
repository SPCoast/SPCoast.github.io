---
title: "Project Design"
tagline: "PCB design workflow with EAGLE — a personal set of practices"
keywords: ["eagle", "pcb", "workflow"]
---

> **Note:** This is legacy content from the SPCoast EAGLE-era workflow. Some
> downloadable files referenced below (SPCoast library, EAGLE scripts, the
> `makeboard` helper) previously lived under `/pub/download/docs/` and did
> not survive the migration. They are preserved on the
> [`archive/jekyll-final`](https://github.com/SPCoast/SPCoast.github.io/tree/archive/jekyll-final)
> tag of this repository for reference. Newer KiCad-based workflows are being
> published via [kproj](https://github.com/plocher/kproj).

---

If you google "EagleCad", you will find many articles about making PC boards.
Most focus on one or two details — how to place parts, draw traces, and,
for the adventuresome, how to make simple parts libraries. What they don't
tell you is *why* you should do things a certain way, what you should do
first, and how to make your PCB design experience easier in the long run.
For that, you need to dig deeper into CAD support forums, email threads and
out-of-the-way blog posts. You might even (shudder) read the very useful
documentation from CadSoft! I've tried to collect some of that wisdom here
for my own sanity; maybe it will help yours as well. :smile:

A little bit of structure is a good thing. When working with PCBs,
repeatability and correctness are keys to success. This workflow (and the
tools I've written to support it) help take the time-consuming "make work"
out of the process, and let me focus on board design.

## Problems this workflow is trying to solve

- I've got dozens of different board designs, most with several revisions
  each. Other than the sheer volume of coffee-table coasters that implies,
  keeping track of them shouldn't be a nightmare.
- In order to fix bugs in board designs — or to fab more copies of the good
  ones — I need to be able to reference the source files (sch, brd, ...)
  for **every** fab run.
- I don't design boards full time, so I need simple actions, scripts and
  tools to help me "do it the right way" every time.
- I want to be able to come back to a project after several years and
  figure out what I was doing.
- I want to easily share things with others — and yet not spend all my time
  updating web pages.
