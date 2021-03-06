# Fast Programs

## Версия 2.1

Программа для быстрого запуска приложений из добавляемой иконки в tray.

### Добавление программ

В папке с программой есть файл *"Programs.txt"*, в него нужно записать полные пути добавляемых программ или пути на ярлыки к ним, в каждой строчке 1 путь. Пример:
```
E:\Программы\Wireshark\Wireshark.exe
"E:\Программы\aida64.exe.lnk"
"E:\Программы\CPU-Z\cpuz.exe"
```
Не оставляйте строчки с пробелами, программа подумает, что это неправильный путь. Пустые строки можно оставлять.

В случае, если путь будет указан неверно или он не указывает на программу или ярлык, появится окно с ошибкой и данный путь не будет добавлен в список. Если как-то неправиль заполнить файл *"Programs.txt"*, появится окно с ошибкой и программа остановится.


### Запуск

Для работы программы нужны библиотеки:
  1. infi.systray
  2. extract_icon
  3. win32com.client

Для их устаноки можно использовать команды соответственно:
```
pip install infi.systray
pip install extract-icon
pip install pywin32
```

После можно запустить программу, для этого нужно иметь Python 3.8 или выше. Для добавления в автозагрузку, нужно сделать ярлык файла *TrayLink.bat* и кинуть его в папку автозагрузки. В *.bat* специально прописан код, чтобы консоль скрывалась после запуска. При запуске через Python версия *.pyw* используется для запуска без консоли.

## Возможные ошибки работы

Иногда может не подгружаться иконка программы, это никак не исправить.

Программа при первом запуске или добавлении новых программ сохраняет в папке *IconCache* иконки, для быстрого запуска в следующий раз. Для перезагрузки иконок нужно нажать *Clean Cache* и перезапустить программу.
