
Mini-NDN-Custom Topology Inherent (33 Node)
***
Tabel Of Content

1. [Penentuan Titik Koordinat](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/ndn-custom-topo-inherent.md#1-penentuan-titik-koordinat) 
2. [Penentuan jarak, Delay dan Bandwith](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/ndn-custom-topo-inherent.md#2-penentuan-jarak-delay-dan-bandwith) 

3. [Running Topology](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/ndn-custom-topo-inherent.md#2-running-topology)
4. [Ping Node](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/ndn-custom-topo-5.md#2-running-topology)

[Back](https://github.com/syaifulahdan/Mini-NDN-Work)

***

 
### <b>1. Penentuan Titik Koordinat</b>   

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/inherent-bb.jpg)

<p text-align=justify> Titik koordinat adalah titik yang berpedoman pada garis latitude dan longitude suatu daerah. Kaitannya dengan latitude dan longitude adalah, kedua garis lintang dan bujur inilah (latitude = garis lintang, longitude = garis bujur) yang menentukan di perolehnya suatu nilai derajat dari suatu titik yang diukur. Titik Koordinat sekolah diperlukan untuk menentukan suatu lokasi node yang akan digunakan secara detail. Dengan mengetahui titik koordinat setiap node kita bisa mengetahui alamat dan letak geografis suatu daerah. Dari titik koordinat tersebut akan didapatkan radius,jarak, delay . Beberapa tolopologi membutuhkan titik koordinat yang nanti akan digunakan untuk implementasi routing berbasis koordinat, tidak semua topologi pada percobaan yang dilakukan menggunakan data koordinat, pada eksperimen ini topologi yang memerlukan data koordinat adalah topologi inherent yang kita jadikan topologi utama untuk dibahas. Untuk menentukan titik koordinat kami menggunakan alat bantu yaitu google map yang nantinya dapat diketahui berapa ukuran jarak yang dapat di estimasi dari setiap titik node yang akan dihubungkan dengan titik node </p text-align=justify> 

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/koordinat-area-1.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/koordinat-area-2.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/koordinat-area-3.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/koordinat-area-4.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/koordinat-area-56.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/koordinat-area-7.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/koordinat-area-8.png)


### <b>2. Penentuan jarak, Delay dan Bandwith</b>   
<p text-align=justify>
untuk mengimplementasikan NLSR routing dan Routing berbasis koordinat perlunya nilai delay yang dipengaruhi berdasarkan media transmisi yang digunakan dan jarak yang ditempuh dari setiap node yang tehubung ke node lain pada percobaan dengan menggunakan topologi inherent kami menggunakan 32 Node yang titiknya sudah ditentukan oleh Inherent Dikti karena itu kami tinggal menambahkan Nilai Delay yang sudah dihitung berdasarkan kesesuaian jarak dan mediat transmisi yang digunakan yaitu dengan menggunakan Fiber Optik Single mode, kapasitas bandwith yang pada setiap node sudah ditentukan berdasarkan skema pembagian bandwith yang tertera pada jaringan Inherent. </p text-align=justify>


![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/bandwith-area-1.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/bandwith-area-1b.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/bandwith-area-2.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/bandwith-area-3.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/bandwith-area-3b.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/bandwith-area-45.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/CustomTopology-Image-Inherent/bandwith-area-6.png)


<pre>
[nodes]
banda-aceh: _ radius=6348531,309 angle=95,3180
medan: _ radius=6218966,849 angle=98,6832
padang: _ radius=6165191,979 angle=100,4200
jambi: _ radius=6008343,767 angle=0103,6897
pekanbaru: _ radius=6121799,488 angle=101,4425
bengkulu: _ radius=6067429,421 angle=102,3119
palembang: _ radius=5940306,46 angle=104,7826
bandar-lampung: _ radius=5893310,374 angle=105,2679
serang: _ radius=5829965,231 angle=91,6518
jkt-ui: _ radius=5783367,44 angle=106,8297
jkt-dikti: _ radius=5785492,732 angle=106,8280
bandung: _ radius=5723100,389 angle=107,6122
semarang: _ radius=5505650,198 angle=110,4312
jogjakarta: _ radius=5495855,106 angle=110,4268
surabaya: _ radius=5297747,653 angle=112,7460
malang: _ radius=5300136,127 angle=112,6273
pontianak: _ radius=5635707,494 angle=109,3363
palangkaraya: _ radius=5222915,24 angle=113,9068
banjarmasin: _ radius=5147091,297 angle=114,6009
samarinda: _ radius=4872832,074 angle=117,1440
gorontalo: _ radius=4163332,249 angle=122,3887
manado: _ radius=3757477,627 angle=124,8394
palu: _ radius=4526275,571 angle=119,8767
makasar: _ radius=5523638,754 angle=119,4379
kendari: _ radius=4133570,405 angle=122,5181
denpasar: _ radius=5032151,98 angle=115,2218
mataram: _ radius=5032151,98 angle=115,2218
kupang: _ radius=3907345,816 angle=123,6064
ternate: _ radius=3273647,687 angle=127,3616
ambon: _ radius=3087269,572 angle=128,1971
manokwari: _ radius=4037893,026 angle=140,6748
jayapura: _ radius=4025088,225 angle=140,6748
host: _ radius=4507134,354 angle=134,535


[links]
banda-aceh:medan delay=2,1ms
medan:pekanbaru delay=2,3ms
medan:padang delay=2,7ms
padang:jambi delay=1,8ms
pekanbaru:palembang delay=2,6ms
palembang:bengkulu delay=2,5ms
pekanbaru:bandar-lampung delay=1,4ms
jambi:bandar-lampung delay=2,3ms
serang:bandar-lampung delay=0,6ms
serang:jkt-ui delay=0,4ms
jkt-ui:jkt-dikti delay=0,1ms
jkt-ui:bandung delay=0,5ms
bandung:jogjakarta delay=1,6ms
jogjakarta:malang delay=1,2ms
jogjakarta:semarang delay=0,4ms
semarang:surabaya delay=1,2ms
surabaya:malang delay=0,4ms
banda-aceh:pontianak delay=8,2ms
pontianak:palangkaraya delay=2,8ms
palangkaraya:banjarmasin delay=0,7ms
banjarmasin:samarinda delay=2,1ms
banjarmasin:surabaya delay=2,4ms
samarinda:manado delay=4,3ms
gorontalo:manado delay=1,3ms
gorontalo:palu delay=1,6ms
palu:makasar delay=2,3ms
makasar:kendari delay=1,8ms
makasar:surabaya delay=3,8ms
denpasar:surabaya delay=1,5ms
denpasar:mataram delay=0,5ms
denpasar:kupang delay=4,6ms
</pre>

Download : [[minindn.topo-inherent.conf]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%203:NDN-CustomTopology/minindn.topo-inherent.conf)

Next, copy the topology file: **minindn.topo-inherent.conf** into the mini-ndn/topologies directory.




### <b>2. Running Topology</b>   

run mini-ndn with the following command

<pre>
& sudo python examples/mnndn.py topologies/minindn.topo-custom-10.conf
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
