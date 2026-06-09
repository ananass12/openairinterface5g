# Развертывание 5G SA сети: Open5GS + OAI gNB + USRP B200


## Структура файлов

- `playbook.yaml` — основной скрипт развертывания
- `inventory.ini` — файл инвентаризации
- `vars.yml` — переменные конфигурации
- `templates/oai_gnb.conf.j2` — шаблон конфига базовой станции

## Запуск установки


```bash
cd ~/openairinterface5g
ansible-playbook -i inventory.ini playbook.yaml --ask-become-pass
```

---

# Проверка корректности установки

## USRP B200

```bash
uhd_find_devices
```

## Ядро (Open5GS)

```bash
systemctl status open5gs-amfd open5gs-upfd open5gs-nrfd mongod --no-pager -l
```