**PSync Installation Instructions**

Prerequisites
![[ndn-cxx]](https://named-data.net/doc/ndn-cxx) and its dependencies

**Clone & Install PSync**
<pre>
$ git clone https://github.com/named-data/PSync
</pre>

![[alt tag]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NDNrg-Image-PSync-1/gitclone-PSync1.png)
  




**Build**
<pre>
./waf configure
./waf
sudo ./waf install
</pre>

<pre>
$ cd Psync
$ ./waf configure
</pre>
![[alt tag]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NDNrg-Image-PSync-1/PSync1-waf-configure.png)
 
 
**Noted :** 

Checking for lzma support in boost iostreams  : no 

Checking for zstd support in boost iostreams  : no 

<pre>
$ ./waf  
</pre>
![[alt tag]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NDNrg-Image-PSync-1/PSync1-waf.png)
  

<pre>
$ sudo ./waf install  
</pre>
![[alt tag]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NDNrg-Image-PSync-1/PSync1%20waf-install.png)
 
 
