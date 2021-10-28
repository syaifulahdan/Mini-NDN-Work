### Setting up the configuration file <b>nlsr.conf</b> Router UTI (5 Node)
***
Source : https://named-data.net/doc/NLSR/current/beginners-guide.html#ndnnfdusage
Instructions on how to use the configuration file are already provided at the NLSR’s Router Configuration page [NLSRrtrconf]. Read the information in this page to understand NLSR router configuration. The following text describes the instructions that have been modified at the default <b>nlsr.conf</b> file for Router1 <b>(RouterX2)</b>:
***
![alt img](https://raw.githubusercontent.com/syaifulahdan/Mini-NDN-Work/main/Assignment%202%3ANDNrg-Topology/NDNrg-Image-Node1/NFD-Image-Node1/network-itb.png)



<pre>
general
{
  network /ndn/                             
  site /ndnrg/itb                         
  router /%C1.Router/routerX   

  lsa-refresh-time 1800         
  lsa-interest-lifetime 4      
  ;sync-protocol psync    
  ;sync-interest-lifetime 60000 
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
	name /ndn/ndnrg/uti/%C1.Router/routerX2 
	face-uri  udp4://routerX2.uti.ndnrg
    	link-cost 15    
	}
neighbor
	{
	name /ndn/ndnrg/telu/%C1.Router/routerX3
	face-uri  udp4://routerX3.telu.ndnrg    
    	;face-uri  udp://192.168.59.4            
    	link-cost 25       
	}                  
  	
}

hyperbolic
{
state off 
radius   123.456
angle    1.45,2.36
}

fib
{
max-faces-per-prefix 3
;routing-calc-interval 15
}

advertising
{
  prefix /ndn/ndnrg/itb/telmat/residen 
  prefix /ndn/ndnrg/itb/telmat/labipnet   
    
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
        type name
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

  cert-to-publish "root.cert"      

  cert-to-publish "site.cert"     

  cert-to-publish "op.cert"        

  cert-to-publish "routerX.cert"  
}



</pre>

View Detail file Configuration : [[nlsr-itb-5-node.conf]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/nlsr-itb-5-node.conf)
