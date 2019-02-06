HMAX documentation
==================

[![Build Status](https://travis-ci.org/EEVCOM-Montpellier/hmax-documentation.svg?branch=master)](https://travis-ci.org/EEVCOM-Montpellier/hmax-documentation)

This documentation is build with [MkDocs](https://www.mkdocs.org), with the theme [ReadTheDocs](https://readthedocs.org) and the Python Markdown plugin [PyMdown Extension](https://facelessuser.github.io/pymdown-extensions/) for TeX support.

Requirement
-----------

In order to contribute, you need to have the following installed:

| Software           | Version        |
|--------------------|----------------|
| Python             | ≥ 2.7 or ≥ 3.3 |
| MkDocs             | ≥ 0.17.4       |
| PyMdown Extensions | ≥ 4.11.        |

1. Install [Python](https://www.python.org) on your computer
2. In a terminal, use `pip` to install MkDocs and PyMdown Extensions:
    ```bash
    pip install mkdocs pymdown-extensions
    ```

Preview
-------

You can serve locally the documentation by running in your terminal:

```bash
mkdocs serve
```

The documentation is automatically deploy when push on the branch master.

Write documentation
-------------------

Pages are written in [Markdown](https://daringfireball.net/projects/markdown/) in the `docs` folder.

In order to add a new page, add a `.md` file in the `docs` folder and add the new entry in the [mkdocs.yml](/mkdocs.yml) file, in the pages section.