.. highlight:: sh

Setup Guide
===========

This guide explains how to install the required components to run EarthOrbitPlan. The pipeline is built around
the :math:`\mathrm{M^4OPT}` `toolkit <https://m4opt.readthedocs.io/en/latest/>`_
and also makes use of `observing-scenarios`_  to generate realistic
gravitational wave follow-up situations. It is recommended to use a virtual environment (e.g. via conda or venv)
to avoid conflicts between dependencies.

.. note::

   EarthOrbitPlan is designed for educational use and builds directly on :math:`\mathrm{M^4OPT}`.
   It provides a guided way to run simulations based on skymaps from GW detectors and
   schedule follow-up facilities with  such as UVEX, ULTRASAT, ZTF, and Rubin.

Dependencies
------------

You will need the following:

- Python >= 3.11
- `M⁴OPT <https://m4opt.readthedocs.io/en/latest/>`_
- `observing-scenarios`_


Environment setup (using conda)
-------------------------------

.. code-block:: bash

   conda create -n earthorbitplan python=3.11
   conda activate earthorbitplan


:math:`\mathrm{M^4OPT}` Setup
-----------------------------

.. toctree::
   :maxdepth: 2

   m4opt


.. note::

   For general use, installing M4OPT is sufficient to run all simulations and test cases provided by EarthOrbitPlan.

   If you wish to explore additional GW–only scenarios, please refer to the `observing-scenarios`_
   repository for more details. Alternatively, you can install it manually using the following steps:


Observing Scenarios Setup
-------------------------

Clone and install observing-scenarios
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: bash

   curl -sSL https://install.python-poetry.org | python3 -
   git clone https://github.com/lpsinger/observing-scenarios-simulations.git
   cd observing-scenarios-simulations

   poetry run pip install --upgrade pip
   poetry install
   poetry shell


.. note::

   The `observing-scenarios`_ package is optional, but useful for testing standalone GW follow-up strategies without electromagnetic scheduling.
   It provides realistic skymaps and scenarios commonly used in follow-up campaigns.


.. _observing-scenarios: https://github.com/lpsinger/observing-scenarios-simulations

.. _m4opt: https://m4opt.readthedocs.io/en/latest/
