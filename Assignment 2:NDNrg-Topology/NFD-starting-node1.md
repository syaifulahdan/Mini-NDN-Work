### Starting and configuring NFD (Node 1 : ITB) .
To start and configure NFD it is necessary to open two terminal windows. The first one will be used to start NFD by means of the <b>nfd-start</b> command. This terminal will also display the logs that NFD generates. By default, NFD only generates informational logs (INFO). However, it is possible to obtain different levels of verbosity for these logs. These levels can be set before NFD starts by editing the <b>/usr/local/etc/ndn/nfd.conf</b> file. Open this file using a regular text editor, read the information provided about logging and then modify the default-level variable at the log section according to the instructions provided in the file. Additional information about NFD configuration may be found at [NDNNFDUSAGE](https://named-data.net/doc/NLSR/current/beginners-guide.html#ndnnfdusage)
***

1. Create a configuration file by running the following command as root:
<pre>
$ cp /usr/local/etc/ndn/nfd.conf.sample /usr/local/etc/ndn/nfd.conf
</pre>


2. After the configuration file has been created, NFD’s behavior may be changed by modifying this file. Once the configuration file has been created, it is recommended to start NFD by using the following command:

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NFD-Image-Node1/NFD-Opentwoterminal-node1.png)


<pre>
$ nfd-start
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NFD-Image-Node1/NFD-Start-node1.png)

3.This command does not properly allow to employ the command window to enter new commands; however it displays the NFD logs. Therefore, it is recommended to open a new command window. This second window may be used to verify NDF’s status and then stop NFD by using the following commands:

<pre>
$ nfd-status
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NFD-Image-Node1/NFD-Status-node1.png)

<pre>
bertopeng17-1@NDN-Node1-ITB:~$ nfd-status
General NFD status:
                version=0.7.1-35-g2c61bad9
              startTime=20211013T093750.660000
            currentTime=20211013T112733.282000
                 uptime=6582 seconds
       nNameTreeEntries=19
            nFibEntries=2
            nPitEntries=8
   nMeasurementsEntries=0
             nCsEntries=3
           nInInterests=150
          nOutInterests=150
                nInData=45
               nOutData=35
               nInNacks=0
              nOutNacks=0
    nSatisfiedInterests=34
  nUnsatisfiedInterests=95
Channels:
  tcp4://0.0.0.0:6363
  tcp6://[::]:6363
  udp4://0.0.0.0:6363
  udp6://[::]:6363
  unix:///run/nfd.sock
  ws://0.0.0.0:9696
  ws://[::]:9696
  dev://enp0s3
  dev://enp0s8
  dev://enp0s9
Faces:
  faceid=1 remote=internal:// local=internal:// congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 45d 0n 42705B} out={149i 0d 0n 9070B}} flags={local permanent point-to-point local-fields}
  faceid=254 remote=contentstore:// local=contentstore:// mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={local permanent point-to-point}
  faceid=255 remote=null:// local=null:// mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={local permanent point-to-point}
  faceid=256 remote=ether://[01:00:5e:00:17:aa] local=dev://enp0s3 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=1500 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access}
  faceid=257 remote=ether://[01:00:5e:00:17:aa] local=dev://enp0s8 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=1500 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access}
  faceid=258 remote=ether://[01:00:5e:00:17:aa] local=dev://enp0s9 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=1500 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access}
  faceid=259 remote=fd://36 local=unix:///run/nfd.sock congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={142i 0d 0n 7170B} out={1i 34d 0n 39537B}} flags={local on-demand point-to-point local-fields congestion-marking}
  faceid=260 remote=udp4://224.0.23.170:56363 local=udp4://10.0.2.15:34860 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
  faceid=261 remote=udp4://224.0.23.170:56363 local=udp4://192.168.56.101:57542 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
  faceid=262 remote=udp4://224.0.23.170:56363 local=udp4://192.168.59.3:35940 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
  faceid=263 remote=udp6://[ff02::1234%enp0s3]:56363 local=udp6://[fe80::58ac:acc1:5451:d1f5%enp0s3]:56910 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
  faceid=264 remote=udp6://[ff02::1234%enp0s8]:56363 local=udp6://[fe80::2bf0:93fb:9782:15a4%enp0s8]:41852 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
  faceid=265 remote=udp6://[ff02::1234%enp0s9]:56363 local=udp6://[fe80::5dc4:8d00:8779:3369%enp0s9]:38523 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
  faceid=267 remote=udp4://192.168.56.101:6363 local=udp4://192.168.56.101:6363 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local persistent point-to-point congestion-marking}
  faceid=268 remote=fd://49 local=unix:///run/nfd.sock congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={7i 0d 0n 312B} out={0i 0d 0n 0B}} flags={local on-demand point-to-point congestion-marking}
