
Добро пожаловать в бонусную часть дня. Эта часть не является обязательной для сегодняшних упраженений, но она будет полезна в вашей карьере в роли разработчика и на протяжении самого бассейна тоже. Итак, ранее мы говорили о ст.п.вывода и на самом деле, он не на 100% точный.

Существует два типа вывода: 
* ст. поток вывода 
* и ст. поток ошибок. 

Итак, используем наш любимый пример: "cat file.txt", все прошло прекрасно, содержимое файла отобразилось в ст.п. вывода.

Однако, если мы попробуем выполнить "cat" на файле, который не существует, то нам отобразится сообщение в ст.п. ошибок. Допустим, я выполню "cat file.txt | rev". Содержимое файла отобразилось в обратном порядке, что означает что содержимое файла отобразилось в ст.п. вывода.

Конвейер "|" интерпретировал ст.п. вывода, как ст.п. ввода "rev" и сам "rev" выполнил свою задачу. Однако, если я выполню это на несуществующем файле, то "cat" нам выведет ошибку в ст.п. ошибок, а "rev" не считать из этого ст.п. ошибок, т.к. он может считывать только из ст.п. вывода, который в данный момент является ст.п. ввода, все это значит, что сообщение не отобразится. Это все может быть занимательным, а может и нет.

Вы также можее реверсировать сообщение об ошибке, если захотите. Как? Добавив дополнительные переадресации, если мы хотим перенаправить сообщение ст.п. ошибок, и обработать его так, как если бы он был ст.п. вывода. Чтож, сделаем это. Итак, "2" представляет собой ст.п. вывода ошибок, а "1" - ст.п. вывода.

Мы говорим ему, что все, что есть в ст.п. ошибок, должно обрабатываться, как если бы это был ст.п. вывода. Итак, если мы добавим " | rev", то мы увидим сообщение в реверсе, потому что оно было обработано, как ст.п. вывода. Аналогично, мы можем перенаправить все, что есть в ст.п. ошибок "2" в файл.

Например, если я сделаю это "cat azeaze 2> error", я прошу "2" перенаправить в "error" и сохранив все это в самом "error". Мы можем посмотреть наше предыдущее сообщение об ошибке (error), и еще раз, если мы сделаем это 2-3 раза подряд, то оно будет отображаться только один раз, потому что оно было перезаписано. Также ведь есть двойное перенаправление ">>", которое позволяет вам разместить сообщения об ошибках в конце файла.

Все это может быть вполне практичным, если у вас есть список файлов, которые содержат сообщения об ошибках, но вы хотите сохранить только ту часть, которая работала, или только ту, которая не работала и т.д.... Благодаря этим переадресациям, вы сможете собрать все ошибочные файлы в один файл с сообщениями об ошибках.

И еще кое-что, то что может быть вам полезно. Очень особенный файл. На самом деле это не файл, но да ладно. Он называется "/dev/null". Что это? По сути, все что будет списано в "/dev/null", будет попросту стерто, забыто. Итак, тут ничего не произойдет, файл "/dev/null" на самом деле не существует. Так что ничего в него добавлено не было. Неважно. Так в каких ситуациях его можно применить?

Мы можем применить его, например, для удаления какой-либо части и сохранения только сообщений об ошибках. У нас будет полный бардак, если мы захотим отобраить все сообщения об ошибках. Мы все время будем матать назад, проверять и все такое... Если мы скажем "Все что работает - перенаправить в /dev/null", и вуаля! Выводятся только сообщения об ошибках. Так что еще раз повторюсь, это может быть очень практично для отладки (debug) или проверки того, работают ли ваши скрипты так, как они должны работать. Это очень важно знать на будущее.