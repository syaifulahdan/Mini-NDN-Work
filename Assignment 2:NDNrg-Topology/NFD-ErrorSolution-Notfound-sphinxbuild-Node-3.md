### Sphinx-Build Not Found (Solution)

<pre>
bertopeng17-3@NDN-Node3-TELU:~$ <b>pip install sphinx</b>
</pre>

Show document install : Sphinx-Build :[[read]](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node3/NFD-ErrorSolution-Notfound-sphinxbuild-Node-3.txt)

<pre>
bertopeng17-3@NDN-Node3-TELU:~/NFD$ <b>pip show sphinx</b>
DEPRECATION: Python 2.7 reached the end of its life on January 1st, 2020. Please upgrade your Python as Python 2.7 is no longer maintained. pip 21.0 will drop support for Python 2.7 in January 2021. More details about Python 2 support in pip can be found at https://pip.pypa.io/en/latest/development/release-process/#python-2-support pip 21.0 will remove support for this functionality.
Name: Sphinx
Version: 1.8.5
Summary: Python documentation generator
Home-page: http://sphinx-doc.org/
Author: Georg Brandl
Author-email: georg@python.org
License: BSD
Location: /home/bertopeng17-3/.local/lib/python2.7/site-packages
Requires: alabaster, typing, snowballstemmer, Jinja2, packaging, requests, sphinxcontrib-websupport, imagesize, Pygments, docutils, setuptools, babel, six
Required-by: 
bertopeng17-3@NDN-Node3-TELU:~/NFD$ 
</pre>

if it doesn't work, do the following steps :

**For Python 3:**
<pre>
$ apt-get install python3-sphinx
</pre>

**For Python 2:**
<pre>
$ apt-get install python-sphinx
</pre>

<pre>
$ ./waf configure
</pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node3/NDNrg-Image-NFD-3/waf-configure-success.png)

.
