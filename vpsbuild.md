# Building a VPS from scratch

We use a Debian or Ubuntu Virtual Private Server supplied by Fasthosts. This can be easily rebuilt/reinitialized by pressing a few buttons on the Fasthosts control panel. Having done that we need to do a few things for ourselves:- It is assumed that you have basic competence with Debian and/or Ubuntu servers and will use 'sudo' as appropriate.

## Basic security
- Change the password for *root*
- useradd bob
- mkhomedir_helper bob
- usermod -aG sudo bob
- passwd bob

Now quit then re-login as bob

## Toolchain build
- wget https://go.dev/dl/go1.20.4.linux-amd64.tar.gz # Check for actual desired version
- tar -C /usr/local -xzf go1.20.4.linux-amd64.tar.gz
- export PATH=$PATH:/usr/local/go/bin
- include last statement in .profile for persistence
- apt install git
- on Debian not Ubuntu:  apt install build-essential
- git clone https://github.com/ibauk/ebcimg
- cd ebcimg
- go mod tidy
- go build
- cd ..
- git clone https://github.com/ibauk/ebcfetch
- cd ebcfetch; go mod tidy; go build; cd ~
- apt install sqlite3

## Caddy server - Debian not Ubuntu
- apt install -y debian-keyring debian-archive-keyring apt-transport-https
- curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/gpg.key' | gpg --dearmor -o /usr/share/keyrings/caddy-stable-archive-keyring.gpg
- curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/debian.deb.txt' | tee /etc/apt/sources.list.d/caddy-stable.list
- apt update
- apt install caddy
- systemctl enable --now caddy

## PHP
- apt install software-properties-common ca-certificates lsb-release apt-transport-https 
### Debian not Ubuntu
- sh -c 'echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" > /etc/apt/sources.list.d/php.list' 
- wget -qO - https://packages.sury.org/php/apt.gpg | apt-key add -
- apt update

### as you were
- apt install php8.3
- apt install -y php8.3-fpm php8.3-cli 
- nano /etc/php/8.3/fpm/pool.d/www.conf
- uncomment listen.
- usermod -aG www-data caddy
- systemctl start php8.3-fpm
- systemctl enable php8.3-fpm
- nano /etc/caddy/Caddyfile and include 'php_fastcgi unix//run/php/php8.3-fpm.sock'
- apt install php8.3-sqlite3
- Edit /etc/php/8.3/apache2/php.ini and uncomment the various sqlite entries
- reboot

## Harden security
You now have a fairly powerful server operating permanently on the internet and consequently attractive to every hacker and his uncle.

Firstly, make sure to use proper passwords and not Mickey Mouse ones. Secondly, take the usual precautions to secure the server, especially remote access. Disable root logons etc.

### Debian security updates
Edit the file */etc/apt/sources.list* to include the line *deb http://security.debian.org/debian-security bullseye-security main contrib non-free*. apt update && apt upgrade

Edit the file */etc/apt/apt.conf.d/50unattended-upgrades* to uncomment the lines

- "origin=Debian,codename=${distro_codename}-updates";
- "origin=Debian,codename=${distro_codename}-proposed-updates";
- "Unattended-Upgrade::Remove-Unused-Dependencies "false"; and change to "true".

Run *dpkg-reconfigure -plow unattended-upgrades* and agree to unattended upgrades.

## ebcfetch.service
To run ebcfetch as a service using systemd do:-

- cd ~
- git clone https://github.com/ibauk/ebcfetch
- apt install golang-go
- cd ~/ebcfetch
- go build
- load a copy of https://github.com/ibauk/ebcfetch/blob/main/ebcfetch.service
- edit appropriately
- install this file in /etc/systemd/system
- systemctl daemon-reload
- systemctl enable ebcfetch.service

## Additional users
The production server hosting *ironbutt.co.uk* uses public key encryption as the only authentication method for remote access. New users can be setup using this procedure on Ubuntu servers:-

- adduser *newuser*
- usermod -aG sudo *newuser*
- su - *newuser*
- mkdir ~/.ssh
- chmod 700 ~/.ssh
- touch ~/.ssh/authorized_keys
- chmod 600 ~/.ssh/authorized_keys
- ssh-keygen -t ed25519
- cat ~/.ssh/id_25519.pub >> ~.ssh/authorized_keys

Assuming access from a Windows device, use SFTP or similar to copy ~/.ssh/id_ed25519 to local drive for use with Filezilla and/or Putty. In either case, the Windows app will want to convert the file to its own format.

Yes I know that Putty includes a key pair generator but it all works so much better if you do things this way. The listed procedure can be adapted to suit the circumstances and/or skillset of the user.

