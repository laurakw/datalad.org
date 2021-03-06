Get DataLad
###########
:save_as: get_datalad.html
:url: /get_datalad.html

When there isn't anything more convenient (see below), DataLad is most easily
installed via pip_. To automatically install DataLad and its software
dependencies type ::

  pip install datalad

.. _pip: https://pip.pypa.io/en/stable/

There is one additional dependency — git-annex_ — that is not installed
automatically when using pip. Be sure to have a recent version of git-annex
installed on your system.

.. _git-annex: http://git-annex.branchable.com

DataLad can be installed without admin privileges, into your home directory,
using ``pip``'s ``--user`` option. Git-annex can be deployed by extracting
pre-built binaries from a tarball (that also includes an up-to-date Git
installation). `Obtain the tarball
<https://downloads.kitenet.net/git-annex/linux/current/>`_, extract it, and set
the ``PATH`` environment variable to include the root of the extracted tarball.
If this sounds complicated, then one of the options below might be a better fit.

(Neuro)Debian, Ubuntu, and similar systems
------------------------------------------
For Debian-based operating systems, the most convenient installation method
is to enable the NeuroDebian_ repository. The following command installs DataLad
and all of its software dependencies (including the git-annex-standalone
package) ::

  sudo apt-get install datalad

.. _neurodebian: http://neuro.debian.net

OS X
----
A common way to install packages on OS X is via the homebrew_ package manager.
git-annex can be installed using the command ::

  brew install git-annex

Once git-annex is available, DataLad can be installed via ``pip`` as described
above. ``pip`` comes with Python distributions, such as anaconda_.

.. _homebrew: https://brew.sh
.. _anaconda: https://www.continuum.io/downloads

HPC environments or any system with singularity installed
---------------------------------------------------------
If you want to use DataLad on a high-performance computing (HPC) environment,
such as a computer cluster or a similar multi-user machine, where you don't
have admin privileges, chances are that `Singularity
<http://singularity.lbl.gov>`_ is already installed. And if it isn't installed,
the singularity website has a page dedicated to helping you make a `solid case
<http://singularity.lbl.gov/install-request>`_ to help convince your admin why
they *really* want to install it.

On any system with Singularity installed, you can pull a container with a full
installation of DataLad (~300 MB) straight from `Singularity Hub`_. The
following command pulls the latest container for the DataLad development version
(check on `Singularity Hub`_ for alternative container variants) ::

  singularity pull shub://datalad/datalad:fullmaster

This will produce an executable image file. You can rename this image to
``datalad`` and put the directory it is located in into your ``PATH``
environment variable. From there on, you will have a ``datalad`` command
available from the command line that transparently executes all DataLad
functionality through the container.

.. _Singularity Hub: https://singularity-hub.org/collections/667
