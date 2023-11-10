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


## Работа с логами

```
git log
```

Получить сокращённый лог :  **git log --oneline**

Примечание: *Обратите внимание: если выход из просмотра логов не произошёл автоматически, нажмите клавишу Q (от англ. Quit — «выйти») в английской раскладке клавиатуры.*

---


SSH использует пару ключей для обеспечения безопасности — публичный и приватный: 
Приватный ключ (англ. private key) хранится только на вашем компьютере и не должен передаваться кому-либо ещё. Он используется для расшифровки данных.
Публичный ключ (англ. public key) доступен всем и используется для шифрования данных. Они могут быть расшифрованы парным приватным ключом.

Для генерации SSH-пары можно использовать программу ssh-keygen.

```
ssh-keygen -t rsa -b 4096 -C
```

---

Инициализировать репозиторий можно с помощью команды **git init**.

Проверить статус, или состояние, репозитория поможет команда **git status**.

Если вы ошиблись и случайно инициализировали не ту папку, можно «разгитить» её — удалить скрытую подпапку .git.


Привязать удалённый репозиторий к локальному — **git remote add**

$ git remote add origin git@github.com:%ИМЯ_АККАУНТА%/%ИМЯ ПРОЕКТА%

Убедиться, что репозитории связаны, — **git remote -v**


---


Команда **git add** позволяет подготовить файл к сохранению.

Команда **git add --all** подготовит к сохранению сразу все файлы.

С помощью **git add .** можно добавить в репозиторий текущую папку со всеми файлами.

Коммит можно сделать с помощью команды **git commit**

Ключ **-m** позволяет присвоить коммиту сообщение. Помните, что такие сообщения должны быть информативными: чётко описывать изменения.

Команда **git log** — используйте её, чтобы оглянуться назад и посмотреть коммиты

Kоммиты хранятся в ветках. Начальная ветка создаётся автоматически и называется main или master.

За отправку изменений на удалённый репозиторий отвечает команда **git push**.

Интерфейс GitHub позволяет удобно просмотреть все коммиты в репозитории, а также изменения в этих коммитах.

---

## Хеш — идентификатор коммита
---


В процессе работы с Git вам будет часто встречаться понятие «хеш коммита». Эти странные строчки с бессмысленным (на первый взгляд) набором букв и цифр вы могли видеть, когда вызывали команду **git log** и выводили историю коммитов.

 (от англ. hash, «рубить», «крошить», «мешанина») — это способ преобразовать набор данных и получить их «отпечаток» (англ. fingerprint).
Информация о коммите — это набор данных: когда был сделан коммит, содержимое файлов в репозитории на момент коммита и ссылка на предыдущий, или родительский (англ. parent), коммит

Git преобразует информацию о коммитах с помощью алгоритма SHA-1 и для каждого из них рассчитывает уникальный идентификатор — хеш.

Хеш — основной идентификатор коммита и позволяет узнать его автора, дату и содержимое закоммиченных файлов.

Все хеши, а также таблицу соответствий хеш → информация о коммите Git хранит в папке .git.

---

## Исследуем лог

---

В этом уроке рассмотрим подробнее, из каких элементов состоит описание коммита, а также как вывести сокращённый лог (от англ. log — «журнал [записей]»). Сокращённый лог полезен, если нужно быстро найти нужный коммит среди сотни других.

**git log --oneline** умещается максимум 72


Разберём элементы, из которых состоит описание:

строка из цифр и латинских букв после слова *commit* — это хеш коммита;

*Author* — имя автора и его электронная почта;

*Date* — дата и время создания коммита;

в конце находится сообщение коммита.

---

## HEAD — всему голова

---

Файл HEAD (англ. «голова», «головной») — один из служебных файлов папки .git. Он указывает на коммит, который сделан последним (то есть на самый новый).

В этом можно убедиться с помощью терминала. Перейдите в .git командой cd. Посмотрите содержимое файла HEAD командой cat.

---

## Статусы файлов в Git

---

### Статусы untracked/tracked, staged и modified


Одна из ключевых задач Git — отслеживать изменения файлов в репозитории. Для этого каждый файл помечается каким-либо статусом. Рассмотрим основные.
_untracked_ (англ. «неотслеживаемый»)

Мы говорили, что новые файлы в Git-репозитории помечаются как untracked, то есть неотслеживаемые. Git «видит», что такой файл существует, но не следит за изменениями в нём. У untracked-файла нет предыдущих версий, зафиксированных в коммитах или через команду **git add**.
_staged_ (англ. «подготовленный»)
  После выполнения команды **git add** файл попадает в _staging area_ (от англ. stage — «сцена», «этап [процесса]» и area — «область»), то есть в список файлов, которые войдут в коммит. В этот момент файл находится в состоянии _staged_.
 
_tracked_ (англ. «отслеживаемый»)

Состояние _tracked_ — это противоположность untracked. Оно довольно широкое по смыслу: в него попадают файлы, которые уже были зафиксированы с помощью **git commit**, а также файлы, которые были добавлены в _staging area_ командой git add. То есть все файлы, в которых Git так или иначе отслеживает изменения.
_modified_ (англ. «изменённый»)

Состояние _modified_ означает, что Git сравнил содержимое файла с последней сохранённой версией и нашёл отличия. Например, файл был закоммичен и после этого изменён.
💡 Для файлов в состояниях _staged_ и _modified_ обычно не указывают, что они также tracked, потому что это состояние подразумевается.

---

## Жизненый цикл файлов в Git. Статусы.

```mermaid
  graph TD;
      untracked--git add-->staged+tracked;
      staged+tracked-->tracked;
      tracked-->modified;
      modified-->staged+tracked;
      staged+tracked-->modified;
```

---

## Git status 

---

Частая ошибка при использовании Git — закоммитить лишнее или, наоборот, забыть добавить важный файл в коммит. Этого легко избежать, если не забывать проверять статусы файлов с помощью команды **git status**.

---

## Оформление сообщений к коммитам

---

Есть общие рекомендации по тому, как правильно составить сообщение. Оно должно быть:

*относительно коротким, чтобы его было легко прочитать;

*информативным.

Вот пример полезного сообщения в репозитории новостного сайта: Исправление опечатки в заголовке главной страницы на хорватском. Такое сообщение даёт много информации:

*Исправление опечатки значит, что исправлена ошибка, которая была допущена при наборе. Такое исправление не меняет смысл. То есть, например, главному редактору не нужно перепроверять этот заголовок.

*На хорватском говорит о том, что переводчикам на другие языки этот коммит можно смело пропускать.

*В заголовке главной страницы указывает, где произошли изменения. Если, например, кто-то зайдёт на сайт и ему не понравится новый заголовок, он легко найдёт по истории (git log) автора этого коммита и спросит у него, почему заголовок теперь такой.

Пример плохого сообщения для того же коммита:_Исправлена опечатка_.

* Это сообщение даёт мало информации. В такой коммит придётся «заглядывать» — разбираться, что именно поменялось и зачем.

---

Шпора по Маркдауну: https://gist.github.com/fomvasss/8dd8cd7f88c67a4e3727f9d39224a84c

ВЫЙТИ из VIM: https://techrocks.ru/2021/06/25/how-to-exit-vim/ (:q!)

30 актуальных команд в Git: https://habr.com/ru/companies/ruvds/articles/599929/


---

## ~~Всякое разное~~

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
