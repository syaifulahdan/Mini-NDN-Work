 To see the status of routing on the node:

<pre>
nfdc status report
</pre>

<b>1. Running Example Topology</b>
<pre>
$ sudo python examples/mnndn.py
</pre>
![[alt tag]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NDNrg-Image-NFD-1-Works/running-example%20topology.png)

<b>2. see the status of routing on the node:</b>

<pre>
mini-ndn> nfdc status report
</pre>

![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NDNrg-Image-NFD-1-Works/nfd-status-node-a-1.png)
![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NDNrg-Image-NFD-1-Works/nfd-status-node-a-2.png)
![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NDNrg-Image-NFD-1-Works/nfd-status-node-a-3.png)


will show the results as below

[[Detail Status nfdc node a]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NDNrg-Image-NFD-1-Works/nfd-status-node-a.txt)

[[Detail Status nfdc node b]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NDNrg-Image-NFD-1-Works/nfd-status-node-b.txt)

<b>2. Detail status of routing on the node:</b>
<pre>
mini-ndn> a nfdc status report
</pre>

<pre>
General NFD status:
                version=22.02
              startTime=20220830T160218.540000
            currentTime=20220830T163233.112000
                 uptime=1814 seconds
       nNameTreeEntries=58
            nFibEntries=17
            nPitEntries=2
   nMeasurementsEntries=0
             nCsEntries=280
           nInInterests=633
          nOutInterests=652
                nInData=356
               nOutData=377
               nInNacks=2
              nOutNacks=17
    nSatisfiedInterests=348
  nUnsatisfiedInterests=32
  
  </pre>
  
  <pre>
Channels:
  tcp4://0.0.0.0:6363
  tcp6://[::]:6363
  unix:///run/a.sock
  dev://a-eth0
  dev://a-eth1Channels:
  tcp4://0.0.0.0:6363
  tcp6://[::]:6363
  unix:///run/a.sock
  dev://a-eth0
  dev://a-eth1
  udp4://0.0.0.0:6363
  udp6://[::]:6363
  ws://0.0.0.0:9696
  ws://[::]:9696
  udp4://0.0.0.0:6363
  udp6://[::]:6363
  ws://0.0.0.0:9696
  ws://[::]:9696
  
  </pre>
  
  <pre>
Faces:
  faceid=1 remote=internal:// local=internal:// congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 125d 0n 56253B} out={152i 0d 0n 21649B}} flags={local permanent point-to-point local-fields}
  faceid=254 remote=contentstore:// local=contentstore:// mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={local permanent point-to-point}
  faceid=255 remote=null:// local=null:// mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={local permanent point-to-point}
  faceid=256 remote=ether://[01:00:5e:00:17:aa] local=dev://a-eth0 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=1500 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access}
  faceid=257 remote=ether://[01:00:5e:00:17:aa] local=dev://a-eth1 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=1500 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access}
  faceid=258 remote=fd://32 local=unix:///run/a.sock congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={91i 39d 0n 26726B} out={39i 62d 0n 37007B}} flags={local on-demand point-to-point local-fields congestion-marking}
  faceid=259 remote=udp4://224.0.23.170:56363 local=udp4://10.0.0.1:46668 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
  faceid=260 remote=udp4://224.0.23.170:56363 local=udp4://10.0.0.5:42988 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
  faceid=261 remote=udp6://[ff02::1234%a-eth0]:56363 local=udp6://[fe80::cc60:72ff:fe60:896a%a-eth0]:54494 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
  faceid=262 remote=udp6://[ff02::1234%a-eth1]:56363 local=udp6://[fe80::bcc4:18ff:fe82:a1c7%a-eth1]:45907 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
  faceid=264 remote=udp4://10.0.0.2:6363 local=udp4://10.0.0.1:6363 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={110i 48d 0n 31810B} out={113i 47d 0n 31822B}} flags={non-local permanent point-to-point congestion-marking}
  faceid=266 remote=udp4://10.0.0.6:6363 local=udp4://10.0.0.5:6363 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={115i 44d 2n 31350B} out={114i 58d 0n 36440B}} flags={non-local permanent point-to-point congestion-marking}
  faceid=267 remote=fd://41 local=unix:///run/a.sock congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={232i 84d 0n 56113B} out={213i 141d 4n 83171B}} flags={local on-demand point-to-point local-fields congestion-marking}
  faceid=274 remote=fd://44 local=unix:///run/a.sock congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={60i 18d 0n 18561B} out={23i 58d 0n 28164B}} flags={local on-demand point-to-point local-fields congestion-marking}
  faceid=275 remote=fd://45 local=unix:///run/a.sock congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={3i 0d 0n 137B} out={0i 2d 0n 614B}} flags={local on-demand point-to-point congestion-marking}
  
  </pre>
  
  
  <pre>
