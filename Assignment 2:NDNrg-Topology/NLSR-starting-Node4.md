### Starting NLSR (LIPI)
It is recommended to open a third command terminal and run NLSR in this window. After the NLSR configuration file has been edited and saved as nlsr.conf, it is possible to start NLSR by running either of the following two commands:
***
<pre>
$ nlsr
$ nlsr -f <configuration-file>
</pre>

However, to verify what is NLSR doing, it becomes necessary to employ NLSR’s logging facility [NLSRstarting]. A brief description on how to use NDN’s logging facility may be displayed by entering the man ndn-log command. This guide recommends using one of the following two instructions to start NLSR:
<pre>
$ export NDN_LOG=nlsr.*=TRACE && nlsr
$ export NDN_LOG=nlsr.*=TRACE && nlsr -f <configuration-file>
</pre>

<pre>
bertopeng17-2@NDN-Node2-UTI:~$ export NDN_LOG=nlsr.*=TRACE && nlsr -f /home/bertopeng17-2/NLSR/nlsr-uti.conf 
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node4/NLSR-Image-Node4/NLSR-start-node4-1.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node4/NLSR-Image-Node4/NLSR-start-node4-2.png)


<pre>
bertopeng17-4@NDN-Node4-LIPI:~$ export NDN_LOG=nlsr.*=TRACE && nlsr -f /home/bertopeng17-4/NLSR/nlsr-lipi-5-node.conf 
1635367228.868002 TRACE: [nlsr.ConfParameter] Loading Certificate Name: /ndn/KEY/%B9%14%1A%F0%83%D1Wd/self/v=1635358304232
1635367228.868891 TRACE: [nlsr.ConfParameter] Loading Certificate Name: /ndn/ndnrg/lipi/KEY/%16%D9%40%8F%DAI%5C%A1/NA/v=1635359359491
1635367228.868944 TRACE: [nlsr.ConfParameter] Loading Certificate Name: /ndn/ndnrg/lipi/%C1.Operator/op/KEY/%11a%1C%7Dnz%01%EB/NA/v=1635359715442
1635367228.868989 TRACE: [nlsr.ConfParameter] Loading Certificate Name: /ndn/ndnrg/lipi/%C1.Router/routerX4/KEY/%C2%C1%28%14.%23%D8%94/NA/v=1635360239898
1635367228.869028  INFO: [nlsr.ConfParameter] Router Name: /%C1.Router/routerX4
1635367228.869038  INFO: [nlsr.ConfParameter] Site Name: /ndnrg/lipi
1635367228.869040  INFO: [nlsr.ConfParameter] Network: /ndn
1635367228.869042  INFO: [nlsr.ConfParameter] Router Prefix: /ndn/ndnrg/lipi/%C1.Router/routerX4
1635367228.869046  INFO: [nlsr.ConfParameter] Sync Prefix: /localhop/ndn/nlsr/sync/v=10
1635367228.869050  INFO: [nlsr.ConfParameter] Sync LSA prefix: /localhop/ndn/nlsr/LSA
1635367228.869052  INFO: [nlsr.ConfParameter] Hello Interest retry number: 3
1635367228.869054  INFO: [nlsr.ConfParameter] Hello Interest resend second: 1
1635367228.869055  INFO: [nlsr.ConfParameter] Info Interest interval: 60
1635367228.869058  INFO: [nlsr.ConfParameter] LSA refresh time: 1800
1635367228.869060  INFO: [nlsr.ConfParameter] FIB Entry refresh time: 3600
1635367228.869061  INFO: [nlsr.ConfParameter] LSA Interest lifetime: 4 seconds
1635367228.869078  INFO: [nlsr.ConfParameter] Router dead interval: 3600
1635367228.869083  INFO: [nlsr.ConfParameter] Max Faces Per Prefix: 3
1635367228.869085  INFO: [nlsr.ConfParameter] State Directory: /var/lib/nlsr/
1635367228.869088  INFO: [nlsr.ConfParameter] Adjacency LSA build interval:  5
1635367228.869094  INFO: [nlsr.ConfParameter] Routing calculation interval:  15
1635367228.869098 DEBUG: [nlsr.ConfParameter] Initializing Key ...
1635367228.869330  WARN: [nlsr.ConfParameter] Identity /ndn/ndnrg/lipi/%C1.Router/routerX4/nlsr does not exist
1635367228.869562 ERROR: [nlsr.ConfParameter] Cannot set non-existing identity `/ndn/ndnrg/lipi/%C1.Router/routerX4/nlsr` as default
1635367228.869575 ERROR: [nlsr.ConfParameter] Unable to create identity, NLSR will run without security!
1635367228.869577 ERROR: [nlsr.ConfParameter] Can be ignored if running in non-production environments.
1635367228.869593 TRACE: [nlsr.SyncProtocolAdapter] SyncProtocol value: 0
1635367228.869600 DEBUG: [nlsr.SyncProtocolAdapter] Using PSync
1635367228.872295 DEBUG: [nlsr.SequencingManager] Seq File Name: /var/lib/nlsr//nlsrSeqNo.txt
1635367228.872331 DEBUG: [nlsr.SequencingManager] Adj LSA seq no: 0
1635367228.872334 DEBUG: [nlsr.SequencingManager] Name LSA Seq no: 0
1635367228.872345 DEBUG: [nlsr.Lsdb] Setting interest filter for LsaPrefix: /localhop/ndn/nlsr/LSA
1635367228.872469 DEBUG: [nlsr.SequencingManager] Adj LSA seq no: 0
1635367228.872483 DEBUG: [nlsr.SequencingManager] Name LSA Seq no: 1
1635367228.872577 DEBUG: [nlsr.Lsdb] Adding NAME LSA
1635367228.872589 DEBUG: [nlsr.Lsdb]     NAME LSA:
      Origin Router      : /ndn/ndnrg/lipi/%C1.Router/routerX4
      Sequence Number    : 1
      Expires in         : 3599999 milliseconds
      Names:
        Name 0: /ndn/ndnrg/lipi/tik/labit1
        Name 1: /ndn/ndnrg/lipi/tik/labit2

