# Linux Setup – FiveM


apt update & apt upgrade -y

apt-get install xz-utils

apt-get install git
(Frage mit "Y" beantworten)

apt-get install screen

mkdir -p /home/FiveM/server

cd /home/FiveM/server

wget https://runtime.fivem.net/artifacts/fivem/build_proot_linux/master/7314-c18c3214cb5d2fec62cd59e528073442bc063c63/fx.tar.xz

tar xf fx.tar.xz

ls

rm fx.tar.xz



# Datenbank Setup PHPMyAdmin

apt-get update & apt upgrade -y

apt install ca-certificates apt-transport-https lsb-release gnupg curl nano unzip -y

wget -q https://packages.sury.org/php/apt.gpg -O- | apt-key add -

echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" | tee /etc/apt/sources.list.d/php.list

apt update & apt install apache2 -y

apt install php7.4 php7.4-cli php7.4-curl php7.4-gd php7.4-intl php7.4-json php7.4-mbstring php7.4-mysql php7.4-opcache php7.4-readline php7.4-xml php7.4-xsl php7.4-zip php7.4-bz2 libapache2-mod-php7.4 -y

apt install mariadb-server mariadb-client -y

mysql_secure_installation
(Erste Frage mit "N" beantworten die restlichen dann mit "Y")

cd /usr/share

wget https://files.phpmyadmin.net/phpMyAdmin/5.1.1/phpMyAdmin-5.1.1-all-languages.zip -O phpmyadmin.zip

unzip phpmyadmin.zip

rm phpmyadmin.zip

mv phpMyAdmin-*-all-languages phpmyadmin

chmod -R 0755 phpmyadmin

nano /etc/apache2/conf-available/phpmyadmin.conf
( Alles aus diesen link rein Kopieren STRG+C und den STRG+V https://pastebin.com/VFAuWSyq )

systemctl reload apache2

a2enconf phpmyadmin

mkdir /usr/share/phpmyadmin/tmp/

chown -R www-data:www-data /usr/share/phpmyadmin/tmp/

mysql -u root

UPDATE mysql.user SET plugin = 'mysql_native_password' WHERE user = 'root' AND plugin = 'unix_socket';

FLUSH PRIVILEGES;

exit

http://deineip/phpmyadmin

# TxAdmin Setup

screen -t txadmin /home/FiveM/server/run.sh
( Folge nun der schritt für schritt anleitung von Txadmin )