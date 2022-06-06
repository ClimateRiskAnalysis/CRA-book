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
  + What Is Climate Risk? (Klaus Keller and Vivek Srikrishnan)
  + Why is Uncertainty Important? (Vivek Srikrishnan, James Doss-Gollin, and Klaus Keller)
  + Types of Uncertainty (Vivek Srikrishnan and Klaus Keller)
  + What Are Approaches to Risk Analysis? (Vivek Srikrishnan and Klaus Keller) 
  + The Role of Prior Distributions (Vivek Srikrishnan, Ben S. Lee, and James Doss-Gollin)
* Software Tools
  + Julia Basics (Vivek Srikrishnan and James Doss-Gollin)
  + Tools for Risk Analysis in Julia (Vivek Srikrishnan and James Doss-Gollin)
* Case Study 1: Coastal Flood Risk
  + Climate Change and Coastal Flood Risk
  + Framing the Problem
  + Modeling Sea-Level Rise
    - Specifying a Likelihood Function (Vivek Srikrishnan, Kelsey L. Ruckert, and Klaus Keller)
    - Frequentist Method: The Bootstrap (Vivek Srikrishnan, Patrick L. Applegate, and Klaus Keller)
    - Bayesian Method: Markov Chain Monte Carlo  (Kelsey L. Ruckert, Tony E. Wong, Ben S. Lee, Yawen Guan, Vivek Srikrishnan, and Murali Haran)
  + Characterizing Tidal Extremes
    - Fat-Tailed Distributions and Risk (Ben S. Lee, James Doss-Gollin, Vivek Srikrishnan, and Klaus Keller)
    - Storm Surge Extremes and Model Selection (Tony E. Wong, James Doss-Gollin, and Vivek Srikrishnan)
  + The Impact of Risk Analysis on Seawall Height (Vivek Srikrishnan and Klaus Keller)
  + The Levee Effect: Socioeconomic Scenarios and Risk (Vivek Srikrishnan and Klaus Keller)
* Case Study 2: Climate-System Uncertainty
  + A Simple Climate Model (Vivek Srikrishnan, Ryan L. Sriver, and Klaus Keller)
  + Emulation and Surrogate Modeling (Ben S. Lee, Vivek Srikrishnan, and Klaus Keller)
  + Applying Emulation to Climate Modeling (Vivek Srikrishnan, Ben S. Lee, Tony E. Wong, and Klaus Keller)
* Case Study 3: What Drives Baseline CO_2 Emissions?
  + A Simple Mechanistic Model of CO_2 Emissions (Vivek Srikrishnan and Klaus Keller)
  + Sensitivity Analysis of Future CO_2 Emissions (Tony E. Wong, Vivek Srikrishnan, and Klaus Keller)
    - Simple Sensitivity Analyses (Tony E. Wong, Kelsey Ruckert, Vivek Srikrishnan, and Klaus Keller)
    - Global Sensitivity Analyses (Tony E. Wong, Kelsey Ruckert, Vivek Srikrishnan, and Klaus Keller)
* Case Study 4: Forest Fire Risk
  + Spatial Modeling (Ben S. Lee, James Doss-Gollin, Vivek Srikrishnan, and Klaus Keller)
  + Selecting a Variogram (Ben S. Lee, James Doss-Gollin, Vivek Srikrishnan, and Klaus Keller)
* Case Study 5: The Impact of Hydrologic Variability on Energy Systems[^1]

[^1]: This would be good to develop to introduce machine learning and energy applications. I could ask Scott Steinschneider, Lindsay Anderson, and Vivienne Liu (Lindsay's Ph.D student) to be co-authors? We'd be building off their work.
