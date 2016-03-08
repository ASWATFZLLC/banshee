#Freeswitch for Aswat Telecom

Based on Freeswitch 1.6 commit d2d0b3283ae393b15e2476159db50386300eea69

## Installation on FreeBSD


```
pkg install autoconf automake curl git gmake jpeg ldns libedit libtool openssl pcre pkgconf speex sqlite3 wget sudo luajit lua52 opus libshout mpg123 lame libsndfile libvpx flite hiredis libyuv portaudio
./bootstrap.sh -j 
cp modules.conf.sample modules.conf
./configure
sed -i -e 's#/usr/include/lame#/usr/local/include/lame#g' src/mod/formats/mod_shout/Makefile
gmake
gmake install cd-sounds-install cd-moh-install
```
