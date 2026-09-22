# === Задание 1 ===
cd /etc

grep ":" passwd | cut -d: -f1 | sort

# === Задание 2 ===
cat /etc/protocols | sort -k2 -nr | head -5

# === Задание 3 ===
