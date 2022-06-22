# How to Contribute

The book is published using [JupyterBook](https://jupyterbook.org/en/stable/intro.html). 

## Adding New Content

* You can fork the repository before adding new content, and submit a pull request when you want to merge new content.
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
* Notebooks should use the `julia-1.7` kernel.

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
