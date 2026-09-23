# === Задание 1 ===
cd /etc

grep ":" passwd | cut -d: -f1 | sort

# === Задание 2 ===
cat /etc/protocols | sort -k2 -nr | head -5

# === Задание 3 ===
nano banner

## Внутри banner
#!/bin/bash

text="$1"

len=${#text}

line=$(printf '%*s' $((len + 2)) '' | tr ' ' '-')

echo "+$line+"

echo "| $text |"

echo "+$line+"

## После сохранения файла
chmod +x banner

./banner "Hello from RTU MIREA!"

# === Задание 4 ===
grep -oE '[a-zA-Z_][a-zA-Z0-9_]*' hello.c | sort -u

# === Задание 5 ===

nano reg

## Внутри reg

#!/bin/bash

chmod 755 "$1"
cp "$1" /usr/local/bin/

## После сохранения файла

chmod +x reg

./reg banner

# === Задание 6 ===

nano check

## Внутри файла

'''#!/bin/bash

for file in *.c *.j *.py
do
    [ -f "$file" ] || continue

    if head -n 1 "$file" | grep -qE '^//|^#'
    then
        echo "$file: есть комментарий"
    else
        echo "$file: нет комментария"
    fi
done

## После создания

chmod +x check

./check
