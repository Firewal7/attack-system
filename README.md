```
┌──(root㉿kali)-[/home/kali]
└─# nmap -sV 192.168.0.10
Starting Nmap 7.93 ( https://nmap.org ) at 2022-12-15 10:40 EST
Nmap scan report for msi (192.168.0.10)
Host is up (0.00015s latency).
Not shown: 998 closed tcp ports (reset)
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 8.4p1 Debian 5+deb11u1 (protocol 2.0)
80/tcp open  http    nginx 1.18.0
MAC Address: 08:00:27:FB:87:FE (Oracle VirtualBox virtual NIC)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 12.99 seconds
```

Какие уязвимости были вами обнаружены (список со ссылками - достаточно 3х уязвимостей)


https://www.exploit-db.com/exploits/17491

https://www.exploit-db.com/exploits/15449

https://www.exploit-db.com/exploits/37721

SYN, FIN, Xmas, UDP

Чем отличаются эти режимы сканирования с точки зрения сетевого трафика?

Трафик отличается флагами, при сканирования TCP портов, SYN сканирование не до конца устанавливает соединение, т.к. флаг FIN отсутсвует в таком трафике. Трафик при UDP сканировании выглядит иначе, в случае закрытого порта, в ответ приходит ICMP ошибка.

Как отвечает сервер?

Не во всех режимах сканирования гарантировано определяется открыт порт или фильтруется, только в случае SYN это можно точно определить. При сканировании UDP определяются только UDP порты.

