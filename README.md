# Инструкция по работе с Git

## Содержание
1. [Создание учётной записи GitHub](#1-создание-учётной-записи-github)
2. [Установка Git](#2-установка-git)
3. [Работа с локальным репозиторием](#3-работа-с-локальным-репозиторием)
4. [Работа с удалённым репозиторием и форки](#4-работа-с-удалённым-репозиторием-и-форки)

---

## 1. Создание учётной записи GitHub

1. Перейди на [github.com](https://github.com)
2. Нажми **Sign up**
3. Введи email, пароль, имя пользователя
4. Подтверди email

---

## 2. Установка Git

### Windows
Скачай установщик с [git-scm.com](https://git-scm.com) и запусти его.

После установки настрой имя и email:
\`\`\`bash
git config --global user.name "Имя Фамилия"
git config --global user.email "email@example.com"
\`\`\`

### Проверка установки
\`\`\`bash
git --version
\`\`\`

---

## 3. Работа с локальным репозиторием

### Инициализация репозитория
\```bash
git init
# Пример: создать репозиторий в папке project/
mkdir project && cd project && git init
\```

### Просмотр статуса
\```bash
git status
# Пример: показывает изменённые и неотслеживаемые файлы
\```

### Добавление файлов в индекс
\```bash
git add <файл>      # конкретный файл
git add .           # все изменения
# Пример:
git add README.md
\```

### Создание коммита
\```bash
git commit -m "сообщение"
# Пример:
git commit -m "feat: добавлен раздел о локальной работе"
\```

### Просмотр истории
\```bash
git log
git log --oneline   # краткий вид
# Пример вывода: a3f1c2b feat: начало проекта
\```

### Работа с ветками
\```bash
git branch              # список веток
git branch <имя>        # создать ветку
git checkout <имя>      # переключиться
git checkout -b <имя>   # создать и переключиться
# Пример:
git checkout -b feature/login
\```

### Слияние веток
\```bash
git merge <ветка>
# Пример: находясь в main, влить ветку local:
git checkout main
git merge local
\```

### Отмена изменений
\```bash
git restore <файл>          # отменить изменения в файле
git reset HEAD~1            # отменить последний коммит (файлы остаются)
# Пример:
git restore README.md
\```

---

## 4. Работа с удалённым репозиторием и форки

### Привязка удалённого репозитория
\```bash
git remote add origin <url>
# Пример:
git remote add origin https://github.com/user/repo.git
\```

### Просмотр удалённых репозиториев
\```bash
git remote -v
# Пример вывода:
# origin  https://github.com/user/repo.git (fetch)
# origin  https://github.com/user/repo.git (push)
\```

### Отправка изменений
\```bash
git push origin <ветка>
# Пример:
git push origin main
\```

### Получение изменений
\```bash
git fetch origin        # скачать, но не сливать
git pull origin main    # скачать и слить
\```

### Клонирование репозитория
\```bash
git clone <url>
# Пример:
git clone https://github.com/user/repo.git
\```

### Работа с форками

**Форк** — личная копия чужого репозитория на GitHub.

**Процесс:**
1. Нажми **Fork** на странице репозитория на GitHub
2. Клонируй свой форк:
\```bash
git clone https://github.com/твой-ник/repo.git
\```
3. Добавь оригинальный репозиторий как upstream:
\```bash
git remote add upstream https://github.com/оригинальный-автор/repo.git
\```
4. Синхронизация с оригиналом:
\```bash
git fetch upstream
git merge upstream/main
\```
5. После изменений — создай **Pull Request** через GitHub.