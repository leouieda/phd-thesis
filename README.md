# PhD Thesis: Gravity forward modeling and inversion in spherical coordinates

Author: [Leonardo Uieda](http://www.leouieda.com)

Advisor: [Valéria C. F. Barbosa](http://lattes.cnpq.br/0391036221142471)

Institution: [Observatório Nacional](http://www.on.br/)

## Abstract

## Contributions

Each of the following chapters have been published or submitted for
publication.

### Tesseroids: forward modeling gravitational fields in spherical coordinates

We present the open-source software Tesseroids, a set of command-line programs
to perform the forward modeling of gravitational fields in spherical
coordinates.  The software is implemented in the C programming language and
uses tesseroids (spherical prisms) for the discretization of the subsurface
mass distribution.  The gravitational fields of tesseroids are calculated
numerically using the Gauss-Legendre Quadrature (GLQ).  We have improved upon
an adaptive discretization algorithm to guarantee the accuracy of the GLQ
integration.  Our implementation of adaptive discretization uses a "stack"
based algorithm instead of recursion to achieve more control over execution
errors and corner cases.  The algorithm is controlled by a scalar value called
the distance-size ratio (D) that determines the accuracy of the integration as
well as the computation time.  We determined optimal values of D for the
gravitational potential, gravitational acceleration, and gravity gradient
tensor by comparing the computed tesseroids effects with those of a homogeneous
spherical shell.  The values required for a maximum relative error of 0.1% of
the shell effects are D = 1 for the gravitational potential, D = 1.5 for the
gravitational acceleration, and D = 8 for the gravity gradients.  Contrary to
previous assumptions, our results show that the potential and its first and
second derivatives require different values of D to achieve the same accuracy.
These values were incorporated as defaults in the software.

Accepted for publication in the journal Geophysics.
See [pinga-lab/paper-tesseroids](https://github.com/pinga-lab/paper-tesseroids)
for the source code and data associated with the paper.

### Modeling the Earth with Fatiando a Terra

Geophysics is the science of using physical observations of the Earth to infer
its inner structure.  Generally, this is done with a variety of numerical
modeling techniques and inverse problems.  The development of new algorithms
usually involves copy and pasting of code, which leads to errors and poor code
reuse.  Fatiando a Terra is a Python library that aims to automate common tasks
and unify the modeling pipeline inside of the Python language.  This allows
users to replace the traditional shell scripting with more versatile and
powerful Python scripting.  The library can also be used as an API for
developing stand-alone programs.  Algorithms implemented in Fatiando a Terra
can be combined to build upon existing functionality.  This flexibility
facilitates prototyping of new algorithms and quickly building interactive
teaching exercises.  In the future, we plan to continuously implement sample
problems to help teach geophysics as well as classic and state-of-the-art
algorithms.

Published in the [Proceedings of the 12th Python in Science Conference (Scipy
2013)](http://www.leouieda.com/talks/scipy2013.html).

### Fast non-linear gravity inversion in spherical coordinates with application to the South American Moho

Estimating the relief of the Moho from gravity data is a computationally
intensive non-linear inverse problem.  What is more, the modeling must take the
Earths curvature into account when the study area is of regional scale or
greater.  We present a regularized non-linear gravity inversion method that has
a low computational footprint and employs a spherical Earth approximation.  To
achieve this, we combine the highly efficient Bott's method with smoothness
regularization and a discretization of the anomalous Moho into tesseroids
(spherical prisms).  The computational efficiency of our method is attained by
harnessing the fact that all matrices involved are sparse.  The inversion
results are controlled by three hyper-parameters: the regularization parameter,
the anomalous Moho density-contrast, and the reference Moho depth.  We estimate
the regularization parameter using the method of hold-out cross-validation.
Additionally, we estimate the density-contrast and the reference depth using
knowledge of the Moho depth at certain points.  We apply the proposed method to
estimate the Moho depth for the South American continent using satellite
gravity data and seismological data.  The final Moho model is in accordance
with previous gravity-derived models and seismological data.  The misfit to the
gravity and seismological data is worse in the Andes and best in oceanic areas,
central Brazil and Patagonia, and along the Atlantic coast.  Similarly to
previous results, the model suggests a thinner crust of 30-35 km under the
Andean foreland basins.  Discrepancies with the seismological data are greatest
in the Guiana shield, the central Solimões and Amazon basins, the Paraná basin,
and the Borborema province.  These differences suggest the existence of crustal
or mantle density anomalies that were unaccounted for during gravity data
processing.

Submitted for publication in the Geophysical Journal International.
See [pinga-lab/paper-moho-inversion-tesseroids](https://github.com/pinga-lab/paper-moho-inversion-tesseroids)
for the source code and data associated with the paper.
