Linux System Administrator/DevOps Interview Questions
====================================================

A collection of linux sysadmin/devops interview questions. Feel free to contribute via pull requests, issues or email messages.


## <a name='toc'>Table of Contents</a>

  1. [Contributors](#contributors)
  1. [General Questions](#general)
  1. [Simple Linux Questions](#simple)
  1. [Medium Linux Questions](#medium)
  1. [Hard Linux Questions](#hard)
  1. [Expert Linux Questions](#expert)
  1. [Networking Questions](#network)
  1. [MySQL Questions](#mysql)
  1. [DevOps Questions](#devop)
  1. [Fun Questions](#fun)
  1. [Demo Time](#demo)
  1. [Other Great References](#references)


#### [[⬆]](#toc) <a name='contributors'>Contributors:</a>

* [moregeek](https://github.com/moregeek)
* [typhonius](https://github.com/typhonius)
* [schumar](https://github.com/schumar)
* [negesti](https://github.com/negesti)
* peter
* [andreashappe](https://github.com/andreashappe)
* [quatrix](https://github.com/quatrix)
* [biyanisuraj](https://github.com/biyanisuraj)
* [pedroguima](https://github.com/pedroguima)
* Ben
* [bharatnc](https://github.com/bharatnc)


#### [[⬆]](#toc) <a name='general'>General Questions:</a>

* What did you learn yesterday/this week?
* Talk about your preferred development/administration environment. (OS, Editor, Browsers, Tools etc.)
Ubuntu/Debian, nano/sublime/brackets, mc, docker, Rancher, Chrome, bash/zsh

* Tell me about the last major Linux project you finished.
* Tell me about the biggest mistake you've made in [some recent time period] and how you would do it differently today. What did you learn from this experience?
  испортил файловую систему сервера. научило бэкапить данные _непосредственно перед_ каждым серьезным действием.

* Why we must choose you?
* What function does DNS play on a network?
распределенная система именования доменных имен

* What is HTTP?
протокол уровня приложений для доставки «гипертекстового» контента 

* What is an HTTP proxy and how does it work?
промежуточный сервер между конечной точкой доставки HTTP-контента и веб-сервером, применяется для прозрачного выполнения косвенных запросов (для кэширования, либо для передачи запросов из "серых" сетей)

* Describe briefly how HTTPS works.
расширение протокола http для шифрования трафика(при помощи сертификатов SSL или TLS, выданных доверенными регистраторами)

* What is SMTP? Give the basic scenario of how a mail message is delivered via SMTP.
Простой протокол передачи почтовых сообщений. Текстовый "HELO EHLO" со всеми вытекающими.

* What is RAID? What is RAID0, RAID1, RAID5, RAID10?
0 - страйп
1 - миррор
5 - по сути страйп с сохранением бита четности на дополнительном диске (на двух распределяем данные, на третьм храним бит, позволяющий восстановить данные при утере одного из дисков)
10 - страйп + миррор (4 диска, лишняя избыточность)

* What is a level 0 backup? What is an incremental backup?
Полный бэкап. Инкрементальный бэкап хранит разницу между текущим уровнем и предыдущим вплоть до нулевого

* Describe the general file system hierarchy of a Linux system.
ман Filesystem Hierarchy Standard


#### [[⬆]](#toc) <a name='simple'>Simple Linux Questions:</a>

* What is the name and the UID of the administrator user?
root/0

* How to list all files, including hidden ones, in a directory?
ls -a
* What is the Unix/Linux command to remove a directory and its contents?
rm -R *

* Which command will show you free/used memory? Does free memory exist on Linux?
free

* How to search for the string "my konfi is the best" in files of a directory recursively
grep -rn word /directory

* How to connect to a remote server or what is SSH?
ssh user@server

* How to get all environment variables and how can you use them?
env

* I get "command not found" when I run ```ifconfig -a```. What can be wrong?
use ip, Luke!

* What happens if I type TAB-TAB?
список команд

* What command will show the available disk space on the Unix/Linux system?
df -h

* What commands do you know that can be used to check DNS records?
nslookup, host, dig

* What Unix/Linux commands will alter a files ownership, files permissions?
ls -l

* What does ```chmod +x FILENAME``` do?
добавляет исполняемый бит к FILENAME

* What does the permission 0750 on a file mean?
Исполняемый/доступный для записи для владельца, исполняемый/читаемый для группы, недоступный для всех

* What does the permission 0750 on a directory mean?
доступная для записи/читаемая для владельца, читаемая группой, недоступная всем

* How to add a new system user without login permissions?
шелл /bin/false или /bin/sbin/nologin

* How to add/remove a group from a user?
adduser igor sudo

* What is a bash alias?
короткий псевдоним для команды (команд)

* How do you set the mail address of the root/a user?
man ~/.forward или /etc/aliases

* What does CTRL-c do?
прерывает выполнение и выбрасывает в шелл (традиционно в юниксах)

* What is in /etc/services?
список сетевых сервисов

* How to redirect STDOUT and STDERR in bash? (> /dev/null 2>&1)
yourcommand &>filename

* What is the difference between UNIX and Linux.
- коммерческая система, которая принадлежала AT&T (а теперь ее наследникам)
- ядро, разрабатываемое сообществом. по некоторым признакам не является полностью удовлетворяющей стандартам UNIX

* What is the difference between Telnet and SSH?
нешифруется/шифруется

* Explain the three load averages and what do they indicate. What command can be used to view the load averages?
1, 5, 15 минут. 
top, w, uptime, cat /proc/loadawr

* Can you name a lower-case letter that is not a valid option for GNU ```ls```?
-e :)

* What is a Linux kernel module?
бинарный (динамически загружаемый) объект уровня ring 0, который позволяет добавить в ядро необходимый функционал

* Walk me through the steps in booting into single user mode to troubleshoot a problem.
смотрим в grub 
init=/bin/sh

* Walk me through the steps you'd take to troubleshoot a 404 error on a web application you administer.
недоступен адрес страницы

#### [[⬆]](#toc) <a name='medium'>Medium Linux Questions:</a>

* What do the following commands do and how would you use them?
 * ```tee```
 пишем в файл
 
 * ```awk```
 процессор обработки текстовых файлов (чаще всего в табличном виде)
 
 * ```tr```
 посимвольная обработка строки (например, замена знака)
 
 * ```cut```
 конкатенатор файлов
 
 * ```tac```
 конкатенатор в реверсивном режиме
 
 * ```curl```
 программа для формирования http-запросов
 
 * ```wget```
 получение "файлов" по http-протоколу
 
 * ```watch```
 перезапускатель команды через определенный промежуток времени
 
 * ```head```
 смотрим определенное количество строк в начале файла
 
 * ```tail```
 в конце файла
 
* What does an ```&``` after a command do?
отправляем задачу в фон

* What does ```& disown``` after a command do?
отправляем задачу в фон и разрываем связь с "родителем"

* What is a packet filter and how does it work?
фильтр соединений (iptables, ufw)

* What is Virtual Memory?
адресация памяти без привязки к физическому устройству памяти

* What is swap and what is it used for?
файл подкачки страничной памяти

* What is an A record, an NS record, a PTR record, a CNAME record, an MX record?
  ресурсные записи dns:
  A -  адрес
  NS - неймсервер
  PTR - обратная зона (канон)
  CNAME - алиас адреса
  MX - почтовый маршрутизатор

* Are there any other RRs and what are they used for?
  их много, например SRV, SOA или TXT

* What is a Split-Horizon DNS?
разделение DNS по доступу

* What is the sticky bit?
дополнительный бит доступа, для того, чтобы только владелец каталога мог удалить файл (или запустить файл от имени владельца файла)

* What does the immutable bit do to a file?
атрибут неизменяемости

* What is the difference between hardlinks and symlinks? What happens when you remove the source to a symlink/hardlink?
хардлинк линкует иноду с дополнительным именем, симлинк создает "ярлык". хардлинкт _только_ на одной файловой, симлинк - где угодно. харлинк равнозначени имени (удаление "исходного" файла не портит хардлинк), симлинк не отвечает за это

* What is an inode and what fields are stored in an inode?
адресный идентификатор (фактически ссылка на сектор/блок, если вульгарно интерпретировать)

* How to force/trigger a file system check on next reboot?
``` # touch /forcefsck```


* What is SNMP and what is it used for?
упрощеная реализация ntp, пинги :)

* What is a runlevel and how to get the current runlevel?
who -r

* What is SSH port forwarding?
туннелирование порта через ssh

* What is the difference between local and remote port forwarding?
Локальная переадресация делает удаленный порт локально доступным.
Удаленная переадресация делает локальный порт удаленно доступным.

* What are the steps to add a user to a system without using useradd/adduser?
править напрямую файл /etc/passwd

* What is MAJOR and MINOR numbers of special files?
Драйвер, физическое устройство

* Describe the mknod command and when you'd use it.
создание специального файла блочного устройства

* Describe a scenario when you get a "filesystem is full" error, but 'df' shows there is free space.
закончились иноды

* Describe a scenario when deleting a file, but 'df' not showing the space being freed.
есть хардлинк, инода открыта

* Describe how 'ps' works.
список процессов и их PID

* What happens to a child process that dies and has no parent process to wait for it and what’s bad about this?
зомби,kill -9 PID

* Explain briefly each one of the process states.
R - работает
D - спит, непрерываемо (ждет ответа от IO)
S - спит прерываемо (ожидает действий)
Z - зомби
T - умирает

* How to know which process listens on a specific port?
netstat
fuser
lsof /proc/$pid/

* What is a zombie process and what could be the cause of it?
процесс закончил выполнение, но не передал родительскому процессу сигнала о том, что он умер. Процесс при завершении освобождает все свои ресурсы (за исключением PID — идентификатора процесса) и становится «зомби» — пустой записью в таблице процессов, хранящей код завершения для родительского процесса. 

* You run a bash script and you want to see its output on your terminal and save it to a file at the same time. How could you do it?

"программа" 2>&1 | tee my.log

* Explain what echo "1" > /proc/sys/net/ipv4/ip_forward does.
передаем единичку в файл /proc/sys/net/ipv4/ip_forward 
по факту включаем маскарад сети

* Describe briefly the steps you need to take in order to create and install a valid certificate for the site https://foo.example.com.
man let's encrypt

* Can you have several HTTPS virtual hosts sharing the same IP?
да

* What is a wildcard certificate?
сертификаты, применямые по маске * ко всем дочерним доменам сертификата

* Which Linux file types do you know?
Обычные файлы
Файлы директорий
Специальные файлы:
Блочные устройства
Символьные устройства
Именованые каналы
Символические ссылки
Сокет-файлы

* What is the difference between a process and a thread? And parent and child processes after a fork system call?
Поток является частью процесса. У одного процесса может быть несколько потоков. Процесс имеет PID, нить — нет.

* What is the difference between exec and fork?
системный вызов exec порождает новый процесс, порождается от исполняемого файла. Системный вызов fork порожает практически идентичный процесс для уже запущенного, от которого порождается потомок.

* What is "nohup" used for?
UNIX-утилита, запускающая указанную команду с игнорированием сигналов потери связи (SIGHUP). Таким образом, команда будет продолжать выполняться в фоновом режиме и после того, как пользователь выйдет из систем (разрывает связь со стандартными потоками ввода-вывода.

* What is the difference between these two commands?
 * ```myvar=hello```
 объявляет переменную только для процесса, запускаемого вместе с объявляемой переменной окружения
 
 * ```export myvar=hello```
 применяется для всего сеанса 
 
* How many NTP servers would you configure in your local ntp.conf?
4

* What does the column 'reach' mean in ```ntpq -p``` output?
состояние восьми последних попыток запроса времени у сервера в восьмеричном представлении (в случае успешной попытки устанавливается соответствующий бит);


* You need to upgrade kernel at 100-1000 servers, how you would do this
ansible puppets or other

* How can you get Host, Channel, ID, LUN of SCSI disk?
cat /proc/scsi/scsi

* How can you limit process memory usage?
cat /sys/fs/cgroup/memory/memory.limit_in_bytes

* What is bash quick substitution/caret replace(^x^y)?
заменит x на y

* Do you know of any alternative shells? If so, have you used any?
sh, zsh, csh, fish, ash, ksh

* What is a tarpipe (or, how would you go about copying everything, including hardlinks and special files, from one server to another)?
закатать в tar (tar сохраняет только одну копию файла с хардлинками)

* How can you tell if the httpd package was already installed?
apt-cache policy apache2


* How can you list the contents of a package?
dpkg -L

* How can you determine which package is better: openssh-server-5.3p1-118.1.el6_8.x86_64 or openssh-server-6.6p1-1.el6.x86_64 ?
второй лучше (версия новее)

* Can you explain to me the difference between block based, and object based storage?
сущность хранения блочного устройства — инода (один файл — много инод), в OBS — файл с метаданными (может быть поверх блочного устройства.


#### [[⬆]](#toc) <a name='hard'>Hard Linux Questions:</a>

* What is a tunnel and how you can bypass a http proxy?


* What is the difference between IDS and IPS?
IDS (система обнаружения вторжений) и IPS (система предотвращения вторжений) 

* What shortcuts do you use on a regular basis?
Ctrl +R : обратный поиск
W : удаление слова перед курсором
U : удалить команду
C : прерывание последней команды 
W : прибить сессию терминала

Alt + F(1-6) : перейти в tty

* What is the Linux Standard Base?
стандарт совместимости дистрибутивов линуск

* What is an atomic operation?
неделимая на составляющие операция (например cp namefile namefile2)

* Your freshly configured http server is not running after a restart, what can you do?
смотрю в логи, смотрю, не висит ли кто-то уже на 80-м порту

* What kind of keys are in ~/.ssh/authorized_keys and what it is this file used for?
файлы публичных ssh-ключей пользователей, которые могут подключаться к серверу. имея приватный ключ пользователя к серверу можно подключаться без пароля

* I've added my public ssh key into authorized_keys but I'm still getting a password prompt, what can be wrong?
приватный ключ (на клиентской стороне) может иметь пароль доступа

* Did you ever create RPM's, DEB's or solaris pkg's?
да, с помощью утилиты alien

* What does ```:(){ :|:& };:``` do on your system?


* How do you catch a Linux signal on a script?
* Can you catch a SIGKILL?
* What's happening when the Linux kernel is starting the OOM killer and how does it choose which process to kill first?
* Describe the linux boot process with as much detail as possible, starting from when the system is powered on and ending when you get a prompt.
* What's a chroot jail?
* When trying to umount a directory it says it's busy, how to find out which PID holds the directory?
* What's LD_PRELOAD and when it's used?
* You ran a binary and nothing happened. How would you debug this?
* What are cgroups? Can you specify a scenario where you could use them?
* How can you remove/delete a file with file-name consisting of only non-printable/non-type-able characters?
* How can you increase or decrease the priority of a process in Linux?
* What are run-levels in Linux?


#### [[⬆]](#toc) <a name='expert'>Expert Linux Questions:</a>

* A running process gets ```EAGAIN: Resource temporarily unavailable``` on reading a socket. How can you close this bad socket/file descriptor without killing the process?


#### [[⬆]](#toc) <a name='network'>Networking Questions:</a>

* What is localhost and why would ```ping localhost``` fail?
* What is the similarity between "ping" & "traceroute" ? How is traceroute able to find the hops.
* What is the command used to show all open ports and/or socket connections on a machine?
* Is 300.168.0.123 a valid IPv4 address?
* Which IP ranges/subnets are "private" or "non-routable" (RFC 1918)?
* What is a VLAN?
* What is ARP and what is it used for?
* What is the difference between TCP and UDP?
* What is the purpose of a default gateway?
* What is command used to show the routing table on a Linux box?
* A TCP connection on a network can be uniquely defined by 4 things. What are those things?
* When a client running a web browser connects to a web server, what is the source port and what is the destination port of the connection?
* How do you add an IPv6 address to a specific interface?
* You have added an IPv4 and IPv6 address to interface eth0. A ping to the v4 address is working but a ping to the v6 address gives you the response ```sendmsg: operation not permitted```. What could be wrong?
* What is SNAT and when should it be used?
* Explain how could you ssh login into a Linux system that DROPs all new incoming packets using a SSH tunnel.
* How do you stop a DDoS attack?
* How can you see content of an ip packet?
* What is IPoAC (RFC 1149)?



#### [[⬆]](#toc) <a name='mysql'>MySQL questions:</a>

* How do you create a user?
* How do you provide privileges to a user?
* What is the difference between a "left" and a "right" join?
* Explain briefly the differences between InnoDB and MyISAM.
* Describe briefly the steps you need to follow in order to create a simple master/slave cluster.
* Why should you run "mysql_secure_installation" after installing MySQL?
* How do you check which jobs are running?
* How would you take a backup of a MySQL database?

#### [[⬆]](#toc) <a name='devop'>DevOps Questions:</a>

* Can you describe your workflow when you create a script?
* What is GIT?
* What is a dynamically/statically linked file?
* What does "./configure && make && make install" do?
* What is puppet/chef/ansible used for?
* What is Nagios/Zenoss/NewRelic used for?
* What is Jenkins/TeamCity/GoCI used for?
* What is the difference between Containers and VMs?
* How do you create a new postgres user?
* What is a virtual IP address? What is a cluster?
* How do you print all strings of printable characters present in a file?
* How do you find shared library dependencies?
* What is Automake and Autoconf?
* ./configure shows an error that libfoobar is missing on your system, how could you fix this, what could be wrong?
* What are the advantages/disadvantages of script vs compiled program?
* What's the relationship between continuous delivery and DevOps?
* What are the important aspects of a system of continuous integration and deployment?
* How would you enable network file sharing within AWS that would allow EC2 instances in multiple availability zones to share data?

#### [[⬆]](#toc) <a name='fun'>Fun Questions:</a>

* A careless sysadmin executes the following command: ```chmod 444 /bin/chmod ``` - what do you do to fix this?
* I've lost my root password, what can I do?
* I've rebooted a remote server but after 10 minutes I'm still not able to ssh into it, what can be wrong?
* If you were stuck on a desert island with only 5 command-line utilities, which would you choose?
* You come across a random computer and it appears to be a command console for the universe. What is the first thing you type?
* Tell me about a creative way that you've used SSH?
* You have deleted by error a running script, what could you do to restore it?
* What will happen on 19 January 2038?
* How to reboot server when reboot command is not responding?


#### [[⬆]](#toc) <a name='demo'>Demo Time:</a>

* Unpack test.tar.gz without man pages or google.
* Remove all "*.pyc" files from testdir recursively?
* Search for "my konfu is the best" in all *.py files.
* Replace the occurrence of "my konfu is the best" with "I'm a linux jedi master" in all *.txt files.
* Test if port 443 on a machine with IP address X.X.X.X is reachable.
* Get http://myinternal.webserver.local/test.html via telnet.
* How to send an email without a mail client, just on the command line?
* Write a ```get_prim``` method in python/perl/bash/pseudo.
* Find all files which have been accessed within the last 30 days.
* Explain the following command ```(date ; ps -ef | awk '{print $1}' | sort | uniq | wc -l ) >> Activity.log```
* Write a script to list all the differences between two directories.
* In a log file with contents as ```<TIME> : [MESSAGE] : [ERROR_NO] - Human readable text``` display summary/count of specific error numbers that occurred every hour or a specific hour.


#### [[⬆]](#toc) <a name='references'>Other Great References:</a>

Some questions are 'borrowed' from other great references like:

* https://github.com/darcyclarke/Front-end-Developer-Interview-Questions
* https://github.com/kylejohnson/linux-sysadmin-interview-questions/blob/master/test.md
* http://slideshare.net/kavyasri790693/linux-admin-interview-questions