FIB:
  /localhost/nfd/rib nexthops={faceid=259 (cost=0)}
  /localhost/nfd nexthops={faceid=1 (cost=0)}
RIB:
  /localhost/nfd routes={nexthop=259 origin=app cost=0 flags=child-inherit expires=never}
CS information:
  capacity=65536
     admit=on
     serve=on
  nEntries=3
     nHits=0
   nMisses=150
Strategy choices:
  prefix=/ strategy=/localhost/nfd/strategy/best-route/v=5
  prefix=/localhost strategy=/localhost/nfd/strategy/multicast/v=4
  prefix=/ndn/broadcast strategy=/localhost/nfd/strategy/multicast/v=4
  prefix=/localhost/nfd strategy=/localhost/nfd/strategy/best-route/v=5
bertopeng17-1@NDN-Node1-ITB:~$ 
</pre>

View FIle Otuput [[NFD Status]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/nfd-status-node1.txt)

4.Employ the following command to configure each face that a computer uses to connect to a neighboring computer:
<pre>
$ nfdc face create udp4://<remote-ip-address>
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NFD-Image-Node1/network%20ITB.png)
<pre>
bertopeng17-1@NDN-Node1-ITB:~$ nfdc face create udp://192.168.56.101
</pre>

<pre>
face-exists id=267 local=udp4://192.168.56.101:6363 remote=udp4://192.168.56.101:6363 persistency=persistent reliability=off congestion-marking=on congestion-marking-interval=100ms default-congestion-threshold=65536B mtu=8800
bertopeng17-1@NDN-Node1-ITB:~$ 
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NFD-Image-Node1/ndn-face-create-node1.png)

5. The face id may be displayed by running either nfd-status or:
<pre>
$ nfdc face list
</pre>
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NFD-Image-Node1/NFD-nfdc-facelist-node1.png)

<pre>
bertopeng17-1@NDN-Node1-ITB:~$ nfdc face list
faceid=1 remote=internal:// local=internal:// congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 104d 0n 122368B} out={412i 0d 0n 24405B}} flags={local permanent point-to-point local-fields}
faceid=254 remote=contentstore:// local=contentstore:// mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={local permanent point-to-point}
faceid=255 remote=null:// local=null:// mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={local permanent point-to-point}
faceid=256 remote=ether://[01:00:5e:00:17:aa] local=dev://enp0s3 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=1500 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access}
faceid=257 remote=ether://[01:00:5e:00:17:aa] local=dev://enp0s8 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=1500 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access}
faceid=258 remote=ether://[01:00:5e:00:17:aa] local=dev://enp0s9 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=1500 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access}
faceid=259 remote=fd://36 local=unix:///run/nfd.sock congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={403i 1d 0n 19930B} out={1i 84d 0n 114620B}} flags={local on-demand point-to-point local-fields congestion-marking}
faceid=260 remote=udp4://224.0.23.170:56363 local=udp4://10.0.2.15:34860 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
<b>faceid=261 remote=udp4://224.0.23.170:56363 local=udp4://192.168.56.101:57542 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800</b> counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
<b>faceid=262 remote=udp4://224.0.23.170:56363 local=udp4://192.168.59.3:35940 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800</b>
counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
faceid=263 remote=udp6://[ff02::1234%enp0s3]:56363 local=udp6://[fe80::58ac:acc1:5451:d1f5%enp0s3]:56910 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
faceid=264 remote=udp6://[ff02::1234%enp0s8]:56363 local=udp6://[fe80::2bf0:93fb:9782:15a4%enp0s8]:41852 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
faceid=265 remote=udp6://[ff02::1234%enp0s9]:56363 local=udp6://[fe80::5dc4:8d00:8779:3369%enp0s9]:38523 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
faceid=267 remote=udp4://192.168.56.101:6363 local=udp4://192.168.56.101:6363 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local persistent point-to-point congestion-marking}
faceid=270 remote=fd://49 local=unix:///run/nfd.sock congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={1i 0d 0n 43B} out={0i 0d 0n 0B}} flags={local on-demand point-to-point congestion-marking}
bertopeng17-1@NDN-Node1-ITB:~$ 
</pre>
View FIle Otuput [[NFD Face List]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/nfdc-facelist.txt)

6. The status of the face may be verified by using the following command:
<pre>
$ nfdc face show id <face-id>
</pre>
