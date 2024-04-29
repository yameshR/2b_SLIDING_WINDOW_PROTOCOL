# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## Name:N.NAVYA SREE
## REG NO:212223040138
## AIM
To write a python program to perform sliding window protocol
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program

# PROGRAM
## CLIENT:
import socket     
s=socket.socket()    
s.bind(('localhost',8000))   
s.listen(5)   
c,addr=s.accept()    
size=int(input("Enter number of frames to send : "))    
l=list(range(size))    
s=int(input("Enter Window Size : "))    
st=0   
i=0    
while True:    
 while(i<len(l)):   
 st+=s    
 c.send(str(l[i:st]).encode())    
 ack=c.recv(1024).decode()    
 if ack:    
 print(ack)   
 i+=s    
 
# SERVER:
import socket    
s=socket.socket()   
s.connect(('localhost',8000))   
while True:    
 print(s.recv(1024).decode())    
 s.send("acknowledgement recived from the server".encode())   
 
# OUTPUT
## CLIENT:
![Screenshot 2024-04-09 155001](https://github.com/23004513/ChatStudy/assets/138973069/68e67df6-3f82-449c-8159-c2f81e6b304f)
## SERVER:
![Screenshot 2024-04-09 155009](https://github.com/23004513/ChatStudy/assets/138973069/82d9e11a-fb40-49c9-a9ea-44f7aa5d9ed0)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
