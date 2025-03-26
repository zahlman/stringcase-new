stringcase
==========

Convert string cases between camel case, pascal case, snake case etc...

|pypi_version_badge|

About this fork
---------------

This is a manually created fork of the original ``stringcase`` by `Taka Okunishi <http://okunishitaka.com>`__ (`@okunishinishi <http://github.com/okunishinishi>`__), intended to:

* Fix failing tests
* Modernize and simplify the packaging setup
* Distribute a wheel on PyPI

Commits and merges from the original repository that were made after the last release have been moved onto a separate branch, and will be cherry-picked in as appropriate - where they actually fix bugs or move the project in the direction I intend.

Version numbers continue where the original left off, so that maintainers only need to change ``stringcase`` to ``stringcase-new`` in their ``pyproject.toml``, ``requirements.txt`` etc. files.

The code continues to be available under an MIT license.

No meaningful new functionality is introduced, and the bugfixes are straightforward, so I assert no additional copyright.

This fork was prompted by `recent ecosystem breakage resulting from the breaking change in Setuptools 78 <https://github.com/pypa/setuptools/issues/4910>`__, which affected many users of this previously source-only project. Providing a wheel also `greatly speeds up installation <https://pradyunsg.me/blog/2022/12/31/wheels-are-faster-pure-python/>`__.

-- Your humble maintainer, Karl Knechtel (@zahlman).

Usage
-----

.. code:: python

    import stringcase
    stringcase.camelcase('foo_bar_baz') # => "fooBarBaz"
    stringcase.camelcase('FooBarBaz') # => "fooBarBaz"
    stringcase.capitalcase('foo_bar_baz') # => "Foo_bar_baz"
    stringcase.capitalcase('FooBarBaz') # => "FooBarBaz"
    stringcase.constcase('foo_bar_baz') # => "FOO_BAR_BAZ"
    stringcase.constcase('FooBarBaz') # => "_FOO_BAR_BAZ"
    stringcase.lowercase('foo_bar_baz') # => "foo_bar_baz"
    stringcase.lowercase('FooBarBaz') # => "foobarbaz"
    stringcase.pascalcase('foo_bar_baz') # => "FooBarBaz"
    stringcase.pascalcase('FooBarBaz') # => "FooBarBaz"
    stringcase.pathcase('foo_bar_baz') # => "foo/bar/baz"
    stringcase.pathcase('FooBarBaz') # => "/foo/bar/baz"
    stringcase.sentencecase('foo_bar_baz') # => "Foo bar baz"
    stringcase.sentencecase('FooBarBaz') # => "Foo bar baz"
    stringcase.snakecase('foo_bar_baz') # => "foo_bar_baz"
    stringcase.snakecase('FooBarBaz') # => "_foo_bar_baz"
    stringcase.spinalcase('foo_bar_baz') # => "foo-bar-baz"
    stringcase.spinalcase('FooBarBaz') # => "-foo-bar-baz"
    stringcase.titlecase('foo_bar_baz') # => "Foo Bar Baz"
    stringcase.titlecase('FooBarBaz') # => " Foo Bar Baz"
    stringcase.trimcase('foo_bar_baz') # => "foo_bar_baz"
    stringcase.trimcase('FooBarBaz') # => "FooBarBaz"
    stringcase.uppercase('foo_bar_baz') # => "FOO_BAR_BAZ"
    stringcase.uppercase('FooBarBaz') # => "FOOBARBAZ"
    stringcase.alphanumcase('_Foo., Bar') # =>'FooBar'
    stringcase.alphanumcase('Foo_123 Bar!') # =>'Foo123Bar'


Install
-------

Because I do not own the original PyPI project, a new PyPI name is required:

::

    $ pip install stringcase-new

License
-------

This software is released under the `MIT License <https://github.com/zahlman/stringcase-new/blob/master/LICENSE>`__.


.. |pypi_version_badge| image:: https://img.shields.io/pypi/v/stringcase-new.svg
   :target: https://pypi.python.org/pypi/stringcase-new

