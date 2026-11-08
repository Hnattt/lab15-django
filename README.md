# Навчальний проєкт моніторингу — ЛР15, варіант 3

**Номер профілю:** 3 (`profiles_15_18.json`, `variant: 3`) — однаковий для ЛР15–ЛР18.  
**Ситуація:** холодильна кімната. Пристрої: Холод камера (V03-A), Холод шлюз (V03-B), Склад (V03-C). Пошук «Холод», поріг 0 °C.

## Етап ЛР15

Створено Django-проєкт `config` і застосунок `monitoring`, зафіксовано залежності (`requirements.txt`, `requirements-lock.txt`), додано README та `.gitignore`. Для порівняння фреймворків є мінімальні приклади Flask і FastAPI у `framework_examples/`. Моделей і даних на цьому етапі ще немає.

**План даних за профілем:**
- ЛР16 — модель `Device` і три пристрої з профілю;
- ЛР17 — два паспорти, три мітки та десять вимірювань;
- ЛР18 — власник пристрою та форма введення вимірювань.

## Середовище

ОС: Windows 11. Перевірено: Python 3.13.17, Django 6.1.2, SQLite 3.50.4. Підтримується Python 3.12–3.14.

## Запуск (Windows, PowerShell)

Усі команди виконуються з кореня репозиторію (де лежить `manage.py`).

```
py -3.13 -m venv .venv
.venv\Scripts\python -m pip install -r requirements-lock.txt
.venv\Scripts\python manage.py migrate
.venv\Scripts\python manage.py check
.venv\Scripts\python manage.py runserver 127.0.0.1:8000
```

Linux / macOS: `python3.13 -m venv .venv`, далі ті самі команди через `.venv/bin/python`.

## Перевірка

```
.venv\Scripts\python manage.py check
.venv\Scripts\python manage.py runserver 127.0.0.1:8000
```
Відкрийте http://127.0.0.1:8000/ і порівняйте з http://127.0.0.1:8000/missing/ (очікується 404). Зупинка сервера — Ctrl+C.

## Безпека

`.venv`, `db.sqlite3`, `__pycache__`, `.env`, паролі та ключі в репозиторій не додаються (див. `.gitignore`). `DEBUG` і запасний ключ — лише для локального навчання; реальний ключ задається змінною середовища `DJANGO_SECRET_KEY`.

Репозиторій етапу: https://github.com/Hnattt/lab15-django
