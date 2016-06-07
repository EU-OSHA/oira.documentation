API Documentation
=================

This section contains a low level documentation of the code - modules, classes, methods and functions.

.. todo::

    Provide a docstring according to convention for every listed function in the api section.
    

Conventions
-----------

.. note::

    These conventions are derived from `an_example_pypi_project <http://packages.python.org/an_example_pypi_project/>`_.

Every code file should have inline documentation that can be parsed like this:

.. code::

    """
    .. module:: useful_1
       :platform: Unix
       :synopsis: A useful module indeed.

    .. moduleauthor:: Andrew Carter <andrew@invalid.com>


    """

    def public_fn_with_sphinxy_docstring(name, state=None):
        """This function does something.

        .. note::

           An example of intersphinx is this: you **cannot** use :mod:`pickle` on this class.

        A really great idea.  A way you might use me is

        >>> print public_fn_with_googley_docstring(name='foo', state=None)
        0

        BTW, this always returns 0.  **NEVER** use with :class:`MyPublicClass`.

        :param name: The name to use.
        :type name: str.
        :param state: Current state to be in.
        :type state: bool.
        :returns:  int -- the return code::

              0 -- Success!
              1 -- No good.
              2 -- Try again.

        :raises: AttributeError, KeyError

        """
        return 0


