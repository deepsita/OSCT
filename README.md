# VLSI Open-Source Tool Installation Instructions

Here’s a list of instructions to install various open-source tools for VLSI design, including Yosys, OpenROAD, Magic, KLayout, and NGspice. 
These steps are for Linux-based systems (typically Ubuntu or other Debian-based distributions). 
This requires a minimum of Ubuntu 20.04. 
Most of the below tools have dependencies packaged along with the source to build and compile. However, there could be requirements in the process that OS throws Warnings or Errors on the dependencies required. 

VLSI Flows: 
1. Semi Custom 
2. Full Custom 

List of tools required: 

1. Xschem
2. Ngspice
3. Magic
4. Klayout
5. Any RTL Simulator of choice 
6. Openroad flow

## Xschem
Github source : https://github.com/StefanSchippers/xschem

Installation steps: 
   
    git clone https://github.com/StefanSchippers/xschem.git xschem-src
    cd xschem-src
    ./configure
    sudo make install

Test the setup:

    xschem

## Ngspice
This is a packaged tool and hence can be directly downloaded, installed. 
The source to do so is [here](https://ngspice.sourceforge.io/download.html).

## Magic
Project Page : http://opencircuitdesign.com/magic/

Installation steps: 

    git clone https://github.com/RTimothyEdwards/magic
    ./configure [options]
	make
	make install
Look for INSTALL file to know more about the [options]

## Klayout

This is a packaged tool, can be downloaded and built from [here](https://www.klayout.de/build.html).

## Openroad
RTL-to-GDS flow built entirely on open-source tools. 
To build the binaries and run gcd through the flow:

    Minimum: 1 CPU core and 8GB RAM.

    Recommended: 4 CPU cores and 16GB of RAM.

Installation Methods

1. Docker
2. Pre-built Binaries
3. WSL               - Not Recommended
4. Local Installation



The following instructions install & build using Local Installation

    git clone --recursive https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts

    cd OpenROAD-flow-scripts
    
    sudo ./setup.sh

    ./build_openroad.sh --local

Verify Installation :

The binaries should be available on your $PATH after setting up the environment.

    source ./env.sh
    yosys -help
    openroad -help
    cd flow
    make

Environment variables are used in the OpenROAD flow to define various platform, design and tool specific variables to allow finer control and user overrides at various flow stages. These are defined in the config.mk file located in the platform and design specific directories.

Following the steps outlined above, you can set up all the essential open-source tools for VLSI design. Ensure that your system has the required dependencies installed before proceeding with the installations. These tools are regularly updated, so it's a good practice to periodically check for updates to take advantage of new features or bug fixes.


Thanks to the open source community that democratised chip design.
Join the Opensource silicon community available at Slack [here](https://join.slack.com/t/open-source-silicon/shared_invite/zt-2sebfx2xj-keD_BjeM7E6nk3GTzRtQ~w).

