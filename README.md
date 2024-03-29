#Roadmap основы работы с Git
---
##**Для начала работы с Git необходимо знать базовые команды в консоли**

##**Список базовых команд для работы с консолью**

###**Навигация**

* _pwd_ (от англ. print working directory, «показать рабочую папку») — покажи, в какой я папке;
* _ls_ (от англ. list directory contents, «отобразить содержимое директории») — покажи файлы и папки в текущей папке;
* _ls -a_ — покажи также скрытые файлы и папки, названия которых начинаются с символа .;
* _cd first-project_ (от англ. change directory, «сменить директорию») — перейди в папку first-project;
* _cd first-project/html_ — перейди в папку html, которая находится в папке first-project; 
* _cd .._ — перейди на уровень выше, в родительскую папку;
* _cd ~_ — перейди в домашнюю директорию (/Users/Username);
* _cd /_ — перейди в корневую директорию.

##**Работа с файлами**

###**Создание**
* _touch index.html_ (англ. touch, «коснуться») — создай файл index.html в текущей папке;
* _touch index.html style.css script.js_ — если нужно создать сразу несколько файлов, можно напечатать их имена в одну строку через пробел;
* _mkdir second-project_ (от англ. make directory, «создать директорию») — создай папку с именем second-project в текущей папке.

###**Копирование и перемещение**
* _cp file.txt ~/my-dir_ (от англ. copy, «копировать») — скопируй файл в другое место;
* _mv file.txt ~/my-dir_ (от англ. move, «переместить») — перемести файл или папку в другое место.

###**Чтение**
* _cat file.txt_ (от англ. concatenate and print, «объединить и распечатать») — распечатай содержимое текстового файла file.txt.

###**Удаление**
* _rm about.html_ (от англ. remove, «удалить») — удали файл about.html;
* _rmdir images_ (от англ. remove directory, «удалить директорию») — удали папку images;
* _rm -r second-project_ (от англ. remove, «удалить» + recursive, «рекурсивный») — удали папку second-project и всё, что она содержит.

##**Полезные возможности**
* Команды необязательно печатать и выполнять по очереди. Можно указать их списком — разделить двумя амперсандами (&&).
* У консоли есть собственная память — буфер с несколькими последними командами. По ним можно перемещаться с помощью клавиш со стрелками вверх (↑) и вниз (↓).
* Чтобы не вводить название файла или папки полностью, можно набрать первые символы имени и дважды нажать Tab. Если файл или папка есть в текущей директории, командная строка допишет путь сама.
Например, вы находитесь в папке dev. Начните вводить cd first и дважды нажмите Tab. Если папка first-project есть внутри dev, командная строка автоматически подставит её имя. Останется только нажать Enter.


##Инициализация репозитория
---
###**Команда git init**

Чтобы Git начал отслеживать изменения в проекте, папку с файлами этого проекта нужно сделать **Git-репозиторием** (от англ. repository — «хранилище»). Для этого следует переместиться в неё и ввести команду **git init** (от англ. initialize — «инициализировать»).
Например, можно создать папку **project** и сделать ее Git-репозиторием. Для этого переходим в папку **project** с помощью команды **cd** и выполняем git init:
```
$ cd ~/dev/first-project # перешли в нужную папку

$ git init # создали репозиторий 
```

###«Разгитить» папку, если что-то пошло не так, — **rm -rf .git**
Если вы случайно сделали Git-репозиторием не ту папку, её можно «разгитить». Для этого нужно удалить скрытую подпапку .git.
```
$ cd <папка с репозиторием> # перешли в папку

$ rm -rf .git # удалили подпапку .git
```
###Проверка состояния репозитория - **git status**
После инициализации репозитория first-project запустите команду git status (от англ. status — «статус», «состояние») — она показывает текущее состояние репозитория.

Команда git status выведет:
* название текущей ветки: On branch master или On branch main;
* сообщение о том, что в репозитории ещё нет коммитов: No commits yet;
* сообщение, которое говорит: «чтобы что-нибудь закоммитить (то есть зафиксировать), нужно сначала это создать» — nothing to commit (create/copy files and use "git add" to track).


