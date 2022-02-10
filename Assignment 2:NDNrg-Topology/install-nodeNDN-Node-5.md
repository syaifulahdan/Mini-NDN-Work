**Installastion Node NDN** https://named-data.net/doc/ndn-cxx/current/INSTALL.html

Tabel Of Content
***
[1. Prerequisites](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/install-nodeNDN-Node-2.md#1-prerequisites)

[2. Upgrade Ubuntu](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/install-nodeNDN-Node-2.md#2-upgrade-ubuntu)

[3. Install Git](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/install-nodeNDN-Node-2.md#3-install-git)

[4. Git Clone ndn-cxx](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/install-nodeNDN-Node-2.md#4-git-clone-ndn-cxx)

[5. Install ndn-cxx](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/install-nodeNDN-Node-2.md#5-install-ndn-cxx)

[<< Back](https://github.com/syaifulahdan/Mini-NDN-Work)

***

### 1. Prerequisites 

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

### 2. Upgrade Ubuntu
<pre>
$ sudo apt update && apt-get full-upgrade -y
</pre>
![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDN-Installation/1-upgrade-ubuntu.png)

### 3. Install Git
<pre>
$ sudo apt-get install git
</pre>
![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDN-Installation/2-install-git.png)

### 4. Git Clone ndn-cxx

first install the dependency file ndn-cxx
<pre>
sudo apt install g++ pkg-config python3-minimal libboost-all-dev libssl-dev libsqlite3-dev -y
sudo apt install doxygen graphviz python3-pip -y
sudo apt install libpcap-dev libsystemd-dev -y
</pre>

<pre>
$ sudo apt install g++ pkg-config python3-minimal libboost-all-dev libssl-dev libsqlite3-dev -y
</pre>

 ![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDN-Installation/5-dependency-1-install.png)


<pre>
$ sudo apt install doxygen graphviz python3-pip -y
</pre>
![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDN-Installation/6-dependency-2-install.png)

Show Progess Install [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDN-Installation/dependency-2-progress.txt) 

<pre>
$ sudo apt install libpcap-dev libsystemd-dev -y
</pre>
![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDN-Installation/7-dependency-3-install.png)

Show Progess Install [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDN-Installation/dependency-3-progress.txt) 

<pre>
$ git clone https://github.com/named-data/ndn-cxxit
</pre>

 ![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDN-Installation/3-gitclone-ndncxx.png)


### 5. Install ndn-cxx
 
install ndn-cxx
<pre>
./waf configure
./waf 
./waf install
</pre>
 
<pre>
$ cd ndn-cxx
$ ./waf configure
</pre>

![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDN-Installation/8-ndncxx-waf-configure.png)
Show Progess ndn-cxx waf configure [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDN-Installation/ndncxx-waf-configure-progress.txt) 

**Noted :** 
-Building Static Library    : no
-'sphinx-build'             : not found

 
<pre>
$ ./waf 
</pre> 
![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDN-Installation/9-ndncxx-waf.png)
![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDN-Installation/10-ndncxx-waf-finish.png)
Show Progess ndn-cxx waf [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDN-Installation/ndncxx-waf-progress.txt) 
 

<pre>
$ sudo ./waf install
</pre>
![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDN-Installation/11-ndncxx-waf-install-1.png)
![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDN-Installation/12-ndncxx-waf-install-2.png)
Show Progess ndn-cxx waf install[[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDN-Installation/ndncxx-waf-install-progress.txt)  
 
 
 
 
