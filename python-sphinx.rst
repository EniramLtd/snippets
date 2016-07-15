==============================
 Tips for working with Sphinx
==============================

Compiling a single restructuredtext ``.rst`` file
=================================================

If you have an ``.rst`` file which uses Sphinx-specific directives,
you won't get clean HTML by doing a ``rst2html my.rst >my.html``
using docutils.

However, you don't need to set up a complete Sphinx documentation project
and configuration. Instead, you can build one file like this:

.. code-block:: bash

   $ sphinx-build -C -D master_doc=my . /tmp/html
   
As a result, you'll get ``/tmp/html/my.html`` cleanly rendered into HTML.
You won't see any custom theming of course, but the result is way better
than with docutils.
