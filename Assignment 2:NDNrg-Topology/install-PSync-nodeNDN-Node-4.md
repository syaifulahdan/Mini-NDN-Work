**PSync Installation Instructions**

Prerequisites
![[ndn-cxx]](https://named-data.net/doc/ndn-cxx) and its dependencies

**Clone & Install PSync**
<pre>
$ git clone https://github.com/named-data/PSync
</pre>

![[alt tag]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node4/NDNrg-Image-PSync-4/1-gitclone-psync4.png)
 Show Progess Clone Psync [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node4/NDNrg-Image-PSync-4/psync4-gitclone.txt)




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
![[alt tag]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node4/NDNrg-Image-PSync-4/2-psync-4-waf-configure.png)
 Show Progess Psync waf configure[[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node3/NDNrg-Image-PSync-3/psync2-waf-configure.txt)
 
**Noted :** 

Checking for lzma support in boost iostreams  : no 

Checking for zstd support in boost iostreams  : no 

<pre>
$ ./waf  
</pre>
![[alt tag]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node3/NDNrg-Image-PSync-3/3-psync-3-waf.png)
 Show Progess Psync waf [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node3/NDNrg-Image-PSync-3/psync3-waf.txt)
 

<pre>
$ sudo ./waf install  
</pre>
![[alt tag]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node3/NDNrg-Image-PSync-3/4-psync-3-waf-install.png)
 Show Progess Psync waf install [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node3/NDNrg-Image-PSync-3/psync3-waf-install.txt)
 
