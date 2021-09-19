
Mini-NDN-Custom Topology
Tabel Of Content

1. Create Custom Topology [Inline Formatting](#inline-formatting)
2. [[Running Topology]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/ndn-custom-topo-5.md#2-running-topology)
 
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
sudo python examples/mnndn.py topologies/minindn.topo-custom-5.conf
</pre>
![[alt image]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-5-Nodes/running-ct5nodes.png)
