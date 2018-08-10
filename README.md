
# Ubuntu Installation Guide

### update & upgrade

```
sudo apt update && sudo apt upgrade
```

### chromium browser
```
sudo apt-get install chromium-browser
```

### lampp server 
> [Download](https://www.apachefriends.org/download.html)  last version
```
cd ~/Download

sudo chmod +x xampp-linux-*

sudo ./xampp-linux-*
```
Then add lampp php to path 
```
gedit ~/.bashrc
```
add this line :
```
export PATH="$PATH:/opt/lampp/bin"
```
then install net-tools :
```
sudo apt install net-tools
```
then add luncher alias 
```
echo "alias lampp='sudo /opt/lampp/lampp'" >> ~/.bash_aliases
```
now you can use :
```
lampp start
lampp restart
lampp stop
```

### Install Composer
```
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('SHA384', 'composer-setup.php') === '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"

sudo mv composer.phar /usr/bin/composer
```

### Install Nodejs
```bash
curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
sudo apt-get install -y nodejs
```
