Write Your Docs
---------------

You have two options for formatting your documentation:

* :ref:`in-rst`
* :ref:`in-markdown`

.. _in-rst:

In reStructuredText
~~~~~~~~~~~~~~~~~~~

There is `a screencast`_ that will help you get started if you prefer.

Sphinx_ is a tool that makes it easy to create beautiful documentation.
Assuming you have Python_ already, `install Sphinx`_::

    $ pip install sphinx sphinx-autobuild

Create a directory inside your project to hold your docs::

    $ cd /path/to/project
    $ mkdir docs

Run ``sphinx-quickstart`` in there::

    $ cd docs
    $ sphinx-quickstart

.. note:: You can use ``sphinx-autobuild`` to auto-reload your docs. Run ``sphinx-autobuild . _build_html`` instead.

Once you have Sphinx documentation in a public repository, you can start using Read the Docs.

.. _in-markdown:

In Markdown
~~~~~~~~~~~

You can use Markdown and reStructuredText in the same Sphinx project.
We support this natively on Read the Docs, and you can do it locally::

    $ pip install recommonmark

Then in your ``conf.py``:
