Public Suffix List module for Python
====================================

This module allows you to get the public suffix of a domain name using the
Public Suffix List from http://publicsuffix.org

A public suffix is one under which Internet users can directly register
names. Some examples of public suffixes are .com, .co.uk and pvt.k12.wy.us.
Accurately knowing the public suffix of a domain is useful when handling
web browser cookies, highlighting the most important part of a domain name
in a user interface or sorting URLs by web site.

The Python module ships with a (possibly out-dated) copy of the Public
Suffix List so that it is usable out of the box. It's up the user to keep
it up-to-date with the most recent version of the list available on
http://publicsuffix.org


Module content
--------------

The module exports a class that parses the Public Suffix List and allows
queries for individual domain names::

    >>> import publicsuffix
    >>> publicsuffix.get_public_suffix("www.example.com")
    'example.com'

Please note that the ``host`` part of an URL can contain strings that are
not plain DNS domain names (IP addresses, Punycode-encoded names, name in
combination with a port number or an username, etc.). It is up to the caller
to ensure only domain names are passed to the get_public_suffix() method.


Source (MIT/Expat License)
--------------------------

Pengkui Luo's folk:
http://github.com/pengkui/publicsuffix

from Tomaz Solc's pypi repo
http://pypi.python.org/pypi/publicsuffix


Other implementations
---------------------

By Joel Watts <joel@joelwatts.com>, Apache License v2.0

http://github.com/jpwatts/publicsuffix

Their lookup complexity is as high as O(N), where N is the total number of
rules. Note: ``matches = sorted(r for r in self if r.match(host))`` in tld().


A Ruby version by Simone Carletti <weppos@weppos.net>, MIT/Expat license

http://github.com/weppos/publicsuffix-ruby


And implementations in other languges mentioned on the official page:

http://publicsuffix.org/learn/

