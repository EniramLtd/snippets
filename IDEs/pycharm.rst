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
