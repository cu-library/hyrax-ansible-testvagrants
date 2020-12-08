# hyrax-ansible-testvagrants

This Vagrantfile brings up a CentOS, Debian, and Ubuntu VM to test the roles in https://github.com/cu-library/hyrax-ansible
Running this Vagrantfile will use 12288 MB of RAM. At least 16 GB of RAM on the host is recommend.

## CentOS 7:

Guest: 80 -> host: http://localhost:8080<br/>
Guest: 8080 -> host: http://localhost:8081<br/>
Guest: 8983 -> host: http://localhost:8082

http://localhost:8081/manager<br/>
http://localhost:8081/fcrepo


## CentOS 8:

Guest: 80 -> host: http://localhost:8083<br/>
Guest: 8080 -> host: http://localhost:8084<br/>
Guest: 8983 -> host: http://localhost:8085

http://localhost:8084/manager<br/>
http://localhost:8084/fcrepo

## Ubuntu 18.04:

Guest: 80 ->, host: http://localhost:8180<br/>
Guest: 8080 -> host: http://localhost:8181<br/>
Guest: 8983 -> host: http://localhost:8182

http://localhost:8181/manager<br/>
http://localhost:8181/fcrepo

## Ubuntu 20.04:

Guest: 80 ->, host: http://localhost:8183<br/>
Guest: 8080 -> host: http://localhost:8184<br/>
Guest: 8983 -> host: http://localhost:8185

http://localhost:8184/manager<br/>
http://localhost:8184/fcrepo

## Debian 9:

Guest: 80 ->, host: http://localhost:8280<br/>
Guest: 8080 -> host: http://localhost:8281<br/>
Guest: 8983 -> host: http://localhost:8282

http://localhost:8281/manager<br/>
http://localhost:8281/fcrepo

## Debian 10:

Guest: 80 ->, host: http://localhost:8283<br/>
Guest: 8080 -> host: http://localhost:8284<br/>
Guest: 8983 -> host: http://localhost:8285

http://localhost:8284/manager<br/>
http://localhost:8284/fcrepo
