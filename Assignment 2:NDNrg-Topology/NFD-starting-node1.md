### Starting and configuring NFD
To start and configure NFD it is necessary to open two terminal windows. The first one will be used to start NFD by means of the <b>nfd-start</b> command. This terminal will also display the logs that NFD generates. By default, NFD only generates informational logs (INFO). However, it is possible to obtain different levels of verbosity for these logs. These levels can be set before NFD starts by editing the <b>/usr/local/etc/ndn/nfd.conf</b> file. Open this file using a regular text editor, read the information provided about logging and then modify the default-level variable at the log section according to the instructions provided in the file. Additional information about NFD configuration may be found at [NDNNFDUSAGE](https://named-data.net/doc/NLSR/current/beginners-guide.html#ndnnfdusage)
***
The first one will be used to start NFD
<pre>
$ nfd-start
</pre>
The second terminal will be used to monitor the NFD status:
<pre>
$ nfd-status
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NFD-Image-Node1/NFD-Opentwoterminal-node1.png)
