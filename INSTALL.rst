.. _install:

Installing Simple Bandwidth Scanner
===================================

The recommended method  is to install it from your system
distribution.

In Debian/Ubuntu systems::

    sudo apt install sbws

To install also the documentation::

    sudo apt install sbws-doc

Continue reading to install ``sbws`` in other ways.

System requirements
--------------------

- Tor
- Python 3 (>= 3.5)
- virtualenv_ (while there is not ``stem`` release > 1.6.0, it is
  recommended to install the required python dependencies in a virtualenv)

In Debian::

    sudo apt install tor python3 virtualenv

Python dependencies
--------------------

- Stem_ >= 1.7.0
- Requests_ (with socks_ support) >= 2.10.0

To install the Python dependencies, create a ``virtualenv`` first

::

    virtualenv venv -p /usr/bin/python3
    source venv/bin/activate

Clone ``sbws``::

    git clone https://gitweb.torproject.org/sbws.git

Install the python dependencies::

    cd sbws && pip install .

``sbws`` needs :term:`destination` s to request files from.

Please, see ./DEPLOY.rst (or `/DEPLOY.rst </DEPLOY.rst>`_ or :ref:`deploy`)
to configure, deploy and run ``sbws``.

System physical requirements
-----------------------------

- Bandwidth: at least 20MB/s (160 Mbit/s). The more the better.
- Free RAM: at least 1.5GB
- Free disk: at least 3GB

``sbws`` and its dependencies need around 20MB of disk space.
After 90 days ``sbws`` data files use around 3GB.
If ``sbws`` is configured to log to files (by default will log to the
system log), it will need a maximum of 500MB.

It is recommended to set up an automatic disk space monitoring on ``sbws`` data
and log partitions.

Details about ``sbws`` data:

``sbws`` produces around 100MB of data a day.
By default raw results' files are compressed after 10 days and deleted after 90.
The bandwidth files are compressed after 7 days and deleted after 1.
After 90 days, the disk space used by the data will be aproximately 3GB.
It will not increase further.
If ``sbws`` is configured to log to files, logs will be rotated after they
are 10MB and it will keep 50 rotated log files.

.. _virtualenv: https://virtualenv.pypa.io/en/stable/installation/
.. _Stem: https://stem.torproject.org/
.. _socks: http://docs.python-requests.org/en/master/user/advanced/#socks
.. _Requests: http://docs.python-requests.org/
.. _Flake8: http://flake8.pycqa.org/
.. _pytest: https://docs.pytest.org/
.. _tox: https://tox.readthedocs.io
.. _Coverage: https://coverage.readthedocs.io/