1635367228.872608 DEBUG: [nlsr.Lsdb] Scheduling expiration in: 1810 seconds for /ndn/ndnrg/lipi/%C1.Router/routerX4
1635367228.872627 DEBUG: [nlsr.HelloProtocol] Setting interest filter for Hello interest: /ndn/ndnrg/lipi/%C1.Router/routerX4/nlsr/INFO
1635367228.872798 DEBUG: [nlsr.update.PrefixUpdateProcessor] Setting dispatcher to capture Interests for: /localhost/nlsr/prefix-update
1635367228.872843 DEBUG: [nlsr.Nlsr] Initializing Nlsr
1635367228.873035 DEBUG: [nlsr.Nlsr] Default NLSR identity: /
1635367228.873288 DEBUG: [nlsr.Nlsr] Enabling incoming face id indication for local face.
1635367228.873454 TRACE: [nlsr.Nlsr] Initializing Faces...
1635367228.874430 DEBUG: [nlsr.AdjacencyList] -------Adjacency List--------
1635367228.874447 DEBUG: [nlsr.AdjacencyList] Adjacent: /ndn/ndnrg/ittj/%C1.Router/routerX5
		Connecting FaceUri: udp4://36.86.63.182:6363
		Link cost: 10
		Status: 0
		Interest Timed Out: 0

1635367228.874464 DEBUG: [nlsr.AdjacencyList] Adjacent: /ndn/ndnrg/telu/%C1.Router/routerX3
		Connecting FaceUri: udp4://36.86.63.182:6363
		Link cost: 28
		Status: 0
		Interest Timed Out: 0

1635367228.874469 DEBUG: [nlsr.Nlsr] Name prefix list: {
/ndn/ndnrg/lipi/tik/labit1
Sources:
  
/ndn/ndnrg/lipi/tik/labit2
Sources:
  
}

1635367228.874542 TRACE: [nlsr.CertificateStore] Certificate inserted successfully
1635367228.874581 TRACE: [nlsr.CertificateStore] Certificate inserted successfully
1635367228.874611 TRACE: [nlsr.CertificateStore] Certificate inserted successfully
1635367228.874661 TRACE: [nlsr.CertificateStore] Certificate inserted successfully
FATAL: 1635367228.875372 DEBUG: [nlsr.route.Fib] Clean called
../ndn-cxx/transport/detail/stream-transport-impl.hpp(143): Throw in function connectHandler
Dynamic exception type: boost::exception_detail::clone_impl<boost::exception_detail::error_info_injector<ndn::Transport::Error> >
std::exception::what: error while connecting to the forwarder (No such file or directory)
===== Stacktrace =====
 0# ndn::detail::StreamTransportImpl<ndn::UnixTransport, boost::asio::local::stream_protocol>::connectHandler(boost::system::error_code const&) at ../ndn-cxx/transport/detail/stream-transport-impl.hpp:143
 1# boost::asio::detail::reactive_socket_connect_op<ndn::detail::StreamTransportImpl<ndn::UnixTransport, boost::asio::local::stream_protocol>::connect(boost::asio::local::basic_endpoint<boost::asio::local::stream_protocol> const&)::{lambda(auto:1 const&)#2}>::do_complete(boost::asio::detail::task_io_service*, boost::asio::detail::task_io_service_operation*, boost::system::error_code const&, unsigned long) at /usr/include/boost/asio/detail/reactive_socket_connect_op.hpp:84
 2# boost::asio::detail::task_io_service::run(boost::system::error_code&) at /usr/include/boost/asio/detail/impl/task_io_service.ipp:149
 3# ndn::Face::doProcessEvents(boost::chrono::duration<long, boost::ratio<1l, 1000l> >, bool) at ../ndn-cxx/face.cpp:286
 4# main at ../src/main.cpp:98
 5# 0x00007F13EBAF4BF7 in /lib/x86_64-linux-gnu/libc.so.6
 6# 0x00005642FE1B505A in nlsr
======================

bertopeng17-4@NDN-Node4-LIPI:~$ 

</pre>


