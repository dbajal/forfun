#### Как проверить, что на таком-то хосте открыт такой-то порт?

```python
import socket
sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM) 
result = sock.connect_ex(('127.0.0.1',80))
if result == 0:
    print "Port is open" 
else: 
    print "Port is not open"
```

`SOCK_STREAM` - Socket type TCP connections

`SOCK_DGRAM` - Socket type UDP connections

Сканер портов на питон: http://www.pythonforbeginners.com/code-snippets-source-code/port-scanner-in-python

#### Что такое telnet?

> TELNET (англ.  TErminaL NETwork) — сетевой протокол для реализации текстового интерфейса по сети (в современной форме — при помощи транспорта TCP). Название «telnet» имеют также некоторые утилиты, реализующие клиентскую часть протокола. Современный стандарт протокола описан в RFC 854. Выполняет функции протокола прикладного уровня модели OSI.

#### Как выглядит http запрос?

```
GET /index.html HTTP/1.1
HOST: domain.tld
Accept: application/json

<body here>
```

*GET URI* — для версии протокола 0.9.
*<METHOD> <URI> HTTP/<version>* — для остальных версий.


#### Какие функции intertools ты используешь?

http://pymotw.com/2/itertools/
https://docs.python.org/2/library/itertools.html
http://jmduke.com/posts/a-gentle-introduction-to-itertools/


#### Что такое GIL и зачем он нужен?

> Global Interpreter Lock (GIL) — это способ синхронизации потоков(тредов), который используется в некоторых интерпретируемых языках программирования, например в Python, Ruby и Java Script.

https://ru.wikipedia.org/wiki/Global_Interpreter_Lock
http://habrahabr.ru/post/84629/
https://wiki.python.org/moin/GlobalInterpreterLock
http://asvetlov.blogspot.ru/2011/07/gil.html


#### Чем отличаются треды от процессов в python?

Треды живут в одном процессе. Шарят ресурсы. Поэтому остановка в одном треде на, например, read с диска, блокирует остальные.
https://ru.wikipedia.org/wiki/%D0%9F%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81_(%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%82%D0%B8%D0%BA%D0%B0)
https://ru.wikipedia.org/wiki/%D0%9F%D0%BE%D1%82%D0%BE%D0%BA_%D0%B2%D1%8B%D0%BF%D0%BE%D0%BB%D0%BD%D0%B5%D0%BD%D0%B8%D1%8F


#### Что такое файлы .pyc и зачем они нужны?

Байткод. Это делает только CPython. Байткод потом исполняется виртуальной машиной.
https://docs.python.org/release/1.5.1p1/tut/node43.html
https://ru.wikipedia.org/wiki/%D0%91%D0%B0%D0%B9%D1%82-%D0%BA%D0%BE%D0%B4


#### В чем отличие интерпретируемых языков от исполнимых?

> **Интерпретируемый язык программирования** — язык программирования, в котором исходный код программы не преобразовывается в машинный код для непосредственного выполнения центральным процессором (как в компилируемых языках), а исполняется с помощью специальной программы-интерпретатора.
В общем случае, любой язык может быть компилируемым и интерпретируемым, так что данное разделение относится к практике применения языка, а не является его свойством. При этом для многих языков существует различие в производительности между компилируемой и интерпретируемой реализацией.
Большое количество языков, включая BASIC, C, Lisp, Pascal и Python, имеют обе реализации. В Java используется JIT-компиляция для генерации машинного кода, хотя изначально он переводится в интерпретируемую форму. Языки Microsoft .NET Framework компилируются в Common Intermediate Language (CIL), который во время выполнения компилируется в нативный код. Большинство реализаций Lisp позволяют смешивать оба вида кода.
**Компилируемый язык программирования** — язык программирования, исходный код которого преобразуется компилятором в машинный код и записывается в файл, с особым заголовком и/или расширением, для последующей идентификации этого файла, как исполняемого, операционной системой (в отличие от интерпретируемых языков программирования, чьи программы выполняются программой-интерпретатором).
Программы на интерпретируемых языках (таких как Бейсик или Python) не транслируются в машинный код; вместо этого они либо исполняются непосредственно интерпретатором языка, либо транслируются в псевдокод (байт-код). Однако интерпретаторы этих языков (которые сами можно рассматривать как процессоры), как правило, представлены в машинном коде.
Это сложный филосовский вопрос. Рассуждения про ‘интерпретируемый ли это язык?’ это уже софистика в современном мире. Например java можно считать интерпретируемой. А питон можно считать компилируемым.


#### Запускается интерпретатор python, что происходит дальше?

