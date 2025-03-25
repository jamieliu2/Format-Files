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

  * Extra Colors for xcolor (dvipsnames, svgnames, x11names):
    * `baseColors` (default)
    * `extraColors`

  * Pre-defined environments; theorem, proposition, corollary, problem, solution, example, definition, biohazard, remark:
    * `useEnvs` (default)
    * `noEnvs`

### Known Issues:
  * Using option `[extraColors]` seems to cause an option clash warning in .Rtex files due to code coloring.

## pltstyle.py

A Python script to set up my style configuration for Matplotlib.

### Usage:
In a Jupyter Notebook, use the line magic `%run pltstyle.py`, which will import Matplotlib and configure the style.
* Use style `seaborn-v0_8`
* Use font `monospace`
* Set default plot linewidth to `0.5`
* Set default plot markersize to `3`

## jupyter.theme

A theme for pandoc compilation that intends to mimic the default Python syntax highlighting in Jupyter Notebook.

### Usage:
In the command line, use
> <pre>pandoc -f [<i>original file type</i>] -t [<i>new file type</i>] [<i>file name</i>] -o [<i>output file</i>] --highlight-styles=jupyter.theme</pre>

See pandoc.org/MANUAL.html for more details. Note that it's unclear whether `--highlight-languages=python` is also necessary.

In RMarkdown header, use:
> <pre>output:</pre>
>> <pre>[<i>file type</i>]:</pre>
>>> <pre>highlight: jupyter.theme</pre>

### Known Issues:
  * The formatting settings are not polished an may be missing some functionalities.
  * pandoc does not seem to correctly tokenize Python methods and attributes, giving them the same coloring as plaintext.
  * Non-Python languages may be highlighted oddly due to differing tokenization conventions and lack of careful style definitions for non-Python tokens.
