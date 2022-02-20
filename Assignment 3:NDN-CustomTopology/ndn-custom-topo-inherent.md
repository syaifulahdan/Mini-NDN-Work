
Mini-NDN-Custom Topology Inherent (33 Node)
***
Tabel Of Content

1. [Determination of Coordinate Points](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/ndn-custom-topo-inherent.md#1-determination-of-coordinate-points-) 
2. [Determination of distance, delay and bandwidth](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/ndn-custom-topo-inherent.md#2-determination-of-distance-delay-and-bandwidth) 
3. [Running Topology](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/ndn-custom-topo-inherent.md#3-running-topology)
4. [Ping Node](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/ndn-custom-topo-inherent.md#3-ping-node)
5. [View forwarder status on Nodes](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/ndn-custom-topo-inherent.md#5-view-forwarder-status-on-nodes)
6. [View routing status on nodes:](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/ndn-custom-topo-inherent.md#6-view-routing-status-on-nodes)

[Back](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%200:Chapter/Chapter-4.md)

***

 
### <b>1. Determination of Coordinate Points </b>  

Mini-NDN uses a configuration file describing the topology and its parameters to setup a network.

https://minindn.memphis.edu/experiment.html

https://minindn.memphis.edu/howtos.html#add-a-node-in-root-namespace

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/inherent-bb.jpg)

<p text-align=justify> Coordinate points are points that are guided by the latitude and longitude lines of an area. The relation with latitude and longitude is, these two latitudes and longitudes (latitude = latitude, longitude = longitude) determine the degree value obtained from a point being measured. School coordinates are needed to determine a node location that will be used in detail. By knowing the coordinates of each node, we can find out the address and geographic location of an area. From these coordinate points, the radius, distance, delay will be obtained. Some topologies require coordinate points which will later be used for the implementation of coordinate-based routing, not all topologies in the experiments carried out use coordinate data, in this experiment the topologies that require coordinate data are inherent topologies that we make the main topology to be discussed. To determine the coordinates, we use a tool, namely a google map which can later be known how much distance can be estimated from each node point that will be connected to the node point. </p text-align=justify> 

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/koordinat-area-1.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/koordinat-area-2.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/koordinat-area-3.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/koordinat-area-4.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/koordinat-area-56.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/koordinat-area-7.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/koordinat-area-8.png)


### <b>2. Determination of distance, delay and bandwidth</b>   
<p text-align=justify>
To implement NLSR routing and coordinate-based routing, the delay value is influenced by the transmission media used and the distance traveled from each connected node to other nodes in the experiment using the inherent topology, we use 32 nodes whose points have been determined by the Inherent Dikti. just add the Delay Value that has been calculated based on the suitability of the distance and transmission media used, namely by using Single Mode Optical Fiber, the bandwidth capacity of each node has been determined based on the bandwidth sharing scheme listed on the Inherent network.. </p text-align=justify>


![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/bandwith-area-1.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/bandwith-area-1b.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/bandwith-area-2.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/bandwith-area-3.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/bandwith-area-3b.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/bandwith-area-45.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/bandwith-area-6.png)


<pre>
[nodes]
aceh: _ radius=6348531.309 angle=95.3180
medan: _ radius=6218966.849 angle=98.6832
padang: _ radius=6165191.979 angle=100.4200
jambi: _ radius=6008343.767 angle=0103.6897
pekanbaru: _ radius=6121799.488 angle=101.4425
bengkulu: _ radius=6067429.421 angle=102.3119
palembang: _ radius=5940306.46 angle=104.7826
lampung: _ radius=5893310.374 angle=105.2679
serang: _ radius=5829965.231 angle=91.6518
ui: _ radius=5783367.44 angle=106.8297
dikti: _ radius=5785492.732 angle=106.8280
bandung: _ radius=5723100.389 angle=107.6122
semarang: _ radius=5505650.198 angle=110.4312
jogjakarta: _ radius=5495855.106 angle=110.4268
surabaya: _ radius=5297747.653 angle=112.7460
malang: _ radius=5300136.127 angle=112.6273
pontianak: _ radius=5635707.494 angle=109.3363
palangkaraya: _ radius=5222915.24 angle=113.9068
banjarmasin: _ radius=5147091.297 angle=114.6009
samarinda: _ radius=4872832.074 angle=117.1440
gorontalo: _ radius=4163332.249 angle=122.3887
manado: _ radius=3757477.627 angle=124.8394
palu: _ radius=4526275.571 angle=119.8767
makasar: _ radius=5523638.754 angle=119.4379
kendari: _ radius=4133570.405 angle=122.5181
denpasar: _ radius=5032151.98 angle=115.2218
mataram: _ radius=5032151.99 angle=115.2218
kupang: _ radius=3907345.816 angle=123.6064
ternate: _ radius=3273647.687 angle=127.3616
ambon: _ radius=3087269.572 angle=128.1971
manokwari: _ radius=4037893.026 angle=140.6748
jayapura: _ radius=4025088.225 angle=140.6748
vsat: _ radius=4507134.354 angle=134.535
[links]
aceh:medan delay=2.1ms bw=8 
medan:pekanbaru delay=2.3ms bw=8
medan:padang delay=2.7ms bw=8
padang:jambi delay=1.8ms bw=8
pekanbaru:palembang delay=2.6ms bw=8
palembang:bengkulu delay=2.5ms bw=8
lampung:palembang delay=1.4ms bw=8
lampung:jambi delay=2.3ms bw=8
serang:lampung delay=0.6ms bw=8
serang:ui delay=0.4ms bw=8
ui:dikti delay=0.1ms bw=155
ui:bandung delay=0.5ms bw=155
dikti:semarang delay=0.1ms bw=155
bandung:jogjakarta delay=1.6ms bw=155
jogjakarta:malang delay=1.2ms bw=155
jogjakarta:semarang delay=0.4ms bw=155
semarang:surabaya delay=1.2ms bw=155
surabaya:malang delay=0.4ms bw=155
gorontalo:manado delay=1.3ms bw=8
gorontalo:palu delay=1.6ms bw=8
palu:makasar delay=2.3ms bw=8
makasar:kendari delay=1.8ms bw=8
makasar:surabaya delay=3.8ms bw=8
denpasar:surabaya delay=1.5ms bw=8
denpasar:mataram delay=0.5ms bw=8
denpasar:kupang delay=4.6ms bw=8
kendari:kupang delay=1.8ms bw=1
aceh:pontianak delay=8.2ms bw=1
samarinda:manado delay=4.3ms bw=1
bengkulu:mataram delay=1.8 bw=1
vsat:ui delay=1.2ms bw=2
vsat:ternate delay=1.2ms bw=2
vsat:ambon delay=1.2ms bw=2
vsat:jayapura delay=1.2ms bw=2
vsat:manokwari delay=1.2ms bw=2

</pre>

Download : [[minindn.topo-inherent.conf]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/minindn.topo-inherent.conf)

Next, copy the topology file: **minindn.topo-inherent.conf** into the mini-ndn/topologies directory.




### <b>3. Running Topology</b>   

run mini-ndn with the following command

<pre>
& sudo python examples/mnndn.py topologies/minindn.topo-custom-10.conf
</pre>
![[alt image]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/running-inherentnodes.png)

### <b>4. Ping Node</b>   
<pre>
mini-ndn> surabaya ndnping makasar
</pre>
![[alt image]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-5-Nodes/ct5nodes-ping-surabaya-makasar.png)

<pre>
mini-ndn> surabaya ndnping makasar
</pre>
### <b>5. View forwarder status on Nodes:</b>   
<pre>
mini-ndn> a nfdc status report
</pre>
<pre>
mini-ndn> aceh nfdc status report
</pre>

![[alt image]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/nfdcstatusreport.png)


<pre>
mini-ndn> aceh nfdc status report
General NFD status:
                version=0.7.1-35-g2c61bad9
              startTime=20220220T171608.360000
            currentTime=20220220T171950.925000
                 uptime=222 seconds
       nNameTreeEntries=19
            nFibEntries=2
            nPitEntries=8
   nMeasurementsEntries=0
             nCsEntries=4
           nInInterests=26
          nOutInterests=26
                nInData=23
               nOutData=16
               nInNacks=0
              nOutNacks=0
    nSatisfiedInterests=15
  nUnsatisfiedInterests=3
Channels:
  tcp4://0.0.0.0:6363
  tcp6://[::]:6363
  udp4://0.0.0.0:6363
  udp6://[::]:6363
  dev://aceh-eth0
  dev://aceh-eth1
  unix:///run/aceh.sock
  ws://0.0.0.0:9696
  ws://[::]:9696
Faces:
  faceid=1 remote=internal:// local=internal:// congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 23d 0n 6320B} out={25i 0d 0n 2084B}} flags={local permanent point-to-point local-fields}
  faceid=254 remote=contentstore:// local=contentstore:// mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={local permanent point-to-point}
  faceid=255 remote=null:// local=null:// mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={local permanent point-to-point}
  faceid=256 remote=ether://[01:00:5e:00:17:aa] local=dev://aceh-eth0 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=1500 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access}
  faceid=257 remote=ether://[01:00:5e:00:17:aa] local=dev://aceh-eth1 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=1500 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access}
  faceid=258 remote=fd://34 local=unix:///run/aceh.sock congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={17i 0d 0n 1141B} out={1i 14d 0n 3707B}} flags={local on-demand point-to-point local-fields congestion-marking}
  faceid=259 remote=udp4://224.0.23.170:56363 local=udp4://10.0.0.1:59930 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
  faceid=260 remote=udp4://224.0.23.170:56363 local=udp4://10.0.0.5:50268 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
  faceid=261 remote=udp6://[ff02::1234%aceh-eth0]:56363 local=udp6://[fe80::c9e:f4ff:fe57:ac04%aceh-eth0]:40846 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
  faceid=262 remote=udp6://[ff02::1234%aceh-eth1]:56363 local=udp6://[fe80::6cdc:76ff:fed3:d5c1%aceh-eth1]:56003 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
  faceid=264 remote=udp4://10.0.0.2:6363 local=udp4://10.0.0.1:6363 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent point-to-point congestion-marking}
  faceid=266 remote=udp4://10.0.0.6:6363 local=udp4://10.0.0.5:6363 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent point-to-point congestion-marking}
  faceid=267 remote=fd://43 local=unix:///run/aceh.sock congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={7i 0d 0n 312B} out={0i 0d 0n 0B}} flags={local on-demand point-to-point congestion-marking}
FIB:
  /localhost/nfd/rib nexthops={faceid=258 (cost=0)}
  /localhost/nfd nexthops={faceid=1 (cost=0)}
RIB:
  /localhost/nfd routes={nexthop=258 origin=app cost=0 flags=child-inherit expires=never}
CS information:
  capacity=65536
     admit=on
     serve=on
  nEntries=4
     nHits=0
   nMisses=26
Strategy choices:
  prefix=/ strategy=/localhost/nfd/strategy/best-route/v=5
  prefix=/localhost strategy=/localhost/nfd/strategy/multicast/v=4
  prefix=/ndn/broadcast strategy=/localhost/nfd/strategy/multicast/v=4
  prefix=/localhost/nfd strategy=/localhost/nfd/strategy/best-route/v=5
mini-ndn> 
</pre>

### <b>6. View routing status on nodes</b>   
<pre>
mini-ndn> a nlsrc status
</pre>

<pre>
mini-ndn> aceh nlsrc status
</pre>
