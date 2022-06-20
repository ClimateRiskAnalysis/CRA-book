# Modeling Sea Level Rise

We often have to make inferences about system behaviors using limited data. This problem can be especially acute in climate science, where observational records of temperature and sea level rise (for example) go back a few hundred years at most.  Given these limited data, how can we make inferences about the past and future of the climate system, while accurately representing our uncertainties?

In this section, we will develop and calibrate a model of global sea-level rise. In [](#selecting-a-sea-level-model), we will discuss several choices for a model structure. In [](sec:slr-likelihood), we will propose several statistical models to represent deviations between our chosen model and historical observations, also called *residuals* or *discrepancies*.
```{margin} Modeling Residuals
The statistical model used for residuals plays an important role in sound parameter inferences and projections {cite:p}`brynjarsdottirLearningPhysicalParameters2014`. 
```
Finally, we will learn about and apply frequentist and Bayesian approaches to parameter inferences in [](sec:slr-bootstrap) and [](sec:slr-mcmc), respectively.
