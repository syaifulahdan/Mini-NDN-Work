### Starting NLSR (UTI)
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

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NLSR-Image-Node2/NLSR-start-node2-1.png)
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NLSR-Image-Node2/NLSR-start-node2-2.png)


<pre>
bertopeng17-2@NDN-Node2-UTI:~$ export NDN_LOG=nlsr.*=TRACE && nlsr -f /home/bertopeng17-2/NLSR/nlsr-uti.conf 
Wrong configuration section: hello-retries
Wrong configuration section: hello-timeout
Wrong configuration section: hello-interval
Wrong configuration section: adj-lsa-build-interval
Wrong configuration section: face-dataset-fetch-tries
Wrong configuration section: face-dataset-fetch-interval
1634157068.615748 TRACE: [nlsr.ConfParameter] Loading Certificate Name: /ndn/KEY/%C7%96%E1%E8w%C8-%0B/self/v=1633716835538
1634157068.616029 TRACE: [nlsr.ConfParameter] Loading Certificate Name: /ndn/ndnrg/uti/KEY/%D0%93%3F%E6%14%BB%22j/NA/v=1633717793473
1634157068.616320 TRACE: [nlsr.ConfParameter] Loading Certificate Name: /ndn/ndnrg/uti/%C1.Operator/op/KEY/%E8%D08%09%85%EB%FD%1D/NA/v=1633718199068
1634157068.616504 TRACE: [nlsr.ConfParameter] Loading Certificate Name: /ndn/ndnrg/uti/%C1.Router/routerX2/KEY/%26%F7%D1%03m%C04z/NA/v=1633718745400
1634157068.616637  INFO: [nlsr.ConfParameter] Router Name: /%C1.Router/RouterX2
1634157068.616675  INFO: [nlsr.ConfParameter] Site Name: /ndnrg/uti
1634157068.616684  INFO: [nlsr.ConfParameter] Network: /ndn
1634157068.616690  INFO: [nlsr.ConfParameter] Router Prefix: /ndn/ndnrg/uti/%C1.Router/RouterX2
1634157068.616702  INFO: [nlsr.ConfParameter] Sync Prefix: /localhop/ndn/nlsr/sync/v=10
1634157068.616713  INFO: [nlsr.ConfParameter] Sync LSA prefix: /localhop/ndn/nlsr/LSA
1634157068.616721  INFO: [nlsr.ConfParameter] Hello Interest retry number: 3
1634157068.616728  INFO: [nlsr.ConfParameter] Hello Interest resend second: 1
1634157068.616734  INFO: [nlsr.ConfParameter] Info Interest interval: 60
1634157068.616740  INFO: [nlsr.ConfParameter] LSA refresh time: 1800
1634157068.616746  INFO: [nlsr.ConfParameter] FIB Entry refresh time: 3600
1634157068.616752  INFO: [nlsr.ConfParameter] LSA Interest lifetime: 4 seconds
1634157068.616800  INFO: [nlsr.ConfParameter] Router dead interval: 3600
1634157068.616818  INFO: [nlsr.ConfParameter] Max Faces Per Prefix: 3
1634157068.616823  INFO: [nlsr.ConfParameter] State Directory: /var/lib/nlsr
1634157068.616890  INFO: [nlsr.ConfParameter] Adjacency LSA build interval:  10
1634157068.616901  INFO: [nlsr.ConfParameter] Routing calculation interval:  15
1634157068.616909 DEBUG: [nlsr.ConfParameter] Initializing Key ...
1634157068.617667  WARN: [nlsr.ConfParameter] Identity /ndn/ndnrg/uti/%C1.Router/RouterX2/nlsr does not exist
1634157068.618327 ERROR: [nlsr.ConfParameter] Cannot set non-existing identity `/ndn/ndnrg/uti/%C1.Router/RouterX2/nlsr` as default
1634157068.618362 ERROR: [nlsr.ConfParameter] Unable to create identity, NLSR will run without security!
1634157068.618372 ERROR: [nlsr.ConfParameter] Can be ignored if running in non-production environments.
1634157068.618413 TRACE: [nlsr.SyncProtocolAdapter] SyncProtocol value: 0
1634157068.618430 DEBUG: [nlsr.SyncProtocolAdapter] Using PSync
1634157068.620973 DEBUG: [nlsr.SequencingManager] Seq File Name: /var/lib/nlsr/nlsrSeqNo.txt
1634157068.621198 DEBUG: [nlsr.SequencingManager] Adj LSA seq no: 30
1634157068.621221 DEBUG: [nlsr.SequencingManager] Name LSA Seq no: 33
1634157068.621257 DEBUG: [nlsr.Lsdb] Setting interest filter for LsaPrefix: /localhop/ndn/nlsr/LSA
1634157068.621672 DEBUG: [nlsr.SequencingManager] Adj LSA seq no: 30
1634157068.621712 DEBUG: [nlsr.SequencingManager] Name LSA Seq no: 34
1634157068.623015 DEBUG: [nlsr.Lsdb] Adding NAME LSA
1634157068.623054 DEBUG: [nlsr.Lsdb]     NAME LSA:
      Origin Router      : /ndn/ndnrg/uti/%C1.Router/RouterX2
      Sequence Number    : 34
      Expires in         : 3599998 milliseconds
      Names:
        Name 0: /ndn/ndnrg/uti/ftik/labnetwork
        Name 1: /ndn/ndnrg/uti/ftik/labict

