1) Написать bash скрипт, который будет выводить инофрмацию о системе (формат любой, главное читабельный)
  - версия ОС
  - количество ядер (cpu)
  - объем памяти
2) Получить список установленного ПО командой ```apt list --installed``` и найти в списке fdisk (grep); затем вывести только версию установленного пакета
3) Создать файл с таким содержимым
```
$ORIGIN .
$TTL 80 ; 1 minute 20 seconds
nyc                     IN SOA  ns.nyc. support.nyc. (
                                2012063696 ; serial
                                10800      ; refresh (3 hours)
                                900        ; retry (15 minutes)
                                1814400    ; expire (3 weeks)
                                10800      ; minimum (3 hours)
                                )
                        NS      ns.nyc.
$ORIGIN nyc.
continius-local-staging A       10.7.6.109
continius-studyproxy    A       10.7.6.109
controller              A       10.7.10.12
                        A       10.7.10.13
                        A       10.7.10.14
hiera                   A       10.7.10.12
                        A       10.7.10.13
                        A       10.7.10.14
hiera2                  A       10.7.10.12
                        A       10.7.10.13
                        A       10.7.10.14
hub-nomad               A       10.7.10.227
hub-nomad-tvf           A       10.7.10.227
hub-nomad-tvf-psm       A       10.7.10.227
hub0                    A       10.7.10.7
hub0-fr                 A       10.7.10.131

```
И вывести все имена в A-записях
4) Получить из вывода команды ```uptime``` значения load_average
5) Из файла /proc/meminfo выести всю информацию о HugePages (там скорее всего будет всё по нулям, это норма)
6) Вывести id (3 поле в строке) пользователя www-data офильтровав содержимое файла /etc/passwd
7) Выпонить команду
```
ip -o a
```
получить ip машины (нужно получить только ip), то есть вывод команды такой
```
root@ruvds-wil5w:~# ip -o a
1: lo    inet 127.0.0.1/8 scope host lo\       valid_lft forever preferred_lft forever
1: lo    inet6 ::1/128 scope host \       valid_lft forever preferred_lft forever
2: eth0    inet 195.133.199.48/24 scope global eth0\       valid_lft forever preferred_lft forever
2: eth0    inet6 fe80::215:5dff:fe0c:33e5/64 scope link \       valid_lft forever preferred_lft forever
3: docker0    inet 172.17.0.1/16 brd 172.17.255.255 scope global docker0\       valid_lft forever preferred_lft forever
3: docker0    inet6 fe80::42:ffff:fe83:f708/64 scope link \       valid_lft forever preferred_lft forever
49: br-7f6b2a795952    inet 172.21.0.1/16 brd 172.21.255.255 scope global br-7f6b2a795952\       valid_lft forever preferred_lft forever
49: br-7f6b2a795952    inet6 fe80::42:6eff:fed1:17a/64 scope link \       valid_lft forever preferred_lft forever
50: br-bcb69017f222    inet 172.22.0.1/16 brd 172.22.255.255 scope global br-bcb69017f222\       valid_lft forever preferred_lft forever
50: br-bcb69017f222    inet6 fe80::42:92ff:fefa:4b8c/64 scope link \       valid_lft forever preferred_lft forever
55: br-e66bd26eec4f    inet 172.23.0.1/16 brd 172.23.255.255 scope global br-e66bd26eec4f\       valid_lft forever preferred_lft forever
55: br-e66bd26eec4f    inet6 fe80::42:b3ff:fe9f:3ac1/64 scope link \       valid_lft forever preferred_lft forever
56: br-6a21e8afa4e8    inet 172.24.0.1/16 brd 172.24.255.255 scope global br-6a21e8afa4e8\       valid_lft forever preferred_lft forever
56: br-6a21e8afa4e8    inet6 fe80::42:afff:feb3:bca8/64 scope link \       valid_lft forever preferred_lft forever
61: br-1a68cb1ae613    inet 172.25.0.1/16 brd 172.25.255.255 scope global br-1a68cb1ae613\       valid_lft forever preferred_lft forever
61: br-1a68cb1ae613    inet6 fe80::42:a5ff:fe56:fd1d/64 scope link \       valid_lft forever preferred_lft forever
62: br-70eaefbd8c8a    inet 172.26.0.1/16 brd 172.26.255.255 scope global br-70eaefbd8c8a\       valid_lft forever preferred_lft forever
62: br-70eaefbd8c8a    inet6 fe80::42:b6ff:fe61:dafc/64 scope link \       valid_lft forever preferred_lft forever
67: br-e578a222aff7    inet 172.27.0.1/16 brd 172.27.255.255 scope global br-e578a222aff7\       valid_lft forever preferred_lft forever
67: br-e578a222aff7    inet6 fe80::42:8dff:fe9c:4b7d/64 scope link \       valid_lft forever preferred_lft forever
68: br-c2aad6b2db24    inet 172.28.0.1/16 brd 172.28.255.255 scope global br-c2aad6b2db24\       valid_lft forever preferred_lft forever
68: br-c2aad6b2db24    inet6 fe80::42:5cff:fef1:3077/64 scope link \       valid_lft forever preferred_lft forever
75: br-8d6fa7670f10    inet 172.29.0.1/16 brd 172.29.255.255 scope global br-8d6fa7670f10\       valid_lft forever preferred_lft forever
75: br-8d6fa7670f10    inet6 fe80::42:33ff:fe9b:322c/64 scope link \       valid_lft forever preferred_lft forever
90: br-728dc5cb31e8    inet 192.168.32.1/20 brd 192.168.47.255 scope global br-728dc5cb31e8\       valid_lft forever preferred_lft forever
90: br-728dc5cb31e8    inet6 fe80::42:1fff:feda:3223/64 scope link \       valid_lft forever preferred_lft forever
92: veth0ed8d99    inet6 fe80::b492:73ff:fec2:7b5b/64 scope link \       valid_lft forever preferred_lft forever
root@ruvds-wil5w:~#
```
из него надо выкусить ```195.133.199.48```
