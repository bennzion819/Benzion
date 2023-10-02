# Benzion
b16
@echo off
rem COPYIT.BAT копирует все файлы во всех подкаталогах
rem исходного диска или каталога (%1) на другой диск

rem или в другой каталог (%2)

?? xcopy %1 %2 /s /e

??if errorlevel 4 goto lowmemory
?if errorlevel 2 goto abort
?if errorlevel 0 goto exit

??:lowmemory ?
echo Недостаточно памяти для копирования файлов,
задан недопустимый ?echo диск или ошибка в синтаксисе командной строки.
?goto exit
??
:abort ?
echo Нажата комбинация CTRL+C для остановки копирования.
?goto exit ?
