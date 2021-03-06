Final Degree Project: *DeepGProp*
=================================

   Neural Networks optimization with Genetic Algorithms

-  **Author: Luis Liñán Villafranca**
-  **Mentor: Juan Julián Merelo Guervós**

Index
-----

-  `Index <#index>`__
-  `Installation <#installation>`__

   -  `Virtual environment creation <#virtual-environment-creation>`__
   -  `Installing the DeepGProp CLI <#installing-the-deepgprop-cli>`__
   -  `Extra modules <#extra-modules>`__

-  `Tests and formatting <#tests-and-formatting>`__
-  `Frameworks <#frameworks>`__
-  `Utilidades <#utilidades>`__
-  `Licencia <#licencia>`__

--------------

Installation
------------

The first prerequisite is to have `Python
3.6, 3.7 or 3.8 <https://www.python.org/downloads/>`__ and
`pip <https://pypi.org/project/pip/>`__ installed on the system. It is
recommended to create a virtual environment to isolate the used package
versions. For more information about
`pip <https://pypi.org/project/pip/>`__ and
`venv <https://docs.python.org/3/library/venv.html>`__ check the
`official
tutorial <https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/>`__.

Virtual environment creation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

First, you need to install a version of python that’s been compiled with
``-fPIC``. ``pyenv`` versions by default are not, so you will need to
issue something like this:

.. code:: shell

   env PYTHON_CONFIGURE_OPTS="--enable-shared" pyenv install 3.7.9

We can then use a core module to create the virtual environment, it’s
been working since version 3.3

.. code:: shell

   python -m venv .venv

..

Please make sure when you do this that all ``__pycache__``
directories have been deleted; otherwise, it might fail in some
unexpected place.

This will create a virtual environment in the ``.venv`` directory. Once
that’s been done, we need to activate it; use one of the following
commands (depending on the interpreter) (obtained from the official
`venv <https://docs.python.org/3/library/venv.html>`__ documentation):

======== =============== =======================================
Platform Shell           Command to activate virtual environment
======== =============== =======================================
POSIX    bash/zsh        ``$ source <venv>/bin/activate``
         fish            ``$ . <venv>/bin/activate.fish``
         csh/tcsh        ``$ source <venv>/bin/activate.csh``
         PowerShell Core ``$ <venv>/bin/Activate.ps1``
Windows  cmd.exe         ``C:\> <venv>\Scripts\activate.bat``
         PowerShell      ``PS C:\> <venv>\Scripts\Activate.ps1``
======== =============== =======================================

Table 1.1: *Activating the virtual environment.*

You won’t need to create the virtual environment in the case you’re
using global installation of modules via version managers such as
``pyenv``.

Installing the DeepGProp CLI
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To run DeepGProp first we need to install its cli. You can install it
with ``pip``:

.. code:: shell

   pip install -U DeepGProp

Or downloading the repository with:

.. code:: shell

   pip install .

On the other hand, if we want the code to be updated as we change it, we
will need to install DeepGProp in editable mode. To do this, we need to
add the option ``-e/--editable`` to the installation command:

.. code:: shell

   pip install -e .

After installing it, we will be able to use it through the command
``dgp``. You can run ``dgp --help`` to list the available options.

Extra modules
~~~~~~~~~~~~~

I’ve divided all the used packages in different groups to avoid
installing undesirable ones for specific use of the repository:

+---------+-------------------------+--------------------------------------------------------------------------------------------------+
| Purpose | File path               | Description                                                                                      |
+=========+=========================+==================================================================================================+
| Test    | requirements/tests.txt  | Necessary packages for tests. `Nox`_ installs them automaticly when running the tests.           |
+---------+-------------------------+--------------------------------------------------------------------------------------------------+
| Lint    | requirements/lint.txt   | Necessary packages for linting. `Nox`_ installs them automaticly when linting the code.          |
+---------+-------------------------+--------------------------------------------------------------------------------------------------+
| Format  | requirements/format.txt | Necessary packages for formatting. `Nox`_ installs them automaticly when running format command. |
+---------+-------------------------+--------------------------------------------------------------------------------------------------+
| Dev     | requirements/dev.txt    | All above packages.                                                                              |
+---------+-------------------------+--------------------------------------------------------------------------------------------------+

.. _Nox: https://nox.thea.codes/en/stable

To install any of these packages you can run:

.. code:: shell

   pip install -r <file path>

If you are not using any virtual environment, make sure you install
these packages so that they are available in the required Python
version.

Tests and formatting
--------------------

.. note:: To be able to run the DeepGProp tests, you will need to
   install it in editable mode. checkout in `Installing the DeepGProp
   CLI <#installing-the-deepgprop-cli>`__ section how to do it.

First, we need to install the
`Nox <https://nox.thea.codes/en/stable/>`__ tool:

.. code:: shell

   pip install -U nox

To run all the tests:

.. code:: shell

   nox -k test

To run the linters:

.. code:: shell

   nox -k lint

You can check all the possible sessions with the following command:

.. code:: shell

   nox -l

Frameworks
----------

-  `Keras <https://keras.io/>`__ - base library to create and run the
   neural networks.

-  `DEAP <https://deap.readthedocs.io/en/master/>`__ - genetic
   algorithms library used to optimize the models hyper parametters.

Utilidades
----------

-  Automation:

   -  `Nox <https://nox.thea.codes/en/stable/>`__ - automation tool to
      run different tasks as the tests or the code formatting check.

-  Tests:

   -  `pytest <https://docs.pytest.org/en/latest/>`__ - Python test
      framework to run the tests.

Licencia
--------

The original code can be found in the `DeepGProp
<https://github.com/lulivi/dgp-lib>`__ repo under GPLv3 License.
