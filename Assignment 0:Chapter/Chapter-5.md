***
## NDN Essential Tools 
Source : [[named-data.net]](https://named-data.net/codebase/platform/) ndn-tools is a collection of basic tools for Named Data Networking. Tools in this collection include:
***
  
    
![[peek]](https://github.com/named-data/ndn-tools/blob/master/tools/peek): transmit a single Interest/Data packet between a consumer and a producer

![[chunks]](https://github.com/named-data/ndn-tools/blob/master/tools/chunks): segmented file transfer between a consumer and a producer

![[ping]](https://github.com/named-data/ndn-tools/blob/master/tools/ping): test reachability between two NDN nodes

![[dump]](https://github.com/named-data/ndn-tools/blob/master/tools/dump): capture and analyze live traffic on an NDN network

![[dissect]](https://github.com/named-data/ndn-tools/blob/master/tools/dissect): inspect the TLV structure of an NDN packet

![[dissect-wireshark]](https://github.com/named-data/ndn-tools/blob/master/tools/dissect-wireshark): Wireshark extension to inspect the TLV structure of NDN packets
***

 ## ndn-tools Build Instructions

This document describes how to build and install ndn-tools.

## Prerequisites

-  Install the [ndn-cxx](https://named-data.net/doc/ndn-cxx/current/) library and its prerequisites.
   Please see [Getting Started with ndn-cxx](https://named-data.net/doc/ndn-cxx/current/INSTALL.html)
   for how to install ndn-cxx.
   Note: If you have installed ndn-cxx from a binary package, please make sure development headers
   are installed (e.g., if using Ubuntu PPA, the `libndn-cxx-dev` package is needed).

   Any operating system and compiler supported by ndn-cxx is supported by ndn-tools.

-  `libpcap`

    Comes with the base system on macOS.

    On Ubuntu:

        sudo apt install libpcap-dev
 
## Build Steps

To configure, compile, and install ndn-tools, type the following commands
in ndn-tools source directory:
<pre>
    ./waf configure
    ./waf
    sudo ./waf install
</pre>

To uninstall ndn-tools:
<pre>
    sudo ./waf uninstall
 </pre>   
    
    PROBLEM libndn-cxx not found https://named-data.net/doc/ndn-cxx/current/releases.html#all-ndn-cxx-releases

<pre>
sudo add-apt-repository ppa:named-data/ppa
sudo apt-get update
sudo apt-get install ndn-cxx-dev
</pre>

PROBLEM SPHINX ERROR / UPGRADE SPINX (https://askubuntu.com/questions/1050447/how-to-upgrade-sphinx)
<pre>
sudo apt-get install sphinxsearch
sphinx-build --version
pip3 install git+https://github.com/sphinx-doc/sphinx
</pre>
    
    
*** 
 
 
 
 
## 5.1. Install NDN Essential Tools Node 1 (ITB) 
   ***
   


- Installing Peek [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/install-nodeNDN-Node-1.md)
   - Installing Chunk [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/install-nodeNDN-Node-1.md)
   - Installing Ping [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/install-nodeNDN-Node-1.md)
   - Installing Dump [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/install-nodeNDN-Node-1.md)
   - Installing dissect [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/install-nodeNDN-Node-1.md)
   - Installing dissect-wireshark: [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/install-nodeNDN-Node-1.md)

## 5.3. Install NDN Essential Tools Node 3 (Tel-U) 
   ***
   - Installing Peek [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/install-nodeNDN-Node-1.md)
   - Installing Chunk [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/install-nodeNDN-Node-1.md)
   - Installing Ping [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/install-nodeNDN-Node-1.md)
   - Installing Dump [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/install-nodeNDN-Node-1.md)
   - Installing dissect [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/install-nodeNDN-Node-1.md)
   - Installing dissect-wireshark: [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/install-nodeNDN-Node-1.md)


    
*** 
