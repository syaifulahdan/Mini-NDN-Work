### Starting NLSR (ITB)
It is recommended to open a third command terminal and run NLSR in this window. After the NLSR configuration file has been edited and saved as nlsr.conf, it is possible to start NLSR by running either of the following two commands:
***
<pre>
$ nlsr
$ nlsr -f <configuration-file>
</pre>

However, to verify what is NLSR doing, it becomes necessary to employ NLSR’s logging facility [NLSRstarting]. A brief description on how to use NDN’s logging facility may be displayed by entering the man ndn-log command. This guide recommends using one of the following two instructions to start NLSR:
<pre>
$ export NDN_LOG=nlsr.*=TRACE && nlsr
$ export NDN_LOG=nlsr.*=TRACE && nlsr -f <configuration-file>
</pre>

<pre>
bertopeng17-1@NDN-Node1-ITB:~$ export NDN_LOG=nlsr.*=TRACE && nlsr -f /home/bertopeng17-1/NLSR/nlsr-itb-5-node.conf 
</pre>

or
<pre>
sudo NDN_LOG='nlsr.*=DEBUG' nlsr -f /home/bertopeng17-1/NLSR/nlsr-itb-5-node.conf
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NLSR-Image-Node1/NLSR-start-node1-1.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NLSR-Image-Node1/NLSR-start-node1-2.png)


<pre>
bertopeng17-1@NDN-Node1-ITB:~$ export NDN_LOG=nlsr.*=TRACE && nlsr -f /home/bertopeng17-1/NLSR/nlsr-itb.conf
1634228310.857014 TRACE: [nlsr.ConfParameter] Loading Certificate Name: /ndn/KEY/%B7%BCm%3E%15%F0%05n/self/v=1633706199529
1634228310.857171 TRACE: [nlsr.ConfParameter] Loading Certificate Name: /ndn/ndnrg/itb/KEY/t%89%2F%A0%BF%DB%05s/NA/v=1633706270792
1634228310.857246 TRACE: [nlsr.ConfParameter] Loading Certificate Name: /ndn/ndnrg/itb/%C1.Operator/op/KEY/%A7%C6%0B%90%E0%5E%E0%C5/NA/v=1633706306471
1634228310.857314 TRACE: [nlsr.ConfParameter] Loading Certificate Name: /ndn/ndnrg/itb/%C1.Router/routerX/KEY/%D0%0A%B0%B3%14R%A3%DB/NA/v=1633706338642
1634228310.857361  INFO: [nlsr.ConfParameter] Router Name: /%C1.Router/routerX
1634228310.857378  INFO: [nlsr.ConfParameter] Site Name: /ndnrg/itb
1634228310.857386  INFO: [nlsr.ConfParameter] Network: /ndn
1634228310.857390  INFO: [nlsr.ConfParameter] Router Prefix: /ndn/ndnrg/itb/%C1.Router/routerX
1634228310.857398  INFO: [nlsr.ConfParameter] Sync Prefix: /localhop/ndn/nlsr/sync/v=10
1634228310.857406  INFO: [nlsr.ConfParameter] Sync LSA prefix: /localhop/ndn/nlsr/LSA
1634228310.857413  INFO: [nlsr.ConfParameter] Hello Interest retry number: 3
1634228310.857417  INFO: [nlsr.ConfParameter] Hello Interest resend second: 1
1634228310.857421  INFO: [nlsr.ConfParameter] Info Interest interval: 60
1634228310.857425  INFO: [nlsr.ConfParameter] LSA refresh time: 1800
1634228310.857429  INFO: [nlsr.ConfParameter] FIB Entry refresh time: 3600
1634228310.857434  INFO: [nlsr.ConfParameter] LSA Interest lifetime: 4 seconds
1634228310.857471  INFO: [nlsr.ConfParameter] Router dead interval: 3600
1634228310.857485  INFO: [nlsr.ConfParameter] Max Faces Per Prefix: 3
1634228310.857524  INFO: [nlsr.ConfParameter] State Directory: /var/lib/nlsr
1634228310.857531  INFO: [nlsr.ConfParameter] Adjacency LSA build interval:  10
1634228310.857538  INFO: [nlsr.ConfParameter] Routing calculation interval:  15
1634228310.857545 DEBUG: [nlsr.ConfParameter] Initializing Key ...
1634228310.857981  WARN: [nlsr.ConfParameter] Identity /ndn/ndnrg/itb/%C1.Router/routerX/nlsr does not exist
1634228310.858413 ERROR: [nlsr.ConfParameter] Cannot set non-existing identity `/ndn/ndnrg/itb/%C1.Router/routerX/nlsr` as default
1634228310.858438 ERROR: [nlsr.ConfParameter] Unable to create identity, NLSR will run without security!
1634228310.858442 ERROR: [nlsr.ConfParameter] Can be ignored if running in non-production environments.
1634228310.858465 TRACE: [nlsr.SyncProtocolAdapter] SyncProtocol value: 0
1634228310.858471 DEBUG: [nlsr.SyncProtocolAdapter] Using PSync
1634228310.860454 DEBUG: [nlsr.SequencingManager] Seq File Name: /var/lib/nlsr/nlsrSeqNo.txt
1634228310.860525 DEBUG: [nlsr.SequencingManager] Adj LSA seq no: 40
1634228310.860532 DEBUG: [nlsr.SequencingManager] Name LSA Seq no: 48
1634228310.860564 DEBUG: [nlsr.Lsdb] Setting interest filter for LsaPrefix: /localhop/ndn/nlsr/LSA
1634228310.860797 DEBUG: [nlsr.SequencingManager] Adj LSA seq no: 40
1634228310.860820 DEBUG: [nlsr.SequencingManager] Name LSA Seq no: 49
1634228310.861021 DEBUG: [nlsr.Lsdb] Adding NAME LSA
1634228310.861033 DEBUG: [nlsr.Lsdb]     NAME LSA:
      Origin Router      : /ndn/ndnrg/itb/%C1.Router/routerX
      Sequence Number    : 49
      Expires in         : 3599999 milliseconds
      Names:
        Name 0: /ndn/ndnrg/itb/telmat/residen
        Name 1: /ndn/ndnrg/itb/telmat/labipnet