FIB:
  /localhop/ndn/nlsr/sync/v=10 nexthops={faceid=267 (cost=0), faceid=274 (cost=0), faceid=264 (cost=10), faceid=266 (cost=10)}
  /localhost/nfd/rib nexthops={faceid=258 (cost=0)}
  /ndn/d-site/%C1.Router/cs/d nexthops={faceid=264 (cost=20)}
  /ndn/c-site/%C1.Router/cs/c nexthops={faceid=266 (cost=10)}
  /ndn/c-site/c nexthops={faceid=266 (cost=10)}
  /ndn/d-site/d nexthops={faceid=264 (cost=20)}
  /ndn/a-site/%C1.Router/cs/a/nlsr/KEY nexthops={faceid=267 (cost=0), faceid=274 (cost=0)}
  /localhop/ndn/nlsr/LSA nexthops={faceid=267 (cost=0), faceid=274 (cost=0), faceid=264 (cost=10), faceid=266 (cost=10)}
  /ndn/a-site/%C1.Router/cs/a/nlsr nexthops={faceid=267 (cost=0), faceid=274 (cost=0)}
  /ndn/b-site/%C1.Router/cs/b nexthops={faceid=264 (cost=10)}
  /localhost/nfd nexthops={faceid=1 (cost=0)}
  /ndn/a-site/%C1.Router/cs/a/nlsr/INFO nexthops={faceid=267 (cost=0), faceid=274 (cost=0)}
  /ndn/b-site/b nexthops={faceid=264 (cost=10)}
  /ndn/a-site/%C1.Operator nexthops={faceid=267 (cost=0), faceid=274 (cost=0)}
  /ndn/a-site/%C1.Router/cs/a/KEY nexthops={faceid=267 (cost=0), faceid=274 (cost=0)}
  /localhost/nlsr nexthops={faceid=267 (cost=0), faceid=274 (cost=0)}
  /ndn/a-site/KEY nexthops={faceid=267 (cost=0), faceid=274 (cost=0)}
  
  </pre>
  
  <pre>
