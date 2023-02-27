### 1.  Написать скрипт очистки директорий. На вход принимает путь к директории. Если директория существует, то удаляет в ней все файлы с расширениями .bak, .tmp, .backup. Если директории нет, то выводит ошибку.
    cat <<EOF>delbaks.sh
```bash
#!/bin/bash
#
#
if [[ -n "$1" ]];
    then
        if [[ -e $1 ]]; then
            find $1 -type f \( -name '*.bak' -o -name '*.tmp' -o -name '*.backup' \) -delete
        else
            echo "Directory '$1' does not exist!"
        fi
    else
        echo "No directory selected"
fi
```
    bash delbaks.sh <dir>

### 2.  * Создать скрипт ownersort.sh, который в заданной папке копирует файлы в директории, названные по имени владельца каждого файла. Учтите, что файл должен принадлежать соответствующему владельцу.
