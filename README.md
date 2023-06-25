# Шпаргалка по работе с Git

## Навигация в командной строке
1. **"pwd"** - показывает текущую дирректорию  
2. **"cd"** *'имя дирректории'* - переход в другую дирректорию  
3. **"ls** *'имя дирректории'* - показывает сожержимое дирректории  
3.1. **"ls -a** *'имя дирректории'* - показывает сожержимое дирректории со скрытыми файлами  
3.2. **"ls ~"** - покажет содержимое домашней дирректории, вне зависимости от дирректории нахождения  
3.3. **"ls .."** - покажет содержимое родительской дирректории, вне зависимости от дирректории нахождения  
4. **" ~ "** - домашняя дирректория  
5. **" .. "** - указывается в пути файла для перехода на одну дирректорию вверх  

## Создание, удаление новых файлов и дирректорий
1. **"touch"** *'имя файла'* - создание нового файла (название нужно указывать с расширением)  
2. **"mkdir"** *'имя дирректории'* - создание новой дирректории  
2.1. **"mkdir -p"** *имена дирректорий через /* - создание новой группы дирректорий  
3. **"rm"** *'имя файла'* - удаление файла  
3.1. **"rmdir"** *'имя дирректории'* - удаление __*пустой*__ дирректории  
3.2. **"rm -r"** *'имя дирректории'* - удаление дирректории со всем содержимым  

## Действия с файлами
1. **"cp"** *'что'* *'куда'* (или *'что'* *'что'* *'куда'*) - копирование файлов  
2. **"mv"** *'что'* *'куда'* (или *'что'* *'что'* *'куда'*) - перемещение файлов  
3. **"cat"** *'имя файла'* - чтение файлов (только текстовых)  
---
##### *Чтобы выполнить сразу несколько команд, нужно использовать __" && "__*  
##### *Чтобы обратиться к ранее введенным командам, нужно использовать __" ↑ "__ или __" ↓ "__ на клавиатуре.*  
##### *Если не получается вспомнить команду, введите все, что помните и нажмите __"Tab"__. Командная строка предложит вам все возможные варианты.*  
---
## Действия с репозиториями
1. **"git init"** - сделать папку репозиторием  
2. **"git status"** - проверить состояние репозитория  
3. **"git add"** - подготовить файлы к сохранению  
3.1. **"git add -all"** - подготовить __*все*__ файлы к сохранению
4. **"git commit -m"** - выполнить коммит (сохранение) с сообщением-пометкой
5. **"git log"** - посмотреть историю коммитов
6. **"git push"** - отправить изменения на удаленный репозиторий

## Хеш — идентификатор коммита
- Git преобразует информацию о коммитах с помощью алгоритма SHA-1 и для каждого из них рассчитывает уникальный идентификатор — хеш.
- Хеш — основной идентификатор коммита и позволяет узнать его автора, дату и содержимое закоммиченных файлов.
- Все хеши, а также таблицу соответствий *хеш → информация о коммите* Git хранит в папке *.git*.

## Описание коммита
Элементы, из которых состоит описание:  
- строка из цифр и латинских букв после слова **commit** — это хеш коммита;
- **Author** — имя автора и его электронная почта;
- **Date** — дата и время создания коммита;
- в конце находится сообщение коммита.  


Можно вызвать не только полный лог, но и сокращённый — это делается командой _**git log --oneline**_.  
В сокращённом логе выводятся сокращённые хеши — их можно использовать точно так же, как и полные.

## Файл HEAD
Файл **HEAD** — один из служебных файлов папки **.git**. Он указывает на коммит, который сделан последним (то есть на самый новый).  
* В числе прочих файлов в папке **.git** есть служебный файл _**HEAD**_. Он указывает на самый свежий коммит.
* Вместо хеша последнего коммита можно написать слово _**HEAD**_ — Git вас поймёт.

## Статусы файлов в Git
* Статусом _**untracked**_ помечается файл, о существовании которого Git знает, но не следит за изменениями в нём. Этот статус — противоположность _**tracked**_, в который попадают все файлы, отслеживаемые Git.
* Файл переходит в статус _**staged**_ после выполнения *git add*.
* Статус _**modified**_ означает, что файл был изменён.
* Большинство файлов в проектах «шагает» по следующему циклу: «изменён» → «добавлен в список на коммит» → «закоммичен» → «изменён» → и так далее.
* Команда **git status** всегда подскажет, что происходит с файлом: например, он добавлен в список «на коммит» или ещё вообще не отслеживается, или изменён.
* **git status** показывает явно следующие состояния файлов: _**untracked**_, _**staged**_ и _**modified**_.
* **git status** подсказывает, какие команды можно выполнить, чтобы поменять состояние файла.

## Оформление сообщений к коммитам
То, как написаны сообщения коммитов, тоже может подчиняться определённым правилам. Иногда эти правила продиктованы культурой команды, а иногда техническими ограничениями.  


Например, в выводе команды **git log --oneline** умещается максимум 72 первых символа сообщения, поэтому многие правила включают пункт: «Сообщение не должно быть длиннее 72 символов».  


_**Зачем вообще писать сообщения?**_ У каждого коммита в Git есть сообщение — то, что передаётся после параметра -m. Сообщения коммитов можно сравнить с надписями на коробках в кладовке. Если надписей нет, то нужную коробку будет сложно найти: придётся заглянуть в каждую, чтобы понять, что там. А если надписи есть, то нужная найдётся сразу. 

 
Есть общие рекомендации по тому, как правильно составить сообщение. Оно должно быть:  
* относительно коротким, чтобы его было легко прочитать;
* информативным.