# Building a VPS from scratch

We use a Debian Virtual Private Server supplied by Fasthosts. This can be easily rebuilt/reinitialized by pressing a few buttons on the Fasthosts control panel. Having done that we need to do a few things for ourselves:-

## Basic security
- Change the password for *root*
- useradd bob
- mkhomdir_helper bob
- usermod -aG sudo bob
- apt install wget
- wget https://go.dev/dl/go1.19.3.linux-amd64.tar.gz
- tar -C /usr/local -xzf go1.19.3.linux-amd64.tar.gz
- apt install imagemagick


