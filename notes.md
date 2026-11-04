# День 1. Файлы и папки

- > перезаписывает, >> дописывает
- mv = перемещение + переименовывание
- rm -rf опасно, корзины нет
# День 2. grep, ругулярки, find

- grep "error" file.log           # строки с error
grep -i "error" file.log        # без учёта регистра
grep -c "error" file.log        # сколько их
grep -v "INFO" file.log         # всё, КРОМЕ INFO
grep -r "password" .            # по всем файлам в папке
grep -E "error|fail" file.log   # error ИЛИ fail
grep -l "error" *.log           # только имена файлов с совпадением

# Кто сколько запросов сделал
awk '{print $1}' access_test.log | sort | uniq -c | sort -rn

# Сколько сканеров (sqlmap + nikto)
grep -icE "sqlmap|nikto" access_test.log

# Кто долбит логин (много 401)
grep '" 401 ' access_test.log | awk '{print $1}' | sort | uniq -c | sort -rn
