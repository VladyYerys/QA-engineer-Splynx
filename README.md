# QA-engineer-Splynx
Assignment task End date:15.12.2022  11am

Тестове завдання
QA engineer
<img src="https://user-images.githubusercontent.com/106797604/208827011-7fc52bcc-12f7-49ed-bf95-efdbba2194ae.png" align="right">
# 1) Встановити Splynx на віртуальну машину (license key: 96920c0b2d7d3de6874eb52f836a1325) ОС - Ubuntu 20.04 (server)
![Screenshot_179](https://user-images.githubusercontent.com/106797604/208830737-c7f71db8-7ce4-48a3-96d4-24ac56b9274c.png)
![Screenshot_180](https://user-images.githubusercontent.com/106797604/208830934-c67a91e2-8de2-463e-b70f-e0ffdcaf69fd.png)

# 2) Додати кастомера, створити йому інвойс на суму рівну поточній даті в форматі “MMDD”
![Screenshot_181](https://user-images.githubusercontent.com/106797604/208832133-f69cdf50-cb80-4e14-9f63-83722023a317.png)



# 3) Встановити аддон “Splynx IpPay” https://docs.splynx.com/payment_systems/ippay
![Screenshot_182](https://user-images.githubusercontent.com/106797604/208832439-e17a8416-a283-48cb-96c8-a18497ef90f4.png)


# 4) Сконфігурувати аддон для роботи в sandbox (проставити (‘isProduction’ => false) - це можназробити в файлі /var/www/splynx/addons/splynx-ippay/config/params.php, також, потрібно в конфізі аддона задати ‘Terminal ID’ = ‘TESTTERMINAL’ )
![Screenshot_183](https://user-images.githubusercontent.com/106797604/208832643-7b4159f5-2b32-424b-8a47-698ba5f78ce2.png)


# 5) Зайти на портал кастомерів під створеним в пункті 2 кастомером і оплатити інвойс ззбереженням тестової карти встановленим аддоном.
![Screenshot_170](https://user-images.githubusercontent.com/106797604/208800210-82ced700-1d14-40ea-abff-9777bf1470c2.png)
![Screenshot_171](https://user-images.githubusercontent.com/106797604/208800212-553e7f08-7caa-4ac1-94d9-f212d2862601.png)
![Screenshot_172](https://user-images.githubusercontent.com/106797604/208804012-73a7c6ba-e555-4a45-a4d7-fb6eaab1248b.png)

 ```
 Card holder name: test test
Test card number: 4111 1111 1111 1111
Exp. To: any date in future
```
# 6) До кожного пункту створити 1-2 скріншота і опис, по закінченню відправити архів все наostap.yeris@splynx.com
```
#!/bin/bash
echo "=====================Install Nginx Server=========================="
sudo apt update && sudo apt-get upgrade -y 
sudo apt install nginx
sudo ufw app list
sudo ufw allow 'Nginx HTTP'
sudo ufw enable
sudo ufw status
sleep 2
systemctl status nginx 
sudo apt update && sudo apt-get upgrade -y
sleep 2

#Install PHP 
echo "=====================Install PHP7.4================================"
sudo apt -y install php7.4 php7.4-cli php7.4-fpm php7.4-json php7.4-pdo php7.4-mysql php7.4-zip php7.4-gd php7.4-mbstring php7.4-curl php7.4-xml php-pear php7.4-bcmath
echo "=====================PHP7.4 ENABLE================================="
echo "`php --version`"
sleep 5
sudo apt update && sudo apt-get upgrade -y
sleep 5

# Install MySql server
echo "=====================Install MySQL serve==========================="
sudo apt update && sudo apt install mysql-server -y 
echo "`mysql -V`"
sleep 2
sudo systemctl start mysql.service && systemctl status mysql.service
sleep 2
sudo apt-get upgrade -y
sleep 2

# Install Splynx
echo "=====================Install Splynx================================"
dpkg-reconfigure tzdata
wget -qO- https://deb.splynx.com/setup_4_0 | bash -
apt-get install splynx -y
apt-get install ca-certificates -y
update-ca-certificates

```
