# Информация представлена для обучения и исследования работы сети.

# SYN-flood-DDOS

TCP/IP 3х-стороннее рукопожатие выполняется для установления соединения между клиентом и сервером. 

Процесс:
 
	1. Client --SYN Packet--> Server
	2. Server --SYN/ACK Packet --> Client
	3. Client --ACK Packet --> Server

Вышеуказанные 3 шага выполняются для установления соединения между источником и пунктом назначения.

Атаки SYN Flood DOS включают отправку слишком большого количества SYN-пакетов (с плохим или случайным источником ip) на целевой сервер. Эти запросы SYN попадают в очередь в буфере сервера и используют ресурсы и память сервера. Это может привести к сбою или зависанию серверной машины. 
После отправки SYN-пакета это полуоткрытое соединение, и он берет ресурсы на серверной машине. Поэтому, если злоумышленник отправляет syn-пакеты быстрее, чем память освобождается на сервере, тогда это будет ситуация с переполнением. Поскольку ресурсы сервера используются, реакция на законных пользователей замедляется, что приводит к отказу в обслуживании.

Для получения дополнительной информации о TCP Syn DOS атаки прочитайте RFC 4987.

Для установки:
	- git clone https://github.com/Vecnik88/SYN-flood-DDOS
	- cd SYN-flood-DDOS
	- make

Пример запуска программы:
	- sudo ./syn-flood -a ip.ru -p 80 -t 128

	Unknown option: -h
	usage:
		[-a | --addr]   ip address destination attack machine
		[-h | --help]   help
		[-p | --port]   port destination attack machine
		[-t | --thread] number of threads
