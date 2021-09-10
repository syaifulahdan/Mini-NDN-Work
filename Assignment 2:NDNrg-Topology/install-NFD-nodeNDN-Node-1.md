Getting Started with NFD Building from Source: https://named-data.net/doc/NFD/0.6.3/INSTALL.html

Downloading from Git
The first step is to obtain the source code for NFD and, its main dependency, the ndn-cxx library. If you are not planning to work with the bleeding edge code, make sure you checkout the correct release tag (e.g., *-0.6.0) for both repositories:


**Download NFD**
<pre>
$git clone --recursive https://github.com/named-data/NFD
</pre>

<pre>
bertopeng17-1@NDN-Node1-ITB:~$ **git clone --recursive https://github.com/named-data/NFD**
Cloning into 'NFD'...
remote: Enumerating objects: 17722, done.
remote: Counting objects: 100% (596/596), done.
remote: Compressing objects: 100% (498/498), done.
remote: Total 17722 (delta 378), reused 314 (delta 96), pack-reused 17126
Receiving objects: 100% (17722/17722), 7.81 MiB | 1.15 MiB/s, done.
Resolving deltas: 100% (13852/13852), done.
Submodule 'websocketpp' (https://github.com/cawka/websocketpp.git) registered for path 'websocketpp'
Cloning into '/home/bertopeng17-1/NFD/websocketpp'...
remote: Enumerating objects: 12253, done.        
remote: Total 12253 (delta 0), reused 0 (delta 0), pack-reused 12253        
Receiving objects: 100% (12253/12253), 8.68 MiB | 901.00 KiB/s, done.
Resolving deltas: 100% (7417/7417), done.
Submodule path 'websocketpp': checked out 'ac4e021333675fc80b96eb7be45d218581c897e2'
bertopeng17-1@NDN-Node1-ITB:~$ 
</pre>

![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image/gitclonenfd.png)

**Install On Ubuntu 18.04**
<pre>
$sudo apt-get install build-essential pkg-config libboost-all-dev \libsqlite3-dev libssl-dev libpcap-dev
</pre>


