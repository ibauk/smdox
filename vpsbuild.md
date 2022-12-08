# Building a VPS from scratch

We use a Debian Virtual Private Server supplied by Fasthosts. This can be easily rebuilt/reinitialized by pressing a few buttons on the Fasthosts control panel. Having done that we need to do a few things for ourselves:-

## Basic security
- Change the password for *root*
- useradd bob
- mkhomdir_helper bob
- usermod -aG sudo bob

## Toolchain build
- apt install wget
- wget https://go.dev/dl/go1.19.3.linux-amd64.tar.gz
- tar -C /usr/local -xzf go1.19.3.linux-amd64.tar.gz
- apt install imagemagick
- apt install git
- git clone https://github.com/ibauk/ebcfetch
- cd ebcfetch; go build
- apt install sqlite3

## Caddy server
- apt install -y debian-keyring debian-archive-keyring apt-transport-https
- curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/gpg.key' | sudo gpg --dearmor -o /usr/share/keyrings/caddy-stable-archive-keyring.gpg
- curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/debian.deb.txt' | sudo tee /etc/apt/sources.list.d/caddy-stable.list
- apt update
- apt install caddy
- systemctl enable --now caddy

## PHP
- apt install software-properties-common ca-certificates lsb-release apt-transport-https 
- sh -c 'echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" > /etc/apt/sources.list.d/php.list' 
- wget -qO - https://packages.sury.org/php/apt.gpg | sudo apt-key add -
- apt update
- apt install php8.1
- apt install -y php8.1-fpm php8.1-cli 
- nano /etc/php/8.1/fpm/pool.d/www.conf
- uncomment listen.
- usermod -aG www-data caddy
- systemctl start php8.1-fpm
- systemctl enable php8.1-fpm
- Edit Caddyfile and include 'php_fastcgi unix//run/php/php8.1-fpm.sock'
- apt install php8.1-sqlite
- Edit /etc/php/8.1/apache2/php.ini and uncomment the various sqlite entries
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






