##### 1. Introduction.

NOTE: Mini-NDN, while providing a high level of emulation of hosts, requires programs to be installed onto your computer. It will not work if they are not installed. If you do not want NDN software installed onto your computer, you can use a virtual machine, which can be quite simply set up with the provided vagrantfile, and anything else that can improve the system! source : https://7th-ndn-hackathon.named-data.net/mini-ndn-documentation/manual/INSTALL.html

If you have all the dependencies (see sections below) installed simply clone this repository and run:
<pre>
./install.sh -i
</pre>

else if you don’t have the dependencies, the following command will install them from source along with Mini-NDN:

<pre>
./install.sh -a
</pre>

##### 2. Clone & Install Mini-NDN form Github.

<pre>
$ git clone https://github.com/named-data/mini-ndn
</pre>
![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDNrg-Image-minindn2/1-gitclone-minindn2.png)
Show Progress clone mini-ndn [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/minindn2-gitclone.txt)


<pre>
$ cd mini-ndn
$ ./install.sh -i
</pre>

![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDNrg-Image-minindn2/2-mini-ndn2-instal-sh-1.png)
![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDNrg-Image-minindn2/2-minindn2-install-sh-i-finish.png)
Show Progress mini-ndn install [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/minindn2-instal-sh-i.txt)
**noted**
<pre>

 ERROR: Command errored out with exit status 1:
     command: /usr/bin/python -c 'import sys, setuptools, tokenize; sys.argv[0] = '"'"'/tmp/pip-install-06WA_s/python-igraph/setup.py'"'"'; __file__='"'"'/tmp/pip-install-06WA_s/python-igraph/setup.py'"'"';f=getattr(tokenize, '"'"'open'"'"', open)(__file__);code=f.read().replace('"'"'\r\n'"'"', '"'"'\n'"'"');f.close();exec(compile(code, __file__, '"'"'exec'"'"'))' egg_info --egg-base /tmp/pip-pip-egg-info-pWDruW
         cwd: /tmp/pip-install-06WA_s/python-igraph/
    Complete output (6 lines):
    Traceback (most recent call last):
      File "<string>", line 1, in <module>
      File "/tmp/pip-install-06WA_s/python-igraph/setup.py", line 465
        raise RuntimeError(f"Failed to clean {folder} with git")
                                                              ^
    SyntaxError: invalid syntax
    ----------------------------------------
ERROR: Command errored out with exit status 1: python setup.py egg_info Check the logs for full command output.
</pre>

##### 3.Install Mini-NDN Wifi
<pre>
$ cd mini-ndn
./install.sh -iw
</pre>

![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDNrg-Image-minindn2/3-mini-ndn2-install-wifi.png)
![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDNrg-Image-minindn2/3-mini-ndn2-install-wifi-finish.png)
Show Progress detail mini-ndn wifi [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/minindn2-instal-sh-iw.txt)

##### 4. Running Example Topology

<pre>
$ sudo python examples/mnndn.pyi
</pre>
![alt tag](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/NDNrg-Image-minindn2/4-minindn2-running-example-topology.png)

Show Progress detail mini-ndn wifi [[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node2/minindn2-running-example-topology.txt)
