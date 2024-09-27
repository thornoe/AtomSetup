# Atom alternatives
[Atom](https://atom.io/) (sunset by GitHub in 2022) was a great solution for handling program languages like LaTeX, Markdown, Python, and R in a single text editor with a smooth user interface.

Read a few comparisons of the currently popular editors to find the right choice for your needs, e.g.:

1.   [Visual Studio Code](https://code.visualstudio.com) by Microsoft is the trending choice and what I would recommend for most users. Its quite plug-and-go as its main edge over other text editors is the range of core features it has out-of-the-box while still offering extensions like [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) in its [Marketplace](https://marketplace.visualstudio.com/).
2.   [Sublime Text](https://sublimetext.com) is the older and therefore very common text editor. However, it is slower than VS Code, has poor word-suggestions and updates are infrequent due to not being open source.

## LaTeX
- I prefer [MiKTeX](https://miktex.org/download) over [TeX Live](https://tug.org/texlive/acquire-netinstall.html) for writing LaTeX with VS Code. Check out this [setup guide](https://geekering.com/programming-languages/filipesalgueiro/how-to-write-latex-documents-using-visual-studio-code) by Filipe Salgueiro. 

## Python
-   Python can be installed as a part of installing [Anaconda](https://anaconda.com/download) or [Miniconda](https://docs.anaconda.com/miniconda) (choose 'Add Anaconda to my PATH environment variable')
    -   If you don't need [Jupyter](https://docs.anaconda.com/ae-notebooks/user-guide/basic-tasks/apps/jupyter), you can skip Anaconda/Miniconda and just install [Python](https://python.org/downloads) directly. As a side note: Though you can edit Jupyter Notebooks within VS Code itself, it's arguably still too buggy as compared to using your browser.
    -   If you need to uninstall Anaconda, read [the documentation](https://docs.anaconda.com/anaconda/install/uninstall) first. Re-installing can overcome accumulated incompatibility issues that prevent updating to newer versions, but older code might break.
-   Update to the latest compatible versions of [Anaconda](https://docs.anaconda.com/free/anaconda/reference/release-notes), [Conda](https://docs.conda.io/projects/conda/en/stable/release-notes.html), [Python](https://python.org/downloads/windows), and related packages as often as possible by running `conda update anaconda`, `conda update conda`, `conda update --all` and `pip_upgrade_outdated` (install [this tool](https://pypi.org/project/pip-upgrade-outdated) first: `pip install pip_upgrade_outdated`).

## R
-   Install [R](https://cran.r-project.org).
-   Optionally, install [IRkernel](https://irkernel.github.io/installation) (R kernel for Jupyter) and/or [Rstudio](https://rstudio.com/products/rstudio/download) (standalone R editor and package manager).
