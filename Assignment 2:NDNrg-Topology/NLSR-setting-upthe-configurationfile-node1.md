### Setting up the configuration file <b>nlsr.conf</b> Router ITB
***
Source : https://named-data.net/doc/NLSR/current/beginners-guide.html#ndnnfdusage
Instructions on how to use the configuration file are already provided at the NLSR’s Router Configuration page [NLSRrtrconf]. Read the information in this page to understand NLSR router configuration. The following text describes the instructions that have been modified at the default <b>nlsr.conf</b> file for Router1 <b>(RouterX)</b>:
***

<b>AT general SECTION:</b>
<pre>
{
  <b>network /ndn/</b>                              <i>; name of the network ITB</i>
  <b>site /ndnrg/itb</b>                            <i>; name of the site ITB</i>
  <b>router /%C1.Router/RouterX</b>                 <i>; name of the router: router1-ITB</i>
}
</pre>


<b>AT neighbors SECTION:</b>
<pre>
neighbors
{
  neighbor
  {
    <b>name /ndn/ndnrg/itb/%C1.Router/RouterX2</b>   <i>; Neighbor router: router2-UTI</i>
    <b>face-uri  udp://192.168.56.103</b>	          <i>; face to the neighbor (IP Router UTI)</i>
    <b>link-cost 25</b>                           <i>; cost of the link Router UTI</i>
  }
}

</pre>

<b>AT advertising SECTION:</b>
<pre>
advertising
{
  <b>prefix /ndn/ndnrg/itb/telmat/residen</b>       ; Advertising destinations
  <b>prefix /ndn/ndnrg/itb/telmat/labipnet</b>      ; for router1-ITB
}
</pre>

<b>AT security SECTION:</b>
<pre>
security
{
  validator
  {
    ...
    trust-anchor
    {
      type file
      file-name "root.cert"        ; root certificate file
    }
  }

  prefix-update-validator
  {
    ...
    trust-anchor
    {
      type file
      file-name "site.cert"        ; site certificate file
    }
  }

  cert-to-publish "root.cert"      ; root certificate file

  cert-to-publish "site.cert"      ; site certificate file

  cert-to-publish "op.cert"        ; operator certificate file

  cert-to-publish "routerX.cert"   ; router1 certificate file
}
</pre>

***
### Setting up the configuration file <b>nlsr.conf</b> Router UTI

The following text shows the modified instructions for router2: <b>(RouterX2)</b>:
***
<b>AT general SECTION:</b>
<pre>
{
  network /ndn/                    <i>; name of the network UTI</i>
  site /ndnrg/uti                  <i>; name of the site UTI</i>
  router /%C1.Router/routerX2      <i>; name of the router: router2-UTI</i>
}
</pre>

<b>AT neighbors SECTION:</b>
<pre>
neighbors
{
  neighbor
  {
    <b>name /ndn/edu/uaslp/%C1.Router/routerX</b>   <i>; Neighbor router: router1-ITB</i>
    <b>face-uri  udp://192.168.56.101</b>          <i>; face to the neighbor (IP Router ITB)</i>
    <b>link-cost 30</b>                             <i>; cost of the link</i>
  }
}
</pre>

<b>AT advertising SECTION:</b>

<pre>
advertising
{
  <b>prefix /ndn/edu/uaslp/labs/networks</b>        ; Advertising destinations
  <b>prefix /ndn/edu/uaslp/labs/hardware</b>        ; for router2-UTI
}
</pre>

<b>AT security SECTION:</b>

<pre>
security
{
  validator
  {
    ...
    trust-anchor
    {
      type file
      file-name "root.cert"        ; root certificate file
    }                              ; this file needs to be copied to
  }                                ; router2-UTI

  prefix-update-validator
  {
    ...
    trust-anchor
    {
      type file
      file-name "site.cert"        ; site certificate file
    }                              ; this file needs to be copied to
  }                                ; router2

  ...
  cert-to-publish "router2.cert"   ; router2 certificate file
}


</pre>
