To see the status of the forwarder on the node:
<pre>
[node-name] <b>nfdc status report<b>
</pre>

1. Running Example Topology
<pre>
$ sudo python examples/mnndn.py
</pre>

2.  see the status of the forwarder on the node

<pre>
mini-ndn> a nfdc status report
</pre>
will show the results as below
<pre>
mini-ndn> a nfdc status report
General NFD status:
                version=0.7.1-35-g2c61bad9
              startTime=20210918T190915.982000
            currentTime=20210918T190942.520000
                 uptime=26 seconds
       nNameTreeEntries=65
            nFibEntries=13
            nPitEntries=9
   nMeasurementsEntries=0
             nCsEntries=62
           nInInterests=102
          nOutInterests=102
                nInData=84
               nOutData=84
               nInNacks=4
              nOutNacks=6
    nSatisfiedInterests=78
  nUnsatisfiedInterests=6
Channels:
  tcp4://0.0.0.0:6363
  tcp6://[::]:6363
  udp4://0.0.0.0:6363
  udp6://[::]:6363
  dev://a-eth0
  dev://a-eth1
  unix:///run/a.sock
  ws://0.0.0.0:9696
  ws://[::]:9696
Faces:
  faceid=1 remote=internal:// local=internal:// congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 56d 0n 21347B} out={55i 0d 0n 9961B}} flags={local permanent point-to-point local-fields}
  faceid=254 remote=contentstore:// local=contentstore:// mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={local permanent point-to-point}
  faceid=255 remote=null:// local=null:// mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={local permanent point-to-point}
  faceid=256 remote=ether://[01:00:5e:00:17:aa] local=dev://a-eth0 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=1500 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access}
  faceid=257 remote=ether://[01:00:5e:00:17:aa] local=dev://a-eth1 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=1500 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access}
  faceid=258 remote=fd://34 local=unix:///run/a.sock congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={30i 15d 0n 10850B} out={16i 30d 0n 13926B}} flags={local on-demand point-to-point local-fields congestion-marking}
  faceid=259 remote=udp4://224.0.23.170:56363 local=udp4://10.0.0.1:53107 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
  faceid=260 remote=udp4://224.0.23.170:56363 local=udp4://10.0.0.5:46933 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
  faceid=261 remote=udp6://[ff02::1234%a-eth0]:56363 local=udp6://[fe80::44df:ecff:fe2a:bdf3%a-eth0]:48386 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
  faceid=262 remote=udp6://[ff02::1234%a-eth1]:56363 local=udp6://[fe80::3c78:9aff:feb2:457f%a-eth1]:44269 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
  faceid=264 remote=udp4://10.0.0.2:6363 local=udp4://10.0.0.1:6363 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={8i 5d 1n 2331B} out={9i 5d 0n 2301B}} flags={non-local permanent point-to-point congestion-marking}
  faceid=266 remote=udp4://10.0.0.6:6363 local=udp4://10.0.0.5:6363 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={7i 3d 3n 1807B} out={9i 6d 0n 2644B}} flags={non-local permanent point-to-point congestion-marking}
  faceid=267 remote=fd://43 local=unix:///run/a.sock congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={48i 5d 0n 10544B} out={13i 41d 6n 20152B}} flags={local on-demand point-to-point local-fields congestion-marking}
  faceid=268 remote=fd://46 local=unix:///run/a.sock congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={7i 0d 0n 312B} out={0i 0d 0n 0B}} flags={local on-demand point-to-point congestion-marking}
FIB:
  /localhost/nfd/rib nexthops={faceid=258 (cost=0)}
  /ndn/c-site/%C1.Router/cs/c nexthops={faceid=266 (cost=10)}
  /ndn/a-site/%C1.Router/cs/a/nlsr/KEY nexthops={faceid=267 (cost=0)}
  /localhop/ndn/nlsr/LSA nexthops={faceid=267 (cost=0), faceid=264 (cost=10), faceid=266 (cost=10)}
  /ndn/a-site/%C1.Router/cs/a/nlsr nexthops={faceid=267 (cost=0)}
  /ndn/b-site/%C1.Router/cs/b nexthops={faceid=264 (cost=10)}
  /localhost/nfd nexthops={faceid=1 (cost=0)}
  /ndn/a-site/%C1.Router/cs/a/nlsr/INFO nexthops={faceid=267 (cost=0)}
  /ndn/a-site/%C1.Operator nexthops={faceid=267 (cost=0)}
  /ndn/a-site/%C1.Router/cs/a/KEY nexthops={faceid=267 (cost=0)}
  /localhost/nlsr nexthops={faceid=267 (cost=0)}
  /localhop/ndn/nlsr/sync/v=10 nexthops={faceid=267 (cost=0), faceid=264 (cost=10), faceid=266 (cost=10)}
  /ndn/a-site/KEY nexthops={faceid=267 (cost=0)}
RIB:
  /ndn/a-site/KEY routes={nexthop=267 origin=app cost=0 flags=capture expires=never}
  /ndn/a-site/%C1.Router/cs/a/KEY routes={nexthop=267 origin=app cost=0 flags=capture expires=never}
  /ndn/a-site/%C1.Router/cs/a/nlsr routes={nexthop=267 origin=app cost=0 flags=child-inherit expires=never}
  /ndn/a-site/%C1.Router/cs/a/nlsr/KEY routes={nexthop=267 origin=app cost=0 flags=capture expires=never}
  /ndn/a-site/%C1.Router/cs/a/nlsr/INFO routes={nexthop=267 origin=app cost=0 flags=capture expires=never}
  /ndn/a-site/%C1.Operator routes={nexthop=267 origin=app cost=0 flags=capture expires=never}
  /ndn/b-site/%C1.Router/cs/b routes={nexthop=264 origin=nlsr cost=10 flags=capture expires=never}
  /ndn/c-site/%C1.Router/cs/c routes={nexthop=266 origin=nlsr cost=10 flags=capture expires=never}
  /localhop/ndn/nlsr/LSA routes={nexthop=267 origin=app cost=0 flags=capture expires=never, nexthop=264 origin=nlsr cost=10 flags=capture expires=never, nexthop=266 origin=nlsr cost=10 flags=capture expires=never}
  /localhop/ndn/nlsr/sync/v=10 routes={nexthop=267 origin=app cost=0 flags=child-inherit expires=never, nexthop=264 origin=nlsr cost=10 flags=capture expires=never, nexthop=266 origin=nlsr cost=10 flags=capture expires=never}
  /localhost/nfd routes={nexthop=258 origin=app cost=0 flags=child-inherit expires=never}
  /localhost/nlsr routes={nexthop=267 origin=app cost=0 flags=child-inherit expires=never}
CS information:
  capacity=65536
     admit=on
     serve=on
  nEntries=62
     nHits=2
   nMisses=100
Strategy choices:
  prefix=/ strategy=/localhost/nfd/strategy/best-route/v=5
  prefix=/ndn/b-site/%C1.Operator strategy=/localhost/nfd/strategy/best-route/v=5
  prefix=/ndn/d-site/%C1.Operator strategy=/localhost/nfd/strategy/best-route/v=5
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
  prefix=/localhop/ndn/nlsr/sync/v=10 strategy=/localhost/nfd/strategy/multicast/v=4
  prefix=/ndn/b-site/%C1.Router/cs/b/nlsr/KEY strategy=/localhost/nfd/strategy/best-route/v=5
mini-ndn> 

</pre>
