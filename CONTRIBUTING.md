

For developers
==============

Please put ALL import statements at the top of the `*.py` file (potentially underneath docstrings, of course).
The only exception is if a package is not listed in `requirements.txt`,then a "function-only" import may be allowed.
If this doesn't make sense to you, just put the import at the top of the file.

Git branching
-------------

We use the [git-flow](http://nvie
.com/posts/a-successful-git-branching-model/) model. So if you have a feature
(called `myfeature` as an example) you want to add, please add it off of the
`dev` branch, as so:

    git checkout -b myfeature dev

When you're done working on your feature, merge it back to `dev` via:

    $ git checkout develop
    Switched to branch 'dev'
    $ git merge --no-ff myfeature
    Updating ea1b82a..05e9557
    (Summary of changes)
    $ git branch -d myfeature
    Deleted branch myfeature (was 05e9557).
    $ git push origin dev

The reason for the `--no-ff` flag is because it makes it easy to reverse
changes in case there was a simple mistake.

Naming conventions
------------------

When in doubt, please defer to [Python Enhancement Proposal 8 (aka [PEP8]
(http://legacy.python.org/dev/peps/pep-0008/)) and the [Zen of Python]
(http://legacy.python.org/dev/peps/pep-0020/)

* Classes are `CamelCase`, e.g.:  `BaseData` and `PCAViz`
* Functions are `lower_case_with_underscores`, e.g. `go_enrichment` and
`binify`
* Explicit is better than implicit


Docstring conventions
---------------------

We will attempt to stick to the [`numpy` docstring specification](https://github.com/numpy/numpy/blob/master/doc/HOWTO_DOCUMENT.rst.txt) (aka
"`numpydoc`").

To make this easier, I use ["Live Templates" in PyCharm]
(http://peter-hoffmann.com/2010/python-live-templates-for-pycharm.html),
check out the instructions [here](https://github
.com/YeoLab/PyCharm-Python-Templates) for how to install and use them.

Testing
=======

In the source directory (wherever you cloned `flotilla` to that has this README.md file), do:

    make test

This will run the unit test suite.

Coverage
--------

To check coverage of the test suite, run

    make coverage

in the source directory.


PEP8 Conventions
----------------

To run `pep8` and `pyflakes` over the code, make sure you have [this fork]
(pip install https://github.com/dcramer/pyflakes/tarball/master) of
`pyflakes` installed (e.g. via `pip install https://github
.com/dcramer/pyflakes/tarball/master`) and run:

    make lint



What flotilla is not
====================

Flotilla does not claim to solve the data management problem of biology,
i.e. how you store all the data associated with a particular study that was
investigating a specific biological question. Flotilla only makes it easy to
integrate all those data parts together.