# bash 

### Задание Bash 1


1. Открыть домашнюю директорию

 /c/Users/Azerty/Desktop/дз тесты/bash_training/bash

2.Определить имя папки, в которой вы находитесь

 $ `pwd`

 /c/Users/Azerty/Desktop/дз тесты/bash_training/bash

3.Создать внутри этой папки каталог  с именем test1

 $ `mkdir test1`

4.Перейти в папку test1

 $ `cd test1`

5.Создать файл 1,2 и 3 внутри каталога test1
 
 $ `touch {1,2,3}.txt`

6.Проверить содержимое каталога test1

 $ `ls`

 1.txt  2.txt  3.txt

7.Перейти в домашнюю директорию

 $ `cd ..`

8.Создать папку test2 внутри домашней директории

 $ `mkdir test2`

9.Удалить папку test2

 $ `rmdir test2`

10.Удалить файл 2 из папки test1

 $ `rm 2.txt ./test1`

11.Создать папку в домашней директории test3 и добавить в нее два файла

$ `mkdir test3`

 $ `cd test3`

 $ `touch {3,4}.txt`

12.Удалить папку test3

 $ `rm -rf test3`

13.Создать папку test4 в домашней директории

 $ `mkdir test4`

14.Переместить файлы 1 и 3 из папки test1 в папку test4

 $ `mv test1/{1,3}.txt test4/`

15.Добавить в файл 1 три строки со словами line

 $ `cd test4`

 $ `echo "line line line"> 1.txt`

16.Посмотреть содержимое файла 1

 $ `cat 1.txt`

 line line line

17.Добавьте в файл 3 три строки со словами line

 $ `echo "line line line"> 3.txt`

18.Просмотрите содержимое двух файлов (1 и 3) сразу

 $ `cat 1.txt 3.txt`

 line line line

19.Используя один из редакторов замените все строки в файле 1

 $ `nano 1.txt`


 ### Задание Bash 2

 1.Зайти в домашнюю директорию

  /c/Users/Azerty/Desktop/дз тесты/bash_training/bash
  $ `cd ~`

 2.Создать папку test 3

  $ `mkdir test3`

 3.Добавить в папку test 3 три файла 4, 5 и 6, в каждом из которых должно быть по 4 строки row1, row2, row3, row4

  $ `touch test3/file {4,5,6}.txt`

  $ `echo row1, row2, row3, row4 > 4.txt`

  $ `echo row1, row2, row3, row4 > 5.txt`

  $ `echo -e "row1\nrow2\nrow3\nrow4" > 6.txt`

 4.Найдите строку row2 в файле 5

  $ `grep "row2" 5.txt`
  
  row1, row2, row3, row4

  5.Найдите строку row в папке test3

  $ `grep 'row' ./test3  -r`
  ./test3/4.txt:row1, row2, row3, row4
  ./test3/5.txt:row1, row2, row3, row4
  row4st3/6.txt:row1
  
  6.Посчитайте сколько строк с содержимым row в файле 6
  
  $ `grep 'row' 6.txt -c`
  4
  
  7.Найдите файл 5 внутри папки test3

  $ `find ./test3  -name 5.txt`

  ./test3/5.txt

  8.Используя команду find, удалите файл 5

  $ `find ./test3  -name 5.txt -delete`

  9.Используя команду echo, добавьте слово test в файл 4

  $ `echo "test" >> ./test3/4.txt`

  10.Замените слово test в файле 4 на fail

  $ `sed 's/test/fail/g' 4.txt`
  row1, row2, row3, row4
  fail

  $ `sed 's/test/fail/g' 4.txt -i`

  11.Добавьте в файл 4 слово test так, чтобы сохранилось содержимое

  $ `echo "test" >> ./test3/4.txt`

  12.Просмотрите все процессы для юзеров не только в консоли, которые происходят в системе

  $ `ps aux`
      
      
      PID    PPID    PGID     WINPID   TTY         UID    STIME COMMAND
      990       1     990      12208  cons0     197609 11:54:30 /usr/bin/bash
     1117     990    1117      11928  cons0     197609 12:44:20 /usr/bin/ps 


  13.Убейте процесс 666 в консоли
  
  $ `Kill  666`

  14.Узнайте доступность ресурса artsiomrusau.com, используя ping
  
  $ `ping artsiomrusau.com`

Обмен пакетами с artsiomrusau.com [185.215.4.92] с 32 байтами данных:
Превышен интервал ожидания для запроса.
Превышен интервал ожидания для запроса.
Превышен интервал ожидания для запроса.
Превышен интервал ожидания для запроса.

Статистика Ping для 185.215.4.92:
    Пакетов: отправлено = 4, получено = 0, потеряно = 4
    (100% потерь)


  15.Отправьте 5 пакетов на сайт artsiomrusau.com

  $ `ping -n 5  artsiomrusau.com`

Обмен пакетами с artsiomrusau.com [185.215.4.92] с 32 байтами данных:
Превышен интервал ожидания для запроса.
Превышен интервал ожидания для запроса.
Превышен интервал ожидания для запроса.
Превышен интервал ожидания для запроса.
Превышен интервал ожидания для запроса.

Статистика Ping для 185.215.4.92:
    Пакетов: отправлено = 5, получено = 0, потеряно = 5
    (100% потерь)

  16.	Используя GET и команду curl, получите информацию о зарегистрированных питомцах на https://petstore.swagger.io/

  curl -X GET https://petstore.swagger.io/v2/pet/{petId}

  17.	Используя POST и команду curl, создайте нового пользователя на https://petstore.swagger.io/

  curl -X POST https://petstore.swagger.io/v2/pet --data “name = Donald” --data “status = available”
