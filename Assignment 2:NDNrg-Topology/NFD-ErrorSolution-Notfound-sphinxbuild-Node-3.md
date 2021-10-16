### Valgrint Not Found (Solution)

<pre>
bertopeng17-3@NDN-Node3-TELU:~$ <b>pip install sphinx</b>
DEPRECATION: Python 2.7 reached the end of its life on January 1st, 2020. Please upgrade your Python as Python 2.7 is no longer maintained. pip 21.0 will drop support for Python 2.7 in January 2021. More details about Python 2 support in pip can be found at https://pip.pypa.io/en/latest/development/release-process/#python-2-support pip 21.0 will remove support for this functionality.
Defaulting to user installation because normal site-packages is not writeable
Collecting sphinx
  Downloading Sphinx-1.8.5-py2.py3-none-any.whl (3.1 MB)
     |████████████████████████████████| 3.1 MB 196 kB/s 
Collecting alabaster<0.8,>=0.7
  Downloading alabaster-0.7.12-py2.py3-none-any.whl (14 kB)
Collecting typing; python_version < "3.5"
  Downloading typing-3.10.0.0-py2-none-any.whl (26 kB)
Collecting snowballstemmer>=1.1
  Downloading snowballstemmer-2.1.0-py2.py3-none-any.whl (93 kB)
     |████████████████████████████████| 93 kB 553 kB/s 
Collecting Jinja2>=2.3
  Downloading Jinja2-2.11.3-py2.py3-none-any.whl (125 kB)
     |████████████████████████████████| 125 kB 508 kB/s 
Requirement already satisfied: packaging in /usr/local/lib/python2.7/dist-packages (from sphinx) (20.9)
Collecting requests>=2.0.0
  Downloading requests-2.26.0-py2.py3-none-any.whl (62 kB)
     |████████████████████████████████| 62 kB 342 kB/s 
Collecting sphinxcontrib-websupport
  Downloading sphinxcontrib_websupport-1.1.2-py2.py3-none-any.whl (39 kB)
Collecting imagesize
  Downloading imagesize-1.2.0-py2.py3-none-any.whl (4.8 kB)
Collecting Pygments>=2.0
  Downloading Pygments-2.5.2-py2.py3-none-any.whl (896 kB)
     |████████████████████████████████| 896 kB 196 kB/s 
Collecting docutils>=0.11
  Downloading docutils-0.17.1-py2.py3-none-any.whl (575 kB)
     |████████████████████████████████| 575 kB 322 kB/s 
Requirement already satisfied: setuptools in /usr/lib/python2.7/dist-packages (from sphinx) (39.0.1)
Collecting babel!=2.0,>=1.3
  Downloading Babel-2.9.1-py2.py3-none-any.whl (8.8 MB)
     |████████████████████████████████| 8.8 MB 159 kB/s 
Requirement already satisfied: six>=1.5 in /usr/local/lib/python2.7/dist-packages (from sphinx) (1.16.0)
Collecting MarkupSafe>=0.23
  Downloading MarkupSafe-1.1.1-cp27-cp27mu-manylinux1_x86_64.whl (24 kB)
Requirement already satisfied: pyparsing>=2.0.2 in /usr/local/lib/python2.7/dist-packages (from packaging->sphinx) (2.4.7)
Collecting certifi>=2017.4.17
  Downloading certifi-2021.10.8-py2.py3-none-any.whl (149 kB)
     |████████████████████████████████| 149 kB 190 kB/s 
Collecting urllib3<1.27,>=1.21.1
  Downloading urllib3-1.26.7-py2.py3-none-any.whl (138 kB)
     |████████████████████████████████| 138 kB 308 kB/s 
Collecting chardet<5,>=3.0.2; python_version < "3"
  Downloading chardet-4.0.0-py2.py3-none-any.whl (178 kB)
     |████████████████████████████████| 178 kB 232 kB/s 
Requirement already satisfied: idna<3,>=2.5; python_version < "3" in /usr/lib/python2.7/dist-packages (from requests>=2.0.0->sphinx) (2.6)
Requirement already satisfied: pytz>=2015.7 in /usr/local/lib/python2.7/dist-packages (from babel!=2.0,>=1.3->sphinx) (2021.1)
Installing collected packages: alabaster, typing, snowballstemmer, MarkupSafe, Jinja2, certifi, urllib3, chardet, requests, sphinxcontrib-websupport, imagesize, Pygments, docutils, babel, sphinx
  WARNING: The script chardetect is installed in '/home/bertopeng17-3/.local/bin' which is not on PATH.
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
  WARNING: The script pygmentize is installed in '/home/bertopeng17-3/.local/bin' which is not on PATH.
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
  WARNING: The script pybabel is installed in '/home/bertopeng17-3/.local/bin' which is not on PATH.
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
  WARNING: The scripts sphinx-apidoc, sphinx-autogen, sphinx-build and sphinx-quickstart are installed in '/home/bertopeng17-3/.local/bin' which is not on PATH.
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
Successfully installed Jinja2-2.11.3 MarkupSafe-1.1.1 Pygments-2.5.2 alabaster-0.7.12 babel-2.9.1 certifi-2021.10.8 chardet-4.0.0 docutils-0.17.1 imagesize-1.2.0 requests-2.26.0 snowballstemmer-2.1.0 sphinx-1.8.5 sphinxcontrib-websupport-1.1.2 typing-3.10.0.0 urllib3-1.26.7
bertopeng17-3@NDN-Node3-TELU:~$ 

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
<pre>

$ ./waf configure
</pre>
![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node3/NDNrg-Image-NFD-3/waf-configure-success.png)
