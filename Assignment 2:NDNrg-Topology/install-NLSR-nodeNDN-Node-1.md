NLSR - Named Data Link State Routing Protocol:  https://named-data.net/doc/NLSR/current/ or https://github.com/named-data/ndn-cxx/blob/master/docs/tutorials/security-validator-config.rst#example-configuration-for-nlsr
***

**3. NLSR Installation Instructions**
Getting Started with NLSR

<pre>
$ git clone https://github.com/named-data/NLSR.git</pre>
</pre>

![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NDNrg-Image-NSLR-1/gitclone-NLSR.png)

**Build NLSR**

To build PSync from source:
<pre>
$ cd NLSR
$./waf configure
$./waf
$ sudo ./waf install
</pre>


<pre>
$ cd NLSR
~/NLSR$./waf configure
</pre>

![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NDNrg-Image-NSLR-1/NLSR-waf-configure.png)

<pre>
~/NLSR$./waf
</pre>

![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NDNrg-Image-NSLR-1/NLSR-Waf.png)

<pre>
~/NSLR$ sudo ./waf install 
</pre>
![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NDNrg-Image-NSLR-1/NLSR-Waf-Install.png)

If ChronoSync support is desired, NLSR needs to be configured with the following option:
<pre>
$./waf configure --with-chronosync
</pre>

![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NDNrg-Image-NSLR-1/waf-configure-choronsync.png)
