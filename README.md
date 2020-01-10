# Atom setup notes
[Atom](https://atom.io/) (developed by GitHub) is a great solution for handling program languages like LaTeX, Markdown, Python, and R in a single text editor with a smooth user interface.

However, it requires quite some setup (see below), fine-tuning, trouble-shooting and practice before you are able to enjoy its full functionality. Thus, before comitting make sure that Atom is the right choice for your needs by reading a few comparisons with other alternatives, e.g.
1.   [Sublime Text](https://www.sublimetext.com/) is the oldest and most common of the text editors but has poor word-suggestions and updates are infrequent due to not being open source
2.   [Visual Studio Code](https://code.visualstudio.com) by Microsoft. One of many pros is that it allows you to edit Jupyter Notebooks outside of your browser. Extensions like [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) are found in the [Marketplace](https://marketplace.visualstudio.com/).

Compared to the two above, Atom can have slower performance but offers great functionality with GitHub when collaborating on a project.

## General installation of Atom:
-   Follow the installation guide <https://flight-manual.atom.io/getting-started/sections/installing-atom/>
-   To install Atom packages either
    1. Press `ctrl-,` in Atom and search for packages under 'install'
    2. Or open the terminal (e.g. Command Prompt in Windows) and run a command like `apm install file-icons`. The first time run `apm` to check apm is installed correctly
-   The choice of UI Theme and Syntax Theme is highly subjective. I find [seti-ui](https://atom.io/themes/seti-ui) and [seti-syntax](https://atom.io/themes/seti-syntax) very pleasant

## LaTeX
-   [TeXLive](https://www.tug.org/texlive/acquire-netinstall.html) works with atom-latex, MiKTeX does not
-   Always install the following Atom packages, e.g. by running the command in terminal:
    ```
    apm install atom-latex language-latex pdf-view
    ```
-   Check the [optional packages listed by Benjamin Gray](https://gist.github.com/Aerijo/5b9522530715e5be6e89fc012e9a72a8) or others (ignore the Linter-packages and see 'Ide' below instead)

## Markdown
-   Install the two packages `apm install markdown-writer language-markdown`
-   `markdown-preview` is pre-installed. Press `ctrl-shift-m` to toogle on/off
-   If you're new to Markdown language, check this [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

## Python
-   Python is installed by installing [Anaconda](https://www.anaconda.com/distribution/#download-section) (choose 'Add Anaconda to my PATH environment variable'), and running it through the [Hydrogen](https://atom.io/packages/hydrogen) package in Atom by marking a snippet of code and pressing `ctrl-enter`
    -   In the terminal run `apm install hydrogen hydrogen-launcher script`
-   All you need is the [Script](https://atom.io/packages/script) package, but consider optional packages from the [list at pythonmania](https://www.pythonmania.net/en/2017/02/27/recommended-atom-packages) (ignore `linter-pydocstyle` & `flake8` but see IDE below instead)
-   Install the [Python Language Server](https://github.com/palantir/python-language-server#python-language-server) (pyls) by running `python -m pip install python-language-server[all]` in the terminal (alternatively, try `python -m pip install 'python-language-server[all]'`. A prerequisite is C++ 14.0 or newer (as the [MSVC standalone compiler](https://wiki.python.org/moin/WindowsCompilers) or included in [Visual Studio](https://visualstudio.microsoft.com/vs/)).
-   Update Python once in a while by running `conda update --all` and `pip_upgrade_outdated` (install [this tool](https://pypi.org/project/pip-upgrade-outdated/) first: `pip install pip_upgrade_outdated`)

## R
-   Install [R](https://cran.r-project.org/), [IRkernel](https://irkernel.github.io/installation/#binary-panel), (and [Rstudio](https://www.rstudio.com/products/rstudio/download/))
-   You can run R in atom through Hydrogen just as descriped for Python above.
-   Setup according to the [guide by Jeff Stafford](https://jstaf.github.io/2018/03/25/atom-ide.html) or similar
-   OBS: The `atom-ide-ui` terminal replaces Linter (i.e. see the Ide not the Linter part below)

## Spell-check
Pre-installed [spell-check](https://atom.io/packages/spell-check) package
-   Add `text.tex.latex, text.tex.latex.beamer, text.md` to "Grammars"
-   Add the following line to "Excluded Scopes":
    - `markup.underline.link.gfm, support.function.latex, meta.preamble.latex, support.type.function.latex, comment.line.percentage.tex, storage.type.function.latex, string.other.math.tex, string.other.math.block.environment.latex, variable.parameter.function.latex, constant.other.reference.latex, meta.reference.latex`
    - To find another scope where the cursor currently is: Open the Command Palette `ctrl-shift-p`, and search for the `Editor: Log Cursor Scope` command.
-   Windows Language (equivalently for Linux):
    - For now you need to set the system language to `English (United States)` for spell-check to work.
    - When a certain bug fix is approved you'll only need to make sure that `English (United States)` is installed in Windows language settings.
    -   Then you will also be able to add `es-ES`, `da-DK` or others after `en-US` under 'Locales' (check the 'Use Locales' box)
-   Place the cursor at a highlighted word and press `ctrl-shift-:` to run spell-check

## IDE
Used for language support instead of Linter due to better functionality with Python and R. Install those of the following Atom packages that you need:
-   [atom-ide-ui](https://atom.io/packages/atom-ide-ui) is the backbone for using any of the packages below.
    - I choose to disable 'Console', 'Debugger', 'atom-ide-refactor', and 'Terminal' under 'Settings' > 'Enabled Features'.
-   [ide-python](https://atom.io/packages/ide-python) for Python language support.
    - I add the [error codes](http://pycodestyle.pycqa.org/en/latest/intro.html#error-codes) `E2, E3, E401, E501, E701, E704, W2, W3, W5` under 'Settings' > 'PyCodeStyle' > 'Ignore'.
    - Automatically changes tab-length to 4 spaces for all .py files (overwrites global Atom settings which you can still set to e.g. 2 for LaTeX and other languages.)
-   [atom-ide-debugger-python](https://atom.io/packages/atom-ide-debugger-python) is an optional debugger for Python code.
-   [ide-r](https://atom.io/packages/ide-r) for R language support.
-   [platformio-ide-terminal](https://atom.io/packages/platformio-ide-terminal) adds a terminal in the bottom of your Atom editor.
```
apm install atom-ide-ui ide-python atom-ide-debugger-python ide-r platformio-ide-terminal
```

## Linter
Common package for language support but suboptimal for Python and R, thus, I recommend using IDE instead
-   However, if you prefer [Linter](https://atom.io/packages/linter) (e.g. if you only use Atom for LaTeX and Markdown) you can install the package `linter` and the relevant [language specific linter packages](https://atomlinter.github.io/), e.g.
    - `linter-markdown`
    - `linter-ui-default` & `linter-chktex` for LaTeX
    - `linter-pydocstyle` & `flake8` for Python (Ignore Error Codes: D100, E266, E305, W391 in flake8)
