
Mini-NDN-Custom Topology 15 Nodes
***
Tabel Of Content

1. [Create Custom Topology 15 Nodes](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/ndn-custom-topo-15.md#1-create-custom-topology-15-node) 
2. [Running Topology](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/ndn-custom-topo-5.md#2-running-topology)
3. [Ping Node](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/ndn-custom-topo-5.md#2-running-topology)

[Back](https://github.com/syaifulahdan/Mini-NDN-Work)

***

 
### <b>1. Create Custom Topology 15 Node</b>   

<pre>
[nodes]
jakarta: _ radius=107,0007857 angle=356.680854
bandung: _ radius=107.8313820 angle=356.336204
tasik: _ radius=108.4655794 angle=356.114135
purwokerto: _ radius=109.4820089 angle=356.111480
magelang: _ radius=110.4711825 angle=356.117822
semarang: _ radius=110.6613764 angle=356.368302
klaten: _ radius=110.9311298 angle=355.999261
medan: _ radius=98.72597954 angle=2.08602249
makasar: _ radius=119.3300154 angle=357.532005
balikpapan: _ radius=116.8375735 angle=359.392869
surabaya: _ radius=112.9854148 angle=356.317153
padang: _ radius=100.4108292 angle=359.459762
jayapura: _ radius=140.6399641 angle=358.944101
manado: _ radius=124.849872 angle=0.67717960
jogjakarta: _ radius=110.0943746 angle=355.959737

[links]
jakarta:bandung delay=8ms
bandung:tasik delay=7ms
tasik:purwokerto delay=8ms
purwokerto:magelang delay=3ms
magelang:jogjakarta delay=3ms
jogjakarta:semarang delay=5ms
semarang:klaten delay=3ms
klaten:surabaya delay=11ms
surabaya:makasar delay=12ms
makasar:balikpapan delay=13ms
balikpapan:manado delay=10ms
manado:jayapura delay=15ms
jayapura:surabaya delay=17ms
medan:padang delay=8ms
padang:jakarta delay=11ms
jakarta:medan delay=13ms
jakarta:tasik delay=8ms
bandung:purwokerto delay=15ms
bandung:padang delay=16ms
bandung:medan delay=17ms
tasik:magelang delay=7ms
tasik:jogjakarta delay=10ms
purwokerto:jogjakarta delay=5ms
purwokerto:semarang delay=5ms
purwokerto:klaten delay=6ms
magelang:semarang delay=5ms
jogjakarta:klaten delay=7ms
surabaya:manado delay=13ms
surabaya:balikpapan delay=16ms
surabaya:tasik delay=18ms
makasar:jayapura delay=15ms
makasar:manado delay=17ms
balikpapan:jayapura delay=13ms
</pre>

Download : [[minindn.topo-custom-15.conf]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/minindn.topo-custom-15.conf)

Next, copy the topology file: **minindn.topo-custom-15.conf** into the mini-ndn/topologies directory.

### <b>2. Running Topology</b>   

run mini-ndn with the following command

<pre>
& sudo python examples/mnndn.py topologies/minindn.topo-custom-15.conf
</pre>
![[alt image]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-15-Nodes/running-ct-15node.png)

### <b>3. Ping Node</b>   
<pre>
mini-ndn> surabaya ndnping makasar
</pre>
![[alt image]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-5-Nodes/ct5nodes-ping-surabaya-makasar.png)
<pre>
mini-ndn> surabaya ndnping makasar

</pre>
