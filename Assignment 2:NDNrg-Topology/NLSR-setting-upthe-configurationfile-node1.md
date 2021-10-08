Setting up the configuration file <b>nlsr.conf</b> Router ITB
Source : https://named-data.net/doc/NLSR/current/beginners-guide.html#ndnnfdusage
Instructions on how to use the configuration file are already provided at the NLSR’s Router Configuration page [NLSRrtrconf]. Read the information in this page to understand NLSR router configuration. The following text describes the instructions that have been modified at the default <b>nlsr.conf</b> file for Router1 <b>(RouterX)</b>:
<pre>
; AT general SECTION:
{
  network /ndn/                    ; name of the network
  site /edu/uaslp                  ; name of the site
  router /%C1.Router/router1       ; name of the router: router1
}

;AT neighbors SECTION:
neighbors
{
  neighbor
  {
    name /ndn/edu/uaslp/%C1.Router/router2   ; Neighbor router: router2
    face-uri  udp://140.220.80.124           ; face to the neighbor
    link-cost 30                             ; cost of the link
  }
}

; AT advertising SECTION:
advertising
{
  prefix /ndn/edu/uaslp/office/bldg1         ; Advertising destinations
  prefix /ndn/edu/uaslp/office/bldg2         ; for router1
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

  cert-to-publish "router1.cert"   ; router1 certificate file
}
</pre>
