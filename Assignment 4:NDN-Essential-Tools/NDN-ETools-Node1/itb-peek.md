# ndn-tools: Use of peek

ndnpeek and ndnpoke

    ndnpeek is a consumer program that sends interest packets and expects data packets
    
    ndnpoke is a producer program that provides data packages and corresponding interest packages
    
    
usage example:
    Start nfd
    Execute in a terminal:
    <pre>
    echo 'HELLO WORLD' | ndnpoke/localhost/demo/hello
    </pre>
