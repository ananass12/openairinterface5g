# Развертывание 5G сети на USRP B200 с Open5GS

## Быстрый старт

1. **Клонируйте репозиторий:**
```bash
   git clone (ссылка)
```

2. **Настройте инвентаризацию**

Отредактируйте inventory.ini, указав IP-адрес вашего сервера

3. **Настройте переменные**

Отредактируйте vars.yml:
- server_ip: IP-адрес сервера
- plmn_mcc / plmn_mnc: Коды вашей сети 

4. **Запустите Ansible Playbook**
```bash
   ansible-playbook -i inventory.ini playbook.yml
   ```

## После установки

1. Добавление абонентов

2. Проверка USRP

```bash
   uhd_find_devices
   ```

3. Запуск базовой станции
```bash
cd build
sudo ./nr-softmodem -O ~/oai_gnb.conf
```

4. Подключение UE (Телефона/Модема)