# Contribution and Style Guide

This document is an overview of how to contribute to the book. The following guidelines are used to ensure consistency across chapters and code chunks. 

The book is published using [JupyterBook](https://jupyterbook.org/en/stable/intro.html). 

## Adding New Content

* You can fork the repository before adding new content, and submit a pull request when you want to merge new content, or we can give you direct access to the book repository.
* Add new pages to `_toc.yml`, per the [JupyterBook guidelines](https://jupyterbook.org/en/stable/structure/toc.html). Otherwise they won't be rendered.
* If creating a new part, use `numbered: true` to [number chapters and sections](https://jupyterbook.org/en/stable/structure/configure.html#number-your-chapters-and-sections). The only parts that won't be numbered are the front-matter (license, acknowledgements, author bios, etc) and end-matter (references, etc).
* New parts should also be given [captions](https://jupyterbook.org/en/stable/structure/configure.html#add-captions-to-parts) to provide headers.
* Test new content using `jupyter-book` (which will involve installing the Python package using `conda` or `pip`) locally before pushing. The relevant command is `jupyter-book build content` from the local repository root. That will build the web version.
* The GitHub repository is set up to automatically compile [the web version](https://viveks.me/CRA-book) using an Action upon a push to the `main` branch.

## Book Structure

### Parts

The book is composed of several parts, each of which correspond to a particular case study. Each part should be self-contained, as the goal of the book is to be modular based on the learning objectives of a particular class or tutorial. Links to other sections are ok when necessary. Each section should include [its own package environment][#environments].

### Narrative and Notebook Pages

* Pages can be narrative pages or notebook pages (also see [File Formatting](#file-formatting)). Narrative pages introduce sections, transition between topics within a section, or introduce concepts that do not have accompanying code. 
* Each page should be associated with certain learning objectives. In general, "active" learning objectives can be associated with notebooks, while "passive" learning objectives . List these at the top of the page in a Markdown list (using [good learning objective constructions](https://www.aamc.org/system/files?file=2019-07/learning-objectives.pdf)). For pages which introduce parts, list the higher-level learning objectives for the overall part.
* Feel free to split "chapters" (within parts) into multiple pages using the [`sections` keyword in `_toc.yml`](https://jupyterbook.org/en/stable/structure/toc.html#use-parts-to-organize-chapters).
* If a page could be used as a coding tutorial, use the notebook format so students and other readers can interact with the notebook file. 
* Narrative pages can include demo code chunks, but these will not be executed and there will not be a downloadable notebook, so these should be used sparingly. 
* JupyterBook compiles notebooks independently of each other, so each notebook should be self-contained. If output from one notebook is intended to be used as input into another (for example, MCMC output for later simulations), you can save the relevant output and import it into another notebook, but ideally these would be combined into a single page.
* Notebooks should use the `julia-1.6` kernel. I couldn't get this to work with `julia-1.7`, at least not yet.

### Section Names

* Use standard Markdown section headers within each page (`#` for the page title, `##` for the main within-page sections, `###` for subsections, etc). These will get knitted together appropriately by JupyterBook within the broader book structure.
* Section names will automatically create anchors, which can be cross-referenced, e.g. `## Section` can be referenced later in a link using `[](#section).
* Automatic anchor generation can create issues if the same names are used across pages. Try to avoid this within your part(s), and we will make sure these are unique across the entire book in the final editing pass.
* Err on the side of using more subsections rather than fewer; these will appear in a table of contents.

### References

Add references in BibTeX to `contents/bibliography/references.bib`. They will get auto-added on compile to the References section.

## Repository Organization

The book contents are stored within `contents/`.

### File Names

Make filenames informative about the topic (so they might mirror the overall page title).

### File Formatting

Narrative pages should be written in (written in [MyST Markdown](https://myst-parser.readthedocs.io/en/latest/)) files with a `.md` extension. Notebook pages should be written in Jupyter notebooks with a `.ipynb` extension.

Each section (or part, in JupyterBook terminology) should have its own subfolder within `contents/`. For example, the flood risk part is in `contents/flood`. If necessary, place `data/` and `images/` subfolders within the main subfolders for each part. External data which is loaded within a chapter should be put in `data/` and cited appropriately within the relevant page(s). Provide external links as appropriate. 

Images which are imported (as opposed to being generated by executed code) should be included in `.png` format in `images/`. See [Images](#images) for more information on how to use images.

## Julia Code

These guidelines build off the [YAS Style Guide](https://github.com/jrevels/YASGuide) and the [Julia Style Guide](https://docs.julialang.org/en/v1/manual/style-guide/). There may be some redunancies between these and what are listed here, which are intended for simplicity's sake as a convenient reference.

### Environments

* Each section should include its own package environment, with a `Project.toml` and a `Manifest.toml`. These should include all necessary packages to run the code(s) within each section, which keeps each section self-contained. 
* [`IJulia.jl`](https://github.com/JuliaLang/IJulia.jl) also needs to be included in each environment to provide access to the `julia-1.6` kernel.
* At the start of each notebook, include the following in a Julia cell to import the environment:
  ```julia
  import Pkg
  Pkg.activate("."; io=devnull);
  Pkg.instantiate(; io=devnull);
  ```

### Imports

* Import all needed packages at the beginning of a notebook, for example:
  ```julia
  using Distributions, LinearAlgebra
  using Plots
  ```
* Multiple imported packages on one `using` line is ok.
* Even though it's redundant, you can import packages with `using` again later in the document when the functions from that package are used if it helps with the flow (for example, if introducing a particular piece of functionality in the narrative).

### Naming Guidelines

* Use lowercase `snake_case` for function and variable names. Small words can be smashed together (for consistency with Julia base functions like `isequal` or `haskey`).
* Use `CamelCase` for type and struct names (which shouldn't be needed often).
* Use uppercase `SNAKE_CASE` for constants.
* While conciseness is valued, make function and variable names descriptive, rather than abbreviations or single letters. Abbreviations can be bad if it is not clear what the root word is, and it's worth being less concise to avoid that confusion.
* Single-letter names (including Greek letters) are ok if they are intuitive or make sense in the context of that function. For example, a coding-demo function with an `x` argument is fine, but a function which is written to be used should use descriptive names for its arguments.

### Comments

* While in general you should comment to answer "why," not "what," there may be times when commenting "what" a particular piece or line of code is doing is pedagogically helpful. Since these are tutorials, add comments liberally throughout your code.
* Use `TODO` to mark TODO comments.

### Spacing

For the following guidelines, lines with comments are never considered empty.

* Use spaces around binary operators, *e.g.* `x+y` is bad, `x + y` is good. The main exception is to not leave spaces around `=` for keyword and `NamedTuple` arguments.
* Use a single space after commas and semi-colons.
* Use 4 spaces for indentation, not tabs.
* Never follow an empty line with another empty line. 
* The first and last lines of indented blocks should never be empty.
* Try to limit line length to 80 characters per line. This may not always be possible (particularly in function definitions or with comments), and is a soft guideline.
* If an argument list spans multiple lines, align new lines with the parentheses or brackets that started the argument list.
* Always put `end` on its own line. For example,
  ```julia
  function f(x)
      return x
  end
  ```
is good, while
  ```julia
  function f(x)
      return x end
  ```
is bad.

### Functions

* Write functions, not scripts! If a piece of code is helpful as a function, and might be reused in a real experiment, writing it as such demonstrates good coding practice and helps to separate the logic of code from its application. For example:
    * when importing data, writing a wrapper function may be useful if the data files have consistent formats;
    * write a function to make multiple similar plots.
* Append `!` to the end of functions which modify their arguments. This is a general Julia convention (and a good one!)
* One-line functions should be written with
  ```julia
  function_name(arguments) = ...
  ```
* Multi-line functions should be written using `function-end` blocks:
  ```julia
  function
      ...
  end
  ```
* Always include a `return` statement in multi-line functions, and omit `return` from single-line definitions.
* Feel free to use the "splat" operator `...` in function definitions with arguments of unknown length. We will introduce this operator in the Julia introduction section.

### Other Syntax 

* Do not end a numeric value with a decimal to force a `Float`; for example, use `1.0` instead of `1.`.
* Use `in` instead of `=` when specifying iteration variables.
* Use Unicode characters instead of writing out Greek characters.
* Separate positional arguments from keyword arguments with a semi-colon.
* Don't use parentheses around logical conditions for *e.g.* `if` and `while`.

## Images

* Images which need to be captioned should be imported and included as figures, as images generated by code cannot be currently captioned. All images in `.md` files must be imported, while images in `.ipynb` files can be either. If generating an image with code is part of the learning objective of the notebook chapter, not captioning is okay, but discuss the relevant parts of the figure in-text after the code chunk.

* Place figure captions in the margins using the `figclass: margin-caption` option for the `{figure}` directive. Keep figures in the main text, rather than placing them in the margins.

## Text

### Margin Notes

* Use margin notes instead of sidebars, as sidebars can screw up spacing if they overlap with code blocks.
* Use margin notes as often as you'd like, particularly if you notice a paragraph getting too long through the inclusion of additional context or technical information. Ideally, give them titles to separate them in case they start to run together.