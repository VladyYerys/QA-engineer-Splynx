# QA-engineer-Splynx
Assignment task End date:15.12.2022  11am

Тестове завдання
QA engineer

# 1) Встановити Splynx на віртуальну машину (license key: 96920c0b2d7d3de6874eb52f836a1325) ОС - Ubuntu 20.04 (server)
![Screenshot_155](https://user-images.githubusercontent.com/106797604/207785731-7c41ee5a-a2f5-4417-842f-a6bb817e088a.png)
![Screenshot_154](https://user-images.githubusercontent.com/106797604/207785729-08441f17-0db8-42c8-b6c8-0289731a08b9.png)
```
sudo apt update && sudo apt-get upgrade -y && sudo apt -y install curl gnupg2 ca-certificates lsb-release && echo "deb http://nginx.org/packages/ubuntu `lsb_release -cs` nginx" | sudo tee /etc/apt/sources.list.d/nginx.list && echo "deb http://nginx.org/packages/mainline/ubuntu `lsb_release -cs` nginx" | sudo tee /etc/apt/sources.list.d/nginx.list && curl -o /tmp/nginx_signing.key https://nginx.org/keys/nginx_signing.key && sudo mv /tmp/nginx_signing.key /etc/apt/trusted.gpg.d/nginx_signing.asc && sudo apt update && sudo apt-get upgrade -y
```
```
sudo apt update && sudo apt install mysql-server -y && sudo systemctl start mysql.service && systemctl status mysql.service && sudo apt-get upgrade -y
```
```
sudo apt-get update && sudo add-apt-repository ppa:ondrej/php && sudo apt -y install php7.4 -y && php -v && sudo apt-get install -y php7.4-cli php7.4-json php7.4-common php7.4-mysql php7.4-zip php7.4-gd php7.4-mbstring php7.4-curl php7.4-xml php7.4-bcmath && sudo apt update && sudo apt-get upgrade -y
```

### В мене була такі трудністі
### 1. The “sub-process /usr/bin/dpkg returned an error code (1)” indicates that there is a problem with the package installer, which is generally caused by an interrupted installation process or a corrupted database

![Screenshot_156](https://user-images.githubusercontent.com/106797604/208024387-ceb69e2c-c0d4-40b7-b15a-2022d6a5b066.png)
![Screenshot_157](https://user-images.githubusercontent.com/106797604/208024388-c1f4fce4-6c17-4a48-9440-6c3dfaec9c54.png)

Думав, що це проблема то з сертифікатом, чи з AWS. Я пробував в Virtual Box, такак сама проблеема. Виясилося проблема в БД.

Як я її ршив
```
sudo mv /var/lib/dpkg/info /var/lib/dpkg/info_silent
sudo mkdir /var/lib/dpkg/info
sudo apt-get update
sudo apt-get -f install
```
![Screenshot_158](https://user-images.githubusercontent.com/106797604/208027318-3ed849a2-9686-46e6-9d30-33c32799597d.png)

![Screenshot_161](https://user-images.githubusercontent.com/106797604/208282838-66d5ec58-9fc2-42e3-8144-2a79a0f86eb6.png)
![Screenshot_162](https://user-images.githubusercontent.com/106797604/208282840-b8cfcd5c-f885-4c51-a284-d3571baf9b00.png)
![Screenshot_163](https://user-images.githubusercontent.com/106797604/208282841-896b62bd-a0f5-4c67-82c9-967eccbcbb85.png)

# 2) Додати кастомера, створити йому інвойс на суму рівну поточній даті в форматі “MMDD”
![Screenshot_164](https://user-images.githubusercontent.com/106797604/208317819-bb719e6c-e681-4ee9-9bd9-dddc67b2cd50.png)


# 3) Встановити аддон “Splynx IpPay” https://docs.splynx.com/payment_systems/ippay
![Screenshot_165](https://user-images.githubusercontent.com/106797604/208800011-b0e7b3b7-7e08-4be4-8841-320cc2812262.png)
![Screenshot_166](https://user-images.githubusercontent.com/106797604/208800017-5a53f841-26f7-46e3-84dc-ae1f71948380.png)

# 4) Сконфігурувати аддон для роботи в sandbox (проставити (‘isProduction’ => false) - це можназробити в файлі /var/www/splynx/addons/splynx-ippay/config/params.php, також, потрібно в конфізі аддона задати ‘Terminal ID’ = ‘TESTTERMINAL’ )
![Screenshot_167](https://user-images.githubusercontent.com/106797604/208800132-37ed7215-e04d-4cba-88ab-c2c9460cf4f5.png)
![Screenshot_169](https://user-images.githubusercontent.com/106797604/208800135-c575194f-d007-446f-90cc-1b1b6a56c819.png)

# 5) Зайти на портал кастомерів під створеним в пункті 2 кастомером і оплатити інвойс ззбереженням тестової карти встановленим аддоном.
![Screenshot_170](https://user-images.githubusercontent.com/106797604/208800210-82ced700-1d14-40ea-abff-9777bf1470c2.png)
![Screenshot_171](https://user-images.githubusercontent.com/106797604/208800212-553e7f08-7caa-4ac1-94d9-f212d2862601.png)

 ```
 Card holder name: test test
Test card number: 4111 1111 1111 1111
Exp. To: any date in future
```
# 6) До кожного пункту створити 1-2 скріншота і опис, по закінченню відправити архів все наostap.yeris@splynx.com
