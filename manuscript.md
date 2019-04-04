---
author-meta:
- Ryan D Velazquez
date-meta: '2019-04-04'
keywords:
- software
- evolution
- statistical methods
- natural selection
lang: en-US
title: HyPhy - Title TBD
...






<small><em>
This manuscript
([permalink](https://rdvelazquez.github.io/hyphy_release_manuscript/v/7877c87ad3d3e0b17cf4538c1b21d3842053a551/))
was automatically generated
from [rdvelazquez/hyphy_release_manuscript@7877c87](https://github.com/rdvelazquez/hyphy_release_manuscript/tree/7877c87ad3d3e0b17cf4538c1b21d3842053a551)
on April 4, 2019.
</em></small>

## Authors



+ **Ryan D Velazquez**<br>
    · ![GitHub icon](images/github.svg){.inline_icon}
    [rdvelazquez](https://github.com/rdvelazquez)<br>
  <small>
     Institute for Genomics and Evolutionary Medicine, Temple University
  </small>



## Abstract {.page_break_before}

Here we announce the latest release of the HyPhy comparative sequence analysis software package. 
HyPhy is widely used, actively supported, open source and freely available on a multitude of platforms. 
The codebase is available at <https://github.com/veg/hyphy>. 
Documentation, tutorials and downloads are available at <https://hyphy.org>.

## Introduction

HyPhy (Hypothesis testing using Phyloginies) is an open source software package for comparative sequence analysis using stochastic evolutionary models. 
Since it’s initial release in 2005 [@OG5Jd8Ck] HyPhy has become an integral tool for the bioinformatics community with over 10,000 registered users, over 2,000 peer-reviewed citations and approximately 1,000 HyPhy jobs processed each week on the datamonkey web server [@E9o1eL84; @1DlzNU0dT; @1DPhLuJmc]. 
Extensions and improvements to the HyPhy package have been ongoing since its inception, with active feedback between users and developers producing new features tailored to the specific needs of the research community. 
Here we announce the release of the newest version of HyPhy (version 2.4.0) and document how the software has been (1) packaged for easy use in a variety of settings (2) optimized for larger datasets (3) redesigned to follow modern bioinformatics best practices and (4) extended to include common methods out of the box.

## Packaged for Easy Use in a Variety of Settings

The users of HyPhy vary greatly in their technical proficiency, from biologists unfamiliar with the command line to bioinformaticians who want to incorporate HyPhy into their own software. 
To meet the needs of this divers user set, HyPhy has been packaged and distributed for use in multiple different forms. 
These include:
  
+ Standard command line tool (Download: <https://github.com/veg/hyphy>; Tutorial: {to be written})  
+ Interactive command line prompt (Download: <https://github.com/veg/hyphy>; Tutorial: <http://hyphy.org/tutorials/current-release-tutorial/>)  
+ Datamonkey [@E9o1eL84; @1DlzNU0dT; @1DPhLuJmc] online web-server (datamonkey.hyphy.org)  
+ Desktop GUI application (Download: <https://github.com/veg/hyphy-gui>; Tutorial: <http://hyphy.org/tutorials/current-release-tutorial_gui/>)  
+ Galaxy [@WBsVRA32] Tools (Installable from the galaxy tool-shed; available pre-installed at <https://galaxy.hyphy.org>)  
+ Integration with the Python Programming Language via PhyPhy[@M8c1F3zk] (Download: <https://github.com/sjspielman/phyphy>; Tutorial: <http://sjspielman.org/phyphy/>)  
+ MEGA [@59wIwwiv] Integration (Download: <http://https://www.megasoftware.net/>)

## Optimized for Larger Datasets

HyPhy has been optimized to analyze datasets with thousands of sequences and tens of thousands of sites. 
This optimization was accomplished by (1) integrating recent algorithmic advances from the fields of machine learning and natural language processing [@TkofEaUO] into the core c++ implementation (2) incorporating fast Bayseian methods [@BLiAMJec] (3) developing parallel implementations for commute intensive porcesses and (4) providing high performance computing infrastructure[@E9o1eL84; @1DlzNU0dT; @1DPhLuJmc] free of charge to the global community, helping to democratize access to scientific compute resources [@16bcy34vy].

## Redesigned to Follow Modern Bioinformatics Best Practices

The design of the original HyPhy implementation emphasized convenient writing and execution of single HyPhy Batch Language (HBL) scripts. 
This decision manifested in the easy to use command line prompt which guided users interactively through selecting the desired analysis and choosing the specific analysis parameters. 
Also, the HBL itself was designed to allow sophisticated models to be specified and fit with concise scripts, facilitated by extensive use of a global namespace. 
As the common use of HyPhy has shifted over the last decade from one-off analyses toward larger studies and use within pipelines, the demands on HyPhy have also shifted. 
HyPhy has therefore been redesigned to address the requirements of these changing use cases. 
Specifically:  
  
+ HyPhy is now installable with bioconda [@sYguBb3Q] (cite conda) which has become the defacto package manager for scientific software. Users no longer need to concern themselves with dependencies, environments and build processes but can simple `conda install hyphy`.  
+ Usage as a typical command line tool (i.e. an executable name followed by key word arguments) has been added alongside the interactive command line prompt. This change, along with the ability to use relative paths to files has made using HyPhy in pipelines and batch analyses seamless.  
+ The extension of the HBL also included implementation of namespaces. Before, all variables were automatically and irrevocably declared at a global scope, which meant that declaring or modifying a variable i in one HBL script could affect the result in another script being run concurrently. Namespaces also facilitated the refactoring and standardization of the template batch files.  
+ Automated testing has been implemented including: unit tests on over 90% of HBL functions, method tests on all the core analyses, likelihood testing [@MOcKAui8] which compares the likelihood values calculated by HyPhy with other popular maximum-likelihood software packages and informs the developers if discrepancies are identified

## Extended to Provide Common Methods out of the Box

Although the HyPhy package provides for limitless customization via writing HBL scripts, users can run many common analyses without needing to concern themselves with the HBL at all. 
The HyPhy package comes with pre-written HBL scripts for easily performing some of the most commonly used analyses. 
These analyses can be executed in the various places HyPhy is available and include (in alphabetical order):  
  
+ aBSREL [@w4iHLQCq; @hX6CSnea] (adaptive Branch-Site Random Effects Likelihood) - Detecting positive selection at individual branches  
+ BGM [@V35tv36N] (Bayesian Graphical Models) - Testing for co-evolving sites  
+ BUSTED [@13wl6FKEJ] (Branch-Site Unrestricted Statistical Test for Episodic Diversification) - Testing gene-wide selection at pre-defined lineages  
+ FADE (FUBAR Approach to Directional Evolution) - Evaluating if sites are subject to directional selection  
+ FEL [@1AP8NmEKg] (Fixed Effects Likelihood) - Infeing nonsynoymous and synonymous substitution rates on a per-site basis for smaller datastes using maximum likelihood  
+ FUBAR (Fast, Unconstrained Bayesian AppRoximation) - Infer non-synonymous and synonymous substitution rates on a per-site basis for larger datasets using Bayesian methods  
+ GARD [@PTZuTBNs] (Genetic Algorithm for Recombination Detection) - Screen multiple sequence alignment for recombination  
+ MEME [@hI0YJStl] (Mixed Effects Model of Evolution) - Test the hypothesis that individual sites have been subject to episodic positive/diversifying selection  
+ RELAX [@OpDB3a8r] - Evaluate whether the strength of natural selection has been relaxed or intensified along a specific set of branches  
+ SLAC [@1AP8NmEKg] (SingleLikelihood Ancestor Counting) - Infer non synonymous and synonymous substitution rates on a per-site basis 

## References {.page_break_before}

<!-- Explicitly insert bibliography here -->
<div id="refs"></div>