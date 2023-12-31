## Psi4-v1.3.2
This version still requires python 3.8.
This version does not require Libint2, only Libint

We can use Conda to intall some required packages:
```bash
$ conda install -c conda-forge libstdcxx-ng=12
$ conda install python=3.8
$ conda install mkl-devel numpy=1.20 networkx msgpack-python mpfr eigen # ( and cmake)
$ conda install -c conda-forge openmp pydantic pint deepdiff # (deepdiff need for v1.3.2)
```

Prepare a do-configure file: (Conda-mkl)
```bash
cmake -S. -B"/home/michaelbishop/softwares/psi4_mod/psi4-1.3.x/compile-psi4" \
        -DCMAKE_INSTALL_PREFIX="/home/michaelbishop/softwares/psi4_mod/psi4-1.3.x/install-psi4" \
        -DCMAKE_PREFIX_PATH="/home/michaelbishop/softwares/psi4_mod/psi4-1.3.x/install-psi4/externals/install-libint" \
        -DMAX_AM_ERI=6 \
        -DENABLE_gdma=ON \
        -DBUILD_SHARED_LIBS=ON \
        -DCMAKE_C_COMPILER=/opt/gcc/8.3.0/bin/gcc \
        -DCMAKE_CXX_COMPILER=/opt/gcc/8.3.0/bin/g++ \
        -DCMAKE_Fortran_COMPILER=/opt/gcc/8.3.0/bin/gfortran \
        -DBLAS_TYPE=MKL \
        -DLAPACK_TYPE=MKL \
        -DBLAS_LIBRARIES=/home/michaelbishop/anaconda3/envs/psi4mod/lib/libmkl_rt.so \
        -DLAPACK_LIBRARIES=/home/michaelbishop/anaconda3/envs/psi4mod/lib/libmkl_rt.so \ # Conda-mkl
        -DBLAS_INCLUDE_DIRS=/home/michaelbishop/anaconda3/envs/psi4mod/include/ \
        -DLAPACK_INCLUDE_DIRS=/home/michaelbishop/anaconda3/envs/psi4mod/include/ \
        -DOpenMP_LIBRARY_DIRS=/home/michaelbishop/anaconda3/envs/psi4mod/lib/
```
Above is the one conda-psi4 uses, and is the quickest.


# <img src="https://github.com/psi4/psi4media/blob/master/logos-psi4/psi4square.png" height=150>

