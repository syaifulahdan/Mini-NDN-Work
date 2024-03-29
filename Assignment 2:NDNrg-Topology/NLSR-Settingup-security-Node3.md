Source : https://named-data.net/doc/NLSR/current/beginners-guide.html

To test the NLSR, the first step is

1. Configure keys and certificates that enforce secure communication between routers.
2. Verify that the computers on the test network are connected, that NFD is running and that the face between computers is configured.
3. Finally, the NLSR configuration file must be edited before running NLSR. The following subsections are provided as a guide for defining and configuring a simple computer network between two computers: router1 and router2.

Setting up the security
Configuring security in an NDN network requires to generate, exchange and install, keys and certificates between the root, site, operator and router computers that form the network [NLSRsecconf], [NLSRdevguide], although in practice, it is possible to keep more than one of these entities in a single machine. The following example and Figure 1 show how to configure security for a single router, called Router X. In this example, the root, site, operator and Router X are in different computers:

![alt img](https://named-data.net/doc/NLSR/current/_images/security_comp.png)


1. At the root server, generate the root key:

<pre>
$ ndnsec-key-gen /ndn/ > root.key
</pre>

2. Generate the certificate for the root key at the root server:
<pre>
$ ndnsec-cert-dump -i /ndn/ > root.cert
</pre>

3. Install the root certificate at the root server:
<pre>
$ ndnsec-cert-install -f root.cert
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node3/NLSR-Image-Node3/nslr-install-rootcert-node3.png)
<pre>
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-key-gen /ndn/ > root.key
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-cert-dump -i /ndn/ > root.cert
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-cert-install -f root.cert
OK: certificate with name [/ndn/KEY/%D6%D9l%10%D9%FA%BF%1C/self/v=1634799970312] has been successfully installed
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# 
</pre>

4. At the site server, generate the site key:
<pre>
$ ndnsec-key-gen /ndn/ndnrg/uti > site.key
</pre>

5. Copy the site key to the root server and generate the certificate for the site server:
<pre>
$ ndnsec-cert-gen -s /ndn/ site.key > site.cert
</pre>


6. Copy the site certificate to the site server and install it:
<pre>
$ ndnsec-cert-install -f site.cert
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node3/NLSR-Image-Node3/nslr-install-sitecert-node3.png)
<pre>
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-key-gen /ndn/ndnrg/telu > site.key
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-cert-gen -s /ndn/ site.key > site.cert
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-cert-install -f site.cert
OK: certificate with name [/ndn/ndnrg/telu/KEY/%7B%D2%B6%E3%EF%89i%BD/NA/v=1634800639586] has been successfully installed
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# 

</pre>

7. At the operator server, generate the operator key:
<pre>
$ ndnsec-key-gen /ndn/ndnrg/telu/%C1.Operator/op > op.key
</pre>

8.Copy the operator key to the site server and generate the certificate for the operator server:
<pre>
$ ndnsec-cert-gen -s /ndn/ndnrg/telu op.key > op.cert
</pre>

9. Copy the operator certificate to the operator server and install it:
<pre>
$ ndnsec-cert-install -f op.cert
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node3/NLSR-Image-Node3/nslr-install-operatorcert-node3.png)

<pre>
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-key-gen /ndn/ndnrg/telu/%C1.Operator/op > op.key
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-cert-gen -s /ndn/ndnrg/telu op.key > op.cert
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-cert-install -f op.cert
OK: certificate with name [/ndn/ndnrg/telu/%C1.Operator/op/KEY/%7D%9B%BF%0E%5E%40%AEF/NA/v=1634801042061] has been successfully installed
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# 


</pre>

10. At the router, generate the router key:
<pre>
$ ndnsec-key-gen /ndn/ndnrg/telu/%C1.Router/routerX3 > routerX3.key
</pre>

11. Copy the router key to the operator server and generate the certificate for the router:
<pre>
ndnsec-cert-gen -s /ndn/ndnrg/telu/%C1.Operator/op routerX3.key > routerX3.cert
</pre>

12. Copy the router certificate to the router and install it:
<pre>
ndnsec-cert-install -f routerX3.cert
</pre>
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node3/NLSR-Image-Node3/nslr-install-routertcert-node3.png)
<pre>
root@Nroot@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-key-gen /ndn/ndnrg/telu/%C1.Router/routerX3 > routerX3.key
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-cert-gen -s /ndn/ndnrg/telu/%C1.Operator/op routerX3.key > routerX3.cert
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-cert-install -f routerX3.cert
OK: certificate with name [/ndn/ndnrg/telu/%C1.Router/routerX3/KEY/%CF%12R%E9%BEBMi/NA/v=1634801347281] has been successfully installed
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# 


</pre>

In the previous step, the labels %C1.Router and %C1.Operator were NDN keywords and should not be changed. This label will also be used by the configuration file (§ 5.4)

The following command may be used to verify that the certificates have been installed in a computer:
<pre>
$ ndnsec-list
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node3/NLSR-Image-Node3/nslr-ndnsec-list-node3.png)

<pre>
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-list
  /ndn
  /ndn/ndnrg/uti
  /ndn/ndnrg/telu
* /ndn/ndnrg/telu/%C1.Router/routerX3
  /ndn/ndnrg/telu/%C1.Operator/op
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# 
</pre>

