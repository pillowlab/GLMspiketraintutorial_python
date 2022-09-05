# GLMspiketraintutorial_python

Simple tutorial on Gaussian and Poisson generalized linear models
(GLMs) for spike train data, written in python.  

**Author**: [Jesse Kaminsky](https://scholar.google.com/citations?user=ZY1PtQ4AAAAJ&hl=en).
(Translated from a [Matlab version](https://github.com/pillowlab/GLMspiketraintutorial) prepared by [Jonathan Pillow](http://pillowlab.princeton.edu)).

**Slides**: This tutorial was prepared for use in a
"Short Course" on [Data Science and Data Skills for Neuroscientists](https://neuronline.sfn.org/scientific-research/data-science-and-data-skills-for-neuroscientists#:~:text=Data%20science%20is%20fast%2Dgrowing,be%20used%20in%20different%20circumstances) organized at the SFN 2016 meeting. The slides used during the 1-hour
presentation are available [here](https://github.com/pillowlab/GLMspiketraintutorial/blob/master/slides/slides_SFNshortcourse_Nov2016.pdf). 

**Dataset**:  A small dataset required for the tutorial (provided by EJ Chichilnisky) is provided in the directory [data_RGCs](https://github.com/pillowlab/GLMspiketraintutorial_python/tree/main/data_RGCs).

**Installation**: Clone the repo into the same directory as the provided dataset. Additionally, this tutorial requires that you have scipy, numpy, matplotlib, and [statsmodels](https://www.statsmodels.org/dev/install.html) installed. This tutorial runs on python 3.

**Description**: The tutorial contains five jupyter notebooks that cover various methods for fitting and analyzing Gaussian and Poisson regression models for spike train data. Each notebook an interactive, self-contained script with 'blocks' of code that demonstrate each step in the fitting / analysis / model comparison pipeline:

* **tutorial1_PoissonGLM.ipynb** - illustrates the fitting of a
linear-Gaussian GLM (also known as the 'linear least-squares
regression model') and a Poisson GLM (aka 'linear-nonlinear-Poisson'
model) to single retinal ganglion cell responses to a temporal white
noise stimulus.

* **tutorial2_spikehistcoupledGLM.ipynb** - fitting of an autoregressive
Poisson GLM (i.e., a GLM with spike-history) and a multivariate
autoregressive Poisson GLM (a GLM with spike-history AND coupling
between neurons).

* **tutorial3_regularization_linGauss.ipynb** - regularizing
  linear-Gaussian model  parameters using maximum a posteriori (MAP)
  estimation under two kinds of priors:
  - (1) ridge regression (aka  "L2 penalty"); 
  - (2) L2 smoothing prior (aka "graph Laplacian").  


* **tutorial4_regularization_PoissonGLM.ipynb** - MAP estimation of
  Poisson-GLM parameters using same two priors considered in
  tutorial3.

* **tutorial5_MAPdecoding.ipynb** - Bayesian (MAP) decoding of the stimulus from spikes under a fitted Poisson GLM (with or without spike-history).  (_Note: this tutorial was added by J. Kaminsky, and does not exist in the Matlab version_)
 
 <br>
 
------- 

**Citation**:  If you wish to cite this tutorial, feel free to acknowledge the paper from which it developed: [Pillow et al, *Nature* 2008](http://pillowlab.princeton.edu/pubs/abs_Pillow08_nature.html).  Or, for the MAP decoding tutorial, cite: [Pillow et al, *Neural Comp* 2011](http://pillowlab.princeton.edu/pubs/abs_pillow11_NC.html).
 



 <br>

-------

**Relevance / comparison to other GLM packages**:

This tutorial is designed primarily for pedagogical purposes. The
tutorial scripts are (almost entirely) self-contained, making it easy
to understand the basic steps involved in simulating and fitting. It
is easy to alter these scripts (e.g., to incorporate different kinds
of regressors, or different kinds of priors for
regularization). However, this implementation is not memory-efficient
and does not support some of the advanced features available in other
GLM packages (e.g., smooth basis functions for spike-history filters,
memory-efficient temporal convolutions, different timescales for
stimulus and spike-history components, low-rank parametrization of
spatio-temporal filters, flexible handling of trial-based data).  For
more advanced features and applications, see the following two
repositories:

- [neuroGLM](http://pillowlab.princeton.edu/code_neuroGLM.html) -
  designed for single-neuron, trial-structured data. Supports flexible design matrices with multiple types of
  regressors. Relevant pub: [Park et al, *Nat Neurosci* 2014](http://pillowlab.princeton.edu/pubs/abs_ParkI_NN14.html).

- [GLMspiketools](http://pillowlab.princeton.edu/code_GLM.html) -
  designed for single- and multi-neuron spike trains with flexible
  nonlinearities, multiple timescales, and low-rank parametrization of
  filters.  Relevant pub: [Pillow et al, *Nature* 2008](http://pillowlab.princeton.edu/pubs/abs_Pillow08_nature.html).
