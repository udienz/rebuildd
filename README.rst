build daemon aiming at rebuilding Debian packages
==================================================

This software allows you to manage a set of jobs. Each job is a package rebuilding task. Rebuilding is done by pbuilder (or cowbuilder if you want), or anything else, since everything is customizable via configuration file. It can also send build logs by email, event each log can be sent to a different email address.

rebuildd is multi-threaded, so you can run multiple build jobs in parallel. It is also administrable via a telnet interface. A Web interface is also embedded so you can see your jobs queue and watch log file in real-time in your browser.

rebuildd is designed to be run on multiple hosts even with different architecture set, and to parallelize the rebuild tasks. 

Directory
=========
My $BASE_DIR is /srv/buildd

* conf
of course, contain configurations.
 * conf/distributions, conf/options, conf/incoming.
   Used for `reprepro<http://qa.qa.debian.org/reprepro>`_ config
 * rebuilddrc
   Same as /etc/rebuildd/rebuilddrc
 * cron.daily
   An example cron *OPTIONAL*
 * dotprofile
   put into your home dir and replace dot with . it was used for gpg-agent, this files can save your gpg/ssh password into tty.
 * dput.cf
   example dput

* bin
  contain binary file for post/pre build, see conf/rebuilddrc.

* incoming
  incoming upload, see conf/dput for example

* apt
  used for caching apt environment, we don't distrub apt'system so we create own
