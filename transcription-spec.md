# Transcription Specification

## Basic Document Example

``` ```


## Transcription

Transcription should generally aim to reproduce the page *as written*, with the following concessions:

* Consistent orthographic mergers (such as व and ब) may be noted in the document header *(see below)* and transcribed as the individually-intended characters for ease of reading.
* Spaces should be placed where possible between words (but not compounds).
* Lines ending in the middle of a word should affix a hyphen (`-`) at the end and optionally a hyphen at the beginning of the next line.


### Transliteration scheme

Transcription should follow the [IAST](https://en.wikipedia.org/wiki/International_Alphabet_of_Sanskrit_Transliteration) transliteration scheme with several extensions for vowels and punctuation as noted below.

| Letter | Transliteration | Example |
| -- | -- | -- |
| *vowels* | *(see IAST)*|
| *consonants* | *(see IAST)*|
| अ before इ or उ | `ä` or `a_` |
| ॰ *(abbreviation)* | `.` |
| • *(dot/period)* | `.` |
| । *(danda)* | `|` |
| ॥ *(double danda)* | `||` |
| line-ending mark | `\` or `¦` |
| notable virāma/hiatus | `_` |


## TEI Manuscript Header

```
```


## Transcription Tags


### Text division & Page layout

#### `pb (n)`
Denotes the start of a folio/page.

  * `n`: the folio number and face *(e.g. "45r", "45v")*


#### `lb (n)`
Denotes the start of a line.

  * `n`: the line number


#### `fw (type, place)`
Contains a kind of repeating marginal note, like a page number or header/footer.

  * `type`: one of *"pageNum, header, footer"*
  * `place`: one or more of *"above, below, left, right, top, bottom, margin"*


#### `div (type, id)` (deprecated: use `space`)
Contains a semantically distinct section of text.

  * `type`: one of *"frame, story, verse"*
  * `id`: a unique identifier


#### `gap (quantity, rend)` (deprecated: use `space`)
Denotes a gap in the text.

  * `quantity`: number of characters the  is wide
  * `rend`: *(optional)* description of the way the gap is rendered *(e.g. "overline", "dash", "[character]")*


#### `space (quantity, rend)`
Denotes an extended space in the text.

  * `quantity`: number of characters the gapspace is wide
  * `rend`: *(optional)* description of the way the space is rendered *(e.g. "overline", "dash", "[character]")*


### Text emendations

#### `add (rend, place)`
Contains a scribal addition.

  * `rend`: *(optional)* one or more of *"caret, above, below"*
  * `place`: one or more of *"above, below, left, right, top, bottom, margin"*


#### `del (rend)`
Contains a scribal deletion.

  * `rend`: one or more of *"overstrike, understrike, strikethrough, scribble"*


#### `subst (type=“transpose”)`
Contains a marked textual transposition.

  * Should contain one `<del>` and one `<add> tag containing the pre and post-correction characters. *(e.g `<subst type="transpose"><del>śana</del><add>naśa</add></subst>`)*
  * Wherever possible, the full akṣara-s of the substitution should be maintained inside the `<subst></subst>` .


### Difficult or missing text

#### `sic` *(optional)*
Contains a portion of text with a difficult or erroneous reading that the transcriber wishes to emphasize is not a transcription error.


#### `g (rend)` *(optional)*
Contains a character or glyph

  * `rend`: *(optional)* a description of the


#### `unclear (reason)`
Contains a portion of text that is not clear to the reader due to writing, fading, ink-spot, blemish, etc. The contents are provided by the transcriber if they are nonetheless decipherable.

  * `reason`: *(optional)* the nature of the unclarity *(e.g. "blemish", "rubbed", "messy")*


#### `damage (reason, quantity)`
Contains a portion of text that is missing or unreadable due to damage. The contents are provided if they are obvious or recoverable.

  * `reason`: the nature of the damage *(e.g. "torn", "hole")*
  * `quantity`: *(optional)* the estimated number of characters obscured by the damage
