---
layout: post
title: WYSIWYG in LaTeX with Rakefile
categories: LaTeX rake
---
First tools to work with text I have learned where WYSIWYG and everywhere I looked they were praised. I really did not know the alternative and could not think a reason for it to exist in time of fast computers. 
But when I was exposed to LaTex I have instantly fell in love. Compared to Word it produces astonishingly beautiful output, takes whole of issues away  (numbering, chapters, pages with one sentence on it, positioning pictures and many, many more) and lets you focus on content (and structure) not on the final look (just like WriteBoard, I am using right now). But it has some issues. Actually my relationship with LaTeX is more like love-hate one. Sooner or later you will want to do some non-trivial thing to do. And you will either have to dig really deeply or find someone who did it before - and neither one may be easy, even on the shoulders of google.
But knowing many its faults I still do know imagine writing a thesis in some word processor instead of LaTeX - that would be just plain stupid...

I would like to share with you a simple script that makes life with LaTeX a little nicer. It is a Rakefile, so you need to have Ruby and Rake gem installed. It contains some simple tasks:
- compile - creates PDF document from the source files. It makes a couple of runs too much, but just to be sure that everything is on the right place, with bibliography, table of content, etc. 
- clean - deletes all the messy and unneeded files if you would like to zip folder and send it somewhere.
- view - tries to display PDF in some reader available on your system.
- run - the most interesting part. I have stolen a concept from autotest. It checks the source files every second and if there are any changes it runs compile. If you have a sane PDF reader (like Sumatra on Windows, or Skim on Mac - not Adobe Reader) then it will refresh pdf as soon as it is ready. So you can have this rake task running in the background, and every time you hit save you will see changes in the pdf.

I consider this to be the best of both worlds. You can write freely for most time, but when you are finishing and want to take care of the final look you can almost instantly see changes in PDF and tweek quirks until you are satisfied.

There are other tools to acomplish similar results. One of them is LyX, but there is a problem with retrieving source tex files from it. And you will need them at some point, to do some tweeking, or something that is not available in LyX, but can be done in LaTeX and it will be painful. So do not even start - its lame. There are also some editors with similar capabilities, but I have my favorite editor, you may have yours - and the scripts works with them all.
{% highlight ruby linenos %}{% include Latex_Rakefile %}
{% endhighlight %}
