# Звіт про результати збору інформації про мережу

---

## Зміст

1. [Вступ](#вступ)
2. [Інформація про мережу](#інформація-про-мережу)
   - [Ідентифікатори мереж (SSID)](#ідентифікатори-мереж-ssid)
   - [Виявлені пристрої](#виявлені-пристрої)
   - [Відкриті порти та сервіси](#відкриті-порти-та-сервіси)
3. [Вразливості та рекомендації](#вразливості-та-рекомендації)
4. [Висновки та рекомендації](#висновки-та-рекомендації)

---

## Вступ

Цей звіт містить результати збору інформації про мережу з метою проведення аудиту безпеки. Основна мета - ідентифікація пристроїв, визначення доступних портів, сервісів та оцінка потенційних вразливостей.

**Інструменти, використані для збору інформації:**
- `airodump-ng`: для виявлення точок доступу та підключених клієнтів.
- `nmap`: для сканування відкритих портів і визначення сервісів.
- `netdiscover`: для виявлення пристроїв у локальній мережі.
- Інші інструменти (за потреби).

---

## Інформація про мережу

### Ідентифікатори мереж (SSID)

| **SSID**           | **Шифрування** | **Ключ**            | **Канал** | **Примітки** |
|--------------------|----------------|----------------------|-----------|--------------|
| Example_Network_1  | WPA2           | Змінено для безпеки | 6         | Головна мережа |
| Example_Network_2  | WPA            | Змінено для безпеки | 11        | Гостьова мережа |

### Виявлені пристрої

| **IP-адреса**   | **MAC-адреса**         | **Тип пристрою** | **Опис**              |
|-----------------|------------------------|------------------|------------------------|
| 192.168.1.101   | AA:BB:CC:DD:EE:01      | Роутер          | Головний роутер мережі |
| 192.168.1.102   | AA:BB:CC:DD:EE:02      | Клієнт          | Ноутбук                |
| 192.168.1.103   | AA:BB:CC:DD:EE:03      | Клієнт          | Смартфон               |
| 192.168.1.104   | AA:BB:CC:DD:EE:04      | Пристрій IoT    | Інтелектуальний датчик |

### Відкриті порти та сервіси

| **IP-адреса** | **Порт** | **Сервіс**       | **Версія**       | **Примітки**                          |
|---------------|----------|------------------|------------------|---------------------------------------|
| 192.168.1.101 | 80       | HTTP            | Apache 2.4       | Веб-сервер                            |
| 192.168.1.101 | 443      | HTTPS           | Apache 2.4       | Захищене з'єднання                    |
| 192.168.1.102 | 22       | SSH             | OpenSSH 7.4      | Відкритий для адміністрування         |
| 192.168.1.104 | 1883     | MQTT            | Mosquitto 1.6.7  | Відкритий порт для IoT пристроїв      |

---

## Вразливості та рекомендації

| **IP-адреса**   | **Порт** | **Вразливість**          | **CVE**     | **Рекомендації**                                |
|-----------------|----------|--------------------------|-------------|-------------------------------------------------|
| 192.168.1.101   | 80       | Недостатній захист HTTP  | CVE-XXXX-XXX | Заборонити HTTP, перейти на HTTPS                |
| 192.168.1.102   | 22       | Старий SSH               | CVE-XXXX-XXX | Оновити OpenSSH до останньої версії              |
| 192.168.1.104   | 1883     | MQTT без шифрування      | CVE-XXXX-XXX | Налаштувати SSL для MQTT з'єднань                |

---

## Висновки та рекомендації

1. **Мережевий захист:** Відключити незахищені порти або налаштувати захищене з'єднання на важливих сервісах.
2. **Оновлення програмного забезпечення:** Перевірити версії сервісів та провести оновлення, де можливо, з урахуванням CVE.
3. **Шифрування:** Використати сучасні стандарти шифрування для безпечної передачі даних, особливо для IoT пристроїв.

> **Примітка:** Всі IP та MAC адреси в цьому звіті є випадково згенерованими для збереження конфіденційності реальної мережі.

---