<b>show all configuration NLSR Security Node 3</b>
<pre>
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-key-gen /ndn/ > root.key
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-cert-dump -i /ndn/ > root.cert
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-cert-install -f root.cert
OK: certificate with name [/ndn/KEY/M%EA%A3Y%9A%C9%AA%F1/self/v=1634802511208] has been successfully installed
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-key-gen /ndn/ndnrg/telu > site.key
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-cert-gen -s /ndn/ site.key > site.cert
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-cert-install -f site.cert
OK: certificate with name [/ndn/ndnrg/telu/KEY/%89%FE%D3%FE%86%B2%B3%0E/NA/v=1634802573311] has been successfully installed
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-key-gen /ndn/ndnrg/telu/%C1.Operator/op > op.key
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-cert-gen -s /ndn/ndnrg/telu op.key > op.cert
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-cert-install -f op.cert
OK: certificate with name [/ndn/ndnrg/telu/%C1.Operator/op/KEY/%0Bv%85%C3z%F7%FA%60/NA/v=1634802606760] has been successfully installed
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-key-gen /ndn/ndnrg/telu/%C1.Router/routerX3 > routerX3.key
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-cert-gen -s /ndn/ndnrg/telu/%C1.Operator/op routerX3.key > routerX3.cert
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-cert-install -f routerX3.cert
OK: certificate with name [/ndn/ndnrg/telu/%C1.Router/routerX3/KEY/%A4o%0A%85%0C%A8%01%60/NA/v=1634802653122] has been successfully installed
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR# ndnsec-list
  /ndn
  /ndn/ndnrg/uti
  /ndn/ndnrg/telu
* /ndn/ndnrg/telu/%C1.Router/routerX3
  /ndn/ndnrg/telu/%C1.Operator/op
root@NDN-Node3-TELU:/home/bertopeng17-3/NLSR#
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node3/NLSR-Image-Node3/all-configuration-nlsr-security.png)



This guide recommends that one machine functions as the root, site, operator and router1, while a different computer only functions as router2. Figure 2 shows this configuration. For router1, the twelve steps described before need to be executed except for exchanging files between computers. For the router2, only steps 10 to 12 are needed to generate this router’s certificate.

Additionally, the following command may be used to print a list and a brief description of all the ndnsec commands:


![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node3/NFD-Image-Node3/network-telu.png)

<b>Configuring the network</b>

The first step is to configure the physical network. If two computers are going to get connected using a single Ethernet cable, it is necessary to verify that this cable is a crossover. The other option is to employ a switch between two computers that are then connected using two regular Ethernet cables.

After the physical network has been assembled, it is necessary to configure the network addresses and cards for all the computers in the network. It is important to remember that computers that are connected to each other should use the same subnetwork address. It is possible to verify the network configuration in a Linux computer by means of the ip addr command

Once the physical network and network cards have been configured, it is necessary to verify that the computers can communicate with each other. The simplest way to do this is by using the ping command:

<pre>
$ ping <remote-ip-address>
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node3/NLSR-Image-Node3/nslr-ping-remote-node-itb.png)

<pre>
bertopeng17-3@NDN-Node3-TELU:~$ ping 192.168.59.3
PING 192.168.59.3 (192.168.59.3) 56(84) bytes of data.
64 bytes from 192.168.59.3: icmp_seq=1 ttl=64 time=0.909 ms
64 bytes from 192.168.59.3: icmp_seq=2 ttl=64 time=1.08 ms
64 bytes from 192.168.59.3: icmp_seq=3 ttl=64 time=0.595 ms
64 bytes from 192.168.59.3: icmp_seq=4 ttl=64 time=0.985 ms
64 bytes from 192.168.59.3: icmp_seq=5 ttl=64 time=1.20 ms
64 bytes from 192.168.59.3: icmp_seq=6 ttl=64 time=0.879 ms
64 bytes from 192.168.59.3: icmp_seq=7 ttl=64 time=1.09 ms
64 bytes from 192.168.59.3: icmp_seq=8 ttl=64 time=1.21 ms
64 bytes from 192.168.59.3: icmp_seq=9 ttl=64 time=1.11 ms
--- 192.168.59.3 ping statistics ---
9 packets transmitted, 9 received, 0% packet loss, time 8081ms
rtt min/avg/max/mdev = 0.595/1.008/1.211/0.185 ms
bertopeng17-3@NDN-Node3-TELU:~$ 

</pre>


![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node3/NLSR-Image-Node3/nslr-ping-remote-node-lipi.png)

<pre>
bertopeng17-3@NDN-Node3-TELU:~$ ping 192.168.58.4
PING 192.168.58.4 (192.168.58.4) 56(84) bytes of data.
64 bytes from 192.168.58.4: icmp_seq=1 ttl=64 time=1.90 ms
64 bytes from 192.168.58.4: icmp_seq=2 ttl=64 time=1.00 ms
64 bytes from 192.168.58.4: icmp_seq=3 ttl=64 time=0.530 ms
64 bytes from 192.168.58.4: icmp_seq=4 ttl=64 time=1.03 ms
64 bytes from 192.168.58.4: icmp_seq=5 ttl=64 time=1.02 ms
64 bytes from 192.168.58.4: icmp_seq=6 ttl=64 time=0.915 ms
--- 192.168.58.4 ping statistics ---
106 packets transmitted, 106 received, 0% packet loss, time 106402ms
rtt min/avg/max/mdev = 0.257/0.885/4.581/0.457 ms
bertopeng17-3@NDN-Node3-TELU:~$ 
</pre>




<b>Starting and configuring NFD</b>

To start and configure NFD it is necessary to open two terminal windows. The first one will be used to start NFD by means of the nfd-start command. This terminal will also display the logs that NFD generates. By default, NFD only generates informational logs (INFO). However, it is possible to obtain different levels of verbosity for these logs. These levels can be set before NFD starts by editing the <b>/usr/local/etc/ndn/nfd.conf</b> file. Open this file using a regular text editor, read the information provided about logging and then modify the default-level variable at the log section according to the instructions provided in the file. Additional information about NFD configuration may be found at
