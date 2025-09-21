# custom-fusionpbx
AI supported voip provider for LLM, FreeSwitch, FusionPBX, Ubuntu24.04 Apache2


Please download from https://sourceforge.net/projects/custom-fusionbbx/



initial  setup;

required  Ubuntu24.04, Apache2, PHP8.4, PostgreSQL

#to install php8.4 on Ubuntu 24.04  run command on your server

add-apt-repository ppa:ondrej/php
apt update -y

sudo apt install -y libapache2-mod-php8.4 php8.4 php8.4-cgi php8.4-cli php8.4-common php8.4-curl php8.4-dev php8.4-enchant php8.4-fpm php8.4-gd php8.4-imap php8.4-intl php8.4-mbstring php8.4-mysql php8.4-opcache php8.4-pgsql php8.4-pspell php8.4-readline php8.4-soap php8.4-sqlite3 php8.4-tidy php8.4-xml php8.4-zip postgresql postgresql-16 postgresql-client-16 postgresql-client-common postgresql-common postgresql-server-dev-16 apache2 apache2-bin apache2-data apache2-utils libapache2-mod-perl2 libapache2-mod-perl2-dev libapache2-mod-php8.4 libapache2-reload-perl


mkdir -p /web/gui ; chown -fR www-data:www-data /web/gui ; chmod -fR 700 /web/gui ; echo "Alias /gui /web/gui" >> /etc/apache2/sites-enabled/002-alias.conf ; /etc/init.d/apache2 restart ; cd /web/gui ; wget https://sf.net//web/gui/fpx-2025-06-29-0101-multi.tar.gz ; tar zxvf /web/gui/fpx-2025-06-29-0101-multi.tar.gz ; chown -fR www-data:www-data /web/gui ; chmod -fR 700 /web/gui


create fusionpbx postgresql user with pasword you like example Test1234567890
create fusionpbx postgresql database owned by fusionpbx user
import sql file /web/gui/fpx/custom-fusionpbx.sql  in to new fusionpbx database

rename  /web/gui/fpx/config.conf

visit  url  via your browser https:// {your ip address or your host} /gui/fpx

setup your own password your own host



WHY I MADE CUSTOMISED FUSIONPBX?

My name is Oğuz Ersöz, I am an electromechanical engineer, I have been an open source fanatic for many years, and I am an open source software developer.

I compiled Asterisk and FreeSwitch software for direct voice communication with artificial intelligence. Due to its host-based multi-tenant features and its suitability for enterprise data traffic, I also had to customize the Custom FusionPBX interface for FreeSwitch.

First, I deleted the project_path definitions from the config.conf file and adapted a new structure that automatically finds them with php to 4000 scripts. This version is now portable.

Then, I developed PHP8.4 php scripts for a large number of php scripts.

Then, I made some changes in the numerous codes to use Apache web server instead of Nginx.


