Tips for PyCharm
================

"Unresolved reference" for packages in virtualenv
-------------------------------------------------

If the editor highlights and marks as "unresolved reference"
those packages which have been installed in the project's virtualenv,
you can try this (tested in PyCharm 2016.1.4):

- open Settings / Project / Project Interpreter
- open "More..." settings (in the cog wheel icon menu)
- select your virtualenv from the list
- open the Edit dialog (pencil icon)
- make sure "Associate this virtual environment with current project" is checked and click OK
- choose File / "Invalidate Caches / Restart"

**However,** in at least one project with PyCharm 2016.1.4, the original problem reappears
after indexing has completed after cache invalidation.


Setting the log level for unit test when running pytest
-------------------------------------------------------

Normally PyCharm only sees log output at the default log level.
If you want to enable e.g. DEBUG level logging to see more details,
you can use the pytest-logging_ package::

  $ pip install pytest-logging

In your Run/Debug Confgurations set Additional Arguments to::

  -vvvv -s

Run your tests and you should see DEBUG level log output.


If you also want to customize the log format,
you'll need the development version of pytest-catchlog_::

  $ pip install -e git+https://github.com/eisensheng/pytest-catchlog.git#egg=pytest-catchlog

The command line options to set in the Additional Arguments field
of the Run/Debug Configurations dialog are now e.g. as follows::

  --log-format="%(message)s" --log-cli-level=DEBUG -s


.. _pytest-logging: https://pypi.python.org/pypi/pytest-logging
.. _pytest-catchlog: https://github.com/eisensheng/pytest-catchlog