RIB:
  /ndn/a-site/KEY routes={nexthop=267 origin=app cost=0 flags=capture expires=never, nexthop=274 origin=app cost=0 flags=capture expires=never}
  /ndn/a-site/%C1.Router/cs/a/KEY routes={nexthop=267 origin=app cost=0 flags=capture expires=never, nexthop=274 origin=app cost=0 flags=capture expires=never}
  /ndn/a-site/%C1.Router/cs/a/nlsr routes={nexthop=267 origin=app cost=0 flags=child-inherit expires=never, nexthop=274 origin=app cost=0 flags=child-inherit expires=never}
  /ndn/a-site/%C1.Router/cs/a/nlsr/KEY routes={nexthop=267 origin=app cost=0 flags=capture expires=never, nexthop=274 origin=app cost=0 flags=capture expires=never}
  /ndn/a-site/%C1.Router/cs/a/nlsr/INFO routes={nexthop=267 origin=app cost=0 flags=capture expires=never, nexthop=274 origin=app cost=0 flags=capture expires=never}
  /ndn/a-site/%C1.Operator routes={nexthop=267 origin=app cost=0 flags=capture expires=never, nexthop=274 origin=app cost=0 flags=capture expires=never}
  /ndn/b-site/b routes={nexthop=264 origin=nlsr cost=10 flags=capture expires=3555s}
  /ndn/b-site/%C1.Router/cs/b routes={nexthop=264 origin=nlsr cost=10 flags=capture expires=never}
  /ndn/c-site/c routes={nexthop=266 origin=nlsr cost=10 flags=capture expires=3555s}
  /ndn/c-site/%C1.Router/cs/c routes={nexthop=266 origin=nlsr cost=10 flags=capture expires=never}
  /ndn/d-site/d routes={nexthop=264 origin=nlsr cost=20 flags=capture expires=3555s}
  /ndn/d-site/%C1.Router/cs/d routes={nexthop=264 origin=nlsr cost=20 flags=capture expires=3555s}
  /localhop/ndn/nlsr/LSA routes={nexthop=267 origin=app cost=0 flags=capture expires=never, nexthop=264 origin=nlsr cost=10 flags=capture expires=never, nexthop=266 origin=nlsr cost=10 flags=capture expires=never, nexthop=274 origin=app cost=0 flags=capture expires=never}
  /localhop/ndn/nlsr/sync/v=10 routes={nexthop=267 origin=app cost=0 flags=child-inherit expires=never, nexthop=264 origin=nlsr cost=10 flags=capture expires=never, nexthop=266 origin=nlsr cost=10 flags=capture expires=never, nexthop=274 origin=app cost=0 flags=child-inherit expires=never}
  /localhost/nfd routes={nexthop=258 origin=app cost=0 flags=child-inherit expires=never}
  /localhost/nlsr routes={nexthop=267 origin=app cost=0 flags=child-inherit expires=never, nexthop=274 origin=app cost=0 flags=child-inherit expires=never}
</pre>

<pre>
CS information:
  capacity=65536
     admit=on
     serve=on
  nEntries=280
     nHits=24
   nMisses=614
   
   </pre>
   
   
   <pre>
Strategy choices:
  prefix=/ strategy=/localhost/nfd/strategy/best-route/v=5
  prefix=/ndn/b-site/%C1.Operator strategy=/localhost/nfd/strategy/best-route/v=5
  prefix=/ndn/d-site/%C1.Operator strategy=/localhost/nfd/strategy/best-route/v=5
  prefix=/localhop/ndn/nlsr/sync/v=10 strategy=/localhost/nfd/strategy/multicast/v=4
  prefix=/ndn/d-site/KEY strategy=/localhost/nfd/strategy/best-route/v=5
  prefix=/ndn/b-site/KEY strategy=/localhost/nfd/strategy/best-route/v=5
  prefix=/localhost strategy=/localhost/nfd/strategy/multicast/v=4
  prefix=/ndn/b-site/%C1.Router/cs/b/KEY strategy=/localhost/nfd/strategy/best-route/v=5
  prefix=/ndn/d-site/%C1.Router/cs/d/nlsr/KEY strategy=/localhost/nfd/strategy/best-route/v=5
  prefix=/ndn/c-site/%C1.Router/cs/c/nlsr/KEY strategy=/localhost/nfd/strategy/best-route/v=5
  prefix=/ndn/broadcast strategy=/localhost/nfd/strategy/multicast/v=4
  prefix=/localhop/ndn/nlsr/LSA strategy=/localhost/nfd/strategy/multicast/v=4
  prefix=/ndn/c-site/KEY strategy=/localhost/nfd/strategy/best-route/v=5
  prefix=/ndn/c-site/%C1.Operator strategy=/localhost/nfd/strategy/best-route/v=5
  prefix=/localhost/nfd strategy=/localhost/nfd/strategy/best-route/v=5
  prefix=/ndn/d-site/%C1.Router/cs/d/KEY strategy=/localhost/nfd/strategy/best-route/v=5
  prefix=/ndn/c-site/%C1.Router/cs/c/KEY strategy=/localhost/nfd/strategy/best-route/v=5
  prefix=/ndn/b-site/%C1.Router/cs/b/nlsr/KEY strategy=/localhost/nfd/strategy/best-route/v=5
  
mini-ndn> 

</pre>
