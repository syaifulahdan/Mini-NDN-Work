Installing Mininet
Mini-NDN is based on Mininet. To install Mininet: ![[7th-ndn-hackathon]](https://7th-ndn-hackathon.named-data.net/mini-ndn-documentation/manual/INSTALL.html)
First, clone Mininet from github:

<pre>
$ git clone --depth 1 https://github.com/mininet/mininet.git
</pre>
![[alt tag]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node3/NDNrg-Image-Mininet3/1-gitclone-mininet3.png)
 Show Progress clone mininet [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node3/NDNrg-Image-Mininet3/mininet3-gitclone.txt)

After Mininet source is on your system, run the following command to install Mininet core dependencies and Open vSwitch:
<pre>
$ ./util/install.sh -nv
</pre>
![[alt tag]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDNrg-Image-Mininet2/2-mininet-util-install.png)
![[alt tag]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDNrg-Image-Mininet2/2-mininet-util-install-finish.png)
Show Progress  Mininet core dependencies and Open vSwitch: [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/mininet2-util-install.txt)

To check if Mininet is working correctly, run this test:
<pre>
sudo mn --test pingall
</pre>

<pre>
$ sudo mn --test pingall
</pre> 
![[alt tag]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDNrg-Image-Mininet2/3-mininet-test-pingall.png)
Show Progress ping-all: [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/mininet2-test-pingall.txt)
