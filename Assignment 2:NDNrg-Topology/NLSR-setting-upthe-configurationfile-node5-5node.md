<pre>
general
{
  network /ndn/                             
  site /ndnrg/ittj                         
  router /%C1.Router/routerX5   

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
	name /ndn/ndnrg/lipi/%C1.Router/routerX4
	face-uri  udp4://routerX4.lipi.ndnrg
    	link-cost 10    
	}
neighbor
	{
	name /ndn/ndnrg/uti/%C1.Router/routerX2
	face-uri  udp4://routerX3.telu.ndnrg    
    	link-cost 34       
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
  prefix /ndn/ndnrg/ittj/telkom/tel1
  prefix /ndn/ndnrg/ittj/telkom/tel2   
    
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
        regex ^[^]*<><>$
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
            k-regex ^([^]*)<>$
            k-expand \\1
            h-relation equal
            p-regex ^([^]*)<><>$
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
        regex ^[^]*
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
            k-regex ^([^]*)<>$
            k-expand \\1
            h-relation equal
            ; the last four components in the prefix should be 
            p-regex ^([^]*)(<>*)<><><><>$
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
        regex ^[^<%C1.Router>]*<%C1.Router>[^]*<><><>$
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
            k-regex ^([^<%C1.Operator>]*)<%C1.Operator>[^]*<>$
            k-expand \\1
            h-relation equal
            p-regex ^([^<%C1.Router>]*)<%C1.Router>[^]*<><><>$
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
        regex ^[^]*<><><>$
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
        ; ////
        ; ///
        regex ^[]<><><>$
      }
      checker
      {
        type customized
        sig-type ecdsa-sha256
        key-locator
        {
          type name
          regex ^([^<%C1.Operator>]*)<%C1.Operator>[^]*<>$
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
        regex ^[^]*<><><>$
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

  cert-to-publish "routerX5.cert"  
}          {
            k-regex ^([^<%C1.Operator>]*)<%C1.Operator>[^]*<>$
            k-expand \\1
            h-relation equal
            p-regex ^([^<%C1.Router>]*)<%C1.Router>[^]*<><><>$
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
        regex ^[^]*<><><>$
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
        ; ////
        ; ///
        regex ^[]<><><>$
      }
      checker
      {
        type customized
        sig-type ecdsa-sha256
        key-locator
        {
          type name
          regex ^([^<%C1.Operator>]*)<%C1.Operator>[^]*<>$
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
        regex ^[^]*<><><>$
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

  cert-to-publish "routerX5.cert"  
}
