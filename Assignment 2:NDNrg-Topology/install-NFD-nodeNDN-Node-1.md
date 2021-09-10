Getting Started with NFD Building from Source: https://named-data.net/doc/NFD/0.6.3/INSTALL.html

Downloading from Git
The first step is to obtain the source code for NFD and, its main dependency, the ndn-cxx library. If you are not planning to work with the bleeding edge code, make sure you checkout the correct release tag (e.g., *-0.6.0) for both repositories:


**Download NFD**
<pre>
$ git clone --recursive https://github.com/named-data/NFD
</pre>


![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image/gitclonenfd.png)

**Prerequisites**

<pre>
$ sudo apt-get install build-essential pkg-config libboost-all-dev \libsqlite3-dev libssl-dev libpcap-dev
</pre>
![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image/nfdprequisit.png)


<pre>
$ sudo apt-get install doxygen graphviz python-sphinx
</pre>

![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image/prequisit2nfd.png)

Show document install : sudo apt-get install doxygen graphviz python-sphinx : https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-doc-Install/prerequisites-nfd.txt


**Build**
The following basic commands should be used to build NFD on Ubuntu:
<pre>
$ ./waf configure
$ ./waf
$ sudo ./waf install
</pre>



<pre>
$sudo apt-get install nfd
</pre>


<

