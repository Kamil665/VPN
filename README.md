# Python SSL Server

Простой TCP сервер с SSL/TLS шифрованием на Python.

## Возможности

- TCP соединения
- SSL/TLS шифрование
- Эхо-ответ клиенту
- Поддержка нескольких подключений

## Требования

- Python 3.8+
- OpenSSL

---

# Установка

## 1. Клонировать проект

```bash
git clone https://github.com/yourname/python-vpn-server.git
cd python-vpn-server
```

---

## 2. Создать SSL сертификаты

### Linux / macOS

```bash
openssl req -new -x509 -days 365 -nodes \
-out server.crt -keyout server.key
```

### Windows (Git Bash)

```bash
openssl req -new -x509 -days 365 -nodes ^
-out server.crt -keyout server.key
```

После генерации появятся:

- `server.crt`
- `server.key`

---

# Запуск сервера

## Linux / macOS

```bash
python3 vpn.py
```

## Windows

```bash
python vpn.py
```

---

# Подключение к серверу

## Локально

```bash
openssl s_client -connect 127.0.0.1:1994
```

---

# Пример работы

После подключения:

```text
hello
```

Сервер:

```text
Получено от клиента: b'hello'
```

---

# Настройки

В файле `vpn.py`:

```python
def vpn_server(host='0.0.0.0', port=1994):
```

## host

- `0.0.0.0` — принимать подключения со всех интерфейсов
- `127.0.0.1` — только локально

## port

Порт сервера.

---

# Важно

Этот проект НЕ является полноценным VPN.

Он:

- не создаёт VPN-туннель
- не маршрутизирует интернет-трафик
- не скрывает IP

Это учебный SSL TCP сервер.

Для настоящего VPN используйте:

- WireGuard
- OpenVPN

---

# Структура проекта

```text
project/
│
├── vpn.py
├── server.crt
├── server.key
└── README.md
```

---

# Лицензия

MIT
