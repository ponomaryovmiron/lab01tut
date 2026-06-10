# Лабораторная работа №1 Tutorial

## Настройка данных пользователя

```bash
git config --global user.name "ponomaryovmiron"
```

Команда задаёт имя пользователя Git для будущих коммитов.

```bash
git config --global user.email "godgezuru@gmail.com"
```

Команда задаёт почту пользователя Git для будущих коммитов.

```bash
export GITHUB_USERNAME=ponomaryovmiron
```

Команда сохраняет имя пользователя GitHub в переменную окружения.

```bash
export GITHUB_EMAIL=godgezuru@gmail.com
```

Команда сохраняет почту пользователя в переменную окружения.

```bash
alias edit=nano
```

Команда создаёт короткое имя `edit` для редактора `nano`.

## Создание рабочего каталога

```bash
mkdir -p ponomaryovmiron/workspace
```

Команда создаёт рабочую папку пользователя.

```bash
cd ponomaryovmiron/workspace
```

Команда переходит в рабочую папку.

```bash
pwd
```

Команда показывает текущий путь.

```bash
cd ..
```

Команда переходит на уровень выше.

```bash
pwd
```

Команда снова показывает текущий путь для проверки.

```bash
mkdir -p workspace/tasks
```

Команда создаёт папку для заданий.

```bash
mkdir -p workspace/projects
```

Команда создаёт папку для проектов.

```bash
mkdir -p workspace/reports
```

Команда создаёт папку для отчётов.

```bash
cd workspace
```

Команда переходит в основную рабочую папку.

## Установка Node.js

```bash
wget https://nodejs.org/dist/v6.11.5/node-v6.11.5-linux-x64.tar.xz
```

Команда скачивает архив Node.js нужной версии.

```bash
tar -xf node-v6.11.5-linux-x64.tar.xz
```

Команда распаковывает архив.

```bash
rm -rf node-v6.11.5-linux-x64.tar.xz
```

Команда удаляет скачанный архив после распаковки.

```bash
mv node-v6.11.5-linux-x64 node
```

Команда переименовывает папку Node.js в более короткое имя `node`.

```bash
ls node/bin
```

Команда показывает исполняемые файлы Node.js.

```bash
echo ${PATH}
```

Команда выводит текущее значение переменной `PATH`.

```bash
export PATH=${PATH}:`pwd`/node/bin
```

Команда добавляет папку `node/bin` в переменную `PATH`.

```bash
echo ${PATH}
```

Команда проверяет, что путь к Node.js был добавлен.

## Создание скрипта активации

```bash
mkdir scripts
```

Команда создаёт папку для скриптов.

```bash
cat > scripts/activate <<EOF
export PATH=\${PATH}:`pwd`/node/bin
EOF
```

Команда создаёт скрипт `activate`, который добавляет Node.js в `PATH`.

```bash
source scripts/activate
```

Команда применяет скрипт активации в текущей консоли.

```bash
node -v
```

Команда проверяет установленную версию Node.js.

```bash
npm -v
```

Команда проверяет установленную версию npm.

## Создание репозитория lab01tut

```bash
cd "/home/vboxuser/Рабочий стол/project/projects"
```

Команда переходит в каталог с проектами.

```bash
mkdir -p ponomaryovmiron_labs
```

Команда создаёт отдельную папку для лабораторных работ аккаунта `ponomaryovmiron`.

```bash
cd ponomaryovmiron_labs
```

Команда переходит в созданную папку.

```bash
mkdir lab01tut
```

Команда создаёт папку проекта `lab01tut`.

```bash
cd lab01tut
```

Команда переходит в папку проекта.

```bash
git init
```

Команда создаёт локальный Git-репозиторий.

```bash
git branch -M main
```

Команда переименовывает основную ветку в `main`.

```bash
git remote add origin https://github.com/ponomaryovmiron/lab01tut.git
```

Команда подключает удалённый репозиторий GitHub.

## Подготовка файлов к отправке

```bash
cd "/home/vboxuser/Рабочий стол/project/projects/ponomaryovmiron_labs/lab01tut"
```

Команда возвращает в корень проекта `lab01tut`.

```bash
cat > .gitignore <<EOF
workspace/node/
*.tar.xz
EOF
```

Команда создаёт `.gitignore`, чтобы не добавлять в репозиторий тяжёлые временные файлы.

```bash
rm -rf workspace/tasks/lab01/.git
```

Команда удаляет вложенный `.git` из скачанного задания, чтобы папка корректно добавилась в основной репозиторий.

```bash
find . -maxdepth 4 -type f | sort
```

Команда показывает список файлов проекта для проверки структуры.

## Отправка на GitHub

```bash
git status
```

Команда показывает изменённые и новые файлы.

```bash
git add .
```

Команда добавляет все файлы проекта в индекс Git.

```bash
git commit -m "complete lab01 tutorial"
```

Команда создаёт коммит с выполненной лабораторной работой.

```bash
git push -u origin main
```

Команда отправляет проект в репозиторий GitHub.
