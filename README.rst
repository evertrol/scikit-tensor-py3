scikit-tensor
=============
.. image:: https://travis-ci.org/evertrol/scikit-tensor-py3.svg?branch=master
  :target: https://travis-ci.org/evertrol/scikit-tensor-py3

scikit-tensor is a Python module for multilinear algebra and tensor
factorizations. Currently, scikit-tensor supports basic tensor operations
such as folding/unfolding, tensor-matrix and tensor-vector products as
well as the following tensor factorizations:

* Canonical / Parafac Decomposition
* Tucker Decomposition
* RESCAL
* DEDICOM
* INDSCAL

Moreover, all operations support dense and tensors.

Note
----

This is a Python 3 only compatible maintenance release. It appears the
development for scikit-tensor has stalled, and the project has been
abandoned. This fork only supports Python 3.5 and later, and is
available on PyPI as `scikit-tensor-py3`, for easier installation.

Issues and pull requests are welcomed, but issues relating algorithms
and requests for additional algorithms may be postponed or ignored
altogether. Technical (code) issues are welcomed.

Dependencies
------------

The required dependencies to build the software are `Numpy` and `SciPy`.

Usage
-----

Example script to decompose sensory bread data (available from
http://www.models.life.ku.dk/datasets) using CP-ALS::


    import logging
    from scipy.io.matlab import loadmat
    from sktensor import dtensor, cp_als

    # Set logging to DEBUG to see CP-ALS information
    logging.basicConfig(level=logging.DEBUG)

    # Load Matlab data and convert it to dense tensor format
    mat = loadmat('../data/sensory-bread/brod.mat')
    T = dtensor(mat['X'])

    # Decompose tensor using CP-ALS
    P, fit, itr, exectimes = cp_als(T, 3, init='random')


Installation
------------

This package uses distutils, which is the default way of installing
python modules. The use of virtual environments is recommended::

    pip install scikit-tensor-py3

To install in development mode::

    git clone https://github.com/evertrol/scikit-tensor-py3.git
    pip install -e scikit-tensor

Contributing & Development
--------------------------

scikit-tensor is still an extremely young project, and I'm happy for
any contributions (patches, code, bugfixes, documentation, whatever)
to get it to a stable and useful point. Feel free to get in touch with
me via email (mnick at AT mit DOT edu) or directly via github. See
also the note above.

Development is synchronized via git. Feel free to fork this project
and make pull requests from that fork.

Authors
-------

* Maximilian Nickel: `Web <http://web.mit.edu/~mnick/www>`_,
  `Email <mailto://mnick AT mit DOT edu>`,
  `Twitter <http://twitter.com/mnick>`_
* Evert Rol (maintenance for Python 3 version): `Email <mailto:evert.rol@gmail.com>`_

License
-------

scikit-tensor-py3 is licensed under the `GPLv3 <http://www.gnu.org/licenses/gpl-3.0.txt>`_

Related Projects
----------------

* `Matlab Tensor Toolbox <http://www.sandia.gov/~tgkolda/TensorToolbox/index-2.5.html>`_:
  A Matlab toolbox for tensor factorizations and tensor operations
  freely available for research and evaluation.

* `Matlab Tensorlab <http://www.tensorlab.net/>`_ A Matlab toolbox for
  tensor factorizations, complex optimization, and tensor optimization
  freely available for non-commercial academic research.
