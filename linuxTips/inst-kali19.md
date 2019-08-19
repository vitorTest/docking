Add Docker PGP key:
```console
root@user:~# curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add -
```

Configure Docker APT repository (Kali is based on Debian testing, which will be called buster upon release, 
and Docker now has support for it):
```console
root@user:~# echo 'deb [arch=amd64] https://download.docker.com/linux/debian buster stable' > /etc/apt/sources.list.d/docker.list
root@user:~# apt-get update
```
### Install Docker

If you had older versions of Docker installed, uninstall them:
```console
root@user:~# apt-get remove docker docker-engine docker.io
```

**Install Docker:**
```console
root@user:~# apt-get install docker-ce
```
Test:
```console
root@user:~# docker run hello-world
```
After installation, Docker service will be started, but not enabled (i.e. it will not be started automatically after reboot). 
To start it:
```console
root@user:~# systemctl start docker
```
