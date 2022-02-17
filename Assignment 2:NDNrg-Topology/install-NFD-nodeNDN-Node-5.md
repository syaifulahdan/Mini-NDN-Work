Getting Started with NFD Building from Source: https://named-data.net/doc/NFD/0.6.3/INSTALL.html

Downloading from Git The first step is to obtain the source code for NFD and, its main dependency, the ndn-cxx library. If you are not planning to work with the bleeding edge code, make sure you checkout the correct release tag (e.g., *-0.6.0) for both repositories:

Download NFD


**1. Clone & Install NFD**
<pre>
$ git clone — recursive https://github.com/named-data/NFD
</pre>

 

<pre>
$ cd NFD
$ ./waf configure
</pre>
 ![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node5/NDNrg-Image-NFD-5/nfd5-waf-configure.png)

 Show Progess nfd waf configure [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDNrg-Image-NFD-2/2-nfd2-waf-configure.png)

<pre>
$ ./waf
</pre>

Show Progess nfd waf [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/nfd2-waf-install-progress.txt)


<pre>
$ sudo ./waf install
</pre>
 ![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node5/NDNrg-Image-NFD-5/nfd5-waf-install.png)
 
 Show Progess nfd waf install [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/nfd2-waf-install-install-progress.txt)
 
 If you have installed ndn-cxx library and/or other dependencies into a non-standard path, you may need to modify PKG_CONFIG_PATH environment variable before running ./waf configure. For example,
<pre>
$  export PKG_CONFIG_PATH=/custom/lib/pkgconfig:$PKG_CONFIG_PATH
$ ./waf configure
$ ./waf
$ sudo ./waf install
</pre>
 
  ![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node5/NDNrg-Image-NFD-5/debugsymbol.png)
  
  Debug symbols The default compiler flags enable debug symbols to be included in binaries. This potentially allows more meaningful debugging if NFD or other tools happen to crash.

If it is undesirable, default flags can be easily overridden. The following example shows how to completely disable debug symbols and configure NFD to be installed into** /usr** with configuration in /etc folder

<pre>
CXXFLAGS="-O2" ./waf configure --prefix=/usr --sysconfdir=/etc
./waf
sudo ./waf install
</pre>

<pre>
$ CXXFLAGS="-O2" ./waf configure --prefix=/usr --sysconfdir=/etc
</pre>

![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node5/NDNrg-Image-NFD-5/debugsymbol2.png)

Running Starting If you have installed NFD from source code, it is recommended to start NFD with the nfd-start script:
<pre>
nfd-start
</pre>

<pre>
$ nfd-start
</pre>
