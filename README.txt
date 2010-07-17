Introduction
-------------

transmogrify.webcrawler is a Python package for `collective.transmogrifier <http://pypi.python.org/pypi/collective.transmogrifier>`_
content import/export framework. It is indended to read a whole web sites for importing.

transmogrify.webcrawler
-----------------------

A source blueprint for crawling content from a site or local HTML files. 
  
Pipeline paramaters
====================

Example::

        [webcrawler]
        blueprint = transmogrify.webcrawler
        site_url  = %s
        ignore =
                cgi-bin
                javascript:
                _static
                _sources
                genindex\.html
                search\.html
                saesrchindex\.js

site_url
++++++++

The remote site to be crawled. If this is not hardcoded and you use a command-line script instead,
use ``%s``.

verbose
+++++++

Possible values:: 0-3. The default is 0.

Verbosity level. This does not really do any good for you. It would be more sensible
to tune Python ``logging`` package verbosity level.

ignore
++++++

URL patterns which are ignored during the crawling.

strip_html_extension
+++++++++++++++++++++

Possible values: ``true`` or `false``.

Remove prefixing ``.html`` or ``.htm`` from outgoing URIs.
This is most useful if you are importing the content to another site
and you want to drop .html extension for stylistic reasons.

Other parameters
++++++++++++++++

Please see ``webcrawler.py``.

transmogrify.webcrawler.typerecognitor
---------------------------------------

A blueprint for assinging content type based on the mime-type as given by the
webcrawler

transmogrify.webcrawler.cache
------------------------------
A blueprint that saves crawled content into a directory structure

