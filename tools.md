# Tools used by people who prepare documents for translation

[For discussion, see issue #4](https://github.com/webiwg/feedback-from-translators/issues/4).

## Tools for find use of passive voice

From https://github.com/w3c/html/issues/310#issuecomment-255944066

> fititnt commented 5 minutes ago
> An advantage of English over other languages is that it is much easier to find tools to evaluate this type of improvement.
> 
> I suggest the following:
> 
> - Atom Editor plugin: https://github.com/gepoch/linter-write-good
> - Shell: http://matt.might.net/articles/shell-scripts-for-passive-voice-weasel-words-duplicates/
> - Perl: https://github.com/devd/Academic-Writing-Check
> - NodeJS: https://www.npmjs.com/package/write-good#passive
> 
> ## See output:
> 
> ```shell
> $ write-good semantics-embedded-content.include 
> 
> In semantics-embedded-content.include
> =============
> e in HTML, when there is only a single image resource,
>                          ^^^^
> "only" can weaken meaning on line 9 at column 43
> -------------
>   However, there are a number of situations for which the author might wish to u
>   ^^^^^^^
> "However" is wordy or unneeded on line 21 at column 2
> (...)
> ```
> Check https://gist.github.com/fititnt/b34f531ed42470412e6fa371e7e7830a for rest of output


## Create diff files between different versions of HTML

From comment https://github.com/w3c/html/issues/634#issuecomment-256813935

> ## How to use for multi part
> To see diff of, for example, new changes to HTML 5.2 (https://www.w3.org/TR/html52/textlevel-semantics.html#textlevel-semantics) from Text-level semantics from HTML 5.1
> - Go to http://services.w3.org/htmldiff
> -  Address of reference document: https://www.w3.org/TR/html51/textlevel-semantics.html#textlevel-semantics
> - Address of new document: https://www.w3.org/TR/html52/textlevel-semantics.html
> - Press "get Diff"
> - New page with diffs will be http://services.w3.org/htmldiff?doc1=https%3A%2F%2Fwww.w3.org%2FTR%2Fhtml51%2Ftextlevel-semantics.html&doc2=https%3A%2F%2Fwww.w3.org%2FTR%2Fhtml52%2Ftextlevel-semantics.html
> 
> ## How to use for single-page (Does not work at the moment)
> Right now does not work, error 500. It's probably a very costly request. URL to test: http://services.w3.org/htmldiff?doc1=https%3A%2F%2Fwww.w3.org%2FTR%2Fhtml51%2Fsingle-page.html&doc2=https%3A%2F%2Fwww.w3.org%2FTR%2Fhtml52%2Fsingle-page.html