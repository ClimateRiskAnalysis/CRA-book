# Contents Overview

This file provides an overview of the [envisioned book contents](#book-structure), along with author assignments and [learning objectives](#part-contents-and-objectives).

## Book Structure

This is a table of the book parts (corresponding to climate risk case studies) and author assignments. Links go to sections specifying a high-level overview and learning objectives for that part. Authors should feel free to expand or modify as need be. The list of other authors is in no particular order.

| Part Title | Primary Author | Other Author(s) |
|    :--:    |      :--:      |       :--:      |
| [Introduction to Climate Risk](#introduction-to-climate-risk) | Klaus Keller | Vivek Srikrishnan |
| [Risk Analysis in Julia](#risk-analysis-in-julia) | Vivek Srikrishnan | James Doss-Gollin |
| [Exploratory Modeling](#exploratory-modeling) | James Doss-Gollin | Vivek Srikrishnan, Klaus Keller, Tony Wong |
| [Uncertainty Quantification](#uncertainty-quantification) | Vivek Srikrishnan | Klaus Keller, James Doss-Gollin, Tony Wong, Ben Lee |
| [Extreme Value Analysis](#extreme-value-analysis) | Vivek Srikrishnan | Tony Wong, James Doss-Gollin, Klaus Keller, Ben Lee
| [Uncertainty and Decision-Making](#uncertainty-and-decision-making) | Vivek Srikrishnan | Tony Wong, Klaus Keller, James Doss-Gollin |
| [Deep Uncertainty](#deep-uncertainty) | Vivek Srikrishnan | James Doss-Gollin, Klaus Keller |
| [Other Considerations](#other-considerations) | James Doss-Gollin | Klaus Keller, Vivek Srikrishnan, Tony Wong, Casey Helgeson (?) |


## Other Potential Topics

Topics we could include if we can identify good learning objectives:


## Part Contents and Objectives

### Introduction to Climate Risk

#### Goal

Introduce the concepts of climate change, uncertainty, and risk.

#### Contents

1. Introduction to climate risk
2. Overview of climate risk management
3. Levee Heightening As A Paradigmatic Problem
4. What is uncertainty?
5. Why does uncertainty matter?


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

### Exploratory Modeling

#### Goals

Demonstrate the purpose and some approaches to exploratory modeling and uncertainty characterization, including scenario analysis and sensitivity analysis.

#### Contents

1. What is Exploratory Modeling?
2. The Use (and Misuse) of Scenarios
3. Sensitivity Analysis

#### Objectives

At the end of this part, readers will be able to:

1. Articulate the purposes of exploratory modeling;
2. Identify appropriate uses and conclusions from scenario analyses;
3. Apply sensitivity analyses for factor ranking and fixing.

### Uncertainty Quantification

#### Goals

Introduce methods and goals for uncertainty quantification.

#### Contents

1. Why Quantify Uncertainties?
2. Parametric vs. Non-Parametric Statistics
3. Model Residuals and Discrepancies
4. Monte Carlo Simulation
5. The Bootstrap
6. Markov Chain Monte Carlo
7. Emulation of Complex Models

#### Learning Objectives

At the end of this part, readers will be able to:

1. Define uncertainty quantification;
2. Distinguish between the methods and assumptions for parametric, semi-parametric, and non-parametric approaches to statistics;
3. Conduct Monte Carlo simulation and compute Monte Carlo standard errors;
4. Quantify model uncertainties with the bootstrap and Markov chain Monte Carlo;
5. Demonstrate how emulation addresses the trade-off between model complexity and the ability to quantify uncertainties.
6. Evaluate different approaches to emulation based on problem characteristics.

### Extreme Value Analysis

#### Goals

Discuss approaches to analyzing extreme values, quantifying uncertainty, and representing nonstationarity.

#### Contents

1. Introduction to Extremes and Return Levels
2. Block Maxima
3. Peaks Over Thresholds
4. Non-Stationarity and Model Selection

#### Learning Objectives

At the end of this part, readers will be able to:

1. Distinguish between block maxima and peaks-over-threshold approaches to extreme value analysis;
2. Apply statistical methods to quantify uncertainty in extremes and return levels;
3. Select model structures using appropriate statistical methods.

### Uncertainty and Decision-Making

#### Goals

Introduce approaches to decision-making under uncertainty and illustrate the influence of uncertainty on decisions.

#### Contents

1. Approaches to Decision-Making
2. Risk and Utility
3. Decision-Making Under Uncertainty
3. Impact of Quantified Uncertainties on Decisions

#### Learning Objectives

At the end of this part, readers will be able to:

1. Apply simple optimization methods for decision-making;
2. Articulate the implications of utility functions and risk-aversion in decision-making under uncertainty;
3. Quantify the value of including uncertainty in decision-making and risk management.


### Deep Uncertainty

#### Goals

Define deep uncertainty and discuss the challenges deep uncertainties raise for UQ and decision-making.

#### Contents

1. Introduction to Deep Uncertainty
2. Aversion to Deep Uncertainty
3. Methods for Characterizing Deep Uncertainty
4. Approaches to Decision-Making Under Deep Uncertainty

#### Learning Objectives

At the end of this part, readers will be able to:

1. Distinguish between deep and well-characterized uncertainties;
2. Articulate how deep uncertainty manifests in climate risk management;
3. Use climate scenarios to characterize deep uncertainty;
4. Define and apply approaches to robustness under deep uncertainty.
