# Инструкция по работе с Git и удалёнными репозиториями

## Что такое git?
**Git** - это наиболее популярная реализация распределённой системы контроля версий. Самая популярная реализация **Git** - это [GitHub](https://github.com/)

## Подготовка репозитория
Для создания репозитория используется команда *git init*. Для этого необходимо в терминале перейти в пустую папку, где в будущем будет репозиторий. Затем в терминале с папкой написать команду *git init*.

## Создание коммитов

### Добавление файла к коммиту
Для добавления файла к будущему коммиту используется команда *git add*. Для этого в терминале с папкой-репозиторием необходимо написать *git add <название файла>*.

### Создание коммита
Для создания коммита используется команда *git commit*. Для этого в терминале с папкой репозиторием необходимо написать *git commit -m <сообщение к коммиту>*. Сообщение к коммиту писать ***ОБЯЗАТЕЛЬНО!!!***.

## Журнал изменений
Для просмотра журнала изменений используется команда *git log*. Для этого в терминале с папкой-репозиторием необходимо написать *git log*.

## Перемещение между коммитами
Для перемещения на предущие коммиты используется команда *git checkout*. 

Для этого необходимо в журнале изменений, как показано в предыдущей части, найти необходимый коммит и его номер. После чего в терминале с папкой-репозиторием написать команду *git checkout <номер коммита>*. После примененения этой команды Вы попадёте в состояние **Detached head**, в котором никакие изменения фиксироваться не будут.

Для возврата в обычное состояние необходимо написать команду *git checkout master*.

##  Работа с ветками в Git

### Создание веток в Git
Для создания новой ветки используется команда *git branch*. Для этого в терминале с папкой-репозиторием необходимо написать *git branch <название ветки>*.

### Просмотр списка веток
Для просмотра списка веток используется команда *git branch*. Для этого в терминале с папкой-репозиторием необходимо написать команду *git branch*. Зелёным цветом с символом **звёздочка** будет выделена текущая ветка.

### Переключение между ветками
Для перехода на другую ветку используется команда *git checkout*. Для этого в терминале с папкой-репозиторием пишем команду *git checkout <название ветки>*. Для перехода на ветку ветка должна быть ***создана***!!!

### Слияние веток и разрешение конфликов
Ветку, в которую мы хотим слить изменения, будем называть основной. А ветку, из которой мы будем их сливать - тематической.

Для слияния мы переходим на основную ветку и используем команду *git merge <тематическая ветка>*.

Если обе ветви меняют одну часть файла, то возникает конфликт слияния - ситуация, в которой Git не знает какую версию файла сохранить. Разрешать конфликты нужно собственноручно.

После разрешения всех конфликтов необходимо использовать *git add <имя файла>* и *git commit -m "сообщение"* для завершения слияния.

## Удаление веток
Команда *git branch -d <имя ветки>* удаляет ветку.

## Работа с удаленными репозиториями

### Определение удаленного репозитория
Удаленными (иногда говорят "внешними") репозиториями называют репозитории, располагающиеся удаленно от нас, где-то в другом месте. Это может быть какой-то сервер, компьютер нашего друга или что-то ещё.

### Клонирование удаленного репозитория
Операция клонирования создает на вашем компьютере точную копию удаленного репозитория (всей папки). Для выполнения этой операции в Git предусмотрена команда *git clone <ссылка на удаленный репозиторий>*.

Для перехода в клонированную папку-репозиторий необходимо в терминале ввести команду *cd <имя папки-репозитория>*.

### Подключение и отключение удаленного репозитория
Для добавления удаленного репозитория в терминале необходимо набрать команду *git remote add origin <ссылка на удаленный репозиторий>*.
Иногда возникает необходимость "забыть" удаленный репозиторий. Для этого существует команда *git remote remove <название удаленного репозитория>*.

### Получение изменений из удаленного репозитория
Команда *git pull origin master* позволяет скачать все из удаленного репозитория на GitHub и автоматически сделать merge с нашей локальной версией.

### Отправка изменений в удаленный репозиторий
Команда *git push origin master* позволяет отправить свою версию репозитория во внешний репозиторий. **!Требует авторизации!** на внешенм репозитории.

### Форки и пулл-реквесты
**Форк** (от англ fork - вилка) - точная копия репозитоия, но на вашем аккаунте.

**Пулл-реквест** (от англ. pull-request - запрос на pull) - функция GitHub, позволяющая попросить владельца репозитория, от которого мы сделали форк, загрузить наши изменения обратно в свой репозиторий.

Форки и пулл-реквесты нужны, чтобы любой пользователь мог внести свой вклад в любой открытый проект, репозиторий которого есть на GitHub.
