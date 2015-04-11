1) Create new user & home directory via sudo (delete user pi)
2) Change keyboard layout to something usable (US) (sudo ./raspi-config)
3) Change ip to be static in /etc/network/interfaces
   * Change dhcp to static
   * Add the following lines
   ** address 192.168.1.3
   ** netmask 255.255.255.0
   ** gateway 192.168.1.1
   ** broadcase 192.168.1.255
3) Update to crontab to run pygodaddy Dynamics DNS code from https://github.com/ngcurrier/PyGoDaddy
   * Make sure to change username and password to the real ones .py file
4) Install nginx
   * sudo apt-get install nginx
   * sudo mkdir /var/www
   * sudo unlink /etc/nginx/sites-enabled/default
   * Add the following to /etc/nginx/sites-available/mysite
   ** server {
        listen 80;
        root /var/www;
        index index.html index.htm;
	      }
   * cd /etc/nginx/sites-enabled
   * sudo ln -s ../sites-available/mysite
   * sudo service nginx start
5) Install python required utilities http://blog.mattwoodward.com/2013/01/setting-up-django-on-raspberry-pi.html
   * sudo apt-get install python-dev python-setuptools supervisor python-pip
