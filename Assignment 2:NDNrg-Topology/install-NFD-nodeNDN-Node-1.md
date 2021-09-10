Getting Started with NFD Building from Source: https://named-data.net/doc/NFD/0.6.3/INSTALL.html

Downloading from Git
The first step is to obtain the source code for NFD and, its main dependency, the ndn-cxx library. If you are not planning to work with the bleeding edge code, make sure you checkout the correct release tag (e.g., *-0.6.0) for both repositories:


**Download NFD**
<pre>
$git clone --recursive https://github.com/named-data/NFD
</pre>

**Install On Ubuntu 18.04**
<pre>
$sudo apt-get install build-essential pkg-config libboost-all-dev \libsqlite3-dev libssl-dev libpcap-dev
</pre>
