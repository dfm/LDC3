# LDC3

LDC3 is a code for sampling physically permissible limb darkening coefficients for the Sing et al. (2009) three-parameter law using the approximate technique described in Kipping (2015) (see http://arxiv.org/abs/XXXX.XXXX). Specifically, we define physically permissible intensity profile as being everywhere-positive, monotonically decreasing from center to limb and having a curl at the limb. The approximate sampling method is analytic and thus very fast, reproducing physically permissible samples in 97.3% of random draws (high validity) and encompassing 94.4% of the physically permissible parameter volume (high completeness).

The python module LDC3.py contains the transformation equations and an example calling routine example.py may be used as a demonstration. This code has been tested with python 2.7 on Mac OS X Yosemite. Compile and run using: python2.7 example.py LDC3.py

We also provide fortran code, LDC3.f90, in a very similar format to the python code, which may be tested using example.f90. This code may be compiled using the Makefile: make example.

An example practical application of this software is for fitting exoplanet transit light curves with an MCMC routine. One may fit for the parameters alpha_h, alpha_t and alpha_r, with uniform (flat) priors between 0 and 1. These three proxy limb darkening terms may be treated like any other fitted parameter in your MCMC. At each realization, call the forward subroutine/definition (for fortran/python respectively) to return the more familiar limb darkening coefficients, c_2, c_3 and c_4. You may now generate your trial light curve as usual using these limb darkening coefficients.
