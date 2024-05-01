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

One creates a python file defining the simulation either based of their own code or the example files and passes this to the CLI using the `--directory` argument. 

{: .note }
In order for Python to find AdHocSim, if you haven't installed this as a apckage, you must set the directory in your environment variable (`$PYTHONPATH`).

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
- `--logging` is a binary argument, essentially acting as --verbose in the running time of the simulation. 
- `--model` allows one to pass in what model the runner will use to decide the flow of packets across the network.
- `--visualise` is a binary arguement deciding whether the model will output a manim visualisation of the simulation. This will show the nodes moving and packets being sent.

## Example
Suppose we'd like to run a NAN model on our dataset created in the example [Dataset CLI page]({{site.baseurl}}/docs/usage/datasetMaker.html#example-usage), we can run the following command:
```
AdHocSim/runner/__main__.py -d {datasetsAbsPathHome}/example30Nodes -m NAN -v True
```
Here we would get a .mp4 output looking something like this:
<video width="800" muted autoplay controls>
    <source src="{{site.baseurl}}/assets/exampleRunthrough.mp4" type="video/mp4">
</video>