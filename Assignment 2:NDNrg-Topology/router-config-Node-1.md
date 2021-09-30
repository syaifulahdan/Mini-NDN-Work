Assume that three routers in the same network, but at three different sites (memphis.edu, arizona.edu, and colostate.edu), are connected to each other to construct the following topology:
***
 1. network and sample configuration
 
  Step 1. Ensuring nfd is running
  
  Step 2. Determining FaceUri
  
  Step 3: Creating configuration file
  
  
  Now, assume that /ndn/memphis.edu/router1 wants to advertise three name prefixes (/ndn/memphis/sports/basketball/grizzlies, /ndn/memphis/entertainment/blues, /ndn/news/memphis/politics/lutherking). The configuration file with the necessary configuration commands follows
  Step 4: Running NLSR on /ndn/memphis.edu/router1

<pre>
                                                ; the general section contains all the general settings for router

<b>general</b>
<b>{</b>
                                                ; mandatory configuration command section network, site and router

  <b>network /ndn/</b>                          ; name of the network the router belongs to in ndn URI format
  <b>site /edu/memphis</b>                      ; name of the site the router belongs to in ndn URI format
  <b>router /%C1.Router/cs/pollux</b>           ; name of the router in ndn URI format

                                                ; lsa-refresh-time is the time in seconds, after which router will refresh its LSAs
  <b>lsa-refresh-time 1800</b>                  ; default value 1800. Valid values 240-7200

                                                ; router-dead-interval is the time in seconds after which an inactive routers
                                                ; LSAs are removed
                                                ; router-dead-interval 3600 ; default value: 2*lsa-refresh-time. Value must be larger
                                                ; than lsa-refresh-time

                                                ; InterestLifetime (in seconds) for LSA fetching
  <b>lsa-interest-lifetime 4</b>                ; default value 4. Valid values 1-60

                                                ; select sync protocol: chronosync or psync
   <b>sync-protocol psync</b>

                                                ; sync interest lifetime of ChronoSync/PSync in milliseconds
   <b>sync-interest-lifetime 60000</b>              ; default value 60000. Valid values 1000-120,000

   <b>state-dir       /var/lib/nlsr</b>         ; path for intermediate state files including sequence directory (Absolute path)
<b>}</b>

                                                ; the neighbors section contains the configuration for router's neighbors and hello protocol behavior

<b>neighbors</b>
<b>{</b>
                                                ; in case hello interest timed out, router will try 'hello-retries' times at 'hello-timeout'
                                                ; seconds interval before giving up for any neighbors (deciding link is down)

   <b>hello-retries 3</b>                       ; interest retries number in integer. Default value 3
                                                ; valid values 1-10

   <b>hello-timeout 1</b>                       ; interest time out value in seconds. Default value 1
                                                ; Valid values 1-15

   <b>hello-interval  60</b>                    ; interest sending interval in seconds. Default value 60
                                                ; valid values 30-90

                                                ; adj-lsa-build-interval is the time to wait in seconds after an Adjacency LSA build is scheduled
                                                ; before actually building the Adjacency LSA

  <b>adj-lsa-build-interval 10</b>             ; default value 10. Valid values 5-30.

  <b>face-dataset-fetch-tries 3</b>            ; default is 3. Valid values 1-10. The FaceDataset is
                                               ; gotten from NFD, and is needed to configure NLSR
                                               ; correctly. It is recommended not to set this
                                               ; variable too high, because it could cause
                                               ; congestion for NFD.
 
  <b>face-dataset-fetch-interval 3600</b>      ; default is 3600. Valid values 1800-5400.
                                               ; This controls how often (in seconds) NLSR will attempt to
                                               ; fetch a FaceStatus dataset from NFD.

                                               ; neighbor command is used to configure router's neighbor. Each neighbor will need
                                               ; one block of neighbor command

  <b>neighbor</b> 
  <b>{</b> 
    <b>name /ndn/edu/memphis/%C1.Router/cs/castor</b>   ; name prefix of the neighbor router consists
                                                        ; of network, site-name and router-name

    <b>face-uri  udp://castor.cs.memphis.edu</b>        ; face uri of the face connected to the neighbor
    <b>link-cost 25</b>                                 ; cost of the connecting link to neighbor
  <b>}</b> 

  <b>neighbor
  <b>{
    <b>name /ndn/edu/memphis/%C1.Router/cs/mira  ; name prefix of the neighbor router consists
                                              ; of network, site-name and router-name

    <b>face-uri  udp://mira.cs.memphis.edu       ; face uri of the face connected to the neighbor
    <b>link-cost 30                              ; cost of the connecting link to neighbor
  <b>}
<b>}

