## Содержание
 
- [Создание учётной записи GitHub](#-создание-учётной-записи-github)
- [Установка Git](#-установка-git)
- [Локальный репозиторий](#-локальный-репозиторий)
- [Удалённый репозиторий и форки](#-удалённый-репозиторий-и-форки)
 
---
 
## Создание учётной записи GitHub
 
1. Перейди на [github.com](https://github.com) → нажми **Sign up**
2. Введи email, пароль, имя пользователя
3. Подтверди email
 
---
 
## Установка Git
 
**Windows** — скачай установщик с [git-scm.com](https://git-scm.com) и запусти его.
 
После установки настрой имя и email:
 
```bash
git config --global user.name "Имя Фамилия"
git config --global user.email "email@example.com"
```
 
Проверка:
 
```bash
git --version
```
 
---
 
## Локальный репозиторий
 
### Инициализация
 
```bash
mkdir project && cd project
git init
```
 
### Основной цикл работы
 
| Команда | Что делает |
|---|---|
| `git status` | Показывает изменённые и неотслеживаемые файлы |
| `git add <файл>` | Добавляет файл в индекс |
| `git add .` | Добавляет все изменения |
| `git commit -m "сообщение"` | Создаёт коммит |
| `git log --oneline` | Краткая история коммитов |
 
**Пример:**
 
```bash
git add README.md
git commit -m "feat: добавлен README"
```
 
### Ветки
 
```bash
git branch                  # список веток
git checkout -b feature/login  # создать и переключиться
git checkout main           # вернуться в main
git merge feature/login     # слить ветку в текущую
```
 
### Отмена изменений
 
```bash
git restore <файл>   # отменить несохранённые изменения
git reset HEAD~1     # отменить последний коммит (файлы остаются)
```
 
---
 
## Удалённый репозиторий и форки
 
### Привязка и базовые операции
 
```bash
git remote add origin https://github.com/user/repo.git
git remote -v                   # проверить привязку
 
git push origin main            # отправить изменения
git pull origin main            # получить изменения
git clone https://github.com/user/repo.git  # клонировать
```
 
### Работа с форком
 
> **Форк** — личная копия чужого репозитория на GitHub.
 
```
Оригинальный репо → [Fork] → Твой репо на GitHub → [Clone] → Локальная копия
```
 
**Шаги:**
 
1. Нажми **Fork** на странице репозитория
2. Клонируй свой форк:
   ```bash
   git clone https://github.com/твой-ник/repo.git
   ```
3. Добавь оригинал как `upstream`:
   ```bash
   git remote add upstream https://github.com/автор/repo.git
   ```
4. Синхронизируй с оригиналом:
   ```bash
   git fetch upstream
   git merge upstream/main
   ```
5. После изменений создай **Pull Request** через GitHub