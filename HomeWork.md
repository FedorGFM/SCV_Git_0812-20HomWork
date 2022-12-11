![logo](images.png)
# Работа с Git

## 1. Проверка наличия установленного Git.
В терминале выполнить команду `git version`
Если Git установлен, Появится сообщение с информацией о версии программы.
Иначе будет сообщение об ошибке.

## 2. Установка Git.
Загружаем последнюю версию Git с сайта https://git-scm.com/downloads. Устанавливаем с настройками по умолчанию.

## 3. Настройка Git
При первом использовании Git необходимо представиться.
Для этого необходимо выполнить в терминале две команды:
```
git config --global user.name «Ваше имя английскими буквами»
git config --global user.email ваша почта@example.com
```

## 4. Инициализация репозитория Git.
`git init` - Начало работы (создание репозитория).Для этого необходимо ввести команду `git init` в терминале. Прив выполнении этой команды в терминале будет создан **репозиторий**.

**Репозиторий** - это место, где хранятся и поддерживаются данные. Чаще всего данные в репозитории хранятся в виде файлов, доступных для дальнейшего распространения по сети.

## 5. Запись изменений в репозитории Git.

`git status` - Эта команда предназначена для получения информации от git о его текущем состоянии. При выполнении этой команды в терминале появится информация о состоянии файла.

`git add` - Добавляет файл или файлы к следующему коммиту. Для выполнения этой команды необходимо в терминале набрать git add(Имя файла), есть функция автозаполнения через **Tab**. Для пользования функцией автозаполнения необходимо ввести несколько первых букв **Имени файла**.

`git commit -m "Перечень изменений"` - Создает коммит.

**Коммит** - Это основные конструктивные элементы временной шкалы проекта Git. Их можно рассматривать как снимки состояния или контрольные точки на временной шкале проекта Git. Коммиты создаются с помощью команды git commit , которая делает снимок состояния проекта на текущий момент времени.

Так же есть команда объединяющая `git add` и `git commit -m` (`git commit -am"Перечень изменений"`)

`git diff` - Дает возможность увидеть разницу между текущим файлом и закоммиченным файлом.

## 6. Просмотр историй коммитов Git.

`git log` - Вывод на экран истории всех коммитов с их уникальными хеш-кодами. У каждого коммита свой уникальный Хеш-код. Для выхода из меню git log необходимо пролистаь в самый низ и нажать **q**.

## 7. Перемещение между сохранениями Git.

`git checkout` - переход от одного коммита к другому. Для этоно необходимо ввести `git checkout` с добавлением **Уникального хеш-кода**.

`git checkout master` - вернуться к актуальному состоянию и продолжить работу(вернется на ветку master) бывает множество разных веток.

## 8. Добавление картинок в Git.
 
 Для этого нам необходимо поместить необходимую картинку в папку с которой мы работаем в Visual Studio Code.

 Слева в столбце появится файл с расширением **png**(это и есть добавленая картинка).

 В Visual Studio Code создать папку .gitignore в ней указать тип расширения(Например *.png, *.txt и т.д.)

 Далее на картинку в левом столбце нажимаем ПКМ и выбираем пункт `Скопировать относитеоьный путь`. Затем в необходимой нам строке прописываем **![logo](Имя картинки)**.

 В случае если картика не сможет загрузиться или будет какая-либо ошибка у нас будет выделяться `[logo]`.

## 9. Игнорирование файлов.
Для того, что бы исключить из отслеживания в репозитории определенные файлы или папки необходимо создать файл `.gitignore` и записать в него их названия или шаблоны, соответствующие таким файлам или папкам.

## 10. Создание веток в Git.
Ветка в Git - Это простой перемещаемый указатель на один из коммитов обычно, последний в цепочке коммитов. 
По умолчанию имя основной ветки в Git - *master*.
В результате создаётся новый указатель на текущий коммит. 

Ветка в Git - Это простой перемещаемый указатель на один из коммитов обычно, последний в цепочке коммитов. 
По умолчанию имя основной ветки в Git - *master*.
 
Создать ветку можно командой:
```
git branch <Имя новой ветки>
```
 Список веток в репозитории можно посмотреть с помощью команды:
 ```
 git branch
 ```
 Текущаяя ветка будет отмечена звездочкой и выделена зеленм цветом: **\*master**.

 \*Комманды для создание новой ветки с моментальным переходом в неё:
 ```
 git checkout -b<Имя ветки>
 git switch -c <Имя ветки>
 ```
## 11. Слияние веток и разрешение конфликтов.
Для слияния выбранной ветки с текущей нужно выполнить команду:
```
git merge <Название выбранной ветки>
```
Если была изменена одна и та же часть файла в обеих ветках, то может возникнуть конфликт, который потребует участие пользователя. VsCode предлагает варианты решения конфликта.

VsCode предложит решить конфликт несколькими способами:
```
1. Accept Current Change - принимает текущее изменение.
2. Accept Incoming Change - принимает входящие изменения.
3. Accept Both Changes - принять оба изменения.
4. Compare Change - сравнить изменения(откроет отдельные окна для сравнения).
```
После того как конфликт решен необходимо выполнить слияние коммита командой `git commit -am"комментарий"`.
## 12. Переход между ветками в Git.
Для того что бы выполнить переход между ветками в Git нам нужны комманды:
```
git checkout <Имя ветки>
git switch <Имя ветки>
```
## 13. Удаление веток в Git.
Для того что бы удалить ветку необходима комманда `git branch -d<Название ветки>`. А так же комманда для удаления ветки(даже если она не объединена) `git branch -D <Название ветки>`. 

*\*Пока мы находимся в ветке, её нельзя удалить, для её удаления нам необходимо перейти на другую ветку, выполнить слияние и затем у нас получится её удалить. А также её нельзя удалить пока не выполнен коммит.*
## 14. Работа с удаленными репозиториями.
Для работы с удаленными репозиториями нужен аккаунт на `GitHub`.

Для этого существуют следующие комманды:
```
git clone <url - адрес репозитория> - Клонирование внешнего репозитория на локальный пк.
git pull - Получение изменений и слияние с локальной версией.
Git push - Отправляет локальную версию репозитория на внешний.
```
Создаем папку в **Visual Studio Code**, затем заходим в аккаунт на `GitHub` в правом верхнем углу находим значек **+** нажимаем на него и выбираем пункт `New repository`, после этого указываем имя репозитория, выбираем публичный доступ к репозиторию, остальные параметры не трогаем и нажимаем **Create repository**.

Появляется страница с информацией на которой указанно что мы можем сделать что бы добавить файлы в наш репозиторий. 
```
echo "# Name" >> README.md - Создание файла.
git init - Инициализация репозитория.
git add README.md - Подготовить файл к фиксации.
git commit -m "first commit" - Зафиксировать изменения.
git branch -M Name - Переименовать текущую ветку(По умолчанию её имя master. 
git remote add (Название может быть любым по умолчанию -origin) <Имя для репозитория><url - адрес репозитория> - Этой коммандой мы связываем локальный репозиторий с удаленным. 
git push -u origin Name - Отправляем локальные изменения на удаленный репозиторий.
```
Комманда `git remote` - показывает какой удаленный репозиторий привязан, `git remote -v` - тоже самое только еще показывает url адреса.

После этой комманды выполняем `git push -u origin Name`
![logo](Git-Logo-1788C.png)

**Дополнительная информаия о языке Markdown доступна по ссылке** https://learn.microsoft.com/ru-ru/contribute/markdown-reference.