# WEEK 0 - Thu, 18 Sep 2025 – Wed, 24 Sep 2025

## Environment + RTL sim basics

**Task 1: Create GitHub repo** 
+ https://github.com/eceelango/Elango_RISC-V-Chip-Tapeout-Program
  
**Task 2: Tool Installation**
  ## Tools installation instructions
 + Oracle virtual machine link : https://www.virtualbox.org/wiki/Downloads
   
**System Check**
+ 6GB RAM, 50 GB HDD
+ Ubuntu 20.04+
+ 4vCPU 

<img width="981" height="480" alt="System Details" src="https://github.com/user-attachments/assets/92a6a29f-0acd-413b-9392-31fbca24488b" />


**Yosys**
```
$ sudo apt-get update
$ git clone https://github.com/YosysHQ/yosys.git
$ cd yosys
$ sudo apt install make               # If make is not installed
$ sudo apt-get install build-essential clang bison flex \
    libreadline-dev gawk tcl-dev libffi-dev git \
    graphviz xdot pkg-config python3 libboost-system-dev \
    libboost-python-dev libboost-filesystem-dev zlib1g-dev
$ make config-gcc
# Yosys build depends on a Git submodule called abc, which hasn't been initialized yet. You need to run the following command before running make
$ git submodule update --init --recursive
$ make 
$ sudo make install
```
<img width="905" height="516" alt="Yosys" src="https://github.com/user-attachments/assets/be57dc4a-39a5-46f8-98e3-5cbeefa8ab49" />


**iVerilog**
```
$ sudo apt-get update
$ sudo apt install gtkwave
```
<img width="940" height="582" alt="iVerilog" src="https://github.com/user-attachments/assets/0f111649-731c-495e-ab49-d00747cee088" />

**GTKWAVE**
```
$ sudo apt-get update
$ sudo apt install gtkwave
```
<img width="866" height="129" alt="GTKWave" src="https://github.com/user-attachments/assets/b8caf5ca-ef29-416f-a289-5043c0891222" />

