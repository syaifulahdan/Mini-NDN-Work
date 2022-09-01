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
