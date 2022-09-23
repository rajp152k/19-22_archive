---
title:  6 months of Emacs
category: Tools
tags: [emacs]
---


### [2021-12-14 Tue 10:13] - 7897

I'd been using vim for 18 months before I shifted full time to Emacs
this past May(2021). I allowed for a fair, healthy, deliberate
acclimatization buffer of 4 days before I passed any judgments - by
the end, I'd settled in my new home (a CLI emigrant). This is a
meta-review: about how a functional customization dilettante
experiences such abstractly potent tooling.

## The Abstractualized[^1]

As with any versatile, complex tool one intends to add to their
repertoire, one always starts out with base expectation as to how the
new tool handles the requests old utilities handled. One slowly
acquaints oneself with orthogonal utilities that have a different
take on tasks - Emacs definitely does not shy away from its own
different takes. 

One definitely can't expect to know about all the bells and whistles
right away: achieving a global efficiency optima (questionable
existence) is probably a non-verifiable experience. In such a
situation, fluid feedback mechanisms and ease-of-access to novel ideas come in handy.

Emacs[^2] does an exceptional job
of being transparent about what your "editor" is actually doing for
you without burdening you with the peculiarities from the get go. It
draws upon the powerful mathematical notion of closure - almost all
are capable of it but none approach what lisp does to make it so
obvious and almost magical[^3]. Elaborating, closure is all about the result
sharing some base abstract structure with the input upon being
processed by an operation.

This may seem like "meh" in the moment... But, if all there is, boils
down[^4] to one representation and retains this upon transformations, with
"all-there-is" encompassing the transformations as well mind you, the
computer is a joy to program: you can have transformable transformed
transformations of "data" (or code).

Now that I'm out of implicit pretentious self-praise, moving on to ...

## The Materialized

One, however, does tend to occasionally settle down for a local
optima and without frequent jitters, won't ever discover what's
possible. Fortunately, a periodic tinge in monotonic pursuits does
excite me [^5].

Post a semester of Emacs, I've thrown a lot of tasks at it and my
present local optima for my root tasks looks something like this:


### Task Management

 - GTD with org-mode and org-agenda
 - org deserves more than a single bullet
 
### Code 

 - LSP mode for uniformity
 - I use it for Racket, Python and C++
 
### Assignments/Presentations

 - drafted in org
 - converted to latex via org-to-latex (does beamer as well)
 - sometimes do directly write in latex using Auctex

### Blogging workflow

 -  Written as markdown ->  Evil(C'est la VIE (Vi Is Everywhere))[^6]
 -  Magit for version control
 -  Projectile and dired for basic file-ops
 -  Rarely call upon eshell if testing locally

### Research workflow

 - org-roam for the note-web (replaced obsidian)
 - org-noter to couple the notes with papers
 - Zotero managing an automated .bib (independent of Emacs)
 - helm-bibtex, org-ref, org-roam-bibtex for citation management
 - reading and annotating papers via pdf-tools
 
### Remote work

 - Tramp is good

[^1]: albeit a good counterpart for materialized, it's not a word
[^2]: Lisp, to be precise
[^3]: I'm not proficient enough to appreciate it fully yet, though...
[^4]: boils up should sound right - but doesn't
[^5]: imagine a(>0)x + b(<a)sin(x)
[^6]: Serendipity is awesome
