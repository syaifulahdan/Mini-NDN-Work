Source : https://named-data.net/doc/NLSR/current/beginners-guide.html

To test the NLSR, the first step is

1. Configure keys and certificates that enforce secure communication between routers.
2. Verify that the computers on the test network are connected, that NFD is running and that the face between computers is configured.
3. Finally, the NLSR configuration file must be edited before running NLSR. The following subsections are provided as a guide for defining and configuring a simple computer network between two computers: router1 and router2.

Setting up the security
Configuring security in an NDN network requires to generate, exchange and install, keys and certificates between the root, site, operator and router computers that form the network [NLSRsecconf], [NLSRdevguide], although in practice, it is possible to keep more than one of these entities in a single machine. The following example and Figure 1 show how to configure security for a single router, called Router X. In this example, the root, site, operator and Router X are in different computers:

![alt img](https://named-data.net/doc/NLSR/current/_images/security_comp.png)

***
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

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node5/NDNrg-Image-NSLR-5/nslr-install-rootcert-node5.png)
<pre>
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-key-gen /ndn/ > root.key
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-cert-dump -i /ndn/ > root.cert
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-cert-install -f root.cert
OK: certificate with name [/ndn/KEY/%02%B3%00%3D%DA%9Ab%DC/self/v=1645110298663] has been successfully installed
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# 

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

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node5/NDNrg-Image-NSLR-5/nslr-install-sitecert-node5.png)
<pre>
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-key-gen /ndn/ndnrg/ittj > site.key
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-cert-gen -s /ndn/ site.key > site.cert
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-cert-install -f site.cert
OK: certificate with name [/ndn/ndnrg/ittj/KEY/%0A%93%23c%19SH2/NA/v=1645111639961] has been successfully installed
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# 

</pre>

7. At the operator server, generate the operator key:
<pre>
$ ndnsec-key-gen /ndn/ndnrg/ittj/%C1.Operator/op > op.key
</pre>

8.Copy the operator key to the site server and generate the certificate for the operator server:
<pre>
$ ndnsec-cert-gen -s /ndn/ndnrg/ittj op.key > op.cert
</pre>

9. Copy the operator certificate to the operator server and install it:
<pre>
$ ndnsec-cert-install -f op.cert
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node5/NDNrg-Image-NSLR-5/nslr-install-operatorcert-node5.png)

<pre>
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-key-gen /ndn/ndnrg/ittj/%C1.Operator/op > op.key
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-cert-gen -s /ndn/ndnrg/ittj op.key > op.cert
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-cert-install -f op.cert
OK: certificate with name [/ndn/ndnrg/ittj/%C1.Operator/op/KEY/%A8%C1~%1CS%D6%81%5B/NA/v=1645112200983] has been successfully installed
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# 

</pre>

10. At the router, generate the router key:
<pre>
$ ndnsec-key-gen /ndn/ndnrg/ittj/%C1.Router/router5 > router5.key
</pre>

11. Copy the router key to the operator server and generate the certificate for the router:
<pre>
ndnsec-cert-gen -s /ndn/ndnrg/ittj/%C1.Operator/op routerX5.key > routerX5.cert
</pre>

12. Copy the router certificate to the router and install it:
<pre>
ndnsec-cert-install -f routerX5.cert
</pre>
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node5/NDNrg-Image-NSLR-5/nslr-install-routertcert-node5.png)
<pre>
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-key-gen /ndn/ndnrg/ittj/%C1.Router/routerX5 > routerX5.key
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-cert-gen -s /ndn/ndnrg/ittj/%C1.Operator/op routerX5.key > routerX5.cert
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-cert-install -f routerX5.cert
OK: certificate with name [/ndn/ndnrg/ittj/%C1.Router/routerX5/KEY/%87%10%83%D5%F5%A1%F9A/NA/v=1645112442211] has been successfully installed
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR#

</pre>

In the previous step, the labels %C1.Router and %C1.Operator were NDN keywords and should not be changed. This label will also be used by the configuration file (§ 5.4)

The following command may be used to verify that the certificates have been installed in a computer:
<pre>
$ ndnsec-list
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NLSR-Image-Node2/nslr-ndnsec-list-node2.png)

