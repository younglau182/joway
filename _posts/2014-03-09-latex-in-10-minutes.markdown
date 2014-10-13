---
layout: post
title: "Latex in 10 minutes"
date: 2014-03-09 03:03
category: latex
tags: featured
---

I was frustrated with complicated tutorials and bunch of text needed to learn LaTeX. Once I figured out everything I need for the beginning I wanted to make this short tutorial. I won't go into installing LaTeX, but all you are ever going to use is pdflatex. To build a document you do `pdflatex file.tex` and you have a PDF ready. You can take a look at my repo [here](https://github.com/andreicek/my-random-school-work/tree/master/Vjezbe_MAT/08-03-2014) to see this in use.

Start the document with the documentclass command `\documentclass{article}`, and then list all the userpackages you are going to use. I use amsmath to have a align environment for my equations, and inputenc UTF-8 because I need čćžšđ for my homework.

Next on `\begin{document}` will start the document and `\end{document}` will end the document. That is the bare bones for our LaTeX document. This will compile just fine but will return a blank PDF. Next on are "meta data" of our document, such as date, title, author, etc. Not surprisingly the commands correspond.

	\title{Točno riješenje zadatka}
	\author{Andrei Zvonimir Crnković, \\
			Programsko inženjerstvo, \\
			Visoka škola za primjenjeno računarstvo, \\
			Zagreb \\
			\texttt{acrnko2@racunarstvo.hr}}
	\date{\today}
	\maketitle

Note `\texttt{acrnko2@racunarstvo.hr}`, this makes your email clikable in the PDF - handy! Next are titles and text. For titles you have abundance of choices but in reality you will only use two: `\section{Our Title}` and `\subsection{Our sub title}`. The first option will create a bigger title, and the other a smaller title. The title will be numbered! To make it unnumbered just add `*` to the end of command, eg. `\subsection*{No numbers - yaay}`. To add a text just write!

	\subsection*{Lorem ipsum}
	Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec justo leo, iaculis vitae nibh a, rhoncus porttitor enim. Proin eu gravida nulla. Etiam pharetra ornare scelerisque. Nullam faucibus arcu eros, nec ullamcorper enim vestibulum vel. Nullam vitae erat eleifend, euismod leo nec, vestibulum tortor. Ut id lacus quis leo cursus ultrices. Vivamus vitae nisl felis. Curabitur id massa vitae neque tristique pellentesque. Aliquam blandit vel augue vitae venenatis.

Now for the fun part! Equations!

There are multiple ways of creating an equation environment. For a single line equations use: `\begin{equation}`, end with `\end{equation}`, but for a longer equations and proofs use `\begin{align}`, as explained in the beginning of this tutorial. In this environment, you choose where the equation will be centered by using `&`. Just write it in front of a character you would like to center against. E.g. `f(x) & = a + b + c` will center around the equal sign. For basic function like fractions and square roots google the exact command when you need it. No need to learn everything the first day. One thing you will use is a new line `\\` you can place it everywhere and the text, or equation will be separated there.

	\begin{align}
	    f(x) & = \frac{(e^x-1)}{x} \\
	    f'(x) & = \frac{(e^x-1)'x-(e^x-1)x'}{x^2} \\
	    f'(x) & = \frac{xe^x-e^x+1}{x^2} \\
	    f'(x) & = \frac{e^x(x-1)+1}{x^2}
	\end{align}

Note that the lines will be numerated, to undo that just add '*' after the align in the begin command. `\begin{align*}`

In the next part of this I will talk a little bit more about text manipulation and graphic in the document.
