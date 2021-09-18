Getting Started with NFD Building from Source: https://named-data.net/doc/NFD/0.6.3/INSTALL.html

Downloading from Git
The first step is to obtain the source code for NFD and, its main dependency, the ndn-cxx library. If you are not planning to work with the bleeding edge code, make sure you checkout the correct release tag (e.g., *-0.6.0) for both repositories:


**Download NFD**
<pre>
$ git clone --recursive https://github.com/named-data/NFD
</pre>


![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NDNrg-Image-NFD-1/gitclone-nfd1.png)

**Prerequisites**
Install the ndn-cxx library and its prerequisites.
On Linux, NFD needs the following dependencies to enable optional features:

<pre>
sudo apt install libpcap-dev libsystemd-dev
</pre>

![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NDNrg-Image-NFD-1/install-libcap-dev-libsystem-dev.png)




<pre>
$ sudo apt-get install build-essential pkg-config libboost-all-dev \libsqlite3-dev libssl-dev libpcap-dev
</pre>
![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image/nfdprequisit.png)


<pre>
$ sudo apt-get install doxygen graphviz python-sphinx
</pre>

![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NDNrg-Image-NFD-1/prequisit2nfd.png)

Show document install : sudo apt-get install doxygen graphviz python-sphinx :[[read]] (https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/prequisite2nfd.txt) 


**Build**

The following basic commands should be used to build NFD on Ubuntu:
<pre>
./waf configure
./waf
sudo ./waf install
</pre>

<pre>
$ ./waf configure
</pre>
![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NDNrg-Image-NFD-1/nfd1-waf-configure.png)

Noted:
Checking for 'libsystemd'                : **not found**
 
checking for header valgrind/valgrind.h  : **not found**

Show Document .waf configure : [[read]] (https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/nfd1-waf-configure.txt)

<pre>
$ ./waf
</pre>


![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NDNrg-Image-NFD-1/nfd1-waf.png)


<pre>
$ sudo ./waf install
</pre>

![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NDNrg-Image-NFD-1/nfd1-waf-install.png)

 If you have installed **ndn-cxx** library and/or other dependencies into a non-standard path, you may need to modify **PKG_CONFIG_PATH** environment variable before running **./waf configure**. For example,
 
 <pre>
$  export PKG_CONFIG_PATH=/custom/lib/pkgconfig:$PKG_CONFIG_PATH
$ ./waf configure
$ ./waf
$ sudo ./waf install
 </pre>
 
![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NDNrg-Image-NFD-1/nfd1-exporPKG.png)

**Debug symbols**
The default compiler flags enable debug symbols to be included in binaries. This potentially allows more meaningful debugging if NFD or other tools happen to crash.

If it is undesirable, default flags can be easily overridden. The following example shows how to completely disable debug symbols and configure NFD to be installed into** /usr** with configuration in **/etc** folder
<pre>
CXXFLAGS="-O2" ./waf configure --prefix=/usr --sysconfdir=/etc
./waf
sudo ./waf install
</pre>


<pre>
$ CXXFLAGS="-O2" ./waf configure --prefix=/usr --sysconfdir=/etc
</pre>

![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NDNrg-Image-NFD-1/debugsymbol.png)

**Running**
Starting
If you have installed NFD from source code, it is recommended to start NFD with the nfd-start script:
<pre>
nfd-start
</pre>

<pre>
$ nfd-start
</pre>

