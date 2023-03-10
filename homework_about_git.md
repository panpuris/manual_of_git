## **Определение программы Git и ее команды**

**Программа Git** - помогает оптимизировать совместное создание и редактирование проектов (файлы, текст, код и т.д.). Предоставляет возможность сохранять не целые копии проектов, а их определенные версии и помогает оперативно обратиться к определенному шагу (моменту редактирования). Какие команды используются для работы с программой **Git** мы обсудим ниже.

## **Команды Git**

    git init

**Команда git init** - используется для инициализации (создания и регистрации) файла в папке в которой Git отслеживает все изменения и работу проекта. Папка становиться репозиторием для работы с файлами Git.


    git status

**Команда git status** - предоставляет нам информацию о текущей версии проекта. В случае обнаружении незафиксированных изменений терминал выдаст следующее сообщение:

    *Changes not staged for commit:
    (use "git add <file>..." to update what will be committed)
    (use "git restore <file>..." to discard changes in working directory)
    modified:   homework_about_git.md*
*git status распространяется на все файлы (сохраненные,несохраненные,добавленные,недобавленные)*    

    git add <filename>

**Команда git add** - добавляет определенный файл (если после add указать имя файла) или все файлы из репозитория в буфер(индекс) для отслеживания и для последующей фиксации изменений (коммита) в программе Git. 

    git commit
    git commit -m "message"
    git commit -a
    git commit -am "message"

**Команда git commit** - фиксирует изменения из индекса (буфера) и предоставляет возможность написания комментария в текстовом редакторе, а не в самом терминале.
Данная команда имеет несколько вариантов:

*git commit -m "message"* - фиксирует изменения и позволяет добавить комментарий об изменениях в самом терминале

*git commit -a* - совмещает в себе функцию добавления изменения в индекс (буфер) и сразу фиксирует данное изменение.

*git commit -am "message"* - совмещает функцию добавления в индекс (буфер), сразу фиксирует изменение и позволяет добавить комментарий в терминале.

    git log
    git log --oneline
    git log --all
    git log --oneline --all

**Команда git log** - предоставляет информацию о всех зафиксированных изменениях (коммитов): длинный номер коммита (хэш суммой) с подписью автора, датой и временем фиксации изменения, комментарием. Данная команда так же имеет несколько вариантов:

*git log --oneline* -выстривает все коммиты с их комментариями в сокращенной форме, для удобства оринтирования среди коммитов. Хэш суммы сокращены, но этого достаточно для ориентировки.

*git log --all* - при путешествии по коммитам (отсоеденении указателя head) показывает где находится head и где основная ветка master, показывет весь подробный log.

*git log --oneline --all* - при путешествии по коммитам (отсоеденении указателя head) показывает где находится head и где основная ветка master, показывает сокращенный log.

    git checkout <hash>

**Команда git checkout** - используется для путешествия по коммитам, для этого необходимо указать короткий номер необходимого коммита.
После путешествий принято возвращаться в основной коммит master или main.

    git diff

**Команда git diff** - используется для вывода сохраненных, но не зафиксированных изменений.    

    git diff <hash1> <hash2>

**Команда git diff hash1 hash2** - показывает разницу между коммитами, номера которых вы указываете на месте *hash1* и *hash2*.    

## Работа с изображениями в Git
Для добавления картинок и изображений используются символы:

    ![] ()
    Например:
    ![food in music](poster_event_2247108.jpg)

![food in music](poster_event_2247108.jpg)
В квадратных скобка пишется название картинки для проекта, в круглых название самого файла картинки/изображения.
В связи с тем что программа Git предназначена для работы с текстовыми файлами, добавление отслеживания файла картинки не принято.
Для этого создается папка **.gitignore**
В данную папку можно добавлять файлы для того чтобы Git их игнорировал.

## Ветвления веток

Ветвления в Git необходимы для работе в программе, без затрагивания основной ветки, это так называемые черновики которые позволяют работать в разных отраслях определенного проекта не рискуя навредить ему во время редактирования.

## Ветки и их просмотр

Для просмотра всех созданных веток и понимания в которой мы сейчас находимся используют команду:

    git branch

Знаком звездочки (*) она показывает в какой ветке мы находимся. Основная ветка называется master или main.

