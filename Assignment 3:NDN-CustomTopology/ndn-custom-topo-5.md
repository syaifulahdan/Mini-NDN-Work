
Mini-NDN-Custom Topology

Tabel Of Content

1. [Create Custom Topology](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/ndn-custom-topo-5.md#1-create-custom-topology) 
2. [Running Topology](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/ndn-custom-topo-5.md#2-running-topology)
3. [Ping Node](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/ndn-custom-topo-5.md#2-running-topology)
 
### <b>1. Create Custom Topology</b>   

<pre>
[nodes]
makasar: _ radius=119.3300154 angle=357.532005
balikpapan: _ radius=116.8375735 angle=359.392869
surabaya: _ radius=112.9854148 angle=356.317153
jayapura: _ radius=140.6399641 angle=358.944101
manado: _ radius=124.849872 angle=0.67717960

[links]
surabaya:makasar delay=12ms
makasar:balikpapan delay=13ms
balikpapan:manado delay=10ms
manado:jayapura delay=15ms
jayapura:surabaya delay=17ms
surabaya:manado delay=13ms
surabaya:balikpapan delay=16ms
makasar:jayapura delay=15ms
makasar:manado delay=17ms
balikpapan:jayapura delay=13ms
</pre>

Download : [[minindn.topo-custom-5.conf]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/minindn.topo-custom-5.conf)

Next, copy the topology file: **minindn.topo-custom-5.conf** into the mini-ndn/topologies directory.

### <b>2. Running Topology</b>   

run mini-ndn with the following command

<pre>
& sudo python examples/mnndn.py topologies/minindn.topo-custom-5.conf
</pre>
![[alt image]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-5-Nodes/running-ct5nodes.png)

### <b>3. Ping Node</b>   
<pre>
mini-ndn> surabaya ndnping makasar
</pre>
![[alt image]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-5-Nodes/ct5nodes-ping-surabaya-makasar.png)
<pre>
mini-ndn> surabaya ndnping makasar
PING /10.0.0.30
nack from /10.0.0.30: seq=1135692866024963264 time=3.50113 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963265 time=5.20804 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963266 time=4.60919 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963267 time=0.393291 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963268 time=1.11631 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963269 time=0.449848 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963270 time=0.468286 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963271 time=6.7422 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963272 time=0.897432 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963273 time=0.742885 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963274 time=9.51562 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963275 time=0.44403 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963276 time=4.32832 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963277 time=1.0984 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963278 time=0.642454 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963279 time=0.912115 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963280 time=1.04506 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963281 time=0.812591 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963282 time=0.801107 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963283 time=0.644165 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963284 time=1.05096 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963285 time=11.3095 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963286 time=3.79353 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963287 time=1.03518 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963288 time=1.03106 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963289 time=0.7019 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963290 time=2.88971 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963291 time=4.50517 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963292 time=0.812343 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963293 time=0.535498 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963294 time=0.711599 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963295 time=0.809905 ms reason=NoRoute
nack from /10.0.0.30: seq=1135692866024963296 time=1.00937 ms reason=NoRoute
</pre>
