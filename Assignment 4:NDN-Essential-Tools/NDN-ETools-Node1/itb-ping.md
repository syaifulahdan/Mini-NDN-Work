# ndn-tools: Use of ping :
Source : https://gerrit.named-data.net/plugins/gitiles/ndn-tools/+/HEAD/tools/ping

### Introduction :

ndnping and ndnpingserver are reachability testing tools for Named Data Networking. They test the reachability between two nodes. The client sends an Interest intended for a node running ndnpingserver. The ping server then sends Data in response. The client then calculates the roundtrip time for the Interest-Data exchange, or marks it as a timeout if the Data is not received within the timeout period.

### Using Client :
The client can be invoked by calling ndnping with a name to ping. For example, to ping /ndn/ndnrg/itb, one would execute:
<pre>
ndnping /ndn/ndnrg/itb
</pre>

There are also a variety of options to control the behavior of the ping client. For example, to send only Ten pings to /ndn/ndnrg/itb, displaying a timestamp with each received Data or timeout, type:

<pre>
ndnping -c 10 -t /ndn/ndnrg/itb
</pre>

Output :
<pre>
bertopeng17-1@NDN-Node1-ITB:~$ ndnping -c 10 -t /ndn/ndnrg/itb
PING /ndn/ndnrg/itb
20220901T160038.469159 - nack from /ndn/ndnrg/itb: seq=13412160586476130027 time=1.47185 ms reason=NoRoute
20220901T160039.470289 - nack from /ndn/ndnrg/itb: seq=13412160586476130028 time=0.997727 ms reason=NoRoute
20220901T160040.470597 - nack from /ndn/ndnrg/itb: seq=13412160586476130029 time=1.03456 ms reason=NoRoute
20220901T160041.471422 - nack from /ndn/ndnrg/itb: seq=13412160586476130030 time=1.48906 ms reason=NoRoute
20220901T160042.479329 - nack from /ndn/ndnrg/itb: seq=13412160586476130031 time=0.69076 ms reason=NoRoute
20220901T160043.481077 - nack from /ndn/ndnrg/itb: seq=13412160586476130032 time=1.34651 ms reason=NoRoute
20220901T160044.490041 - nack from /ndn/ndnrg/itb: seq=13412160586476130033 time=0.284181 ms reason=NoRoute
20220901T160045.495071 - nack from /ndn/ndnrg/itb: seq=13412160586476130034 time=0.929024 ms reason=NoRoute
20220901T160046.495401 - nack from /ndn/ndnrg/itb: seq=13412160586476130035 time=0.825621 ms reason=NoRoute
20220901T160047.496306 - nack from /ndn/ndnrg/itb: seq=13412160586476130036 time=0.873221 ms reason=NoRoute

--- /ndn/ndnrg/itb ping statistics ---
10 packets transmitted, 0 received, 10 nacked, 0% lost, 100% nacked, time 0 ms
bertopeng17-1@NDN-Node1-ITB:~$ 
</pre>

A list of the available options can be found with man ndnping.
<pre>
man ndnping
</pre>

### Using the Server
The server can be invoked by calling ndnpingserver with a name to listen for pings to. For example, to listen for pings to /edu/arizona, one would execute:

<pre>
ndnpingserver /ndn/ndnrg/itb
</pre>

There are also a variety of options to control the behavior of the ping server. For example, to satisfy only 4 ping requests before exiting, execute the following:

<pre>
ndnpingserver -p 10 -t /ndn/ndnrg/itb
</pre>

A list of the available options can be found with man ndnpingserver.

### ndnping Protocol
This section briefly describes ndnping's protocol, in order to allow alternate implementations to be compatible with this implementation. The current protocol version is ndnping protocol version 1. This version number will be incremented in case there's an incompatible change.

### Probe Interests
The client expresses probe Interests that are intended to be forwarded to the server without being aggregated. The Interests MUST have one of the following name structures:

<pre>

ndn:/< prefix >/ping/< seq >
ndn:/< prefix >/ping/< client-identifier >/< seq >

</pre>

<pre>
bertopeng17-1@NDN-Node1-ITB:~$ ndnping ndn:/ndn/ndnrg/itb/ping
PING /ndn/ndnrg/itb/ping
nack from /ndn/ndnrg/itb/ping: seq=5755161568521911114 time=1.36751 ms reason=NoRoute
nack from /ndn/ndnrg/itb/ping: seq=5755161568521911115 time=0.855821 ms reason=NoRoute
nack from /ndn/ndnrg/itb/ping: seq=5755161568521911116 time=0.907511 ms reason=NoRoute
nack from /ndn/ndnrg/itb/ping: seq=5755161568521911117 time=0.746847 ms reason=NoRoute
nack from /ndn/ndnrg/itb/ping: seq=5755161568521911118 time=0.792157 ms reason=NoRoute
nack from /ndn/ndnrg/itb/ping: seq=5755161568521911119 time=0.882581 ms reason=NoRoute
nack from /ndn/ndnrg/itb/ping: seq=5755161568521911120 time=0.861887 ms reason=NoRoute
nack from /ndn/ndnrg/itb/ping: seq=5755161568521911121 time=0.745577 ms reason=NoRoute
nack from /ndn/ndnrg/itb/ping: seq=5755161568521911122 time=0.926996 ms reason=NoRoute
nack from /ndn/ndnrg/itb/ping: seq=5755161568521911123 time=0.756735 ms reason=NoRoute
^C
--- /ndn/ndnrg/itb/ping ping statistics ---
10 packets transmitted, 0 received, 10 nacked, 0% lost, 100% nacked, time 0 ms
bertopeng17-1@NDN-Node1-ITB:~$ 

</pre>




where:

    - <prefix> is the server prefix that contains zero or more NameComponents.
    - <seq> is one NameComponent whose value is an unsigned 64-bit integer, represented as a decimal number in ASCII encoding.
    - <client-identifier> is one NameComponent with arbitrary value.

If a client expresses multiple probe Interests, it is RECOMMENDED for those Interests to have consecutive increasing integers in <seq> field.

If a client uses the name structure with <client-identifier> field, it is RECOMMENDED to use one or more printable characters only, to make it easier for a human operator to read the logs. A client implementation MAY restrict this field to be non-empty and have printable characters only.

The probe Interest SHOULD NOT carry CanBePrefix element.

The probe Interest SHOULD carry MustBeFresh element. A client implementation MAY allow the operator to remove MustBeFresh element.
