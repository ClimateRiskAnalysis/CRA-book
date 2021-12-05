# An Introduction to Climate Risk Analysis 

Edited by Vivek Srikrishnan and Klaus Keller

Contributions by Patrick J. Applegate, Vivek Srikrishnan, Tony E. Wong, James Doss-Gollin, Ryan L. Sriver, Kelsey L. Ruckert, Ben S. Lee, Murali Haran, Yawen Guan, and Klaus Keller

## Preamble

This Github repository contains the complete source code needed to generate the freely-available, open-source e-textbook, [*An Introduction to Climate Risk Management*](https://viveks.me/CRA-book).  The repository also contains the code examples that accompany the book. These code examples are in the [Julia programming language](https://julialang.org/).

We’d like to make *An Introduction to Climate Risk Analysis* as useful as possible. If you find a bug or have a comment about the book or a question about one of the exercises, please post an issue to this Github repository.

## Overview

Greenhouse gas emissions have caused considerable changes in climate, including increased surface air temperatures and rising sea levels.  Rising sea levels increase the risks of flooding for people living near the world's coastlines.  Managing such risks requires an understanding of many fields, including Earth science, statistics, and economics.  

*An Introduction to Climate Risk Analysis* teaches a framework for integrating Earth science and statistical concepts needed to analyze climate-related risks. We cover a range of topics relevant to probability, uncertainty quantification and characterization, and so individual chapters could be relevant for various audiences.

This work was supported by the National Science Foundation through the Network for Sustainable Climate Risk Management (SCRiM) under NSF cooperative agreement GEO-1240507. Any opinions, findings, and conclusions or recommendations expressed in this material are those of the author(s) and do not necessarily reflect the views of the National Science Foundation. Other support was provided by the Center for Climate Risk Management and the Rock Ethics Institute.

## Topics Included

* Introduction
  + Julia Basics (Vivek Srikrishnan and James Doss-Gollin)
  + Climate Change and Risk (Vivek Srikrishnan and Klaus Keller)
  + Types of Uncertainty (Vivek Srikrishnan and Klaus Keller)
  + Why Is Uncertainty Important? (Vivek Srikrishnan and Klaus Keller)
* Probability and Monte Carlo Simulation
  + What is Probability? (Vivek Srikrishnan and Klaus Keller)
  + *Is My Data Normally-Distributed?* (Vivek Srikrishnan and Patrick L. Applegate)
  + *Probability Distributions and Random Sampling* (Vivek Srikrishnan and Patrick L. Applegate)
  + Fat-Tailed Distributions and Risk (Ben S. Lee, James Doss-Gollin, Vivek Srikrishnan, and Klaus Keller)
  + Introduction to Monte Carlo Simulation (Vivek Srikrishnan)
* Uncertainty Quantification: Methods and Applications
  + When Is Uncertainty Quantification Appropriate? (Vivek Srikrishnan and Klaus Keller)
  + *Coin-flipping and the Bootstrap* (Vivek Srikrishnan, Patrick L. Applegate, and Klaus Keller)
  + *Fitting a Polynomial Model for Sea-Level Rise* (Vivek Srikrishnan, Patrick L. Applegate, and Ryan L. Sriver)
  + The Role of Prior Distributions (Vivek Srikrishnan, Ben S. Lee, and James Doss-Gollin)
  + *Bayesian Inference and Markov Chain Monte Carlo Basics* (Kelsey L. Ruckert, Tony E. Wong, Ben S. Lee, Yawen Guan, and Murali Haran)
  + *Calibrating Models with Markov Chain Monte Carlo* (Kelsey L. Ruckert, Tony E. Wong, Yawen Guan, Murali Haran, and Patrick L. Applegate)
  + *Applying Markov Chain Monte Carlo to Sea-Level Rise Data* (Kelsey L. Ruckert, Tony E. Wong, Yawen Guan, and Murali Haran)
  + Storm Surge Extremes and Model Selection (Tony E. Wong, James Doss-Gollin, and Vivek Srikrishnan)
  + Emulation and Surrogate Modeling (Ben S. Lee, Vivek Srikrishnan, and Klaus Keller)
  + Applying Emulation to Climate Modeling (Vivek Srikrishnan, Ben S. Lee, Tony E. Wong, and Klaus Keller)
  + Parallel Methods and Sequential Monte Carlo (Ben S. Lee, Vivek Srikrishnan, and Tony E. Wong)
* Sensitivity Analysis
  + What is Sensitivity Analysis? (Vivek Srikrishnan and Tony E. Wong)
  + *Simple Sensitivity Analyses For A Simple Sea-Level Rise Model* (Tony E. Wong, Kelsey Ruckert, Vivek Srikrishnan, and Klaus Keller)
  + Global Sensitivity Analyses (Tony E. Wong and Vivek Srikrishnan)
  + Closing The Loop: Using Sensitivity Analyses to Inform Uncertainty Quantification (Vivek Srikrishnan, Tony E. Wong, and Klaus Keller)

## Compiling This Book

This book is compiled into `.html`, `.pdf`, and `.epub` versions using [`Bookdown`](https://bookdown.org/). The Julia code interface is provided with the [`JuliaCall`](https://hwborchers.github.io/) R package.

To compile the book yourself (**add more on this**).