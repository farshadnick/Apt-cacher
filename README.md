

APT-Cache-ng is a Life Saver for Situation which you do not want to Give Internet to Your Ubuntu Servers for Updating Packages

apt cahcher is a caching proxy for Debian based distributions that creates a local cache of Debian-based mirrors as well as other Linux distributions. This means that whenever a package is pulled from the official repositories, an APT cache server caches them such that if any other local machine would want to install the same package, it just pulls it from the local caching server. This helps eliminates the bottlenecks of slow internet connections.

Server Side 
========================
You just need to Run following Command:
docker-compose up -d

You can Get access to APT   cacher by entering your http://Machine IP:3172 (192.168.110.200:3172)

Client Side 
=========================
we can config our Client with Two Way 

**First Way**
Send All APT Repository Requests to the Proxy Section By Creating **/etc/apt/apt.conf.d/02proxy** File  and Put Following Section To IT :
```
Acquire::http { Proxy "http://192.168.110.200:3142"; };
# 192.168.110.200 is our apt-cacher-ng ip
```
**OR**

**Second Way**

Appending your APT Cacher URL:PORT to Your APT Repository Like:
```
deb http://192.168.110.200:3142/ftp.debian.org/debian stable main contrib non-free
deb-src http://192.168.110.200:3142/ftp.debian.org/debian stable main contrib non-free
deb http://192.168.110..200:3142/HTTPS///get.docker.com/ubuntu docker main

```

Main Article is from :
https://packops.dev 

author : Farshad Nick 

