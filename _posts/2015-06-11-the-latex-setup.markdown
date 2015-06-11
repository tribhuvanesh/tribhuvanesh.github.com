---
layout: post
title: The LaTeX Setup
modified:
categories:
excerpt: Some words about my collaborative version-controlled LaTeX workflow.
tags: [latex]
comments: true
image:
  feature:
date: 2015-06-11T19:11:03+02:00
---


I've spent (read wasted) an awful amount of time in the past few weeks shuttling
some theoretical results back and forth my handwritten notebook and a LaTeX workbook,
with a lot of refinement on the way.
This made me realize I end up spending a considerable amount of time editing
my LaTeX workbook, a lot of which can be easily avoided.
So, I thought I'd share some tips I picked up en route.

Surprisingly, I hadn't done these before.
Mostly because my previous experience with LaTeX, although plenty, was mostly
 a brain-dump for relatively small project reports, which didn't involve too many
 iterations.
Hence, I didn't get a chance to realize my amortized inefficiency.
Maybe, until now.

So, here's how I go about it currently.

## LaTeX setup
I primarily edit using TeXShop on a Mac, using an additional external display.
Here's how it currently looks like (I'm quite proud of it.)

<figure class="half">
    <a href="/images/latex-setup-1.png"><img src="/images/latex-setup-1.png"></a>
    <a href="/images/latex-setup-2.png"><img src="/images/latex-setup-2.png"></a>
    <figcaption></figcaption>
</figure>

I edit on one screen, hit `cmd-t` to immediately preview it on the other screen.

The editors are themed with
[Solarized Light](https://github.com/altercation/solarized/issues/167), which
I find extremely pleasant and easy on the eyes.


## Sharing and Version Control
I previously shared and used version control using github.
This allowed me to share it easily with my advisors.
Turns out this was inconvenient -- they had to sync their local copies often, commenting
wasn't possible, and most importantly, they couldn't preview the document using
a single click.

The alternate option I found was to use an online collaborative platform like
[Overleaf](https://www.overleaf.com/).
But, in its pure form, it has two major shortcomings -- you need internet and
the previews in their online editor take forever to load.

My current solution involves the best of both.
Overleaf allows the users to access the git repository for documents hosted
on their website.
So, I `git clone` my workbook, edit using the setup I mentioned before
 and commit regularly.
Any collaborator can easily comment, just like in a Google Doc.

There are downsides to this approach though.
First, comments and online edits by collaborators will bite back as merges.
Secondly, if you have a free account like I do, the document is publicly
visible and you'll be restricted to using 200mb.


## Macros and Notation

I've learnt to treat my notation as variables.
So, I maintain a separate file to store the variable to notation mapping -
categorized, organized and commented.
You won't believe, how useful this is when the content is notation-heavy.

For instance, I represent the m-th example in a dataset,
which are a pair of vectors as
{% highlight latex %}
(\inputVecIndexed, \outputVecIndexed)
{% endhighlight %}
which is defined in my macros file like so:
{% highlight latex %}
\newcommand{\didx}{m}
\newcommand{\inputVec}{\bm{x}}
\newcommand{\outputVec}{\bm{y}}

\newcommand{\indexOf}{[1]}{#1^{\didx}}

\newcommand{\inputVecIndexed}{\indexOf{\inputVec}}
\newcommand{\outputVecIndexed}{\indexOf{\outputVec}}
{% endhighlight %}

I also rely heavily on figures, tables, etc., whose boilerplate I ideally want
a click away.
TeXShop again allows user-defined ones using their Macro Editor.
Here's where I store the boilerplates for equations, aligns, subfigures,
tables, etc.


## Tables
As for the style, I use
[Booktabs](http://www.inf.ethz.ch/personal/markusp/teaching/guides/guide-tables.pdf).
Without exceptions.
It's got great documentation and looks extremely elegant.

As for generating the contents within a table, I use
[Latex Table Generator](http://www.tablesgenerator.com/).
It provides a nice interface to populate tables, and get their LaTeX code.
Plus, it takes away the pain from performing often menial tasks, such as merging
rows and columns, add borders, auto-generating captions, labels, etc.


## Illustrations
In case of simple illustrations, like drawing graph structures, grids and things
of that ilk, I rely heavily on Google Drawing.
In most cases, I find this enough to get your idea across to the reader neatly.

Many a times, my illustrations make use of LaTeX symbols.
In which case, I use [CodeCogs Equation Editor](http://www.codecogs.com/latex/eqneditor.php)
to generate the symbols online and obtain its URL.
I then plug this URL into the Google Drawing sheet, which renders it perfectly.


## Bibliography
All my citations and referenced documents are stored and organized in Mendeley.
This has the option to export the citations as a BibTeX file, which I include
in my project folder.

One option I highly suggest enabling is the Citation Key in
`Preferences | Document Details`.
Because, this makes the key immediately accessible when viewing the document.
