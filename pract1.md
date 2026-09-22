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

