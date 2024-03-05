---
layout: page
title: Dataset CLI
parent: Usage
nav_order: 2
---
{: .no_toc }
# Dataset
1. TOC
{:toc}
## What This CLI Does...
Creating a dataset has never been easier. This model creates custom stochastic random walks based off set variables given to the CLI (`AdHocSim/dataset/__main__.py`).
## Usage
### Commands
```
usage: __main__.py [-h] -d DIR -i INTERVAL -nc NODECOUNT -x XSIZE -y YSIZE -t TIME [-p {low,med,high}] [-v {low,med,high}]

DATASET CLI TOOL

options:
  -h, --help            show this help message and exit
  -d DIR, --dir DIR     <Required> arg to the path that you\'d like to create the new dataset in, if it is no
  -i INTERVAL, --interval INTERVAL
                        <Required> arg for size of the interval within the sim
  -nc NODECOUNT, --nodeCount NODECOUNT
                        <Required> arg for the number of nodes
  -x XSIZE, --xSize XSIZE
                        <Required> arg for the width of the simulation area
  -y YSIZE, --ySize YSIZE
                        <Required> arg for the height of the simulation area
  -t TIME, --time TIME  <Required> arg for the running time of the simulation
  -p {low,med,high}, --packetSize {low,med,high}
                        optional arg for the distribution of a packet
  -v {low,med,high}, --volume {low,med,high}
                        optional arg for the volume of packet generation per node per unique recipitent
```

## Format of The Dataset
When creating a simulation of a network, a routing table of sorts is necessary. Within Ad-HocSim this can either be provided, or be created. Either way the format of the dataset must be of the following:
```
.../alldatasets/exampleDataset
├── 1
│   ├── 1.data.csv
│   └── 1.position.csv
├── 12
│   ├── 12.data.csv
│   └── 12.position.csv
...
```
Where the base of a dataset is `exampleDataset` and each directory within it (`1`,`12`) denotes a single **NODE**, containing files:
- `{NODE}.data.csv`
- `{NODE}.position.csv`.

Where they include data (routing table) and position (geographic) in .csv format respectively.

Here is the canonical data file:

| PacketSize(bytes) | Time     | Source        | Dest          |
| ----------------- | -------- | ------------- | ------------- |
| float             | 0<=float | 11.0.0.{NODE} | 11.0.0.{NODE} |
| ...               | ...      | ...           | ...           |


...and here is the canonical position file:


| Time     | xPos  | yPos  | zPos  |
| -------- | ----- | ----- | ----- |
| 0<=float | float (meters) | float(meters) | float(meters) |
| ...      | ...   | ...   | ...   |


{: .note }
For clarity,  `xPos`, `yPos` and `zPos` can have any range, but must be float. After running the simulation, they are converted to scale for visualisation.


## Example
Suppose we wanted to create a dataset of 30 nodes in a 300x300 meter plane over a 800 second time period with a 0.5 second interval on the granularity of the dataset: 
```bash
./__main__.py -d {datasetsAbsPathHome}/example30Nodes -nc 30 -x 300 -y 300 -t 800 -i 0.5
```
This command will create a directory over at `{datasetsAbsPathHome}/example30Nodes` with 30 sub-directories ranging from 1-30, each containing their own respective data and position files. 