Это хз.
https://docs.python.org/2/c-api/init.html


#### Какой порядок поиска методов множественного наследования?

http://habrahabr.ru/post/62203/
От самых близких родителей к самым далёким -) В python2 по-другому, даже скорей не в нём, а в old-style classes, так как они не имеют общего предка.


#### Что хранится в __mro__?

Method resolution order. См. Какой порядок поиска методов множественного наследования?

#### Есть таблица (id, a, b). Сделаю индекс на (a, b), и буду делать запрос по a=x, сработает индекс? А сделаю запрос по b=x? А сделаю запрос по a=b? А сделаю отдельные индексы на a и b?

охуели такое спрашивать? в какой базе? в какой версии этой базы? с какими настройками? как будет выглядеть запрос? не будет ли там хинта для базы? бубубубубуб. угадайте кто это написал.

#### Какой db engine использовал в mysql?
Это очень личное. Вам не стыдно такое спрашивать? Я бы предпочел забыть этот опыт. Как жертва изнасилования.

#### Что такое транзакция?

#### Какие уровни транзакций бывают?
#### Что такое хэш-таблица? Как она работает?

> Хеш-табли́ца — это структура данных, реализующая интерфейс ассоциативного массива, а именно, она позволяет хранить пары (ключ, значение) и выполнять три операции: операцию добавления новой пары, операцию поиска и операцию удаления пары по ключу.

Говоря конкретно о хэш-таблице в Python - вот интересная статья http://habrahabr.ru/post/247843/

#### Какая принципиальная разница между свн и меркуриал/git?

Распределенность. Ветвление. В свн всё хранится в одном репо/бранче. Организуешь версии/изменения сам, например, созданием копий кода в рамках этого репо. В hg/git для этого есть ветвление, фактически, то же, что и в svn ты делал бы руками, но более круто - с сохранением истории изменений, автоматическими мерджами, всё такое. Ну и распределенность - ты просто копируешь удаленный реп себе и работаешь с ним локально - меняешь, коммитишь. Если нужно - шлёшь изменения туда, откуда ветвился. Или ещё куда-то. Они примут или не примут. Кто-то ещё точно так же может начать ветвиться от твоего репо. И везде это - полноценный репозиторий. Со всей историей изменений и всеми ветками, создававшимися в этом репо.

#### Назови паттерны проектирования, все какие знаешь

Эээээ


#### Какие паттерны использовал? Где использовал?

Ээээээ


#### что такое singleton?

Ээээээээ


#### Представь, ты - начальник команды разработчиков, к тебе приходит заказчик, приносит заказ на разработку интернет-магазина, твои дальнейшие действия?

Ээээээ.


#### Таблица: name, comment, datetime , где datetime - время начала сеанса, хочу сходить в кино "как можно быстрее", на любой сеанс, напиши запрос.

Эээээ.


#### принцип работы механизма множественного наследования?

Ээээээ.


#### Какую бд будешь использовать для проекта интернет-магазина, почему?

Ээээээ.



#### Что такое модель OSI? Опиши её. 

Это вот такая картинка
https://upload.wikimedia.org/wikipedia/ru/archive/2/2b/20080403153257!Osi-model.png

#### Расскажи про структуру сетевого пакета

#### Какие бывают рейды? В чём разница? Как бы ты замерял производительность рейдов

В основном бывают зеркала и страйпы, и разные их комбинации. 
И есть куча вариаций с дисками "чётности".   
Разница в различной избыточности хранения данных, скорости ребилда, скорости доступа и записи данных. 
И конечно же они делятся на программные и аппаратные.

Производительность измерял бы сторонней утилитой. Тут есть разница, проверять производительность файловой системы, или блочного устройства. 

#### В чём отличие коммутатора от маршрутизатора

коммутатор - сетевое оборудование, позволяющее связать несколько машин вместе. При этом все пакеты идут широковещательно, попадая на интерфейсы всех устройств этой сети. Принимаются они соответсвтенно только там, где их ждут.
маршрутизатор исходя из заголовков пакета направляет его в нужный порт сразу, и только в него.


#### Что такое транк? Что такое влан? Как работает маршутизатор? Как выглядит таблица маршрутизации? Как работает LSPI?

Транк - это когда между двумя сетевыми устройствами имеется больше одного физического канала связи. 

Влан
http://xgu.ru/wiki/VLAN
LSPI - это транк между свитчом и сервером.


#### Что ты сделал для себя в последнее время? Какой софт поставил по фану и потыкал?  

Ээээээ. Начал делать борду на питоне! Поставил вмвар!
