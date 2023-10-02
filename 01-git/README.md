#   Content-addressible file system

Задание: создать git-подобную "файловую систему".
Бэк-ендом будет обычная файловая система.
Все блобы хранятся как файлы, их SHA-256 хэш это их имя.
Есть два типа файлов: блобы и директории.
Блоб - это просто файл, директорий - отсортированный список вида
````
    file.txt: 68e9ea8ccf107dd46bdff3ce133a0764c3c7420bc8405d2c5527f127e84ced60
    dir1/     84786d4331818e6be54f105f48aa7e6d7c13e0aa504c1d7ac26a3b9dc7edb4e1
````
Разделители `:\t` для файлов и `/\t` для директориев, перевод строки `\n`, т.е.
формат без вольностей. Имя файла - UTF8 от пробела и выше, исключая разделители
`UTF8 - [ \t:\\]`.

Требуется реализовать 5 команд: put, get, ls, rm, mkdir.
Аргументы каждой команды:
````
    ./put-ivanov subdir/README 84786d4331818e6be54f105f48aa7e6d7c13e0aa504c1d7ac26a3b9dc7edb4e1 < README
    ./get-petrov dir/subdir/README 834af9243b300ed2fb9235e74e158c0bcdfd34ef9590ba93b56c70e9f970040f
    ./ls-sidorov dir/ 834af9243b300ed2fb9235e74e158c0bcdfd34ef9590ba93b56c70e9f970040f
    ./rm-boshirov dir 834af9243b300ed2fb9235e74e158c0bcdfd34ef9590ba93b56c70e9f970040f
    ./mkdir-smith dir/newsub 834af9243b300ed2fb9235e74e158c0bcdfd34ef9590ba93b56c70e9f970040f
````

Итого, 2 аргумента: путь и корневой хэш.
Каждая пишущая команда выводит хэш новой версии файловой системы,
а читающая выводит данные (get содержимое файла, ls рекурсивно дерево файлов).

Разрешённые языки:
  - C/C++
  - go
  - bash
  - node.js
  - Zig
  - Rust
  - OCaml

(Python запрещён, .NET тоже. Ха-ха.)