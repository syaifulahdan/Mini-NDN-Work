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

 # ndn-tools Build Instructions

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

    ./waf configure
    ./waf
    sudo ./waf install

To uninstall ndn-tools:

    sudo ./waf uninstall
*** 
 
### 3.1. Install Node 1 (ITB) 
   ***
   - Installing ndn-cxx [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/install-nodeNDN-Node-1.md)
   - Installing NFD [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/install-NFD-nodeNDN-Node-1.md)
   - Installing NLSR [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/install-NLSR-nodeNDN-Node-1.md)  
   - Installing PSync [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/install-PSync-nodeNDN-Node-1.md)
   - Installing ChronoSync [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/install-Chronosync-nodeNDN-Node-1.md)
   - NLSR
      - Router Configuration [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/router-config-Node-1.md)
      - Configuring NLSR  [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NLSR-Configuring-Node1.md)
      - Setup the Security [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NLSR-Settingup-security-Node1.md)
      - Configuring The Network
      - Setting Up the Configuration file : <b>nlsr-itb.conf</b> [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NLSR-setting-upthe-configurationfile-node1.md), <b>nlsr-itb-5 Node.conf</b> [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NLSR-setting-upthe-configurationfile-node1-5node.md)
      - Starting NLSR [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NLSR-starting-Node1.md)
   - NFD
      - Configuring the Network [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NFD-configuring-network-node1.md)
      - Starting and configuring NFD [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NFD-starting-node1.md)
      - NFD Configuration [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NFD-Node1-Configuration.md)
*** 