<pre>
root@NDN-Node2-UTI:/home/bertopeng17-2/NLSR# ndnsec-list 
  /ndn
  /ndn/ndnrg/ittj
* /ndn/ndnrg/ittj/%C1.Router/routerX5
  /ndn/ndnrg/ittj/%C1.Operator/op
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# 
</pre>

<b>show all configuration NLSR Security Node 5/b>
<pre>
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-key-gen /ndn/ > root.key
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-cert-dump -i /ndn/ > root.cert
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-cert-install -f root.cert
OK: certificate with name [/ndn/KEY/%02%B3%00%3D%DA%9Ab%DC/self/v=1645110298663] has been successfully installed
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# 
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-key-gen /ndn/ndnrg/ittj > site.key
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-cert-gen -s /ndn/ site.key > site.cert
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-cert-install -f site.cert
OK: certificate with name [/ndn/ndnrg/ittj/KEY/%0A%93%23c%19SH2/NA/v=1645111639961] has been successfully installed
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# 
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-key-gen /ndn/ndnrg/ittj/%C1.Operator/op > op.key
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-cert-gen -s /ndn/ndnrg/ittj op.key > op.cert
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-cert-install -f op.cert
OK: certificate with name [/ndn/ndnrg/ittj/%C1.Operator/op/KEY/%A8%C1~%1CS%D6%81%5B/NA/v=1645112200983] has been successfully installed
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# 
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-key-gen /ndn/ndnrg/ittj/%C1.Router/routerX5 > routerX5.key
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-cert-gen -s /ndn/ndnrg/ittj/%C1.Operator/op routerX5.key > routerX5.cert
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-cert-install -f routerX5.cert
OK: certificate with name [/ndn/ndnrg/ittj/%C1.Router/routerX5/KEY/%87%10%83%D5%F5%A1%F9A/NA/v=1645112442211] has been successfully installed
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR#

root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# ndnsec-list
  /ndn
  /ndn/ndnrg/uti
  /ndn/ndnrg/ittj
* /ndn/ndnrg/ittj/%C1.Router/routerX5
  /ndn/ndnrg/ittj/%C1.Operator/op
  /localhost/operator
root@ndn-node5-ittj:/home/bertopeng17-2/NLSR# 

</pre>




This guide recommends that one machine functions as the root, site, operator and router1, while a different computer only functions as router2. Figure 2 shows this configuration. For router1, the twelve steps described before need to be executed except for exchanging files between computers. For the router2, only steps 10 to 12 are needed to generate this router’s certificate.

Additionally, the following command may be used to print a list and a brief description of all the ndnsec commands:


![alt img](https://raw.githubusercontent.com/syaifulahdan/Mini-NDN-Work/main/Assignment%202%3ANDNrg-Topology/NDNrg-Image-Node2/NFD-Image-Node2/network-uti.png)

<b>Configuring the network</b>

The first step is to configure the physical network. If two computers are going to get connected using a single Ethernet cable, it is necessary to verify that this cable is a crossover. The other option is to employ a switch between two computers that are then connected using two regular Ethernet cables.

After the physical network has been assembled, it is necessary to configure the network addresses and cards for all the computers in the network. It is important to remember that computers that are connected to each other should use the same subnetwork address. It is possible to verify the network configuration in a Linux computer by means of the ip addr command

Once the physical network and network cards have been configured, it is necessary to verify that the computers can communicate with each other. The simplest way to do this is by using the ping command:

<pre>
$ ping <remote-ip-address>
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NLSR-Image-Node2/nslr-ping-remote-pc1.png)



<b>Starting and configuring NFD</b>

To start and configure NFD it is necessary to open two terminal windows. The first one will be used to start NFD by means of the nfd-start command. This terminal will also display the logs that NFD generates. By default, NFD only generates informational logs (INFO). However, it is possible to obtain different levels of verbosity for these logs. These levels can be set before NFD starts by editing the <b>/usr/local/etc/ndn/nfd.conf</b> file. Open this file using a regular text editor, read the information provided about logging and then modify the default-level variable at the log section according to the instructions provided in the file. Additional information about NFD configuration may be found at
