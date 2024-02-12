Написать скрипт, который будет выводить информацию о пользователях. Скрипт должен работать либо без ключей либо с одним ключом:

-h - вывод справки

-t - вывод логина, UID, GID с сортировкой по UID в порядке возрастания

-x - вывод логина, UID, GID, домашней директории и оболочки

без ключей должны выводиться логин, UID, GID с сортировкой по логину в алфавитном порядке

Пример:
```
root@anestesia:~# ./logins
Debian-exim	107	113
_apt	100	65534
agapochkina	1003	1003
alexkononchuk	1007	1007
anestesia	1000	1000
asashnikov	1004	1004
backup	34	34
bin	2	2
bogdan	1001	1001
daemon	1	1
dmitriy	1002	1002
eblokhina	1009	1009
games	5	60
gnats	41	41
irc	39	39
linux_user	1011	1011
list	38	38
lp	7	7
mail	8	8
man	6	12
messagebus	104	110
news	9	9
nobody	65534	65534

root@anestesia:~# ./logins -h
logins [-htx]
root@anestesia:~#

root@anestesia:~# ./logins -t
root	0	0
daemon	1	1
bin	2	2
sys	3	3
sync	4	65534
games	5	60
man	6	12
lp	7	7
mail	8	8
news	9	9
uucp	10	10
proxy	13	13
www-data	33	33

root@anestesia:~# ./logins -x
Debian-exim	107	113	/usr/sbin/nologin	/var/spool/exim4
_apt	100	65534	/usr/sbin/nologin	/nonexistent
agapochkina	1003	1003	/bin/bash	/home/agapochkina
alexkononchuk	1007	1007	/bin/bash	/home/alexkononchuk
anestesia	1000	1000	/bin/zsh	/home/anestesia
asashnikov	1004	1004	/bin/bash	/home/asashnikov
backup	34	34	/usr/sbin/nologin	/var/backups
bin	2	2	/usr/sbin/nologin	/bin
bogdan	1001	1001	/bin/bash	/home/bogdan
daemon	1	1	/usr/sbin/nologin	/usr/sbin
dmitriy	1002	1002	/bin/bash	/home/dmitriy
```
