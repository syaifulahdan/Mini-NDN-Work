### Starting and configuring NFD (Node 2 : UTI) .
To start and configure NFD it is necessary to open two terminal windows. The first one will be used to start NFD by means of the <b>nfd-start</b> command. This terminal will also display the logs that NFD generates. By default, NFD only generates informational logs (INFO). However, it is possible to obtain different levels of verbosity for these logs. These levels can be set before NFD starts by editing the <b>/usr/local/etc/ndn/nfd.conf</b> file. Open this file using a regular text editor, read the information provided about logging and then modify the default-level variable at the log section according to the instructions provided in the file. Additional information about NFD configuration may be found at [NDNNFDUSAGE](https://named-data.net/doc/NLSR/current/beginners-guide.html#ndnnfdusage)
***

1. Create a configuration file by running the following command as root:
<pre>
$ cp /usr/local/etc/ndn/nfd.conf.sample /usr/local/etc/ndn/nfd.conf
</pre>


2. After the configuration file has been created, NFD’s behavior may be changed by modifying this file. Once the configuration file has been created, it is recommended to start NFD by using the following command:

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NFD-Image-Node2/NFD-Openterminal-node2.png)


<pre>
$ nfd-start
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NFD-Image-Node2/NFD-Start-node2.png)

3.This command does not properly allow to employ the command window to enter new commands; however it displays the NFD logs. Therefore, it is recommended to open a new command window. This second window may be used to verify NDF’s status and then stop NFD by using the following commands:

<pre>
$ nfd-status
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NFD-Image-Node2/NFD-Status-node2.png)

<pre>
bertopeng17-2@NDN-Node2-UTI:~$ nfd-status
General NFD status:
                version=0.7.1-35-g2c61bad9
              startTime=20211013T162813.229000
            currentTime=20211013T162842.927000
                 uptime=29 seconds
       nNameTreeEntries=13
            nFibEntries=2
            nPitEntries=4
   nMeasurementsEntries=0
             nCsEntries=2
           nInInterests=13
          nOutInterests=13
                nInData=19
               nOutData=9
               nInNacks=0
              nOutNacks=0
    nSatisfiedInterests=9
  nUnsatisfiedInterests=0
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
  faceid=1 remote=internal:// local=internal:// congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 19d 0n 5531B} out={13i 0d 0n 1103B}} flags={local permanent point-to-point local-fields}
  faceid=254 remote=contentstore:// local=contentstore:// mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={local permanent point-to-point}
  faceid=255 remote=null:// local=null:// mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={local permanent point-to-point}
  faceid=256 remote=ether://[01:00:5e:00:17:aa] local=dev://enp0s3 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=1500 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access}
  faceid=257 remote=ether://[01:00:5e:00:17:aa] local=dev://enp0s8 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=1500 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access}
  faceid=258 remote=ether://[01:00:5e:00:17:aa] local=dev://enp0s9 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=1500 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access}
  faceid=259 remote=fd://36 local=unix:///run/nfd.sock congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={10i 0d 0n 836B} out={0i 9d 0n 2766B}} flags={local on-demand point-to-point local-fields congestion-marking}
  faceid=260 remote=udp4://224.0.23.170:56363 local=udp4://10.0.2.15:33471 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
  faceid=261 remote=udp4://224.0.23.170:56363 local=udp4://192.168.56.103:53387 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
  faceid=262 remote=udp4://224.0.23.170:56363 local=udp4://192.168.57.4:34371 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
  faceid=263 remote=udp6://[ff02::1234%enp0s3]:56363 local=udp6://[fe80::b71f:eb9e:f52:20d%enp0s3]:39331 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
  faceid=264 remote=udp6://[ff02::1234%enp0s8]:56363 local=udp6://[fe80::949f:a27b:9803:9cb4%enp0s8]:38962 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
  faceid=265 remote=udp6://[ff02::1234%enp0s9]:56363 local=udp6://[fe80::1045:8aa:6596:27a6%enp0s9]:56373 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
  faceid=266 remote=fd://49 local=unix:///run/nfd.sock congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={3i 0d 0n 137B} out={0i 0d 0n 0B}} flags={local on-demand point-to-point congestion-marking}
FIB:
  /localhost/nfd/rib nexthops={faceid=259 (cost=0)}
  /localhost/nfd nexthops={faceid=1 (cost=0)}
RIB:
  /localhost/nfd routes={nexthop=259 origin=app cost=0 flags=child-inherit expires=never}
CS information:
  capacity=65536
     admit=on
     serve=on
  nEntries=2
     nHits=0
   nMisses=17
Strategy choices:
  prefix=/ strategy=/localhost/nfd/strategy/best-route/v=5
  prefix=/localhost strategy=/localhost/nfd/strategy/multicast/v=4
  prefix=/ndn/broadcast strategy=/localhost/nfd/strategy/multicast/v=4
  prefix=/localhost/nfd strategy=/localhost/nfd/strategy/best-route/v=5
bertopeng17-2@NDN-Node2-UTI:~$ 

</pre>

View FIle Otuput [[NFD Status]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/nfd-status-node2.txt)

4.Employ the following command to configure each face that a computer uses to connect to a neighboring computer:
<pre>
$ nfdc face create udp4://<remote-ip-address>
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NFD-Image-Node2/network-uti.png)
<pre>
bertopeng17-2@NDN-Node2-UTI:~$ nfdc face create udp://192.168.56.103
</pre>

