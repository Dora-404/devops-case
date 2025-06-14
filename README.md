# DevOps Case 4: Flask + Docker + GitHub Actions

Простое веб-приложение на Flask с CI/CD через Docker и GitHub Actions.

## Требования
- Python 3.12
- Docker
- GitHub

## Установка
1. Клонируй: `git clone https://github.com/Dora-404/devops-case.git`
2. Сбери образ: `docker build -t devops-case-4 .`
3. Запусти: `docker run -p 5000:5000 devops-case-4`
4. Проверь: `http://localhost:5000` ("Hello, World!").

## GitHub Actions
- Файл: `.github/workflows/main.yml`.
- Триггеры: `push`/`pull_request` на `main`.
- Шаги: чек-аут, установка Python, установка зависимостей, тест приложения, сборка Docker.
- Пайплайн запускается автоматически при изменениях в `main` или создании PR.

## Файлы
- `app.py`: Flask-приложение.
- `requirements.txt`: зависимости.
- `Dockerfile`: сборка и запуск.
- `.github/workflows/main.yml`: CI/CD.

## Обяснение работы workflow
Workflow настроен в .github/workflows/main.yml и выполняется при push или pull_request в ветку main. Он обесечивает:
-Сборку проекта в изолированной среде.
-Локальную проверку работы приложения (запуск и проверка ответа через curl http://localhost:5000).
