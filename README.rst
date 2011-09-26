build daemon aiming at rebuilding Debian packages
==================================================

This software allows you to manage a set of jobs. Each job is a package rebuilding task. Rebuilding is done by pbuilder (or cowbuilder if you want), or anything else, since everything is customizable via configuration file. It can also send build logs by email, event each log can be sent to a different email address.

rebuildd is multi-threaded, so you can run multiple build jobs in parallel. It is also administrable via a telnet interface. A Web interface is also embedded so you can see your jobs queue and watch log file in real-time in your browser.

rebuildd is designed to be run on multiple hosts even with different architecture set, and to parallelize the rebuild tasks. 

Instalasi
=========

Yang dibutuhkan adalah

* `rebuildd <http://qa.debian.org/rebuildd>`_
* `reprepro <http://qa.debian.org/reprepro>`_
* `pbuilder <http://qa.debian.org/pnuilder>`_

Untuk memasang kedua paket tersubut ketikkan::

 sudo apt-get install rebuildd reprepro

Direktori
=========
$BASE_DIR saya adalah /srv/buildd

* conf: Berisikan tentang pengaturan rebuildd

  - conf/distributions, conf/options, conf/incoming.
    Digunakan untuk mengatur `reprepro <http://qa.qa.debian.org/reprepro>`_
  - rebuilddrc
    Sama dengan /etc/rebuildd/rebuilddrc, yaitu pengaturan rebuildd
  - cron.daily
    Contoh penjadwalan *OPTIONAL*. Namun dapat diganti jika anda menyertakan **post_upload_command** di dput
  - dotprofile
    Letakkan di $HOME dan ganti dot dengan . Berkas ini digunakan untuk gpg-agent agar supaya system dapat menyimpan password anda di TTY.
  - dput.cf
    Contoh dput yang berada di sisi client.

* bin
  Berisikan berkas yang dieksekusi ketika post/pre build, lihat conf/rebuilddrc.

* incoming
  incoming upload, see conf/dput for example

* apt
  used for caching apt environment, we don't distrub apt'system so we create own

Lihat juga
========

* `Local Debian Autobuilder <http://codedot.livejournal.com/70998.html>`_
* `A bit of rebuildd history <http://julien.danjou.info/rebuildd.html>`_