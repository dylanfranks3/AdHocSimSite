---
layout: page
title: Runner CLI
parent: Usage
nav_order: 4
---
{: .no_toc }
# Runner CLI
1. TOC
{:toc}
## What This CLI Does...
The purpose of this CLI is to take a source code file defining a Simulation and create a runtime of this with customizability. 

 One creates a python file defining the simualation either based of their own code or the example files and passes this to the CLI using the `-d` coom

The CLI is avaible at (`AdHocSim/runner/__main__.py`).
## Usage
```bash
usage: __main__.py [-h] -d DIRECTORY [-m MODEL] [-v VISUALISE] [-l LOGGING]

SIMULATOR CLI TOOL

options:
  -h, --help            show this help message and exit
  -d DIRECTORY, --directory DIRECTORY
                        <Required> arg to pass the directory, see readme
  -m MODEL, --model MODEL
                        arg that decides the model, pass: normal, NAN
  -v VISUALISE, --visualise VISUALISE
                        arg whether to create a visualising .mp3 in exec path
  -l LOGGING, --logging LOGGING
                        arg whether to show state of network post execution in stdout
```
Here,
