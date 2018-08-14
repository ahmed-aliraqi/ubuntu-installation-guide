
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
cd ~/Downloads

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
#### Fixing npm permissions
1.  Make a directory for global installations:
    
    ```
     mkdir ~/.npm-global
    
    ```
    
2.  Configure npm to use the new directory path:
    
    ```
     npm config set prefix '~/.npm-global'
    
    ```
    
3.  Open or create a  `~/.profile`  file and add this line:
    
	```
	export PATH=~/.npm-global/bin:$PATH
	     
	NPM_CONFIG_PREFIX=~/.npm-global
	    
	```
    
4.  Back on the command line, update your system variables:
    
    ```
     source ~/.profile
    
    ```

#### Add composer global to path
```
gedit ~/.bashrc
```
add this line :
```
export PATH="$PATH:/opt/lampp/bin:$HOME/.config/composer/vendor/bin"
```

### Install git
```
sudo apt install git
```

### Show git branch in terminal:
add this code to `~/.bashrc` file :
```
# Show git branch name
force_color_prompt=yes
color_prompt=yes
parse_git_branch() {
 git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}
if [ "$color_prompt" = yes ]; then
 PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u:\[\033[01;34m\]\w\[\033[01;31m\]$(parse_git_branch)\[\033[00m\]\$ '
else
 PS1='${debian_chroot:+($debian_chroot)}\u:\w$(parse_git_branch)\$ '
fi
unset color_prompt force_color_prompt
```
