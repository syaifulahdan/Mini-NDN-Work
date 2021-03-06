Getting Started with NFD Building from Source: https://named-data.net/doc/NFD/0.6.3/INSTALL.html

Downloading from Git The first step is to obtain the source code for NFD and, its main dependency, the ndn-cxx library. If you are not planning to work with the bleeding edge code, make sure you checkout the correct release tag (e.g., *-0.6.0) for both repositories:

Download NFD


**1. Clone & Install NFD**
<pre>
$ git clone — recursive https://github.com/named-data/NFD
</pre>

 ![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node4/NDNrg-Image-NFD-4/1-gitclone-nfd.png)
 

<pre>
$ cd NFD
$ ./waf configure
</pre>
 ![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node4/NDNrg-Image-NFD-4/2-nfd4-waf-configure.png)
 
 Show Progess nfd waf configure [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node4/NDNrg-Image-NFD-4/2-nfd4-waf-configure.png)

<pre>
$ ./waf
</pre>
 ![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node4/NDNrg-Image-NFD-4/3-nfd4-waf.png)
 ![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node4/NDNrg-Image-NFD-4/3-nfd2-waf2.png)
 ![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node4/NDNrg-Image-NFD-4/3-nfd4-waf3.png)
 ![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node4/NDNrg-Image-NFD-4/3-nfd4-waf4.png)
 ![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node4/NDNrg-Image-NFD-4/3-nfd4-waf5.png)
  
 Show Progess nfd waf [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/nfd2-waf-install-progress.txt)


<pre>
$ sudo ./waf install
</pre>
 ![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node4/NDNrg-Image-NFD-4/5-nfd4-waf-install.png)
 
 Show Progess nfd waf install [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node4/NDNrg-Image-NFD-4/nfd4-waf-install-progress.txt)
