# Style Guide

The following guidelines are used to ensure consistency across chapters and code chunks. 

## Julia Code

These guidelines build off the [YAS Style Guide](https://github.com/jrevels/YASGuide) and the [Julia Style Guide](https://docs.julialang.org/en/v1/manual/style-guide/). There may be some redunancies between these and what are listed here, which are intended for simplicity's sake as a convenient reference.

### Basic Principles

Err on the side of making code clear. There is a good chance that these materials may be a readers' first introduction to Julia, so using more advanced or niche methods or functionality would be too complicated. For example, focus on `Plots.jl` for plotting and use `Turing.jl` for MCMC, not more niche packages. 

In that spirit, try to abide by the following principles:

1. Assume this may be a **first** exposure to programming.
2. Make code as compact as possible while maintaining interpretability. Write functions when code will be reused, and make it explicit that this is the process. For example, if reading in multiple data files with similar structure, show and explain the initial sequence of commands on the first file, then show how to translate those lines into a function which can be used on the remaining files. This mimics the exploratory thought process.
3. Keep code structure and notation **as close to the relevant math as possible**. For example, when implementing a GEV function, use `ξ` instead of `shape` as a variable name. Try to keep the code steps as close to the written-out math or algorithmic steps as possible, even if it's less optimized.
4. Use well-maintained external libraries instead of implementing your own solutions.

### Naming Guidelines

* Use Unicode for math, and ASCII for control flow. In other words, when checking for set membership, use `∈` and `∉`, but when iterating over a vector, use `in` rather than `∈`. 
* Use lowercase `snake_case` for function and variable names. Small words can be smashed together (for consistency with Julia base functions like `isequal` or `haskey`).
* Use `CamelCase` for type and struct names (which shouldn't be needed often).
* Use uppercase `SNAKE_CASE` for constants.
* While conciseness is valued, make function and variable names descriptive, rather than abbreviations or single letters. Abbreviations can be bad if it is not clear what the root word is, and it's worth being less concise to avoid that confusion.
* Single-letter names (including Greek letters) are ok if they are intuitive or make sense in the context of that function. For example, a coding-demo function with an `x` argument is fine, but a function which is written to be used should use descriptive names for its arguments.

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

* Ideally, import all needed packages at the beginning of a notebook, for example:
  ```julia
  using Distributions, LinearAlgebra
  ```
* Multiple imported packages on one `using` line is ok.
* Even though it's redundant, you can import packages with `using` again later in the document when the functions from that package are used if it helps with the flow (for example, if introducing a particular piece of functionality in the narrative).
* Only import `Plots.jl` when needed to improve speed when code is copied and pasted

### Comments

* Avoid redundant comments and comment headers.
* Put comments on their own line to reduce line lengths. Comments should be in all lower-case.
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
* Do not align `=` for multiple variables, *e.g.*:
  ```julia
  # this is bad
  x     =   1.0
  y1    =   2.0

  # instead do this
  x = 1.0
  y1 = 2.0
  ```


### Functions

* If a piece of code is helpful as a function, and might be reused in a real experiment, writing it as such demonstrates good coding practice and helps to separate the logic of code from its application. For example:
    * when importing data, writing a wrapper function may be useful if the data files have consistent formats;
    * write a function to make multiple similar plots.
Begin by showing how the code works in one example, and then how and why to consolidate it into a single function.
* Functions which modify their arguments in-place should be avoided when possible. When not possible, append `!` to the end of functions which modify their arguments. This is a general Julia convention (and a good one!)
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
* When writing a function with multiple return values, return a named tuple, which makes getting specific outputs more readable
  ```julia
    function f(x, y, z)
       return (sum = x + y,  z = z)
    end

    # both of these let us access z
    @unpack z = f(x, y, z)
    z = f(x, y, z).z
  ```

### Other Syntax 

* Use semi-colons `;` at the end of lines to suppress output that is not valuable or necessary.
* Do not specify variable scopes explicitly, *i.e.* you should never use the `local` and `global` keywords.
* Do not end a numeric value with a decimal to force a `Float`; for example, use `1.0` instead of `1.`.
* Use `in` instead of `=` when specifying iteration variables.
* Use Unicode characters instead of writing out Greek characters.
* Separate positional arguments from keyword arguments with a semi-colon.
* Don't use parentheses around logical conditions for *e.g.* `if` and `while`.
* Use `LaTeXStrings.jl` for all LaTeX literals.
* Use named tuples or `@with_kw` (from `Parameters.jl`) to collect parameters, *e.g.* these are both good
  ```julia
  # using a named tuple
  params = (a = 1.0, b = 0.75)

  # using @with_kw to set defaults
  params = @with_kw (a = 1.0, b = 0.75)
  default_params = params()  # => (a = 1.0, b = 0.75)
  changed_params = params(a = 10.0)  # => (a = 10.0, b = 0.75)
  ```
* Preallocate arrays using `similar` or `zeros` instead of using `undef`.
* Iterate directly over arrays or broadcast rather than accessing by index.
* If accessing indices is needed, use `eachindex` instead of iterating over vector sizes:
  ```julia
  x = [1.0, 2.5, 10.0]
  y = similar(x)

  # do this
  for i in eachindex(x)
      y[i] = 2 * x[i]
  end

  # not this
  for i in 1:length(x)
      y[i] = 2 * x[i]
  end

  # but this is even better
  y = 2 .* x
  ```
  * Always seed random number generation using `Random.seed!(...)` for reproducibility.
  * Avoid using comprehensions if broadcasting syntax is clearer (which it usually will be).

## Images

* Images which need to be captioned should be imported and included as figures, as images generated by code cannot be currently captioned. All images in `.md` files must be imported, while images in `.ipynb` files can be either. If generating an image with code is part of the learning objective of the notebook chapter, not captioning is okay, but discuss the relevant parts of the figure in-text after the code chunk.

* Place figure captions in the margins using the `figclass: margin-caption` option for the `{figure}` directive. Keep figures in the main text, rather than placing them in the margins.

## Text

### Admonitions

* Use admonitions as you see fit. There are plenty of styles that work by default, including notes, warnings, and so on.

### Margin Notes

* Use margin notes instead of sidebars, as sidebars can screw up spacing if they overlap with code blocks.
* Use margin notes as often as you'd like, particularly if you notice a paragraph getting too long through the inclusion of additional context or technical information. Give them titles to separate them in case they start to run together.