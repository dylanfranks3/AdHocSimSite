---
layout: default
title: Install Directly From Source
parent: Installation
nav_order: 1
---
# Install Directly From Source
1. TOC
{:toc}

{: .note }
Note, for the most part, this installation is generally *easiest* when **not** using Macos silicon as the Python bindings for ns-3 is not well supported for this hardware. As a general reccomendation, the installation is easier using any basic Linux distro, e.g. Ubuntu, Debian, Fedora etc. 
## Installing Via Docker
The prerequestites for this package can be installed using docker. A [Dockerfile](https://github.com/dylanfranks3/AdHocSim/blob/testingSim/.devcontainer/Dockerfile) is available at `AdHocSim/.devcontainer/Dockerfile` which spins up a ubuntu system and installs all the required prerequisites, ready for [usage](/docs/usage/index.html). Note there is also a [devcontainer.json](https://github.com/dylanfranks3/AdHocSim/blob/testingSim/.devcontainer/devcontainer.json) available at `AdHocSim/.devcontainer/devcontainer.json` for ease of dockerization. 
## Installing Directly
1. If you are using this as standalone tool, clone this repo into your working directory:
``` bash
git clone https://github.com/dylanfranks3/AdHocSim
```
Otherwise, fork this [repo](https://github.com/dylanfranks3/AdHocSim/fork) and then clone the repo:
``` bash
git clone https://github.com/{insertYourAccountName}/AdHocSim
```
2. Head over to the `root` directory and using a Python environment (version >= 3.12) or otherwise install the libraries as follows, ensuring they're installed correctly:
``` bash
cd AdHocSim 
pip install -r requirements.txt
pip list
``` 
### ns3
3. Now, install ns3: 
``` bash
mkdir ns3 
wget https://www.nsnam.org/release/ns-allinone-3.38.tar.bz2
tar -jxvf ns-allinone-3.38.tar.bz2
```
Build:
``` bash
cd ns-allinone-3.38
./build.py --enable-examples --enable-tests
```
Now symlink the install:
``` bash
ln -s ns-3.38/ ../ns3/
```
Clean up and configure:
``` bash
rm ns-allinone-3.38.tar.bz2
cd ns-3.38
./ns3 build
./ns3 configure --enable-python-bindings
```