##Добавление файлов в репозиторий
* Команда git add позволяет подготовить файл к сохранению.
* Команда git add --all подготовит к сохранению сразу все файлы.
* С помощью git add . можно добавить в репозиторий текущую папку со всеми файлами.

##Создание коммита
---
**Коммит** - одна из основных сущностей в системах контроля версий, которая гарантирует, что изменения будут сохранены в истории и при необходимости к ним можно будет «откатиться».
###Команды для создания коммита
* Коммит можно сделать с помощью команды **git commit**.
* Ключ -m позволяет присвоить коммиту сообщение. Помните, что такие сообщения должны быть информативными: чётко описывать изменения.
* В коммит попадает то, что было предварительно добавлено «в корзину», или «в кадр», перед коммитом.

###Для просмтора истории коммитов можно воспользоваться командной **git log**


---
##Создание удаленного репозитория
На данный момент **Project** хранится только локально на компьютере.Чтобы поделиться репозиторием — например, с коллегами, — нужно завести его **удалённую версию**. Для этого можно использовать самую популярную среди предназначенных для командной работы - Github.

Для создания удаленного репозитория сначала необходимо зарегистрироваться на GitHub. В профиле (можно перейти по ссылке **https://github.com/username** , где username -имя, которое вы указали при регистрации.) создаем репозиторий. Для этого перейдите на вкладку **Repositories** (англ. «репозитории»), а затем нажмите на зелёную кнопку **New** (англ. «новый») справа.
Готово! Осталось связать удалённый репозиторий с локальным, который уже есть на вашем компьютере.

Чтобы обеспечить безопасность своего репозитория, необходимо научиться генерации SSH-ключа.
---
##Генерация SSH-ключа

###Что такое SSH
Когда компьютеры обмениваются данными в сети, они следуют сетевым протоколам (англ. network protocols) — правилам обмена данными между компьютерами.
Один из наиболее распространённых сетевых протоколов — **SSH** (от англ. Secure Shell Protocol). Он обеспечивает безопасный обмен данными в сети. С помощью этого протокола можно получать данные с удалённого компьютера или отправлять их на него. Трафик шифруется, поэтому протокол безопасен.

SSH использует пару ключей для обеспечения безопасности — публичный и приватный: 
* Приватный ключ (англ. private key) хранится только на вашем компьютере и не должен передаваться кому-либо ещё. Он используется для расшифровки данных.
* Публичный ключ (англ. public key) доступен всем и используется для шифрования данных. Они могут быть расшифрованы парным приватным ключом.
Только вы можете расшифровать данные с помощью приватного ключа, но любой владелец публичного ключа может их для вас зашифровать. Эти два ключа связаны и образуют SSH-пару. В будущем вы наверняка будете использовать их для взаимодействия с GitHub и другими удалёнными серверами.   

###Инструкция по генерации SSH-ключа
1. Для генерации SSH-пары можно использовать программу **ssh-keygen**. Откройте терминал и введите следующую команду: 
```
$ ssh-keygen -t ed25519 -C "электронная почта, к которой привязан ваш аккаунт на GitHub"
```

Используйте электронную почту, к которой привязан ваш GitHub-аккаунт. 
Если вы видите сообщение об ошибке, то, скорее всего, ваша система не поддерживает алгоритм шифрования ed25519. Ничего страшного: используйте другой алгоритм.
```
$ ssh-keygen -t rsa -b 4096 -C "электронная почта, к которой привязан ваш аккаунт на GitHub"
```
2. Укажите место хранения ключей. Простой вариант — сделать домашний каталог пользователя путём по умолчанию. Для этого нажмите Enter.
3. Программа запросит кодовую фразу (англ. passphrase) для доступа к SSH-ключу. Вы можете оставить поле пустым. Для этого нажмите Enter, а затем ещё раз Enter для подтверждения.
4. Готово! Теперь осталось проверить, что ключи действительно сгенерировались. Для этого вызовите эту команду:
```
ls -a ~/.ssh
```

На экране должны появиться два файла — один с расширением .pub, другой — без. Файл в .pub — публичный, им можно делиться с веб-сайтами или коллегами. Файл без расширения .pub — приватный. Ни в коем случае не передавайте его никому! 

##Инструкция по привязке SSH-ключа к GitHub
1. После выполнения команды ssh-keygen из предыдущего урока в директории ~/.ssh будет создано два файла — id_ed25519 и id_ed25519.pub (или id_rsa и id_rsa.pub — в зависимости от того, какой алгоритм вы использовали):
	* id_ed25519/id_rsa — приватный ключ (файл без .pub в конце). Ни в коем случае не копируйте его и не делитесь им.
	* id_ed25519.pub/id_rsa.pub — публичный ключ (на это указывает расширение .pub).
	Скопируйте содержимое файла с публичным ключом в буфер обмена (Windows):
```
//скопировать содержимое ключа в буфер обмена:
$ clip < ~/.ssh/id_rsa.pub
//для ed25519:
$ clip < ~/.ssh/id_ed25519.pub
```
2. Перейдите на GitHub и выберите пункт Settings (англ. «настройки») в меню аккаунта.
3. В меню слева нажмите на пункт SSH and GPG keys.
4. В открывшейся вкладке выберите New SSH key (англ. «новый SSH-ключ»).
5. В поле Title (англ. «заголовок») напишите название ключа. Например, Personal key (англ. «личный ключ»).
6. В поле Key type (англ. «тип ключа») должно быть Authentication Key (англ. «ключ аутентификации»).
7. В поле Key скопируйте ваш ключ из буфера обмена.
8. Нажмите на кнопку Add SSH key (англ. «добавить SSH-ключ»).
9. Проверьте правильность ключа с помощью следующей команды:
```
$ ssh -T git@github.com
```

##Связывание локального и удаленного репозитория
Сейчас у вас есть локальный репозиторий first-project, который хранится на вашем компьютере, и удалённый репозиторий на GitHub. Вы сгенерировали SSH-ключ для безопасной работы и теперь готовы связать удалённый репозиторий с локальным.

###Привязать удалённый репозиторий к локальному можно с помощью команды **git remote add**
Перейдите на страницу удалённого репозитория, выберите тип SSH и скопируйте URL. Кнопка справа позволит сделать это мгновенно.

Откройте консоль, перейдите в каталог локального репозитория и введите команду git remote add (от англ. remote — «удалённый» и add — «добавить»):
```
$ cd ~/dev/first-project
$ git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git
```

Команде необходимо передать два параметра: имя удалённого репозитория и его URL. В качестве имени используйте слово origin. А URL вы скопировали со страницы удалённого репозитория.
###Убедиться, что репозитории связаны, — **git remote -v**
Вы связали локальный репозиторий с удалённым. Осталось убедиться, что всё работает, с помощью команды git remote -v.


##Синхронизация локального и удалённого репозитории
Вы зарегистрировались на GitHub, сгенерировали SSH-ключ и привязали локальный репозиторий к удалённому. Самое сложное позади! Теперь разберём, как выкладывать свои правки на удалённый репозиторий. Но сначала немного о ветках.

###Основная ветка
Уже упоминалось, что каждый коммит сохраняет актуальное состояние файлов. Сами же коммиты хранятся в ветках (англ. branch).
Если коммит — это снимок состояния файлов, то ветка — временна́я шкала, на которой расположены эти снимки. Ветка всегда начинается от одного из коммитов.
В репозитории может существовать сразу несколько веток — параллельных историй изменений. Также они могут соединяться друг с другом.

Самая первая ветка в репозитории появляется автоматически и называется main (англ. «основная») или master. Её имя нужно указывать при отправке коммитов на удалённый репозиторий или при получении их из него.
###Отправить изменения на удалённый репозиторий — **git push**
Осталось загрузить содержимое локального репозитория на GitHub. За это отвечает команда **git push** (от англ. push — «толкать»).
В первый раз эту команду нужно вызвать с флагом -u и параметрами origin (имя удалённого репозитория) и main или master (название текущей ветки). Флаг -u свяжет локальную ветку с одноимённой удалённой. Как вы связывали локальный и удалённый репозитории в предыдущем уроке, так же и здесь нужно дополнительно связать ветки.
```
$ git push -u origin main # Если команда приведёт к ошибке, попробуйте 
                          # заменить main на master.
```