1634157068.623116 DEBUG: [nlsr.Lsdb] Scheduling expiration in: 1810 seconds for /ndn/ndnrg/uti/%C1.Router/RouterX2
1634157068.623183 DEBUG: [nlsr.HelloProtocol] Setting interest filter for Hello interest: /ndn/ndnrg/uti/%C1.Router/RouterX2/nlsr/INFO
1634157068.623582 DEBUG: [nlsr.update.PrefixUpdateProcessor] Setting dispatcher to capture Interests for: /localhost/nlsr/prefix-update
1634157068.623793 DEBUG: [nlsr.Nlsr] Initializing Nlsr
1634157068.624435 DEBUG: [nlsr.Nlsr] Default NLSR identity: /
1634157068.625910 DEBUG: [nlsr.Nlsr] Enabling incoming face id indication for local face.
1634157068.626248 TRACE: [nlsr.Nlsr] Initializing Faces...
1634157068.626436 DEBUG: [nlsr.AdjacencyList] -------Adjacency List--------
1634157068.626470 DEBUG: [nlsr.Nlsr] Name prefix list: {
/ndn/ndnrg/uti/ftik/labnetwork
Sources:
  
/ndn/ndnrg/uti/ftik/labict
Sources:
  
}

1634157068.626770 TRACE: [nlsr.CertificateStore] Certificate inserted successfully
1634157068.626920 TRACE: [nlsr.CertificateStore] Certificate inserted successfully
1634157068.627819 TRACE: [nlsr.CertificateStore] Certificate inserted successfully
1634157068.628027 TRACE: [nlsr.CertificateStore] Certificate inserted successfully
FATAL: 1634157068.629551 DEBUG: [nlsr.route.Fib] Clean called
../ndn-cxx/transport/detail/stream-transport-impl.hpp(143): Throw in function connectHandler
Dynamic exception type: boost::exception_detail::clone_impl<boost::exception_detail::error_info_injector<ndn::Transport::Error> >
std::exception::what: error while connecting to the forwarder (No such file or directory)
===== Stacktrace =====
 0# ndn::detail::StreamTransportImpl<ndn::UnixTransport, boost::asio::local::stream_protocol>::connectHandler(boost::system::error_code const&) at ../ndn-cxx/transport/detail/stream-transport-impl.hpp:143
 1# boost::asio::detail::reactive_socket_connect_op<ndn::detail::StreamTransportImpl<ndn::UnixTransport, boost::asio::local::stream_protocol>::connect(boost::asio::local::basic_endpoint<boost::asio::local::stream_protocol> const&)::{lambda(auto:1 const&)#2}>::do_complete(boost::asio::detail::task_io_service*, boost::asio::detail::task_io_service_operation*, boost::system::error_code const&, unsigned long) at /usr/include/boost/asio/detail/reactive_socket_connect_op.hpp:84
 2# boost::asio::detail::task_io_service::run(boost::system::error_code&) at /usr/include/boost/asio/detail/impl/task_io_service.ipp:149
 3# ndn::Face::doProcessEvents(boost::chrono::duration<long, boost::ratio<1l, 1000l> >, bool) at ../ndn-cxx/face.cpp:286
 4# main at ../src/main.cpp:98
 5# 0x00007F7CA24C5BF7 in /lib/x86_64-linux-gnu/libc.so.6
 6# 0x000055D2CD87040A in nlsr
======================

bertopeng17-2@NDN-Node2-UTI:~$ 
</pre>


