# Topic 4: Bayesian Tools in Python

The school of Bayesian statistics is incredibly popular in contemporary astronomy, and familiarity with the main Python packages used in Bayesian analyses can therefore be incredibly useful. Below is a non-comprehensive list of some of the major tools currently used in Python, some of which have accompanying problem sheets in this repository.

[emcee](https://emcee.readthedocs.io/en/stable/)
`emcee` is an Markov-Chain Monte-Carlo (MCMC) sampler, and is the starting point for many people's adventures with Bayesian statistics in Python. It is a pure-Python implementation, and so it will involve you specifying functions for your probability functions yourself.

The main benefit of `emcee` over alternative Hamiltonian Monte Carlo (HMC) samplers (see below) is that its pure-Python implementation allows for a user to more easily incorporate Python-based functions into their model, which HMC samplers are less effective for. `emcee` can handle a couple 100 parameters, and is excellent for understanding how to set up likelihood functions in Python.

To get started with `emcee`, [check out this excellent tutorial](https://emcee.readthedocs.io/en/stable/tutorials/line/), which has been copied into this repository.

[PyMC3](https://docs.pymc.io/)
`PyMC3` is a much more compehensive Bayesian analysis tool, mostly because it has its own built-in syntax. We call this a "probabilistic programming language" sometimes, although what it really means is just that we call functions from PyMC3 to set up our model, instead of defining them ourselves like with `emcee`. This comes with the downside that more flexible models are harder to achieve, but with the upside that PyMC3 runs increadibly efficiently, is very intuitive to use, and has more sampling options, such as gradient-based MCMC and Hamiltonian Monte-Carlo (HMC) algorithms with No U-Turns Samplers (NUTS), as well as some other stuff I'm not super familiar with such as variational inference and Stein Variational Gradient Descent. T

This is a bit of a soup of letters, so the important takeaway is that PyMC3 efficiently samples your models, and through the use of HMC sampling, can handle *way* more parameters (in the tens to hundreds of thousands), which are required for cool hierarchical models.

I've included a PyMC3 tutorial in this repository, but if you're interested in (many more) use cases, check out [their tutorials](https://docs.pymc.io/nb_examples/index.html) and [their API](https://docs.pymc.io/api.html), which lists the various available functions.


[Stan](https://mc-stan.org/) and [PyStan](https://pystan.readthedocs.io/en/latest/)
Much like PyMC3, Stan is a "probabilistic programming language" it's a bit more "pure" in the sense that when using Stan's API you can construct your own models using the Stan syntax, without having to resort to solely calling functions that are implemented in the program (like you have to do with PyMC3). This makes it just that little bit better when building complex custom models or priors, although PyMC3 is almost always enough.

Like PyMC3, Stan uses HMC with a NUTS sampler, as well as variational inference for those interested. It can be run in a ton of different langauges including R, but fo the sake of this workshop we will focus on its Python implementation, `PyStan`.

I've included a PyStan tutorial in this repository, which deals with the same example as the PyMC3 tutorial. If you get stuck, check out [the Stan documentation](https://mc-stan.org/users/documentation/), which is unbelievably comprehensive (but has a bit of a learning curve).


[celerité](https://celerite.readthedocs.io/en/stable/)
A recent popular (and very useful development) in astronomy is the application of [Gaussian Processes](http://www.gaussianprocess.org/gpml/) (GPs), which is a manner of model fitting where you essentially model data as correlated noise, instead of as being determined by a strict function. This is especially useful for constraining hard-to-model components of a signal, such as instrumental noise or rotational modulation of star spots on a stellar surface.

Celerité is a python package that efficiently evaluates a Gaussian Process model --- much more efficiently than if you were to evaluate that same GP in PyMC3. This is because it gets C++ to do all the hard work behind the scenes. As a result, Celerité only lets you use particular pre-designed GP kernels (which determine the shape of the GP, or the rate of correlation between points, one could say). It's useful to be familiar with Celerité if you use GPs, just so you know how you can include it to speed up your code.

Celerité has since been updated to [Celerité2](https://celerite2.readthedocs.io/en/latest/), but the original Celerité documentation has better tutorials (and the API for both is the same). If you're curious, I highly recommend checking out [their Python "first steps" tutorial](https://celerite.readthedocs.io/en/stable/tutorials/first/).

Celerité is also implemented in the [`exoplanet`](https://docs.exoplanet.codes/en/latest/) package, which combines a ton of different modelling tools for the purposes of exoplanet characterisation. Using `exoplanet`, Celerité methods can easily be combined with PyMC3. Check out [this tutorial on how to apply it to an asteroseismic target](https://colab.research.google.com/github/dfm/tasc5/blob/master/tasc5-demo.ipynb), although be warned--- it's fairly statistics and syntax heavy.
