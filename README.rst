PyPrinter
=========
Printing everything for everyone!

.. image:: https://img.shields.io/pypi/v/PyPrinter.svg
    :target: https://pypi.python.org/pypi/PyPrinter
    :alt: Latest Version

.. image:: https://travis-ci.org/ofir123/PyPrinter.svg
   :target: https://travis-ci.org/ofir123/PyPrinter
   :alt: Travis CI build status

:Project page: https://github.com/ofir123/PyPrinter

Usage
-----
| The perfect printer for Python 3!
|
| Just create a printer instance, pick your favorite colors and get to work!
| PyPrinter supports all ANSI colors, and crazy encodings!
| It also calculates the console width in order to wrap words properly.
|

.. code:: python

    import pyprinter

    printer = pyprinter.get_printer()

    # Write a simple line.
    printer.write_line(printer.YELLOW + 'Hello World!')

.. image:: docs/images/simple.png

.. code:: python

    # Use indentations.
    with printer.group(indent=4):
        printer.write_line(printer.GREEN + 'Hello Again!')

.. image:: docs/images/indented.png

.. code:: python

    # Write aligned values.
    printer.write_aligned('Awesomeness', 'Check!')

.. image:: docs/images/aligned.png

.. code:: python

    # Write titles.
    printer.write_title('Wow!')

.. image:: docs/images/title.png

.. code:: python

    # Print human-readable file sizes.
    from pyprinter import FileSize

    FileSize(42352352).pretty_print()

.. image:: docs/images/file_size.png

.. code:: python

    # Use tables.
    from pyprinter import Table

    Table('Test', [[1, 2, 3],['a', 'b', 'c']]).pretty_print()

.. image:: docs/images/table.png

.. code:: python

    # Integrate friendly progress bars.
    import time
    from pyprinter import ProgressBar

    progress = ProgressBar(10)
    for i in range(10):
        time.sleep(1)
        progress.eval(i)
    progress.finish()

.. image:: docs/images/progress_bar.png

.. code:: python

    # Use word-wrapping or colors only.
    printer = pyprinter.get_printer(colors=False, width_limit=True)
    printer.write_line(printer.YELLOW + 'Hello World!')

.. image:: docs/images/no_colors.png

Install
^^^^^^^
``pip install pyprinter``