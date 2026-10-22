# Установка WSL 2, Ubuntu, Python, GCC/G++ и PostgreSQL

## 1. Цель работы

Цель работы — установить подсистему Windows для Linux (WSL 2), настроить Ubuntu и установить инструменты для разработки программного обеспечения: Python, компиляторы GCC/G++ и систему управления базами данных PostgreSQL.

## 2. Установка WSL и Ubuntu

Для установки Linux в Windows был запущен PowerShell. Выполнена команда:

```powershell
wsl --install --web-download -d Ubuntu
```

Команда устанавливает WSL и дистрибутив Ubuntu. Параметр `--web-download` позволяет загрузить дистрибутив напрямую, без использования Microsoft Store.

<img width="1920" height="1080" alt="image_2026-10-22_22-22-12" src="https://github.com/user-attachments/assets/5e474754-f9a3-4228-add9-6abf91e15f36" />

## 3. Создание пользователя Ubuntu

При первом запуске Ubuntu необходимо создать имя пользователя и пароль. В данной работе используется пользователь `pinyugina-v-i`.

Для проверки имени пользователя применяется команда:

```bash
whoami
```

Команда выводит имя текущего пользователя Linux.

<img width="1920" height="1080" alt="image_2026-10-22_23-32-18" src="https://github.com/user-attachments/assets/7a48a4f6-598b-40ba-9453-cf154f327801" />

## 4. Обновление пакетов Ubuntu

Перед установкой программ были обновлены сведения о доступных пакетах:

```bash
sudo apt update
```

Затем установлены доступные обновления:

```bash
sudo apt upgrade -y
```

Команда `apt update` обновляет список пакетов, а `apt upgrade` устанавливает доступные обновления программ.

<img width="1920" height="1080" alt="image_2026-10-22_22-49-47" src="https://github.com/user-attachments/assets/2be20847-5a42-48de-882d-7fd63b31a5a3" />
<img width="1920" height="1080" alt="image_2026-10-22_22-56-07" src="https://github.com/user-attachments/assets/86cd6219-5148-49e9-badd-38ffa9080962" />

На скриншоте отображается результат обновления пакетов Ubuntu.

## 5. Установка Python и компиляторов

<img width="1920" height="1080" alt="image_2026-10-22_23-00-02" src="https://github.com/user-attachments/assets/5cb77c15-b930-4ec7-be1b-881455f9de01" />

Для установки Python, менеджера пакетов pip, поддержки виртуальных окружений и инструментов компиляции C/C++ выполнена команда:

```bash
sudo apt install -y python3 python3-pip python3-venv build-essential
```

Назначение установленных компонентов:

- `python3` — интерпретатор языка Python;
- `python3-pip` — инструмент установки библиотек Python;
- `python3-venv` — создание виртуальных окружений;
- `build-essential` — набор инструментов для компиляции программ, включающий GCC и G++.

Для проверки установки использованы команды:

```bash
python3 --version
pip3 --version
gcc --version
g++ --version
```

<img width="1920" height="1080" alt="image_2026-10-22_23-20-41" src="https://github.com/user-attachments/assets/1f0e674f-5ecd-4753-b0b4-f1dbea72f226" />

На скриншоте видны версии Python, pip, GCC и G++.

## 6. Установка PostgreSQL

Для установки системы управления базами данных PostgreSQL выполнена команда:

```bash
sudo apt install -y postgresql postgresql-contrib
```

PostgreSQL предназначен для хранения, обработки и управления структурированными данными.

После установки проверено состояние службы:

```bash
sudo service postgresql status
```

Затем выполнен SQL-запрос для получения информации о версии сервера:

```bash
sudo -u postgres psql -c "SELECT version();"
```

Команда запускает клиент PostgreSQL от имени пользователя `postgres` и выводит сведения о версии сервера.

<img width="1920" height="1080" alt="image_2026-10-22_23-24-20" src="https://github.com/user-attachments/assets/c110bcb6-0d83-4c0e-b241-7809b10f2d33" />

На скриншоте результат вывода команды `SELECT version();`.

## 7. Проверка конфигурации WSL

Для проверки состояния WSL в PowerShell выполнена команда:

```powershell
wsl --status
```

Для просмотра установленных дистрибутивов и используемой версии WSL выполнена команда:

```powershell
wsl -l -v
```

В результате должна отображаться установленная Ubuntu с версией WSL 2.

<img width="1920" height="1080" alt="image_2026-10-22_23-59-13" src="https://github.com/user-attachments/assets/bc6338cd-61e4-41af-942d-1c7a1496c2ee" />

На скриншоте видны установленные дистрибутивы и версия WSL.

## 9. Результат работы

В ходе работы была установлена среда Ubuntu под управлением WSL 2. Также были установлены Python, инструменты компиляции C/C++ и PostgreSQL.

Работоспособность установленных компонентов проверена с помощью команд терминала. Результаты проверок подтверждают, что среда подготовлена для дальнейшей разработки и выполнения учебных заданий.
