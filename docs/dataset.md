---
title: Base Dataset
layout: default
nav_order : 4
---

# Base Dataset 
`AdHocSim/dataset/dartmouthCleanedSimData` contains an example dataset based off a [MANET dataset of outdoor experments for comparing different routing algorithms](https://ieee-dataport.org/open-access/crawdad-dartmouthoutdoor). This was has been cleaned up and refined by the following process:
1. Removed nodes with no gps data
2. Moving the trace data from ARPL.data.parsed to a csv with columns: SRC, DEST, TIME, SIZE. 
3. Fixed erroneous location data
4. Fixed erroneous packet data
5. Formated the files into the [canonical format]({{site.baseurl}}/docs/usage/datasetMaker.html#format-of-the-dataset)
For the program to run successfully, network trace (dataset) must also include data of this form for each node.
TODO explain more