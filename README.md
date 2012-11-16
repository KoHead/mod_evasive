mod_evasive_uri
===========

- This code is available only for Apache 2.0 and greater.

===========

This fork of mod_evasive add an optionnal configuration permitting to block the ip of flooder just for one URI and not for all the site.
The original mod_evasive developped by Jonathan Zdziarski's don't permit of limited his action on only one URI.

INSTALLATION :

APACHE v2.0
-----------

1. Extract this archive

2. Run $APACHE_ROOT/bin/apxs -i -a -c mod_evasive20.c

3. The module will be built and installed into $APACHE_ROOT/modules, and loaded into your httpd.conf

4. Restart Apache

CONFIGURATION

- Just add one paramater in more in you httpd.conf or vitual host file :

DOSGeturi "/index.html"

OR

DOSGeturi_unparsed "/index.html?url=100"

(DOSGeturi_unparsed is the full URI after the domain name)

Example configuration file :
<IfModule mod_evasive20.c>
  DOSHashTableSize 3097
  DOSPageCount 2
  DOSPageInterval 1
  DOSSiteCount 150
  DOSGeturi "/index.html"
  DOSSiteInterval 1
  DOSBlockingPeriod 10
  DOSLogDir "/var/lock/mod_evasive"
</IfModule>


The original mod_evasive is here : http://www.zdziarski.com/blog/

Damien MATHIEU 
System Engineer
www.adthink-media.com
www.mathieudamien.com
