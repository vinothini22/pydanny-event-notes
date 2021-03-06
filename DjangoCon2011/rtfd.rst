==================
Read the Docs
==================

by Eric Holscher

.. note:: arrived late. :(

Intro
=====

 * launched in Django Dash 2010
 * Makes documentation hosting trivial
 * uses sphinx
 
Things you can do
====================

 * Post commit hooks on Github
 * Add custom sphinx theme
 * PDF generation via download think
 * Use their REST API for links to http://djangopackages.com
 
CNAME support 
==============

* Request for docs.fabfile.org
* docs.fabfile.org > (need to finish this out)

Architecture
============

 * Python
 * Front end caching via varnish
 
    * Varnish is the current single point of failure.
 
 * Django front ended via gunicorn and nginx

    * Docs are hosted out via nginx
 
 * Postgres SQL
 * Haystack and SOLR 
 * Chef for deployment
 * Nagios & Munin
 * CoffeeScript (*Where is the Python version? This is only in Ruby*)
 * CLI support via http://rtd.rtfd.org (**need to check this out!**)
 
Open source!
============

Pros:

    * Patches
    * People trust you most because they can see the code
    * BSD license

Cons:   

    * Known architecture information was on github
    * Early version had exposed data like IP addresses and other things
    
Hoping it makes people write more docs
========================================

 * mod_wsgi
 * django-piston
 
Lessons Learned
================

 * Think about your URLs. Really hard
 
    * Adding versions was hard

 * Lay your project out sanely
 
    * started with no tests
    * Shoved code in
    * Racked up a lot of technical debt
    * worked hard to make the project layout a bit more sane

 * Write tests!
 
    * Had a complicated code base without tests
    * They have hosted continuous integration

 * Build around a standard tool
 
    * Lots of good communication between rtfd and Sphinx
    
 * Passing data through systems is hard
 * Serving static files is annoying
 * Log. Everything.
 
    * Hard to find people's problems until they added sophisticated logging
    * I personally like the build reports

 * Promote your projects! 
 
    * Blog
    * Tweet
    * http://djangopackages.com
    * G+
    
 * Find a designer
 * Follow the Unix Philosophy
 
    * Do one thing and do it well
    * Stay to your project goal and don't deviate
    * RTFD does so well cause all it does is Sphinx documentation hosting
    
* Have a mission

    * RTFD fixes the problem in open source that projects are not well documented
    * WIKIs are where your project goes to die
    * Sphinx lets you accept Pull Requests
    
Sponsors
========

 * Revsys
 * PSF
 * Divio
 * pyladies
 
Questions
==========

.. note:: ask Russ his question

 * How easy to deploy internally?
 
    * Open Source
    * Documented
    * Chef
 
 * Designer thoughts? 
 
    * Started with the project with a designer
    
Mirror your project in your test layouts
============================================

.. note:: I love this pattern and use it myself!

 * Create test modules following the same file layout as your project
 * Have as few root test utils as possible 
 
    * Use it sparingly
    * just a few simple helper functions!
 * 