#Freeswitch for Aswat Telecom

Based on Freeswitch 1.6 commit d2d0b3283ae393b15e2476159db50386300eea69

## Installation on FreeBSD 10.3

```
pkg install -y autoconf automake curl git gmake jpeg ldns libedit libtool openssl pcre pkgconf speex sqlite3 wget sudo luajit lua52 opus libshout mpg123 lame libsndfile libvpx flite hiredis libyuv portaudio
git clone https://loic.aswat@freeswitch.org/stash/scm/~loic.aswat/freeswitch.git -b aswat --depth 1
cd freeswitch
./bootstrap.sh -j
wget https://raw.githubusercontent.com/ASWATFZLLC/banshee/master/modules.conf.sample
rm modules.conf
mv modules.conf.sample modules.conf
./configure
sed -i -e 's#/usr/include/lame#/usr/local/include/lame#g' src/mod/formats/mod_shout/Makefile
gmake
gmake install cd-sounds-install cd-moh-install
cd ~
wget https://raw.githubusercontent.com/ASWATFZLLC/banshee/master/freeswitch.rc.d
mv freeswitch.rc.d /usr/local/etc/rc.d/freeswitch
chmod +x /usr/local/etc/rc.d/freeswitch
```
