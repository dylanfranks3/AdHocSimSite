---
title: Base Dataset
layout: default
nav_order : 4
---

### Dataset 
/dataset contains related datasets based off a [MANET dataset of outdoor experments for comparing differnet routing algorithms](https://ieee-dataport.org/open-access/crawdad-dartmouthoutdoor). /dataset/outdoor-run-20031017 contains the cleaned data which has been processed by:
1. Removed nodes with no gps data
2. Moving the trace data from ARPL.data.parsed to a csv with columns: SRC, DEST, TIME, SIZE. 

For the program to run successfully, network trace (dataset) must also include data of this form for each node.
TODO explain more