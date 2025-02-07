# A Repository for Formatting Styles by Jamie Liu

## preamble.sty

General purpose LaTeX style with macros primarily oriented toward math and statistics, in addition to some other helpful utilities.

### Usage:
In the .tex file header, use:
> <pre>\usepackage[<i>options</i>]{preamble}</pre>

### Options:
  * Indenting (via parskip package):
    * `noIndent` (default)
    * `useIndent`

  * Document Header (via fancyhdr package):
    * `noHeader` (default)
    * `useHeader`

  * Override Existing Command Definitions:
    * `noOverride` (default)
    * `Override`

  * Extra Colors fo xcolor (dvipsnames, svgnames, x11names):
    * `baseColors` (default)
    * `extraColors`

### Known Issues:
  * Using option `[extraColors]` seems to cause an option clash error in .Rtex files due to code coloring.


## jupyter.theme

A theme for pandoc compilation that intends to mimic the default Python syntax highlighting in Jupyter Notebook.

### Usage:
In the command line, use
> `pandoc -f [original file type] -t [new file type] [file name] -o [output file] --highlight-styles=jupyter.theme`

See pandoc.org/MANUAL.html for more details. Note that it's unclear whether `--highlight-languages=python` is necessary.

In RMarkdown header, use:
> `output`
>> `[file type]:`
>>> `highlight: jupyter.theme`

### Known Issues:
  * The formatting settings are not polished an may be missing some functionality.
  * pandoc does not seem to correctly tokenize methods or attributes, giving them the same coloring as plaintext.
  * Non-Python languages may be highlighted oddly due to differing tokenizing conventions and lack of careful style definitions for non-Python tokens.
