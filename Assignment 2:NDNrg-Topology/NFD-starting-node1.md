### Starting and configuring NFD
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

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NFD-Image-Node1/NFD-start-node1.png)

3.This command does not properly allow to employ the command window to enter new commands; however it displays the NFD logs. Therefore, it is recommended to open a new command window. This second window may be used to verify NDF’s status and then stop NFD by using the following commands:

<pre>
$ nfd-status
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NFD-Image-Node1/NFD-Status-node1.png)


4.Employ the following command to configure each face that a computer uses to connect to a neighboring computer:
<pre>
$ nfdc face create udp4://<remote-ip-address>
</pre>

<pre>
$ nfd-stop
</pre>

