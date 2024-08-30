## Полностью пройдено

```# "Изучение Git"
githowto-tutorial
(https://githowto.com/ru/)

## Установка имени и электронной почты
git config --global user.name "Your Name"
git config --global user.email "your_email@whatever.com"

## Имя ветки по умолчанию
git config --global init.defaultBranch main

## Создание репозитория 
git init 
git add hello.html 
git commit -m "Initial Commit" 

﻿#﻿# Проверка статуса Гита 
git status
﻿#﻿# Проверка всех изменений репозитория 
git log

## Контроль отображения записей
git log --oneline --max-count=2
git log --oneline --since="5 minutes ago"
git log --oneline --until="5 minutes ago"
git log --oneline --author="Your Name"
git log --oneline --all

## Конечный удобный формат лога
git log --pretty=format:"%h %ad | %s%d [%an]" --date=short
(Для того что б не вводить постоянно команду,
можно добавить её в конфигурацию GIT по умолчанию)
git config --global format.pretty '%h %ad | %s%d [%an]'
git config --global log.date short

## Переключение между разными ветками и коммитами 
git checkout <hash> 
(После выполнения этой команды все файлы в рабочей директории
будут соответствовать состоянию репозитория на момент указанного коммита.)
cat hello.html
(Команда используеться для отображения содержимого текстового файла в терминале.)

Для того что б переместиться к последней версии нашего кода,
нам нужно переключиться на ветку по умолчанию, main.
git switch main

## Теги 
git tag v1
Создает тег для обозначения конкретного коммита, тем самым облегчая работу с проектом,
без использования <hash>.

## Переключение по имени тега
git checkout v1
git checkout v1-beta
(Почему используется checkout, а не switch?
Теги: Команда git switch поддерживает переключение только на ветки,
но не на теги или отдельные коммиты.
Поскольку в примере v1 и v1-beta — это теги, для переключения на них используется git checkout.)

## Просмотр всех тегов
git tag
git log main --all

## Удаление тегов 
git tag -d название тега

## Команда reset
Если выполнить команду reset с указанием ссылки на коммит
(т.е. метки HEAD, имени ветки или тега, хеша коммита), то команда...

1. Изменит текущую ветку, чтобы она указывала на указанный коммит.
2. Опционально сбросит область подготовки до соответствия с указанным коммитом.
3. Опционально сбросит рабочую директорию до соответствия с указанным коммитом.

## Создание ветки 
Старый вариант 
git checkout -b style

Новый вариант
git switch -c style

Оба способа рабочие, но так как checkout напичкан большим количеством функций и флагом,
его лучше не использовать.
"Команда git switch более выразительна и менее восприимчива к ошибкам.
Кроме того, в ней меньше флагов и опций, поэтому ее легче запомнить."

## Просмотр различий для конкретного файла
git show v1

## Слияние веток
git merge main
"Слияние переносит изменения из двух веток в одну."

## Отмена слияния 
git merge --abort

## Когда использовать команду rebase, а когда команду merge?
Используйте команду rebase:

Когда вы получаете изменения из удаленного репозитория и хотите применить их к своей локальной ветке.
Если вы хотите, чтобы история коммитов была линейной и легко читаемой.
Не используйте команду rebase:

Если текущая ветка является публичной и общей.
Переписывание таких веток будет мешать работе других членов команды.
Если важна точная история ветки коммитов (поскольку команда rebase переписывает историю коммитов).

## Создание клона репозитория 
git clone work home
ls
"Теперь должно быть два репозитория: оригинальный репозиторий work и клонированный репозиторий home."

## Удаленные ветки 
git branch
## Список удаленных веток
git branch -a

"Команда fetch позволяет контролировать то, что именно подтягивается и сливается в ваши локальные ветки,
но для удобства существует также команда pull,
которая подтягивает и сливает изменения из удаленной ветки в текущую одним вызовом."

## Команда pull (подтянуть)
git pull 
...эквивалентна следующим двум шагам:
git fetch

git merge origin/main

## Запуск Git-сервера
git daemon --verbose --export-all --base-path=.

КОНЕЦ
```

## Дата сдачи - 27.08.2024
