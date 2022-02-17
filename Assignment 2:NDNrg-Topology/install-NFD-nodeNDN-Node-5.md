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
 ![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDNrg-Image-NFD-2/5-nfd2-waf-install.png)
 
 Show Progess nfd waf install [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/nfd2-waf-install-install-progress.txt)
