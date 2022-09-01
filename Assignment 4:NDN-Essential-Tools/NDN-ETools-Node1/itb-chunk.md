# ndn-tools: Use of Chunk : https://gerrit.named-data.net/plugins/gitiles/ndn-tools/+/a5b60cc0172a1a67dec7e36f457c89169456cc45/tools/chunks

**ndncatchunks and ndnputchunks

ndncatchunks and ndnputchunks are a pair of programs to transfer a file as Data segments.
    ndnputchunks is a producer program that reads a file from the standard input, and makes it available as NDN Data segments. It appends version and segment number components to the specified name, according to the NDN naming conventions.
    ndncatchunks is a consumer program that fetches Data segments of a file, optionally discovering the latest version of the file, and writes the content of the retrieved file to the standard output.
     
     
     
     
    
 
