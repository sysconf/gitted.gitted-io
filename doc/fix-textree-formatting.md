# Textree doc: How to fix textree formatting

The tips in this doc are mostly specific to the Emacs editor.

## Non-breaking spaces

* See: http://en.wikipedia.org/wiki/Non-breaking_space

The non-breaking space char is U+00A0 ( ), or &nbsp; in HTML entities

## Quotation marks

* See: http://en.wikipedia.org/wiki/Quotation_mark#Unicode_code_point_table

### Apostrophe

Single quotes (U+0027 [']), when used as an apostrophe, should be
replaced with the real apostrophe (U+2019 [’]).

On Emacs: ```M-X replace-string``` then key ```'```, ```enter```,  then key ```C-'```


### Double quotes
  
The usual double-quote char (U+0022 ["]), for natural lanuages, should
be replaced with the language-specific double-quoting pair.

* English: “…”
* French: « … » (don't forget the non-breaking spaces)

See the definition for different languages:
http://en.wikipedia.org/wiki/Quotation_mark#Summary_table_for_all_languages

This is why textree paes should use a template that inserts the right
double-quotes with the proper spaces.

Example of textree template:
```
:: q {span.quote {:through}}
```

CSS declaration:
```
.quote:before { content: "« " }
.quote:after { content: " »" }
```

Example of use:
```
div The text {q with {b some} quotes} and that’s all.
```

To replace all pairs of quotes which are on the same line (on Emacs):
```M-X query-replace-regexp```
* then: ```"\([^"]*\)"```
* then: ```{q \1}```


## Various conversions from HTML

### Simple elements with no attributes

Replace all <b>: ```M-X query-replace-regexp```
* replace: ```"\([^"]*\)"```
* with: ```{q \1}```

### <a> pasted MediaWiki

#### Internal <a> link

Replace all <b>: ```M-X query-replace-regexp```
* replace: ```"\([^"]*\)"```
* with: ```{q \1}```

#### External <a rel="nofollow">

```M-X query-replace-regexp```
* replace ```<a [^>]*rel="nofollow" [^>]* href="\([^"]+\)">\([^<]*\)</a>```
* with: ```{ext(href=\1) \2}```
