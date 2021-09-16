**Installastion Node NDN** https://named-data.net/doc/ndn-cxx/current/INSTALL.html

**Prerequisites**
<pre>
Required

    GCC >= 7.4 or clang >= 4.0 (on Linux and FreeBSD)
    Xcode >= 9.0 (on macOS)
    Python >= 3.6
    pkg-config
    Boost >= 1.65.1
    OpenSSL >= 1.0.2
    SQLite 3.x

</pre>

**Optional
**
<pre>
To build tutorials, manpages, and API documentation the following additional dependencies need to be installed:

    doxygen
    graphviz
    sphinx >= 1.3
    sphinxcontrib-doxylink
    

</pre>

The following lists the steps to install these prerequisites on various common platforms.
On Ubuntu: 
<pre>
sudo apt install doxygen graphviz python3-pip
sudo pip3 install sphinx sphinxcontrib-doxylink
</pre>

**1. Upgrade Ubuntu**
<pre>
$ sudo apt update && apt-get full-upgrade -y
</pre>
![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDN-Installation/1-upgrade-ubuntu.png)

**2. Install Git**
<pre>
$ sudo apt-get install git
</pre>
![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDN-Installation/2-install-git.png)

**3. Clone & Install ndn-cxx**
 first install the dependency file ndn-cxx
<pre>
sudo apt install g++ pkg-config python3-minimal libboost-all-dev libssl-dev libsqlite3-dev -y
sudo apt install doxygen graphviz python3-pip -y
sudo apt install libpcap-dev libsystemd-dev -y
</pre>






<pre>
$ git clone https://github.com/named-data/ndn-cxxit
</pre>

 ![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDN-Installation/3-gitclone-ndncxx.png)
 

 
 
 
 
 
 
 **4. Clone NFD**
<pre>
$ git clone — recursive https://github.com/named-data/NFD
</pre>

 ![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDN-Installation/4-gitclone-nfd.png)
 
 **4. Clone NLSR**
<pre>
$ git clone — recursive https://github.com/named-data/NFD
</pre>

 ![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDN-Installation/4-gitclone-nfd.png)
 
