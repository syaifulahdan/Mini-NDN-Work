NLSR - Named Data Link State Routing Protocol:  https://named-data.net/doc/NLSR/current/


Prerequisites

**1. PSync library**
Download the PSync library and build it according to the instructions available at https://github.com/named-data/PSync#build
<pre>
$ git clone https://github.com/named-data/PSync.git
</pre>

![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-NSLR/gitpsync.png)

Build

To build PSync from source:
<pre>
./waf configure
./waf
sudo ./waf install
</pre>


<pre>
$ cd PSync
~/PSync$./waf configure
</pre>

![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-NSLR/PSync-waf-configure.png)

<pre>
~/PSync$./waf
</pre>

![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-NSLR/PSync-waf.png)

<pre>
~/PSync$ sudo ./waf install 
</pre>
![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-NSLR/PSync%20waf-install.png)


**2.[Optional] ChronoSync library**

For testing purposes, NLSR can be optionally built with Chronosync support. Download the ChronoSync library and build it according to the instructions available at https://github.com/named-data/ChronoSync#build

<pre>
$ git clone https://github.com/named-data/ChronoSync#build
</pre>

![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-NSLR/gitclone%20cronosync.png)


Getting Started with NLSR


 
**NLSR Installation Instructions**

<pre>
git clone https://github.com/named-data/NLSR.git</pre>
</pre>

![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image/gitclonenfd.png)
