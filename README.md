[![PyPI](https://img.shields.io/pypi/v/pytoml.svg)](https://pypi.python.org/pypi/pytoml)
[![Build Status](https://travis-ci.org/avakar/pytoml.svg?branch=master)](https://travis-ci.org/avakar/pytoml)

# pytoml

This project aims at being a specs-conforming and strict parser and writer for [TOML][1] files.
The library currently supports [version 0.4.0][2] of the specs and runs with Python 2.6+ and 3.3+.

Install:

    pip install pytoml

The interface is the same as for the standard `json` package.

    >>> import pytoml as toml
    >>> toml.loads('a = 1')
    {'a': 1}
    >>> with open('file.toml', 'rb') as fin:
    ...     obj = toml.load(fin)
    >>> obj
    {'a': 1}

The `loads` function accepts either a bytes object
(that gets decoded as UTF-8 with no BOM allowed),
or a unicode object.

Use `dump` or `dumps` to serialize a dict into TOML.

    >>> print toml.dumps(obj)
    a = 1
    
## tests

To run the tests update the `toml-test` submodule:

    $ git submodule update --init --recursive
    
Then run the tests:

    $ python test/test.py

  [1]: https://github.com/toml-lang/toml
  [2]: https://github.com/toml-lang/toml/blob/master/versions/en/toml-v0.4.0.md
