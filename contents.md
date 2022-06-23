# Contents Overview

This file provides an overview of the [envisioned book contents](#book-structure), along with author assignments and [learning objectives](#part-contents-and-objectives).

## Book Structure

This is a table of the book parts (corresponding to climate risk case studies) and author assignments. Links go to sections specifying a high-level overview and learning objectives for that part. Authors should feel free to expand or modify as need be.

| Part Title | Primary Author | Other Author(s) |
|    :--:    |      :--:      |       :--:      |
| [Introduction](#introduction) | Vivek Srikrishnan | Klaus Keller |
| [Risk Analysis in Julia](#risk-analysis-in-julia) | Vivek Srikrishnan | James Doss-Gollin |
| [Coastal Flood Risk](#coastal-flood-risk) | Vivek Srikrishnan | Tony Wong, Ben Lee |
| [Estimating Climate Sensitivity](#estimating-climate-sensitivity) | Vivek Srikrishnan | Klaus Keller |
| [The Social Cost of Carbon](#the-social-cost-of-carbon) | Frank Errickson | Tony Wong, Vivek Srikrishnan |
| [Agricultural Risk Analysis](#agricultural-risk-analysis) | David Lafferty | Ryan Sriver |
| [Forest Fire Occurrence](#forest-fire-occurrence) | James Doss-Gollin | Ben Lee |


## Other Potential Topics

Topics we could include if we can identify good learning objectives:

* levee effect (ABM/equity?)
* energy-system risk (multisector risk, machine learning?)

## Part Contents and Objectives

### Introduction

#### Goal

Introduce the concepts of climate change, uncertainty, and risk.

#### Contents

1. Introduction to climate risk
2. What is uncertainty?
3. Why does uncertainty matter?

#### Learning Objectives

At the end of this part, readers will be able to:

1. Define risk;
2. Explain the role of climate change in exacerbating societal risks;
3. Differentiate between aleatory and epsitemic uncertainty;
4. Distinguish frequentist from Bayesian interpretations of uncertainty;
5. Articulate the importance of accounting for uncertainties.

### Risk Analysis in Julia

#### Goal

Provide a basic guide to Julia and packages with relevant functionality (data wrangling, UQ, ML, etc).

#### Contents

1. Julia Basics
2. Tools for Risk Analysis in Julia

#### Learning Objectives

At the end of this part, readers will be able to:

1. Install Julia;
2. Write and execute basic programs in the Julia programming language;
3. Make basic plots in Julia;
4. Identify, install, and load packages relevant to risk analysis tasks.

### Coastal Flood Risk

This chapter is based loosely off [Oddo et al (2020)](https://onlinelibrary.wiley.com/doi/10.1111/risa.12888), [Ruckert et al (2017)](http://link.springer.com/10.1007/s10584-016-1858-z), and [Wong et al (2018)](https://iopscience.iop.org/article/10.1088/1748-9326/aacb3d).

#### Goals

Show students how to calibrate (simple) mechanistic and statistical models, as well as introduce model selection, in the context of sea-level rise and storm surge.

#### Contents

1. The Role of Climate Change
2. Modeling and Calibrating Sea-Level Rise Models
3. Statistical Models for Tidal Extremes
4. Impact of Uncertainty on Seawall Height

#### Objectives

At the end of this part, readers will be able to:

1. Explain the causal impact of climate change on rising sea levels;
2. Choose a likelihood function based on residual structure analysis;
3. Use the bootstrap and Markov chain Monte Carlo to calibrate a simple sea-level rise model;
4. Fit an extreme-value distribution to tide gauge data;
5. Evaluate competing model structures using model selection criteria;
6. Explain how uncertainty can impact decision-making.

### Estimating Climate Sensitivity

This chapter is based on either [Olson et al (2011)](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2011JD016620) or [Urban & Keller (2009)](https://www.tandfonline.com/doi/abs/10.1111/j.1600-0870.2010.00471.x), depending on what type of emulation we want to use (GP or mechanistic).

#### Goals

Introduce climate system uncertainties and emulation.

#### Contents

1. How Sensitive is the Climate to CO_2_ Emissions?
2. Challenges in Estimating Climate Sensitivity
3. Emulating Complex Models
4. Calibrating a Climate Emulator

#### Learning Objectives

At the end of this part, readers will be able to:

1. Define the concept of climate sensitivity;
2. Explain how different parts of the climate system compensate in response to warming.
3. Demonstrate how emulation addresses the trade-off between model complexity and the ability to quantify uncertainties.
4. Evaluate different approaches to emulation based on problem characteristics.

### The Social Cost of Carbon

#### Goals

Derive and explain the social cost of greenhouse gases, discuss the importance of discount factors, and demonstrate sensitivity analysis.

#### Contents

1. What is the Social Cost of a Greenhouse Gas?
2. Introduction to Discounting
3. What Uncertainties Influence the Social Cost of CO_2_?

#### Learning Objectives

At the end of this part, readers will be able to:

1. Explain the concept of the social cost of greenhouse gases;
2. Discuss the influence of discount rates on the net present value of monetary flows;
3. Use integrated assessment models to estimate the social cost of CO_2_;
4. Analyze sensitivities of a modeled quantity to relevant uncertainties.

### Agricultural Risk Analysis

This section might build off [Schlenker and Roberts (2009)](https://www.pnas.org/doi/full/10.1073/pnas.0906865106) and [Lafferty et al (2021)](https://www.nature.com/articles/s43247-021-00266-9).

#### Goals

Demonstrate how to analyze risk given multiple climate scenarios and introduce how downscaling contributes uncertainty.

#### Contents

1. Global Climate Model Ensembles
2. Approaches to Downscaling Climate Model Output
3. How Downscaling Impacts Uncertainty
4. Climate Impacts on Agricultural Yields
5. Using Downscaled Climate Products to Analyze Risk

#### Learning Objectives

At the end of this part, readers will be able to:

1. Explain why downscaling global climate model output is necessary for regional risk analyses;
2. Apply methods for statistical and dynamic downscaling (*maybe?*);
3. Discuss how downscaling can increase projection uncertainty;
4. Evaluate risks across an ensemble of climate projections.

### Forest Fire Occurrence

I don't have a good sense of where to start in terms of data or papers. I'm open to swapping this out for something else illustrating spatial analyses.

#### Goals

Introduce spatial models and demonstrate how to make relevant choices (variograms, etc).

#### Contents

Going to leave this up to the authors, since the topic might change.

#### Learning Objectives

At the end of this part, readers will be able to:

1. Explain how climate change intensifies forest fire risk.
2. Implement spatial emulators to model forest fire occurrence probabilities.
