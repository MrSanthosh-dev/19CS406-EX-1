## STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL

## EXP : 1

## DATE : 08-03-2023

## AIM :
To write a python program to perform stop and wait protocol

## ALGORITHM :
```python
1.Start the program.
2.Get the frame size from the user
3.To create the frame based on the user request.
4.To send frames to server from the client side.
5.If your frames reach the server it will send ACK signal to client otherwise it will send NACK signal to client.
6.Stop the program
```

## CLIENT PROGRAM :

```python
import socket
s=socket.socket()
s.bind(('localhost',8080))
s.listen(5)
c,addr=s.accept()
while True:
	i=input("ENter a data:")
	c.send(i.encode())
	ack=c.recv(1024).decode()
	if ack:
		print(ack)
		continue
	else:
		c.close()
		break
```

## SERVER PROGRAM :
```python
import socket
s=socket.socket()
s.connect(('localhost',8080))
while True:
	print(s.recv(1024).decode())
	s.send("Recieved".encode())
```

## CLIENT OUTPUT :
![ex 1 cl output](https://github.com/MrSanthosh-dev/19CS406-EX-1/assets/117916573/3d5903d3-5575-4230-a1c4-811ebbafb63f)


## SERVER OUTPUT :
![ex 1 se output](https://github.com/MrSanthosh-dev/19CS406-EX-1/assets/117916573/f4825024-841a-4e91-bb52-86c9b5287ba1)


## RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