<pre>
bertopeng17-2@NDN-Node2-UTI:~$ nfdc face create udp://192.168.56.103
face-created id=268 local=udp4://192.168.56.103:6363 remote=udp4://192.168.56.103:6363 persistency=persistent reliability=off congestion-marking=on congestion-marking-interval=100ms default-congestion-threshold=65536B mtu=8800
bertopeng17-2@NDN-Node2-UTI:~$ 
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NFD-Image-Node2/ndn-face-create-node2.png)

#### 5. The face id may be displayed by running either nfd-status or:
<pre>
$ nfdc face list
</pre>
[alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NFD-Image-Node2/NFD-nfdc-facelist-node2.png)

<pre>
bertopeng17-2@NDN-Node2-UTI:~$ nfdc face list
faceid=1 remote=internal:// local=internal:// congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 31d 0n 10495B} out={25i 0d 0n 1877B}} flags={local permanent point-to-point local-fields}
faceid=254 remote=contentstore:// local=contentstore:// mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={local permanent point-to-point}
faceid=255 remote=null:// local=null:// mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={local permanent point-to-point}
faceid=256 remote=ether://[01:00:5e:00:17:aa] local=dev://enp0s3 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=1500 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access}
faceid=257 remote=ether://[01:00:5e:00:17:aa] local=dev://enp0s8 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=1500 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access}
faceid=258 remote=ether://[01:00:5e:00:17:aa] local=dev://enp0s9 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=1500 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access}
faceid=259 remote=fd://36 local=unix:///run/nfd.sock congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={17i 1d 0n 1413B} out={1i 14d 0n 4054B}} flags={local on-demand point-to-point local-fields congestion-marking}
faceid=260 remote=udp4://224.0.23.170:56363 local=udp4://10.0.2.15:33471 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
<b>faceid=261 remote=udp4://224.0.23.170:56363 local=udp4://192.168.56.103:53387 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800</b>
counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
<b>faceid=262 remote=udp4://224.0.23.170:56363 local=udp4://192.168.57.4:34371 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800</b> counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
faceid=263 remote=udp6://[ff02::1234%enp0s3]:56363 local=udp6://[fe80::b71f:eb9e:f52:20d%enp0s3]:39331 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
faceid=264 remote=udp6://[ff02::1234%enp0s8]:56363 local=udp6://[fe80::949f:a27b:9803:9cb4%enp0s8]:38962 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
faceid=265 remote=udp6://[ff02::1234%enp0s9]:56363 local=udp6://[fe80::1045:8aa:6596:27a6%enp0s9]:56373 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local permanent multi-access congestion-marking}
<b>faceid=268 remote=udp4://192.168.56.103:6363 local=udp4://192.168.56.103:6363 congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800</b> counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}} flags={non-local persistent point-to-point congestion-marking}
faceid=269 remote=fd://49 local=unix:///run/nfd.sock congestion={base-marking-interval=100ms default-threshold=65536B} mtu=8800 counters={in={1i 0d 0n 43B} out={0i 0d 0n 0B}} flags={local on-demand point-to-point congestion-marking}
bertopeng17-2@NDN-Node2-UTI:~$ 
</pre>
View FIle Otuput [[NFD Face List]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/nfdc-facelist-node2.txt)

#### 6. The status of the face may be verified by using the following command:
<pre>
$ nfdc face show id <face-id>
</pre>

<pre>
bertopeng17-2@NDN-Node2-UTI:~$ nfdc face show id 261
    faceid=261
    remote=udp4://224.0.23.170:56363
     <b>local=udp4://192.168.56.103:53387</b>
congestion={base-marking-interval=100ms default-threshold=65536B}
       mtu=8800
  counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}}
     flags={non-local permanent multi-access congestion-marking}
bertopeng17-2@NDN-Node2-UTI:~$ nfdc face show id 262
    faceid=262
    remote=udp4://224.0.23.170:56363
     <b>local=udp4://192.168.57.4:34371</b>
congestion={base-marking-interval=100ms default-threshold=65536B}
       mtu=8800
  counters={in={0i 0d 0n 0B} out={0i 0d 0n 0B}}
     flags={non-local permanent multi-access congestion-marking}
bertopeng17-2@NDN-Node2-UTI:~$ 

</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NFD-Image-Node2/nfdc-faceshowid-node2.png)

#### 7. Turning everything off:
In order to stop NLSR and NFD, the following sequence of events is recommended:
1. Stop NLSR / NFD by pressing the Ctrl+C keys at the third terminal window.
2. Destroy the face to the remote computers using either of the following two commands at the second terminal window:

<pre>
$ nfdc face destroy <face-id>
$ nfdc face destroy udp4://<remote-ip-address>
</pre>


<pre>
bertopeng17-1@NDN-Node1-ITB:~$ <b>nfdc face destroy 261</b>
face-destroyed id=261 local=udp4://192.168.56.101:57542 remote=udp4://224.0.23.170:56363 persistency=permanent reliability=off congestion-marking=off
bertopeng17-1@NDN-Node1-ITB:~$ <b>nfdc face destroy udp4://192.168.56.101</b>
face-destroyed id=267 local=udp4://192.168.56.101:6363 remote=udp4://192.168.56.101:6363 persistency=persistent reliability=off congestion-marking=off
bertopeng17-1@NDN-Node1-ITB:~$ 
</pre>

![img alt](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NFD-Image-Node1/NFD-facedestroy-node1.png)

3. Stop NFD by entering the following command at the second terminal window:
<pre>
$ nfd-stop
</pre>