; the hyperbolic section contains the configuration settings of enabling a router to calculate
; routing table using [hyperbolic routing table calculation](http://arxiv.org/abs/0805.1266) method

<b>hyperbolic
<b>{
  ; commands in this section follows a strict order
  ; the switch is used to set hyperbolic routing calculation in NLSR

  <b>state off             ; default value 'off', set value 'on' to enable hyperbolic routing table
                        ; calculation which turns link state routing 'off'. set value to 'dry-run'
                        ; to test hyperbolic routing and compare with link state routing.


  <b>radius   123.456      ; radius of the router in hyperbolic coordinate system
  <b>angle    1.45,2.36    ; angle of the router in hyperbolic coordinate system
<b>}


; the fib section is used to configure fib entrys type to ndn FIB updated by NLSR

<b>fib
<b>{
  ; the max-faces-per-prefix is used to limit the number of faces for each name prefixes
  ; by NLSR in ndn FIB

  <b>max-faces-per-prefix 3   ; default value 0. Valid value 0-60. By default (value 0) NLSR adds
                           ; all available faces for each reachable name prefixes in NDN FIB

  ; routing-calc-interval is the time to wait in seconds after a routing table calculation is
  ; scheduled before actually performing the routing table calculation

  <b>routing-calc-interval 15   ; default value 15. Valid values 0-15. It is recommended that
                             ; routing-calc-interval have a higher value than adj-lsa-build-interval
<b>}

; the advertising section contains the configuration settings of the name prefixes
; hosted by this router

<b>advertising
<b>{
  ; the ndnname is used to advertised name from the router. To advertise each name prefix
  ; configure one block of ndnname configuration command for every name prefix.

  <b>prefix /ndn/edu/memphis/cs/netlab           ; name in ndn URI format
  <b>prefix /ndn/edu/memphis/sports/basketball
}

security
{
  validator
  {
    rule
    {
      id "NLSR Hello Rule"
      for data
      filter
      {
        type name
        regex ^[^<nlsr><INFO>]*<nlsr><INFO><><>$
      }
      checker
      {
        type customized
        sig-type ecdsa-sha256
        key-locator
        {
          type name
          hyper-relation
          {
            k-regex ^([^<KEY><nlsr>]*)<nlsr><KEY><>$
            k-expand \\1
            h-relation equal
            p-regex ^([^<nlsr><INFO>]*)<nlsr><INFO><><>$
            p-expand \\1
          }
        }
      }
    }

    rule
    {
      id "NLSR LSA Rule"
      for data
      filter
      {
        type name
        regex ^[^<nlsr><LSA>]*<nlsr><LSA>
      }
      checker
      {
        type customized
        sig-type ecdsa-sha256
        key-locator
        {
          type name
          hyper-relation
          {
            k-regex ^([^<KEY><nlsr>]*)<nlsr><KEY><>$
            k-expand \\1
            h-relation equal
            ; the last four components in the prefix should be <lsaType><seqNo><version><segmentNo>
            p-regex ^<localhop>([^<nlsr><LSA>]*)<nlsr><LSA>(<>*)<><><><>$
            p-expand \\1\\2
          }
        }
      }
    }

    rule
    {
      id "NLSR Hierarchy Exception Rule"
      for data
      filter
      {
        type name
        regex ^[^<KEY><%C1.Router>]*<%C1.Router>[^<KEY><nlsr>]*<KEY><><><>$
      }
      checker
      {
        type customized
        sig-type ecdsa-sha256
        key-locator
        {
          type name
          hyper-relation
          {
            k-regex ^([^<KEY><%C1.Operator>]*)<%C1.Operator>[^<KEY>]*<KEY><>$
            k-expand \\1
            h-relation equal
            p-regex ^([^<KEY><%C1.Router>]*)<%C1.Router>[^<KEY>]*<KEY><><><>$
            p-expand \\1
          }
        }
      }
    }

    rule
    {
      id "NLSR Hierarchical Rule"
      for data
      filter
      {
        type name
        regex ^[^<KEY>]*<KEY><><><>$
      }
      checker
      {
        type hierarchical
        sig-type ecdsa-sha256
      }
    }

    trust-anchor
    {
      type file
      file-name "root.cert"
    }
  }

  prefix-update-validator
  {
    rule
    {
      id "NLSR ControlCommand Rule"
      for interest
      filter
      {
        type name</b>
        ; /<prefix>/<management-module>/<command-verb>/<control-parameters>
        ; /<timestamp>/<random-value>/<signed-interests-components>
        regex ^<localhost><nlsr><prefix-update>[<advertise><withdraw>]<><><>$
      }
      checker
      {
        type customized
        sig-type ecdsa-sha256
        key-locator
        {
          type name
          regex ^([^<KEY><%C1.Operator>]*)<%C1.Operator>[^<KEY>]*<KEY><>$
        }
      }
    }

    rule
    {
      id "NLSR Hierarchy Rule"
      for data
      filter
      {
        type name
        regex ^[^<KEY>]*<KEY><><><>$
      }
      checker
      {
        type hierarchical
        sig-type ecdsa-sha256
      }
    }

    trust-anchor
    {
      type file
      file-name "site.cert"
    }
  }

  ; cert-to-publish "root.cert"  ; optional, a file containing the root certificate
                                 ; Only the router that is designated to publish the root cert
                                 ; needs to specify this

  ; cert-to-publish "site.cert"  ; optional, a file containing the site certificate
                                 ; Only the router that is designated to publish the site cert
                                 ; needs to specify this

  ; cert-to-publish "operator.cert" ; optional, a file containing the operator certificate
                                    ; Only the router that is designated to publish the operator
                                    ; cert needs to specify this

  cert-to-publish "router.cert"  ; required, a file containing the router certificate.
}
</pre>
