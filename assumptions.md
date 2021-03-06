## Work in progress

Copied from https://github.com/w3c/html/issues/588#issuecomment-254992275

----

These proposals which our group in @WebIWG saying represent our opinion. It's better that they are evaluated by people of other languages, not just us, because they would affect all new documentation additions.

Some points exclusively on line break in text.

## 1. If both final HTML as the source code used by the bikeshed will be used by translators, both must be optimized

The final HTML is easier to generate something with good standard, as it is a technical question. Like use the "HTML beautifier" that consider break text lines by sentences, but is better just that code generated by bikeshed already have is optimized.

The source code needs, at least for new additions, text paragraphs break line by sentences. And this involves explaining to people and document the importance of this.

## 2. Break Line in the middle of a sentence is bad. And not just for translations.
A rigid definition of how many characters a column must have, even with little change, you can make a whole paragraph change, because some words are following lines.

An additional advantage of this change is that it does not affect just translations: this should have a positive impact by reducing noise in commits.

### Bad, as today: by number of chars on a line: 7 line changes for one adition

Added **TESTING TESTING TESTING**. The same will occur for removal of words.

```diff
-Specifying the language of content is useful for a wide number of applications, from
-linguistically-sensitive searching to applying language-specific display properties.
-In some cases the potential applications for language information are still
-waiting for implementations to catch up, whereas in others it is a necessity
-today. Adding markup for language information to content is something that
-can and should be done as content is first developed. If not, it will be much
-more difficult to take advantage of any future developments.
+Specifying the language of content is useful for a wide TESTING TESTING TESTING
+number of applications, from linguistically-sensitive searching to applying
+language-specific display properties. In some cases the potential applications for
+language information are still waiting for implementations to catch up, whereas in
+others it is a necessity today. Adding markup for language information to content
+is something that can and should be done as content is first developed. If not, it
+will be much more difficult to take advantage of any future developments.
```

### Possibly better: by sentences, one sentence changed, one line change

```diff
-Specifying the language of content is useful for a wide number of applications,
+Specifying the language of content is useful for a wide TESTING TESTING TESTING number of applications,
from linguistically-sensitive searching to applying language-specific display properties.
In some cases the potential applications for language information are still waiting for implementations to catch up, whereas in others it is a necessity today.
Adding markup for language information to content is something that can and should be done as content is first developed.
If not, it will be much more difficult to take advantage of any future developments.
```

## 3: Avoid long lines of text (needs discussion) 

Allow entire paragraphs stay in one line is worse than we currently have. This does not seem to be better for translators, and any change is always going to "invalidate" the entire paragraph.

A plain text paragraph you can reach 500-700 characters, more than this example. With mixed HTML, like `<code class="kw" translate="no">xml:lang</code>`, you can reach a lot more.

Our group does not have absolute certainty of when lines should be broken, but we're sure must be broken at some point.

### Example of entire paragraph in a line, 442 chars

From https://www.w3.org/TR/i18n-html-tech-lang/ source code

```html
<p>This document provides guidance for developers of HTML that enables support for international deployment. Enabling international deployment is the responsibility of all content authors, not just localization groups or vendors, and is relevant for all content. <!--Ignoring the advice in this document, or relegating it to a later phase in the development process, will only add unnecessary costs and resource issues at a later date.--></p>
```

### Line break at dots, maximum of 131 chars

Line break at ".". Sometimes we break at "," or "(" for very long texts, but this can make some words go up or down. So we are not 100% sure about this.

```html
<p>
  This document provides guidance for developers of HTML that enables support for international deployment.
  Enabling international deployment is the responsibility of all content authors, not just localization groups or vendors, and is relevant for all content.
  <!--Ignoring the advice in this document, or relegating it to a later phase in the development process, will only add unnecessary costs and resource issues at a later date.-->
</p>
```

## 4: Source code more like markdown (really needs discussion)

_Important note: our group has not yet translated sufficient amount of texts with help of bikesheed to be able to say if this is a good suggestion. In a few months we may have an opinion on the subject._

The most efficient way to explain to **new** people how many spaces they should put before the text is saying they should put zero space.

We do not need to define how much is our tabulation, if we use 2 blank spaces, 4 blank spaces, or 8 blank spaces or tabulation with <kbd>Tab</kbd>. Also, we do not need to explain that some code editors convert <kbd>Tab</kbd> to space and needs change.

Using markdown syntax encourages keeping a simpler code. Allows pure HTML, but it might be simpler to centralize some decisions, like "what class must have this header h3?", or even internal links that can change, in the preprocessor, like bikeshed already do, but not all W3C repositories use it, and even for new commits, I guess some people still use raw HTML.

Markdown approach make it more easy for people who do text review, or anyone that uses tablet or phones. It make easy for who use only github web editing for preview result (and if not, we can find people to create browser extensions for hack github web editing and make a better preview), so we can have more people helping us.

The use of less repetitive code and remove indentation makes more easy for who is blind. [Blind programmers tend do not like Python](http://stackoverflow.com/questions/118984/how-can-you-program-if-youre-blind) or are forced to have a [**expensive** braille display](http://www.freedomscientific.com/Products/Blindness/FocusBlueBrailleDisplays). In the same way that today people who are helping us translate are receiving mentoring, we have high interest in training blind people to be programmers.