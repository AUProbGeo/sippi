Install SIPPI
=============

The latest version of SIPPI can be downloaded from
`github <https://github.com/cultpenguin/sippi>`__. See
`https://sippi.readthedocs.io/ <https://sippi.readthedocs.io/>`__ for
documentation and examples.

Install SIPPI from github
----------------------------------

The current development version of SIPPI (less stable and documented) is
hosted on github and can be downloaded (including MGSTAT, SNESIM, VISIM
and MPS) using git:

::

    cd INSTALL_DIR
    git clone --recursive https://github.com/cultpenguin/sippi.git SIPPI

To update this installation (using mGstat and MSPLIB as submodules) use

::

    git pull --recurse-submodules

Then add a path to SIPPI in Matlab using

::

    addpath INSTALL_DIR/SIPPI
    sippi_set_path

To download SIPPI, mGstat and MPSlib seperately use:

::

    cd INSTALL_DIR
    git clone  https://github.com/cultpenguin/sippi.git SIPPI
    git clone  https://github.com/cultpenguin/mgstat.git mGstat
    git clone  https://github.com/ergosimulation/mpslib.git MPSlib

Then add a path to both SIPPI, mGstat and MPS/matlab using

::

    addpath INSTALL_DIR/mGstat
    addpath INSTALL_DIR/SIPPI
    addpath INSTALL_DIR/MPSlib/matlab
    sippi_set_path

Manual compilation
~~~~~~~~~~~~~~~~~~

| SIPPI (optionally) make use of standalone programs from
| `MPS <http://ergosimulation.github.io/mpslib/>`__
  (`github <https://github.com/ergosimulation/mpslib/>`__),
| SNESIM (`github <https://github.com/SCRFpublic/snesim-standalone>`__)
  and
| VISIM (part of `mGstat <https://github.com/cultpenguin/mGstat>`__). Pre-compiled
  slef-contained binaries are available for windows and Linux, but for
  use on OS-X one may need to manually these programs.

These programs are needed to make use of the
`MPS </chapSIPPI/prior/mps.md>`__, `VISIM </chapSIPPI/prior/visim.md>`__
and `SNESIM </chapSIPPI/prior/visim.md>`__ type `a priori
models <#prior_types>`__ (and can hence be ignored if not used).

Compiling VISIM
^^^^^^^^^^^^^^^

The source code for VISIM is located in ``mGstat/visim/visim_src``. The
compiled program should be placed in ``mGstat/bin`` and called
``visim``.

VISIM use pre-allocation of memory (set before compilation). This is
defined in ``visim.inc``. If this file is changed, VISIM must be
recomiled.

Compiling SNESIM
^^^^^^^^^^^^^^^^

The source code for SNESIM is available from
`github <https://github.com/SCRFpublic/snesim-standalone>`__.

The compiled program should be placed in ``mGstat/bin`` and called
``snesim.exe`` (windows) ``snesim_glnxa64.exe`` (64 bit Linux)
``snesim_maci64.exe`` (64 but OS X).

Compiling MPS
^^^^^^^^^^^^^

The source code for MPS is available from `github <#>`__. To dowload and
compile MPS use for example

::

    cd INSTALL_DIR
    git clone  https://github.com/ergosimulation/mpslib.git MPSLIB
    cd MPS
    make all

Matlabs path should be updated to include ``INSTALL_DIR/MPSLIB/matlab``.

SGeMS (optional)
~~~~~~~~~~~~~~~~

To make use of the SISIM and SNESIM\_STD type prior models, SGeMS needs
to be available.

Currently only SGeMS version 2.1 (`download <#>`__) for Windows is
supported by SIPPI.

Support for SGeMS will be discontinued after relevase v1.5, as the
`MPS <#>`__ library will be used instead.
