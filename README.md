# QA-engineer-Splynx
Assignment task End date:15.12.2022  11am

Тестове завдання
QA engineer

### 1) Встановити Splynx на віртуальну машину (license key: 96920c0b2d7d3de6874eb52f836a1325) ОС - Ubuntu 20.04 (server)
![Screenshot_155](https://user-images.githubusercontent.com/106797604/207785731-7c41ee5a-a2f5-4417-842f-a6bb817e088a.png)
![Screenshot_154](https://user-images.githubusercontent.com/106797604/207785729-08441f17-0db8-42c8-b6c8-0289731a08b9.png)
```
sudo apt update && sudo apt-get update && sudo apt-get install apache2
```
```
sudo apt update && sudo apt install mysql-server && sudo systemctl start mysql.service && systemctl status mysql.service
```
```
sudo apt-get update && sudo apt -y install software-properties-common && sudo add-apt-repository ppa:ondrej/php && sudo add-apt-repository ppa:ondrej/php && sudo apt -y install php7.4 && php -v && sudo apt-get install -y php7.4-cli php7.4-json php7.4-common php7.4-mysql php7.4-zip php7.4-gd php7.4-mbstring php7.4-curl php7.4-xml php7.4-bcmath && sudo nano hello.php && <?php echo 'Hello World!';?> && php hello.php
```








### 2) Додати кастомера, створити йому інвойс на суму рівну поточній даті в форматі “MMDD”
### 3) Встановити аддон “Splynx IpPay” https://docs.splynx.com/payment_systems/ippay
### 4) Сконфігурувати аддон для роботи в sandbox (проставити (‘isProduction’ => false) - це можназробити в файлі /var/www/splynx/addons/splynx-ippay/config/params.php, також, потрібно в конфізі аддона задати ‘Terminal ID’ = ‘TESTTERMINAL’ )

### 5) Зайти на портал кастомерів під створеним в пункті 2 кастомером і оплатити інвойс ззбереженням тестової карти встановленим аддоном.
 ```
 Card holder name: test test
Test card number: 4111 1111 1111 1111
Exp. To: any date in future
```
### 6) До кожного пункту створити 1-2 скріншота і опис, по закінченню відправити архів все наostap.yeris@splynx.com
