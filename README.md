HMAX documentation
==================

This documentation is build with [MkDocs](https://www.mkdocs.org), with the theme [ReadTheDocs](https://readthedocs.org) and the Python Markdown plugin [PyMdown Extension](https://facelessuser.github.io/pymdown-extensions/) for TeX support.

Requirement
-----------

In order to contribute, you need to have the following installed:

| Software           | Version        |
|--------------------|----------------|
| Python             | ≥ 2.7 or ≥ 3.3 |
| MkDocs             | ≥ 0.17.4       |
| PyMdown Extensions | ≥ 4.11.        |

[Pipenv](https://docs.pipenv.org/) is recommanded but not required.

1. Install [Python](https://www.python.org) on your computer
2. In a terminal, use `pip` to install MkDocs:
    ```bash
    pip install mkdocs
    # Or
    pipenv install mkdocs
    ```
3. In the same way, install PyMdown Extensions
    ```bash
    pip install pymdown-extensions
    # Or
    pipenv install pymdown-extensions
    ```

Preview
-------

You can serve locally the documentation by running in your terminal:

```bash
mkdocs serve
```

Deploy on Github:
```
mkdocs gh-deploy
```
