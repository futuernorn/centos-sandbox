# Apache Setup
[Configuration](docs/apache_setup.md)
http://www.thegeekstuff.com/2012/05/install-apache-2-on-centos-6/
yum install gcc
yum install openssl-devel


[vagrant@localhost ~]$ sudo yum install gcc


[vagrant@localhost ~]$ sudo yum install openssl-devel

[vagrant@localhost ~]$ sudo yum install apr-util-devel



[vagrant@localhost src]$ sudo wget http://apache.spinellicreations.com//httpd/httpd-2.4.10.tar.gz


[vagrant@localhost src]$ sudo tar xvzf httpd-2.4.10.tar.gz

[vagrant@localhost httpd-2.4.10]$ sudo ./configure --enable-ssl --enable-so
configure: WARNING: skipped APR at apr-1-config, version not acceptable
no
configure: error: APR not found.  Please read the documentation.

[vagrant@localhost src]$ sudo wget http://www.gtlib.gatech.edu/pub/apache//apr/apr-1.5.1.tar.gz

[vagrant@localhost src]$ sudo wget http://www.gtlib.gatech.edu/pub/apache//apr/apr-util-1.5.4.tar.gz

[vagrant@localhost src]$ sudo tar xvzf apr-1.5.1.tar.gz

[vagrant@localhost src]$ sudo tar xvzf apr-util-1.5.4.tar.gz

[vagrant@localhost apr-1.5.1]$ sudo ./configure

[vagrant@localhost apr-1.5.1]$ sudo make

[vagrant@localhost apr-1.5.1]$ sudo make install

[vagrant@localhost httpd-2.4.10]$ sudo yum install rpm-build

[vagrant@localhost httpd-2.4.10]$ sudo yum install redhat-rpm-config
[vagrant@localhost src]$ sudo wget http://www.gtlib.gatech.edu/pub/apache//apr/apr-1.5.1.tar.bz2

[vagrant@localhost src]$ sudo wget http://www.gtlib.gatech.edu/pub/apache//apr/apr-util-1.5.4.tar.bz2
[vagrant@localhost src]$ sudo rpmbuild -ts apr-1.5.1.tar.bz2
Wrote: /root/rpmbuild/SRPMS/apr-1.5.1-1.src.rpm
[vagrant@localhost src]$ sudo rpmbuild -ts apr-util-1.5.4.tar.bz2
Wrote: /root/rpmbuild/SRPMS/apr-util-1.5.4-1.src.rpm
[vagrant@localhost src]$ rpm -Uhv /root/rpmbuild/SRPMS/apr-1.5.1-1.src.rpm



When it tells you Please read documentation it means that you should go read Apache documentation ( http://httpd.apache.org/docs/2.4/install.html ) which tells you to

download the latest versions of both APR and APR-Util from Apache APR, unpack them into ./srclib/apr and ./srclib/apr-util (be sure the domain names do not have version numbers; for example, the APR distribution must be under ./srclib/apr/)

then do
./configure --with-included-apr
http://stackoverflow.com/a/9436971
./configure --with-included-apr



# Bind Server
https://www.digitalocean.com/community/tutorials/how-to-install-the-bind-dns-server-on-centos-6
[Configuration](docs/bind_setup.md)