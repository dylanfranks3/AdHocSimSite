---
layout: default
title: Structure
parent: Usage
nav_order: 1
---
# Structure
1. TOC
{:toc}
The general class structure of this package is based off the ns3 library with limited dependency on it itself. The library itself has base functionality with root classes with the possibility to extend these with child classes. 

{: .note }
See [nanNetwork, nanNode etc](https://github.com/dylanfranks3/AdHocSim/src) for an example based off of [NAN](https://ieeexplore.ieee.org/document/7096294), an Ad-Hoc networking protocol that gives nodes a roles changing their behaviour. 

## Package Structure
![packages]({{site.baseurl}}/assets/packages.png){:width="70%"}{:style="display:block; margin-left:auto; margin-right:auto"}

## Class Structure

![classes]({{site.baseurl}}/AdHocSimSite/assets/classes.png){:width="90%"}{:style="display:block; margin-left:auto; margin-right:auto"}

## File structure
``` bash
AdHocSim/
├── __init__.py
├── dataset
│   ├── __main__.py
│   └── dataset.py
├── location.py
├── nanNetwork.py
├── nanNode.py
├── network.py
├── node.py
├── packet.py
├── runner
│   ├── __main__.py
│   └── runner.py
└── simulator.py
```



### Network model







- Simulator(class)
    - do ur things

- Network(class)
    - Attributes:
        - node container -> list of node(class)
        - time (wrt. start time of sim) -> float 
        - length of sim -> float
        - output(whether to show std.out) -> bool 
        - interval (how long each time interval is) -> float
    - Modules:
        - nextInterval()
            - check if time + interval > length of sim
            - time += interval
            - iterate nodes
        - statisitcal ones

- NANNetwork(class, parent network):
    - Attributes (append as above):
    - Modules:
        - tell nodes to do things with their roles (pass the NANNetwork instance to the function so it can acess data about the nodes)
        - More analytical (calcRolePercentage)
        


- Node(class)
    - Attributes:
        - location (x,y,z) -> class
        - trace -> path to dataset
            - use [this](https://arc.net/l/quote/tiraorhu)
        - index (current in dataset) -> integer
        - data recieved, data sent -> dictionary/json

    - Modules:
        - updateLocation
            - change index as well

- NANNode(class, parent Node):
    - Attributes:
        - masterPreference -> float

        - 
    - Modules:
        - Related NAN modules TODO


- Location(class)
    - Attributes:
        - pos = [x,y,z]
    - Modules:
        - updateLocation(newLocation)
        - static: distane(pos1,pos2)



### What i want the 'direct' program to do:
1. Create nodes
2. create network
3. create sim
4. add location movements of nodes to requests
5. add packets at time 0 to source of nodes
6. add requests of packet sending 

