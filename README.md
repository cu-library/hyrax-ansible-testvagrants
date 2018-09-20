# hyrax-ansible-testvagrants

This Vagrantfile brings up a CentOS, Debian, and Ubuntu VM to test the roles in https://github.com/cu-library/hyrax-ansible
Running this Vagrantfile will use 6144 MB of RAM. At least 8 GB of RAM on the host is recommend.

## CentOS:

Guest: 80 -> host: http://localhost:8080<br/>
Guest: 8080 -> host: http://localhost:8081<br/>
Guest: 8983 -> host: http://localhost:8082

http://localhost:8081/manager<br/>
http://localhost:8081/fcrepo

## Ubuntu:

Guest: 80 ->, host: http://localhost:8180<br/>
Guest: 8080 -> host: http://localhost:8181<br/>
Guest: 8983 -> host: http://localhost:8182

http://localhost:8181/manager<br/>
http://localhost:8181/fcrepo

## Debian:

Guest: 80 ->, host: http://localhost:8280<br/>
Guest: 8080 -> host: http://localhost:8281<br/>
Guest: 8983 -> host: http://localhost:8282

http://localhost:8281/manager<br/>
http://localhost:8281/fcrepo
