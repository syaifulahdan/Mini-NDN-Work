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

To build ndn-cxx from source, one must first install a C++ compiler and all necessary development tools and libraries:
On Ubuntu
<pre>
sudo apt install g++ pkg-config python3-minimal libboost-all-dev libssl-dev libsqlite3-dev
</pre>

1. Install git
<pre>
bertopeng17-1@NDN-Node1-ITB:~$ sudo apt-get update
bertopeng17-1@NDN-Node1-ITB:~$ sudo apt-get install git
bertopeng17-1@NDN-Node1-ITB:~$ sudo apt install python-pip
</pre>

first install the dependency file ndn-cxx 
<pre>
bertopeng17-1@NDN-Node1-ITB:~$sudo apt install g++ pkg-config python3-minimal libboost-all-dev libssl-dev libsqlite3-dev
</pre>

<pre>
bertopeng17-1@git clone https://github.com/named-data/ndn-cxx.git
</pre>

![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image/gitclone.png)

<pre>
bertopeng17-1@cd ndn-cxx
bertopeng17-1@NDN-Node1-ITB:~/ndn-cxx$ 
</pre>

![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image/cdndncxx.png)

install the dependency file ndn-cxx

<pre>
bertopeng17-1@./waf configure
</pre>

![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image/wafconfigure.png)

<pre>
bertopeng17-1@./waf
</pre>

![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image/Screenshot%20from%202021-09-08%2010-26-58.png)



