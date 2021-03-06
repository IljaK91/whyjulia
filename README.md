# Why Julia?
This is a "why Julia" presentation. It's mainly meant as a teaser for people without any Computer Science background (you might find some of the terminology overly simplistic). I used it to explain to a group of economics PhD students why I use Julia. Some of the reasoning behind the details of the original talk for non-systems biologists can be found in [this](https://discourse.julialang.org/t/preaching-julia-to-biologists/15058?u=yakir12) Discourse topic.

## How to use
First, you need to install [Node.js](https://nodejs.org/en/). [Here](https://blog.teamtreehouse.com/install-node-js-npm-windows) you find some instructions. Then, I used [reveal-md](https://github.com/webpro/reveal-md). So you can download the `presentation.md` and run
```bash
reveal-md -w presentation.md
```
to see it locally on your browser. Or you can
```bash
reveal-md presentation.md --static folder2static
```
to generate a foldeer with all the needed files to host a static site of the presnetation. I hosted my presentation [here](https://iljak91.github.io/#/) on github. Google for answers on how to host a static website on github (e.g. [this](https://pages.github.com)), it's easier than you think.

## Acknowledgements

This presentation is based on the one uploaded by [Yakir Luc Gagnon](https://github.com/yakir12/whyjulia).

I also copy his acknowledgements:

I've shamelessly copied stuff from @johnfgibson's [why julia talk](https://github.com/johnfgibson/whyjulia), [this](http://ucidatascienceinitiative.github.io/IntroToJulia/Html/WhyJulia) presentation, [this](https://discourse.julialang.org/t/what-package-s-are-state-of-the-art-or-attract-you-to-julia-and-make-you-stay-there-not-easily-replicateable-in-e-g-python-r-matlab) detailed Discourse topic, [this](http://gofile.me/3TJXy/mEGZtH0en) great presentation. Many thanks to @NiclasMattsson, @jonathanBieler, @antoine-levitt, @kevbonham, @mauro3, @Tamas_Papp, @alejandromerchan, @ChrisRackauckas, @Zach_Christensen, @stevengj, @mkborregaard, @Datseris, @DNF, @kristoffer.carlsson, @tobias.knopp and many more that helped with comments and suggestions.
