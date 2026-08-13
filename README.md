# Zabbix Server + Agent + Fail2Ban

Автоматизация установки и настройки Zabbix Server, Zabbix Agent и Fail2Ban с использованием Ansible и Semaphore.

## Настройка PSK-шифрования

Для защищённого соединения между Zabbix-сервером и агентом используется Pre-Shared Key (PSK).  
После выполнения плейбука необходимо вручную указать PSK в веб-интерфейсе Zabbix.

### 1. Генерация ключа

Выполните команду OpenSSL:

    # openssl rand -hex 32
    # a1b2c3d4e5f6..z26

### 2. Настройка Zabbix

Data Collection → Hosts → Zabbix Servre → Encryption

1. Connection to host: PSK

2. Connection from host: PSK

Вкладка PSK

1. PSK identity: переменная из секрета

2. PSK: a1b2c3d4e5f6..z26
