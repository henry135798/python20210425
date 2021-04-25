1.hello world
===== Welcome to CTF =====
You successfully reach this problem
Congratulation!!!
Wait for a few second, let me get you the flag

Here you go : CTF{Hel10WorLD123}

2.3rd
from pwn import *

ip = "120.114.62.214"
port = 2400

r = remote(ip,port)

r.recvuntil("Now You Turn")
r.recvuntil(" : ")
res = r.recvline()[:-1]
res = list(map(int, res.split()))
res.sort()
r.recvuntil("answer :")
r.sendline(str(res[-3]))

r.interactive()

[+] Opening connection to 120.114.62.214 on port 2400: Done
[*] Switching to interactive mode
 CTF{yoUaReInth33RdpL4c3}
[*] Got EOF while reading in interactive
$ 
$ 
[*] Closed connection to 120.114.62.214 port 2400
[*] Got EOF while sending in interactive

3.count
from pwn import *

ip = "120.114.62.214"
port = 2403

r = remote(ip,port)

for i in range(1,101):
	r.recvuntil("wave")
	r.recvuntil("?")
	r.sendline(str(i))
	i=i+1

r.interactive()

[+] Opening connection to 120.114.62.214 on port 2403: Done
[*] Switching to interactive mode

CTF{gOOD4tMatHYOUarE}
[*] Got EOF while reading in interactive
$ 
$ 
[*] Closed connection to 120.114.62.214 port 2403
[*] Got EOF while sending in interactive
