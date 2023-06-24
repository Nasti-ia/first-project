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