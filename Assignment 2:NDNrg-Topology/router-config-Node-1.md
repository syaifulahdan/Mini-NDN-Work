Assume that three routers in the same network, but at three different sites (memphis.edu, arizona.edu, and colostate.edu), are connected to each other to construct the following topology:
***
 ### 1. Network and sample configuration
 ![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NLSR-Image-Node2/example-router-config-node1.png)
 Source : https://named-data.net/doc/NLSR/current/ROUTER-CONFIG.html
 
 he number represents the connecting face id. For example
 <b>/ndn/edu/memphis/%C1.Router/router1</b> is connected to <b>/ndn/edu/arizona/%C1.Router/router3</b> via face 11 and the route cost is 25. To reach <b>/ndn/edu/colostate/%C1.Router/router2</b> via face 12, the route cost is 30. We will walk through setting up the faces and creating the configuration file for <b>/ndn/edu/memphis/%C1.Router/router1</b> It is recommended to configure security as described at Security Configuration, before starting router configuration.
   #### Step 1. Ensuring nfd is running
  Type the following in the terminal:
  <pre>
  nfd-status
  </pre>
  #### Step 2. Determining FaceUri
 Assume that <b>/ndn/edu/arizona/%C1.Router/router3</b> has hostname <b>router3.arizona.edu</b> and <b>/ndn/edu/colostate/%C1.Router/router2</b> has IP address <b>79.123.10.145</b>. <b>/ndn/edu/memphis/%C1.Router/router1</b> will consider <b>FaceUri udp4://router3.arizona.edu</b> for router <b>/ndn/edu/arizona/%C1.Router/router3 </b>and <b>FaceUri udp4://79.123.10.145</b> for router <b>/ndn/edu/colostate/%C1.Router/router2</b>.
 
  ![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NLSR-Image-Node1/example-scenario-router-config-node1.png.png)
 
  
 ####  Step 3: Creating configuration file
  
  
  Now, assume that <b>/ndn/memphis.edu/router1</b> wants to advertise three name prefixes <b>/ndn/memphis/sports/basketball/grizzlies, /ndn/memphis/entertainment/blues, /ndn/news/memphis/politics/lutherking)</b>. The configuration file with the necessary configuration commands follows
  
 Step 4: Running NLSR on /ndn/memphis.edu/router1

<pre>
general
{
	network /ndn/
	site /edu/memphis/
	router /%C1.Router/router1

	lsa-refresh-time 1800
	lsa-interest-lifetime 4
	state-dir /var/lib/nlsr/
}
neighbors
{
	hello-retries 3 
	hello-timeout 1
	hello-interval  60
	adj-lsa-build-interval 5
	first-hello-interval  10
	neighbor
	{
		name /ndn/edu/arizona/%C1.Router/router3
		face-uri  udp4://router3.arizona.edu
		link-cost 25
	}
	neighbor
	{
		name /ndn/edu/colostate/%C1.Router/router2
		face-uri  udp4://79.123.10.14
		link-cost 30
	}
}
hyperbolic
{
	state off 
	radius   123.456
	angle    1.45
}
fib
{
	max-faces-per-prefix 3
}

advertising
{
	prefix /ndn/memphis/sports/basketball/grizzlies
    	prefix /ndn/memphis/entertainment/blues
    	prefix /ndn/news/memphis/politics/lutherking
</pre>
