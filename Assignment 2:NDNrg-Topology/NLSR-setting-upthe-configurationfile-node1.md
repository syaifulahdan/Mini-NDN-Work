### Setting up the configuration file <b>nlsr.conf</b> Router ITB

Source : https://named-data.net/doc/NLSR/current/beginners-guide.html#ndnnfdusage
Instructions on how to use the configuration file are already provided at the NLSR’s Router Configuration page [NLSRrtrconf]. Read the information in this page to understand NLSR router configuration. The following text describes the instructions that have been modified at the default <b>nlsr.conf</b> file for Router1 <b>(RouterX)</b>:


<b>AT general SECTION:</b>
<pre>
{
  <b>network /ndn/</b>                              ; name of the network ITB
  <b>site /ndnrg/itb</b>                            ; name of the site ITB
  <b>router /%C1.Router/RouterX</b>                 ; name of the router: router1-ITB
}
</pre>


<b>AT neighbors SECTION:</b>
<pre>
neighbors
{
  neighbor
  {
    <b>name /ndn/ndnrg/itb/%C1.Router/RouterX2</b>   ; Neighbor router: router2-UTI
    <b>face-uri  udp://192.168.56.103</b>	        ; face to the neighbor (IP Router UTI)
    <b>link-cost 25</b>                               ; cost of the link Router UTI
  }
}

</pre>

<pre>
; AT advertising SECTION:
advertising
{
  prefix /ndn/ndnrg/itb/telmat/residen       ; Advertising destinations
  prefix /ndn/ndnrg/itb/telmat/labipnet      ; for router1
}

; AT security SECTION:
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

The following text shows the modified instructions for router2:

; AT general SECTION:
{
  network /ndn/                    ; name of the network
  site /edu/uaslp                  ; name of the site
  router /%C1.Router/router2       ; name of the router: router2
}

;AT neighbors SECTION:
neighbors
{
  neighbor
  {
    name /ndn/edu/uaslp/%C1.Router/router1   ; Neighbor router: router1
    face-uri  udp://140.220.80.121           ; face to the neighbor
    link-cost 30                             ; cost of the link
  }
}

; AT advertising SECTION:
advertising
{
  prefix /ndn/edu/uaslp/labs/networks        ; Advertising destinations
  prefix /ndn/edu/uaslp/labs/hardware        ; for router2
}

; AT security SECTION:
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
  }                                ; router2

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
