.. _documenting:

Installing documentation dependendencies and building it
---------------------------------------------------------

To build the documentation, extra Python dependencies are needed:

- Sphinx_
- recommonmark_
- Pylint_ (only to update the diagrams)

To install them from ``sbws``::

    pip install .[doc]

To build the documentation as HTML::

    cd docs/ && make html

The generated HTML will be in ``docs/build/``.

To build the manual (``man``) pages::

    cd docs/ && make man

The generated man pages will be in ``docs/man/``.

To build the documentation diagrams::

    cd docs/ && make umlsvg

The generated diagrams will be in ``docs/build/_images/``.

To convert the ``LaTeX`` mathematical formulae to images, extra system dependencies
are needed:

- Core and Extra Tex_ Live packages

They are included in most distributions. In Debian install them running::

    apt install texlive-latex-extra


.. _Sphinx: http://www.sphinx-doc.org
.. _recommonmark: https://recommonmark.readthedocs.io/
.. _Pylint: https://www.pylint.org/
.. _Tex: http://www.tug.org/texlive/acquire.html
