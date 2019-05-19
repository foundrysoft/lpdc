# Цифровые технологии  при исследовании и  управлении процессами  изготовления  отливок
Особенности  и возможности созданного ПО планируется опубликовать в журнале "Литейное производство"  в 2019г.  См.   http://foundrymag.ru/

Созданное программное обеспечение (ПО) установлено на  удаленном сервере 37.139.11.127. Возможны следующие варианты использования ПО.

Вариант1. К  компьютеру можно подключиться используя http-протокол и  любой современный браузер (chrome, firefox и др.) Адрес: http://g06u35.nn2000.info 
Используется традиционный веб-интерфейс и в режиме реального времени можно  запускать все или отдельные операции технологичесого процесса литья под регулируемым давлением, которое охватывает литье под низким давлением, литье с противодавлением и литье вакуумным всасыванием. 
Однако на удаленном сервере (он размещен в Нидерландах) невозможно подключить  аналого-цифровые преобразователи термопар ( термопар полуформ, печного пространства, расплавленного металла), пробразователи дискретных входящих сигналов (датчики положения полуформ, датчиков отсутствия  давления (разрежения) в камерах и др.) и исходящих сигналов  на исполнительные механизмы (приводы клапанов и кранов для подачи давлений и сброса давлений  в камеры установки, приводы механизмов перемещения полуформ, установки стержней  и др.).  Поэтому в представленном варианет ПО,  сответствующим переменным присваиваются ожидаемые (близкие к реальным) значения. 
Для реальных процессов в исходных кода  в явном виде указаны и закомментированы переменные которым следует присвоить значения с  аналого-цифровых преобразователей сигналов с термопар и с датчиков дискретных сигналов.

Достоинства работы с браузером: традиционный веб-интерфейс с функциями, которые прописаны в явном виде в виде ссылок, возможность просмотра данных в графическом виде.

Недостатки работы с браузером:   данные  выводятся на экран только после завершения процесса или операции, и невозможно оперативно приостановить или завершить операцию или процесс (необходимо использовать Вариант 2).
 
 
Вариант 2. Можно подключиться к серверу используя ssh-протокол. Для этого на локальном компьютере должна быть установлена программа типа PuTTY, которая обеспечивает прямую связь с удаленным сервером. См. https://www.putty.org/. Для созданного ПО используется кодировка utf-8 (установить в настройках PyTTY) , сервер: 37.139.11.127, логин:g06u35, пароль:user

Достоинства: данные запускаемых процессов отображаются в реальном времени и процессы всегда можно приостановить, продолжить или выключить. Для запуска необходимой функций  необходимо  командой cd ~/cgi-bin перейти в раздел cgi-bin, командой ls посмотреть список доспупных команд и командой типа ./_main.sh (последовательный запуск операций процесса ) произвести запуск необходимого элемента технологичесого процесса или запуск всего технологического цикла.

Недостатки: используется командная строка и соответственно процессы нужно задавать в явном виде, данные в виде графиков и диаграмм  отобразить невозможно. Для просмотра графиков необходимо запускать Вариант 1 и ссылку Диаграммы 

Вариант 3. ПО можно установить на локальный компьютер или на другой удаленный сервер. Предпочтительно использовать unix - подобную операционную систему. Далее на сервере или компьютере необходимо:
- из репозитория соответствующей системы установить: apache2, zip, unzip, bash, gcc, gnuplot, php5, python3, vim, wget
- из домашнего раздела используя поледовательности команд: rm -rf extplorer; mkdir extplorer; chmod 777 extplorer; cd extplorer;wget http://extplorer.net/attachments/download/57/eXtplorer_2.1.7.zip; unzip eXtplorer_2.1.7.zip; chmod 777 ftp_tmp; chmod 777 config/.htusers.php установить в личном разделе текстовый веб-редактор. С использованием запроса типа http://g06u35.nn2000.info/index.php или по ссылке Настройки этот редактор будет работать через веб-интерфейс.
- загрузить сжатый архив https://github.com/vmarshirov/lpdc/blob/master/lpdc.bz2 в домашний раздел, командой tar -xpf
lpdc.bz2 извлечь содержание сжатого архива. И далее можно работать используя Вариант 1 или Вариант 2.

Варианту 3 следует отдавать предпочтение после изучения возможностей Варианта 1 и Варианта 2. В этом случаем к управляющему компьютеру можно подключить  модули с аналого-цифровыми и дискретными преобразователями сигналов. Присваивать их значения соответствующим переменным (они указаны в исходных кодах функций) и далее, с использованием ПО можно можно регистрировать данные,  контролировать процесс  и подбирать оптимальные технологические параметры  процесса получения отливки.

Если у пользователя нет опыта установки и настройки unix-подобных систем, на этапе установки и конфигурирования лучше привлечь соответствуюего специалиста. 