1634228310.861080 DEBUG: [nlsr.Lsdb] Scheduling expiration in: 1810 seconds for /ndn/ndnrg/itb/%C1.Router/routerX
1634228310.861117 DEBUG: [nlsr.HelloProtocol] Setting interest filter for Hello interest: /ndn/ndnrg/itb/%C1.Router/routerX/nlsr/INFO
1634228310.861334 DEBUG: [nlsr.update.PrefixUpdateProcessor] Setting dispatcher to capture Interests for: /localhost/nlsr/prefix-update
1634228310.861397 DEBUG: [nlsr.Nlsr] Initializing Nlsr
1634228310.861730 DEBUG: [nlsr.Nlsr] Default NLSR identity: /
1634228310.862134 DEBUG: [nlsr.Nlsr] Enabling incoming face id indication for local face.
1634228310.862253 TRACE: [nlsr.Nlsr] Initializing Faces...
1634228310.862326 DEBUG: [nlsr.AdjacencyList] -------Adjacency List--------
1634228310.862349 DEBUG: [nlsr.AdjacencyList] Adjacent: /ndn/ndnrg/uti/%C1.Router/routerX2
		Connecting FaceUri: udp4://192.168.56.103:6363
		Link cost: 30
		Status: 0
		Interest Timed Out: 0

1634228310.862384 DEBUG: [nlsr.Nlsr] Name prefix list: {
/ndn/ndnrg/itb/telmat/residen
Sources:
  
/ndn/ndnrg/itb/telmat/labipnet
Sources:
  
}

1634228310.862477 TRACE: [nlsr.CertificateStore] Certificate inserted successfully
1634228310.862606 TRACE: [nlsr.CertificateStore] Certificate inserted successfully
1634228310.862674 TRACE: [nlsr.CertificateStore] Certificate inserted successfully
1634228310.862715 TRACE: [nlsr.CertificateStore] Certificate inserted successfully
1634228310.864658 TRACE: [nlsr.Nlsr] onFaceEventNotification called
1634228310.865853 DEBUG: [nlsr.Lsdb] Successfully registered prefix: /localhop/ndn/nlsr/LSA
1634228310.866114 DEBUG: [nlsr.route.Fib] Successfully set strategy choice: /localhost/nfd/strategy/multicast/v=4 for name: /localhop/ndn/nlsr/LSA
1634228310.866260 DEBUG: [nlsr.route.Fib] Successfully set strategy choice: /localhost/nfd/strategy/multicast/v=4 for name: /localhop/ndn/nlsr/sync/v=10
1634228310.866334 DEBUG: [nlsr.Nlsr] Successfully enabled incoming face id indicationfor face id 269
1634228310.866532 DEBUG: [nlsr.Nlsr] Processing face dataset
1634228310.866554  WARN: [nlsr.Nlsr] The adjacency /ndn/ndnrg/uti/%C1.Router/routerX2 has no Face information in this dataset.
1634228310.866559 DEBUG: [nlsr.Nlsr] Scheduling Dataset Fetch in 3600 seconds
1634228310.866677 DEBUG: [nlsr.HelloProtocol] Successfully registered prefix: /ndn/ndnrg/itb/%C1.Router/routerX/nlsr/INFO
1634228310.866737 DEBUG: [nlsr.Nlsr] Successfully registered prefix: /ndn/ndnrg/itb/%C1.Router/routerX/nlsr
1634228310.866804 DEBUG: [nlsr.Nlsr] Successfully registered prefix: /localhost/nlsr
1634228310.867449 DEBUG: [nlsr.CertificateStore] KEY prefix: /ndn/ndnrg/itb/%C1.Router/routerX/nlsr/KEY registration is successful
1634228310.867506 DEBUG: [nlsr.CertificateStore] KEY prefix: /ndn/ndnrg/itb/%C1.Router/routerX/KEY registration is successful
1634228310.867541 DEBUG: [nlsr.CertificateStore] KEY prefix: /ndn/ndnrg/itb/%C1.Operator registration is successful
1634228310.867802 DEBUG: [nlsr.CertificateStore] KEY prefix: /ndn/ndnrg/itb/KEY registration is successful

</pre>


