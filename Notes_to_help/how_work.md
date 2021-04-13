#### Ваш основной рабочий процесс в стенах `Школы 42` будет примерно таким:

- Вы регистрируетесь в проекте и дожидатесь создания вашего репозитория `git`.
- Копируете `URL` адрес репозитория и клонируете его в папку на вашем компьютере.
- Создаете папку для первого упражнения внутри папки репозитория.
- Создаете файл для первого упражнения.
- Выпоняете упражнение.
- Проверяете наличие дополнительных файлов.
- Проверяете файл через `Norminette`.
- Загружаете выполненное вами задние в ваш `git` репозиторий и переходите к следующему упражнению.
- Убедитесь, что вы все отправили(`git push`).
- `Moulinette` должен будет проверить вашу работу.



#### Подробная версия основного рабочего процесса :

- Скачиваете копию репозитория с задниями:
```
	git clone <repo url> <folder to be created>
```

- Переходите в скачанный каталог:
```
	cd <path to cloned folder>
```

- Создаете папку которая будет содержать выполненое задание:
```
	mkdir ex00
```

- Переходите в каталог где будет храниться выполненное задние:
```
	cd ex00
```

- Пишете код:
```
	vim <exercisename>.c
```

- Компилируете и проверяете код на ошибки:
```
	gcc -Werror -Wall -Wextra <exercisename>.c
```

- Проверяете, что в папке с упражнениями нет посторонних файлов:
```
	ls -la
```

- Проверяете форматирование с помощью `Norminette`.
```
	norminette -R CheckForbiddenSourceHeader
```

- Добавляете файлы, которые хотим зарегестрировать и запушить:
```
	git add <exercisename>.c
```

- Регистрируете изменения, помечая их комментарием:
```
	git commit <exercisename>.c -m "message"
```

- Загружаете файл на сервер, в предоставленный вам репозиторий (после первого раза вы сможете использовать просто `git push`):
```
	git push origin master
```

- переходите к следующему заданию...


