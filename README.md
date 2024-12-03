# rxnutils

[![License](https://img.shields.io/github/license/MolecularAI/reaction_utils)](https://github.com/MolecularAI/reaction_utils/blob/master/LICENSE)
[![Tests](https://github.com/MolecularAI/reaction_utils/workflows/tests/badge.svg)](https://github.com/MolecularAI/reaction_utils/actions?workflow=tests)
[![codecov](https://codecov.io/gh/MolecularAI/reaction_utils/branch/main/graph/badge.svg?token=MQE7BDM1N8)](https://codecov.io/gh/MolecularAI/reaction_utils)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/python/black)

Utilities to work with datasets of chemical reactions, reaction templates and template extraction

## Prerequisites

Before you begin, ensure you have met the following requirements:

* Linux OS (or in principle Windows or macOS)

* You have installed [anaconda](https://www.anaconda.com/) or [miniconda](https://docs.conda.io/en/latest/miniconda.html) with python 3.8

The tool has been developed and fully tested on a Linux platform, but it is only occassionally tested on Windows and macOS.
If you find an issue on a Windows or macOS platform, we might be able to fix, but we might just disable that feature on those platforms.


## Installation

### For users

Setup your python environment and then run

    pip install reaction-utils

Consult the documentation for further information.

For some tasks such as atom-mapping with `rxnmapper` you need to setup additional environment and packages, see [here](https://molecularai.github.io/reaction_utils/uspto.html)

### For developers

First clone the repository using Git.

Then execute the following commands in the root of the repository

    conda env create -f env-dev.yml
    conda activate rxn-env
    poetry install --with dev

the `rxnutils` package is now installed in editable mode.

Lastly, make sure to install pre-commits that are run on every commit

    pre-commit install

## Usage

The package is divided into (currently) three sub-packages:

* `chem` - chemistry routines like template extraction or reaction cleaning
* `data` - routines for manipulating various reaction data sources
* `pipeline` - routines for building and executing simple pipelines for modifying and analyzing reactions
* `routes` - routines for handling synthesis routes

The full auto-generated API document is available [here](https://molecularai.github.io/reaction_utils/), and the documentation also provides a few examples on common tasks.

## Development

### Testing

Tests uses the ``pytest`` package, and is installed by `poetry`

Run the tests using:

    pytest -v

The full command with all flags for CI is available through an `invoke` command

    invoke run-tests

 ### Documentation generation

The documentation is generated by Sphinx from hand-written tutorials and docstrings

The HTML documentation can be generated by

    invoke build-docs

### Linting

Linting is done preferably with `pylint`.

    invoke run-linting

Currently we do not use `mypy` to check type annotations, but this will be switched on in the future.

## Contributing

We welcome contributions, in the form of issues or pull requests.

If you have a question or want to report a bug, please submit an issue.

To contribute with code to the project, follow these steps:

1. Fork this repository.
2. Create a branch: `git checkout -b <branch_name>`.
3. Make your changes and commit them: `git commit -m '<commit_message>'`
4. Push to the remote branch: `git push`
5. Create the pull request.

Please use ``black`` package for formatting, and follow ``pep8`` style guide.


## Contributors

* [@ckannas](https://github.com/ckannas)
* [@SGenheden](https://www.github.com/SGenheden)
* [@anniewesterlund](https://www.github.com/anniewesterlund)
* [@Lakshidaa](https://github.com/Lakshidaa)
* [@CBA087](https://www.github.com/CBA087)
* [@EBjerrum](https://www.github.com/EBjerrum)
* [@A-Thakkar](https://www.github.com/A-Thakkar)

The contributors have limited time for support questions, but please do not hesitate to submit an issue (see above).

## License

The software is licensed under the Apache 2.0 license (see LICENSE file), and is free and provided as-is.

## References

1. Thakkar A, Kogej T, Reymond J-L, et al (2019) Datasets and their influence on the development of computer assisted synthesis planning tools in the pharmaceutical domain. Chem Sci. https://doi.org/10.1039/C9SC04944D

2. Kannas C, Thakkar A, Bjerrum E, Genheden S (2022) rxnutils – A Cheminformatics Python Library for Manipulating Chemical Reaction Data. ChemRxiv. https://doi.org/10.26434/chemrxiv-2022-wt440-v2
