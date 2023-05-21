# Linux
## Install / Setting
<pre>sudo apt update</pre>
<pre>sudo apt install nginx mysql-server sendmail php-fpm php-mysql php-mbstring php-zip php-gd php-dom php-curl git ffmpeg -y</pre>

<pre>curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash</pre>

<pre>source ~/.bashrc</pre>

<pre>nvm install v14.19.1</pre>

<pre>php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"</pre>
<pre>php composer-setup.php</pre>
<pre>sudo mv composer.phar /usr/local/bin/composer</pre>
<pre>sudo ln -s /usr/local/bin/composer /usr/bin/composer</pre>
<pre>sudo chown ubuntu /var/www</pre>
<pre>sudo chown ubuntu /var/www</pre>
<pre>sudo mysql_secure_installation</pre>

<pre>sudo mysql</pre>
<pre>
CREATE DATABASE bitfan;
CREATE USER 'bitfan'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON bitfan.* TO 'bitfan'@'localhost';
FLUSH PRIVILEGES;
</pre>
<pre>cd /var/www</pre>
upload backend files to /var/www/backend<

<pre>cd /var/www/backend</pre>
<pre>chmod -R 0777 storage</pre>
<pre>composer install</pre>
<pre>php artisan storage:link</pre>
<pre>cp .env.example .env</pre>

<pre>cd /var/www</pre>
upload frontend files to /var/www/frontend

<pre>cd /var/www/frontend</pre>
<pre>npm i</pre>
<pre>cp .env.example .env.production</pre>

<pre>sudo vi /etc/nginx/sites-available/default</pre>

<pre>
change:
        root /var/www/frontend/dist

add:
        location ~ \.php$ {
                include snippets/fastcgi-php.conf;
                fastcgi_pass unix:/var/run/php/php7.2-fpm.sock;
        }

        location ~ /\.ht {
                deny all;
        }
	
        location /v1/ {
                proxy_pass http://localhost:8000;
	}
</pre>

<pre>sudo apt install sendmail -y</pre>

<pre>cd /var/www/backend</pre>
<pre>vi .env</pre>
<pre>provide necessary configuration</pre>

<pre>php artisan key:generate</pre>
<pre>php artisan migrate:fresh --seed</pre>

<pre>cd /var/www/frontend</pre>
<pre>vi .env.production</pre>
provide necessary configuration

<pre>npm run build</pre>

## Run
### Backend
<pre>php artisan serve</pre>
### Frontend(ngnix restart)
<pre>sudo service reload nginx</pre>

