---
layout: page
title: Structure
parent: Usage
nav_order: 1
---
{: .no_toc }
# Structure
1. TOC
{:toc}

This page intends to give a high-level overview of the structure of the package, useful for later reference. 

The general class structure of this package is based off the ns3 library with limited dependency on it itself. The library itself has base functionality with root classes with the possibility to extend these with child classes. 


{: .note }
See [nanNetwork, nanNode etc](https://github.com/dylanfranks3/AdHocSim/src) for an example based off of [NAN](https://ieeexplore.ieee.org/document/7096294), an Ad-Hoc networking protocol that gives nodes a roles changing their behaviour. 

## Package Structure
![packages]({{site.baseurl}}/assets/packages.png){:width="70%"}{:style="display:block; margin-left:auto; margin-right:auto"}

## Class Structure

![classes]({{site.baseurl}}/assets/classes.png){:width="90%"}{:style="display:block; margin-left:auto; margin-right:auto"}

## File Structure
```
AdHocSim/
├── __init__.py
├── classes.png
├── dataset
│   ├── __init__.py
│   ├── __main__.py
│   └── dataset.py
├── location.py
├── nanNetwork.py
├── nanNode.py
├── network.py
├── node.py
├── packages.png
├── packet.py
├── runner
│   ├── __init__.py
│   ├── __main__.py
│   ├── runner.py
│   └── utils
│       └── minimumBoundingBox.py
└── simulator.py
```