Для создания новой ветки используется команда:

    git branch branch_name


## Слияния веток

После того как вся работа в сторонней ветке завершена, ее можно залить на основную ветку путем слияния двух веток, для этого используется команда:

    git merge <branch_name>

Необходимо обратить внимание, перемещение происходит в ту ветку в которой мы находимся. Поэтому перед слиянием проводите проверку местонахождения через команду *git branch*.


## Конфликты при слиянии веток

При слияниях веток случаются конфликты, это происходит в связи с тем если вы внесли изменения в основной ветке и они пересекаются с изменениями из вливаемой ветки.
В случае конфликта обычно выбирают одно из трех решений:

* Оставить изменения которые были сделаны в основной ветке
* Внести изменения из переносимой ветки
* Оставить оба варианта для редактирования в ручную


## Переходы между ветками
Для переходов между ветками используют команду:

    git checkout <branch_name>

## Удаление веток

Для удаления веток которые нам больше не нужны используется команда:

    git branch -d <branch_name>

## Удаленные репозитории

Удаленные репозитории необходимы для совместной работы и публичного доступа к Вашим проектам. Так же они будут полезны непосредственно для самих владельцев, так как теперь не имеет значения из какой точки мира продолжать свою работу над проектом.

## Создание нового удаленного репозитория

Для создания нового репозитория необходимо зарегестрироваться на площадке GitHub ( или любом другом ресурсе, который предостваляет аналогичные услуги ).
Находясь на главной странице нажать зеленую кнопку new или (+) в верхнем правом углу рядом с Вашим профилем.

Перейдя в новое окно Вам необходимо:

- выбрать шаблон (если они есть)
- присвоить название репозиторию
- дать описание нового репозтиория (необязательно)
- выбрать тип репозитория (публичный или приватный)
- создать файл README
- добавить папку .gitignore (можно указать тип проекта)
- выбрать лицензию для распространения своего проекта

Нажать Create repositiry

## Окно Quick Setup

Здесь нам предоставляют адрес нашего репозитория, шаблоны команд для: 

1. создания нового репозитория на локальном компьютере
2. заливки (запушивание) своего локального репозитория
3. ипмпорт репозитория с других источников

Выбираем необходимый для нас вариант и переходим в локальный репозиторий.

## Команды для работы с удаленным репозиторием

Для заливки изменений которые были внесены на локальной версии репозитория, используется команда:

    git push

В случае если были внесены какие то изменения в удаленном репозитории, для их выгрузки на локальную версию используется команда :

    git pull

Если мы хотим прервать связь локального и удаленного репозитория используется команда :

    git remote remove origin

Для восстановления связи с удаленным репозиторием, используется команда:

    git remote add origin <Links_on_remote_rep>

Для загрузки удаленного репозитория (своего или чужого) и создания его копии на локальном носителе, используется команда:

    git clone <links_on_remote_rep>

## Работа с чужими репозиториями (форки)

Мы можем выбрать любой публичный проект, скопировать его и внести правки которые потом сможем предложтить владельцу/создателю данного проекта.
Выбрав проект, нажимаем на кнопку "fork" в верхнем правом углу, этот репозиторий появиться и в нашем аккаунте Github.

После этого загружаем его к себе на локальный носитель через команду *git clone*.

Хорошим тоном является создание своей, а точнее отдельной ветки где будут происходить все изменения.
Окончив работу с файлом, заливаем его на удаленный сервер командой git push

Для предложения изменений владельцу проекта мы можем нажать на зеленую кнопку **Compare & pull request** или через кнопку *Contribute* которая находится ниже.

Нас перенесет на окно **Comparing chancges**. Там мы можем оставить комментарий для автора проекта. Далее нажимаем кнопу **Create pull request**


## Принятие изменений которые предложили именно Вам

В случае того если Вам прислали предложения изменений на Ваш репозиторий, это отобразится *pull requests*, нажимаем на нее.
Выбираем предложение от пользователя с изменениями, рассматриваем изменения, в случае если нас все устраивает нажимаем кнопку **Merge pull request** и **Confirm merge**, если необходимо можем оставить комментарий отправителю по кнопке ниже **Comment**!