| **Status** | [![Travis build](https://img.shields.io/travis/psi4/psi4/master.svg?logo=linux&logoColor=white)](https://travis-ci.org/psi4/psi4) [![Azure DevOps builds](https://img.shields.io/azure-devops/build/psi4/e80489d7-9619-4512-8e7b-255e355b3ab8/1/master.svg?logo=windows)](https://dev.azure.com/psi4/psi4/_build?definitionId=1) [![Codecov coverage](https://img.shields.io/codecov/c/github/psi4/psi4.svg?logo=Codecov&logoColor=white)](https://codecov.io/gh/psi4/psi4) [![LGTM analysis](https://img.shields.io/lgtm/grade/python/g/psi4/psi4.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/psi4/psi4/context:python) |
| :------ | :------- |
| **Latest Release** | [![Last release tag](https://img.shields.io/github/release/psi4/psi4.svg)](https://github.com/psi4/psi4/releases)  [![Commits since release](https://img.shields.io/github/commits-since/psi4/psi4/v1.2.svg)](https://github.com/psi4/psi4/releases/tag/v1.2) [![python](https://img.shields.io/badge/python-2.7%2C%203.5%2C%203.6-blue.svg)](http://psicode.org/psi4manual/master/introduction.html#supported-systems) |
| **Communication** | [![User site](https://img.shields.io/badge/home-Psi4-5077AB.svg)](http://www.psicode.org) [![docs latest](https://img.shields.io/badge/docs-latest-5077AB.svg?logo=read%20the%20docs)](http://psicode.org/psi4manual/master/index.html) [![chat on forum](https://img.shields.io/badge/chat-on_forum-808493.svg?logo=Discourse&logoColor=white)](http://forum.psicode.org/) [![dev chat on slack](https://img.shields.io/badge/dev_chat-on_slack-808493.svg?logo=slack)](https://join.slack.com/t/psi4/shared_invite/enQtNDUyOTYzNTE0NjQ3LWExZDhkY2U4MTM1ZDZlNTBkNjMyMDcxZmFkN2NmYmZkMzliNzY2ZDc2OTBlYTk5ZTA2OGRkNWYxNzJmN2QyYWM) |
| **Foundation** | [![license](https://img.shields.io/github/license/psi4/psi4.svg)](https://opensource.org/licenses/LGPL-3.0) [![platforms](https://img.shields.io/badge/Platforms-Linux%2C%20MacOS%2C%20Windows%20WSL-orange.svg)](http://psicode.org/psi4manual/master/introduction.html#supported-systems) [![python](https://img.shields.io/badge/python-3.5+-blue.svg)](http://psicode.org/psi4manual/master/introduction.html#supported-systems) |
| **Installation** | [![obtain latest](https://img.shields.io/badge/obtain-latest-green.svg)](http://vergil.chemistry.gatech.edu/nu-psicode/install-v1.2.1.html) [![Conda](https://img.shields.io/conda/v/psi4/psi4.svg)](https://anaconda.org/psi4/psi4) [![Anaconda-Server Badge](https://anaconda.org/psi4/psi4/badges/latest_release_relative_date.svg)](https://anaconda.org/psi4/psi4) |

<!--  -->
<!-- [![Last release date](https://img.shields.io/github/release-date/psi4/psi4.svg)](https://github.com/psi4/psi4/releases) -->
<!-- [![Anaconda-Server Badge](https://anaconda.org/psi4/psi4/badges/version.svg)](https://anaconda.org/psi4/psi4) -->

<!--<a href="https://psi4.slack.com/messages"> <img src="https://img.shields.io/badge/dev_chat-on_slack-808493.svg" /></a>
<a href="mailto:psi4aiqc+slackinvite@gmail.com?subject=request slack invite (incl. who, where, email)"> <img src="https://img.shields.io/badge/dev_chat-invite-808493.svg" /></a> -->

<!--[![Anaconda-Server Badge](https://anaconda.org/psi4/psi4/badges/installer/conda.svg)](https://anaconda.org/psi4/psi4) 
[![Anaconda-Server Badge](https://anaconda.org/psi4/psi4/badges/platforms.svg)](https://anaconda.org/psi4/psi4) -->

<!--
| **PR Activity** | 
[![commit activity](https://img.shields.io/github/commit-activity/y/psi4/psi4.svg)](https://github.com/psi4/psi4/graphs/contributors) 
[![issues-pr-closed](https://img.shields.io/github/issues-pr-closed-raw/psi4/psi4.svg)](https://github.com/psi4/psi4/pulls)
-->

Psi4 is an open-source suite of *ab initio* quantum chemistry programs
designed for efficient, high-accuracy simulations of
molecular properties. We routinely perform computations with >2500 basis functions on multi-core machines.

With computationally demanding portions written in C++, exports
of many C++ classes into Python via Pybind11, and a flexible Python driver, Psi4
strives to be friendly to both users and developers.

* **Users' Website**  www.psicode.org

* **Downloading and Installing Psi4** http://psicode.org/psi4manual/master/build_faq.html (for the CMake adept, see [CMakeLists.txt](CMakeLists.txt)

* **Manual**  [http://bit.ly/psi4manual](http://psicode.org/psi4manual/master/index.html) (built nightly from master branch) or http://psicode.org/psi4manual/1.2/index.html (last release)

* **Tutorial** http://psicode.org/psi4manual/master/tutorial.html for Psithon (``psi4 job.in``), http://psicode.org/psi4manual/master/psiapi.html for PsiAPI (``python job.py``)

* **Forum** http://forum.psicode.org

* **Communication & Support** http://psicode.org/psi4manual/master/introduction.html#technical-support

* **Github**  https://github.com/psi4/psi4 (authoritative repository)

* **Continuous Integration Status** [![Travis build](https://img.shields.io/travis/psi4/psi4/master.svg?logo=linux&logoColor=white)](https://travis-ci.org/psi4/psi4) on Linux [![Azure DevOps builds](https://img.shields.io/azure-devops/build/psi4/e80489d7-9619-4512-8e7b-255e355b3ab8/1/master.svg?logo=windows)](https://dev.azure.com/psi4/psi4/_build?definitionId=1) on Windows

* **Anaconda**  https://anaconda.org/psi4 (binary available for Linux, Mac, and WSL Windows [![Binstar Badge](https://anaconda.org/psi4/psi4/badges/downloads.svg)](https://anaconda.org/psi4/psi4) ) [instructions](http://psicode.org/psi4manual/master/conda.html#how-to-install-a-psi4-binary-with-the-psi4conda-installer-download-site)

* **Coverage** Python and C++ source code lines hit by running most of the test suite. [![codecov](https://img.shields.io/codecov/c/github/psi4/psi4.svg?logo=Codecov&logoColor=white)](https://codecov.io/gh/psi4/psi4)

* **Interested Developers**  http://psicode.org/developers.php (welcome to fork psi4/psi4 and follow [GitHub contribution procedure](http://psicode.org/psi4manual/master/build_obtaining.html#faq-githubworkflow)) [![PRs welcome](https://img.shields.io/badge/PRs-welcome-yellow.svg)](http://makeapullrequest.com)

* **Sample Inputs**  http://www.psicode.org/psi4manual/master/testsuite.html (also in [`samples/`](samples))

* **Download Tarball** https://github.com/psi4/psi4/releases 

<!--* **Build Dashboard** https://testboard.org/cdash/index.php?project=Psi

* **YouTube Channel** https://www.youtube.com/psitutorials-->


License [![license](https://img.shields.io/github/license/psi4/psi4.svg)](https://opensource.org/licenses/LGPL-3.0)
=======

Psi4: an open-source quantum chemistry software package

Copyright (c) 2007-2019 The Psi4 Developers.

The copyrights for code used from other parties are included in
the corresponding files.

Psi4 is free software; you can redistribute it and/or modify
it under the terms of the GNU Lesser General Public License as published by
the Free Software Foundation, version 3.

Psi4 is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Lesser General Public License for more details.

You should have received a copy of the GNU Lesser General Public License along
with Psi4; if not, write to the Free Software Foundation, Inc.,
51 Franklin Street, Fifth Floor, Boston, MA 02110-1301 USA.

The full text of the GNU Lesser General Public License (version 3) is included in the
COPYING.LESSER file of this repository, and can also be found
[here](https://www.gnu.org/licenses/lgpl.txt).


Citation [![doi](https://img.shields.io/badge/doi-10.1021/acs.jctc.7b00174-5077AB.svg)](http://dx.doi.org/10.1021/acs.jctc.7b00174)
========

The journal article reference describing Psi4 is:

R. M. Parrish, L. A. Burns, D. G. A. Smith, A. C. Simmonett,
A. E. DePrince III, E. G. Hohenstein, U. Bozkaya, A. Yu. Sokolov,
R. Di Remigio, R. M. Richard, J. F. Gonthier, A. M. James,
H. R. McAlexander, A. Kumar, M. Saitow, X. Wang, B. P. Pritchard,
P. Verma, H. F. Schaefer III, K. Patkowski, R. A. King, E. F. Valeev,
F. A. Evangelista, J. M. Turney, T. D. Crawford, and C. D. Sherrill,
J. Chem. Theory Comput. 13(7) 3185&ndash;3197 (2017).
