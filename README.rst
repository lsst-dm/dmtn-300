.. image:: https://img.shields.io/badge/dmtn--300-lsst.io-brightgreen.svg
   :target: https://dmtn-300.lsst.io
.. image:: https://github.com/lsst-dm/dmtn-300/workflows/CI/badge.svg
   :target: https://github.com/lsst-dm/dmtn-300/actions/

#######################################################
Implementing SIAv2 Over Rubin Observatory's Data Butler
#######################################################

DMTN-300
========

The IVOA Simple Image Access version 2 protocol defines an easy way to provide community access to a collection of data. At the Vera C. Rubin Observatory we currently enable ObsTAP access to our data holdings via an ObsCore export or view of our Data Butler repositories. This approach does come with some deployment constraints, such as requiring pgsphere and compatibility with our CADC TAP implementation, so recently we decided to see whether we could instead provide an SIAv2 service that talks directly to our Data Butler. Here we describe our motivation, implementation strategies, and current deployment status, as well as discussing some metadata mismatches between the Butler data models and SIAv2.

Links
=====

- Live drafts: https://dmtn-300.lsst.io
- GitHub: https://github.com/lsst-dm/dmtn-300

Build
=====

This repository includes lsst-texmf_ as a Git submodule.
Clone this repository::

    git clone --recurse-submodules https://github.com/lsst-dm/dmtn-300

Compile the PDF::

    make

Clean built files::

    make clean

Updating acronyms
-----------------

A table of the technote's acronyms and their definitions are maintained in the `acronyms.tex` file, which is committed as part of this repository.
To update the acronyms table in ``acronyms.tex``::

    make acronyms.tex

*Note: this command requires that this repository was cloned as a submodule.*

The acronyms discovery code scans the LaTeX source for probable acronyms.
You can ensure that certain strings aren't treated as acronyms by adding them to the `skipacronyms.txt <./skipacronyms.txt>`_ file.

The lsst-texmf_ repository centrally maintains definitions for LSST acronyms.
You can also add new acronym definitions, or override the definitions of acronyms, by editing the `myacronyms.txt <./myacronyms.txt>`_ file.

Updating lsst-texmf
-------------------

`lsst-texmf`_ includes BibTeX files, the ``lsstdoc`` class file, and acronym definitions, among other essential tooling for LSST's LaTeX documentation projects.
To update to a newer version of `lsst-texmf`_, you can update the submodule in this repository::

   git submodule update --init --recursive

Commit, then push, the updated submodule.

.. _lsst-texmf: https://github.com/lsst/lsst-texmf
