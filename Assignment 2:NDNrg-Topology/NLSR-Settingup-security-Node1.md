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

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NLSR-Image-Node1/nslr-install-rootcert-node1.png.png)
<pre>
root@NDN-Node1-ITB:/home/bertopeng17-1/NLSR# ndnsec-key-gen /ndn/ > root.key
root@NDN-Node1-ITB:/home/bertopeng17-1/NLSR# ndnsec-cert-dump -i /ndn/ > root.cert
root@NDN-Node1-ITB:/home/bertopeng17-1/NLSR# ndnsec-cert-install -f root.cert
OK: certificate with name [/ndn/KEY/%16%D0%E4%8E%950R4/self/v=1633687187749] has been successfully installed
root@NDN-Node1-ITB:/home/bertopeng17-1/NLSR#
</pre>

4. At the site server, generate the site key:
<pre>
$ ndnsec-key-gen /ndn/ndnrg/itb > site.key
</pre>

5. Copy the site key to the root server and generate the certificate for the site server:
<pre>
$ ndnsec-cert-gen -s /ndn/ site.key > site.cert
</pre>


6. Copy the site certificate to the site server and install it:
<pre>
$ ndnsec-cert-install -f site.cert
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NLSR-Image-Node1/nslr-install-sitecert-node1.png)
<pre>
root@NDN-Node1-ITB:/home/bertopeng17-1/NLSR# ndnsec-key-gen /ndn/ndnrg/itb > site.key
root@NDN-Node1-ITB:/home/bertopeng17-1/NLSR# ndnsec-cert-gen -s /ndn/ site.key > site.cert
root@NDN-Node1-ITB:/home/bertopeng17-1/NLSR# ndnsec-cert-install -f site.cert 
OK: certificate with name [/ndn/ndnrg/itb/KEY/%E9%F8%81%C1S~%93%21/NA/v=1633688444541] has been successfully installed
root@NDN-Node1-ITB:/home/bertopeng17-1/NLSR# 
</pre>

7. At the operator server, generate the operator key:
<pre>
$ ndnsec-key-gen /ndn/ndnrg/itb/%C1.Operator/op > op.key
</pre>

8.Copy the operator key to the site server and generate the certificate for the operator server:
<pre>
$ ndnsec-cert-gen -s /ndn/ndnrg/itb op.key > op.cert
</pre>

9. Copy the operator certificate to the operator server and install it:
<pre>
$ ndnsec-cert-install -f op.cert
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NLSR-Image-Node1/nslr-install-operatorcert-node1.png.png)
<pre>
root@NDN-Node1-ITB:/home/bertopeng17-1/NLSR# ndnsec-key-gen /ndn/ndnrg/itb/%C1.Operator/op > op.key
root@NDN-Node1-ITB:/home/bertopeng17-1/NLSR# ndnsec-cert-gen -s /ndn/ndnrg/itb/ op.key > op.cert
root@NDN-Node1-ITB:/home/bertopeng17-1/NLSR# ndnsec-cert-install -f op.cert
OK: certificate with name [/ndn/ndnrg/itb/%C1.Operator/op/KEY/o%1D%1D%E6%AF%C5%FDk/NA/v=1633689386465] has been successfully installed
root@NDN-Node1-ITB:/home/bertopeng17-1/NLSR# 
</pre>

10. At the router, generate the router key:
<pre>
$ ndnsec-key-gen /ndn/ndnrg/itb/%C1.Router/routerX > routerX.key
</pre>

11. Copy the router key to the operator server and generate the certificate for the router:
<pre>
ndnsec-cert-gen -s /ndn/ndnrg/itb/%C1.Operator/op routerX.key > routerX.cert
</pre>

12. Copy the router certificate to the router and install it:
<pre>
ndnsec-cert-install -f routerX.cert
</pre>
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NLSR-Image-Node1/nslr-install-routertcert-node1.png.png)
<pre>
root@NDN-Node1-ITB:/home/bertopeng17-1/NLSR# ndnsec-key-gen /ndn/ndnrg/itb/%C1.Router/routerX > routerX.key
root@NDN-Node1-ITB:/home/bertopeng17-1/NLSR# ndnsec-cert-gen -s /ndn/ndnrg/itb/%C1.Operator/op routerX.key > routerX.cert
root@NDN-Node1-ITB:/home/bertopeng17-1/NLSR# ndnsec-cert-install -f routerX.cert
OK: certificate with name [/ndn/ndnrg/itb/%C1.Router/routerX/KEY/%F2%5E%CF%AF%E5%19%CBq/NA/v=1633692289610] has been successfully installed
root@NDN-Node1-ITB:/home/bertopeng17-1/NLSR# 
</pre>

In the previous step, the labels %C1.Router and %C1.Operator were NDN keywords and should not be changed. This label will also be used by the configuration file (§ 5.4)

The following command may be used to verify that the certificates have been installed in a computer:
<pre>
$ ndnsec-list
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NLSR-Image-Node1/nslr-ndnsec-list-node1.png)

<pre>
root@NDN-Node1-ITB:/home/bertopeng17-1/NLSR# ndnsec-list
  /ndn
  /ndn/ndnrg/itb
* /ndn/ndnrg/itb/%C1.Router/routerX
  /ndn/ndnrg/itb/%C1.Operator/op
root@NDN-Node1-ITB:/home/bertopeng17-1/NLSR# 
</pre>

This guide recommends that one machine functions as the root, site, operator and router1, while a different computer only functions as router2. Figure 2 shows this configuration. For router1, the twelve steps described before need to be executed except for exchanging files between computers. For the router2, only steps 10 to 12 are needed to generate this router’s certificate.

Additionally, the following command may be used to print a list and a brief description of all the ndnsec commands:


![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Topology/network-design.png)
