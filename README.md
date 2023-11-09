# Шпаргалка по ГИТу 

---

## Навигация

pwd (от англ. print working directory, «показать рабочую папку») — покажи, в какой я папке;

ls (от англ. list directory contents, «отобразить содержимое директории») — покажи файлы и папки в текущей папке;

ls -a — покажи также скрытые файлы и папки, названия которых начинаются с символа .;

cd first-project (от англ. change directory, «сменить директорию») — перейди в папку first-project;

cd first-project/html — перейди в папку html, которая находится в папке first-project;

cd .. — перейди на уровень выше, в родительскую папку;

cd ~ — перейди в домашнюю директорию (/Users/Username);

cd / — перейди в корневую директорию.


---

## Работа с файлами и папками
### Создание
touch index.html (англ. touch, «коснуться») — создай файл index.html в текущей папке;

touch index.html style.css script.js — если нужно создать сразу несколько файлов, можно напечатать их имена в одну строку через пробел;

mkdir second-project (от англ. make directory, «создать директорию») — создай папку с именем second-project в текущей папке.


### Копирование и перемещение
cp file.txt ~/my-dir (от англ. copy, «копировать») — скопируй файл в другое место;
mv file.txt ~/my-dir (от англ. move, «переместить») — перемести файл или папку в другое место.


### Чтение
cat file.txt (от англ. concatenate and print, «объединить и распечатать») — распечатай содержимое текстового файла file.txt.


### Удаление
rm about.html (от англ. remove, «удалить») — удали файл about.html;
rmdir images (от англ. remove directory, «удалить директорию») — удали папку images;
rm -r second-project (от англ. remove, «удалить» + recursive, «рекурсивный») — удали папку second-project и всё, что она содержит.


### Полезные возможности
Команды необязательно печатать и выполнять по очереди. Можно указать их списком — разделить двумя амперсандами (&&).
У консоли есть собственная память — буфер с несколькими последними командами. По ним можно перемещаться с помощью клавиш со стрелками вверх (↑) и вниз (↓).
Чтобы не вводить название файла или папки полностью, можно набрать первые символы имени и дважды нажать Tab. Если файл или папка есть в текущей директории, командная строка допишет путь сама.
Например, вы находитесь в папке dev. Начните вводить cd first и дважды нажмите Tab. Если папка first-project есть внутри dev, командная строка автоматически подставит её имя. Останется только нажать Enter.


---


SSH использует пару ключей для обеспечения безопасности — публичный и приватный: 
Приватный ключ (англ. private key) хранится только на вашем компьютере и не должен передаваться кому-либо ещё. Он используется для расшифровки данных.
Публичный ключ (англ. public key) доступен всем и используется для шифрования данных. Они могут быть расшифрованы парным приватным ключом.

Для генерации SSH-пары можно использовать программу ssh-keygen.

'''
$ ssh-keygen -t rsa -b 4096 -C
'''

---

Инициализировать репозиторий можно с помощью команды git init.
Проверить статус, или состояние, репозитория поможет команда git status.
Если вы ошиблись и случайно инициализировали не ту папку, можно «разгитить» её — удалить скрытую подпапку .git.


Привязать удалённый репозиторий к локальному — git remote add
$ git remote add origin git@github.com:%ИМЯ_АККАУНТА%/%ИМЯ ПРОЕКТА%

Убедиться, что репозитории связаны, — git remote -v


---


Команда git add позволяет подготовить файл к сохранению.
Команда git add --all подготовит к сохранению сразу все файлы.
С помощью git add . можно добавить в репозиторий текущую папку со всеми файлами.

Коммит можно сделать с помощью команды '''git commit'''
Ключ -m позволяет присвоить коммиту сообщение. Помните, что такие сообщения должны быть информативными: чётко описывать изменения.
Команда git log — используйте её, чтобы оглянуться назад и посмотреть коммиты

Коммиты хранятся в ветках. Начальная ветка создаётся автоматически и называется main или master.
За отправку изменений на удалённый репозиторий отвечает команда git push.
Интерфейс GitHub позволяет удобно просмотреть все коммиты в репозитории, а также изменения в этих коммитах.


---


Шпора по Маркдауну: https://gist.github.com/fomvasss/8dd8cd7f88c67a4e3727f9d39224a84c

ВЫЙТИ из VIM: https://techrocks.ru/2021/06/25/how-to-exit-vim/ (:q!)

30 актуальных команд в Git: https://habr.com/ru/companies/ruvds/articles/599929/


---

## Всякое разное

pwd  текущая дерикторияtouc

cd (name/ .. )- преход по директориям

ls (-1a) - показать что в директориях

history история команд
|||(ctrl +r ) реверсивный поиск

stat статус 

cat прочитать фаил

head прочитать первые 10 строк

tail прочитать последние 10 строк

tail -f дописывает новые строки

less пейджер

man мануал

grep поиск текста по файлу

vim solution вим редактор||| (:q выход)

echo вывод текста|||
|||(> >> ) пренаправление потоков
|||( | ) пайслайн(запуск разных програм)

touch создание файла

mkdir создание дериктории
    |||(-p) для рекурсивного созд. директорий 

rm удалить фаил
   |||(-r) для рекурсивного удалиния
    |||(-f) для удал. игнор доступа

mv переименовать фаил

cp  копирование (-r) для директорий 

evn список переменных

whoami кто пользователь

ps отчет о процессах
   ||| ( aux) под кем запущен

id индификатор пользователя

sudo запуск из под root

tee утилита создает фаил и пишет ввод

chmod изминение прав доступа

apt пакетный менеджер(установщик)
