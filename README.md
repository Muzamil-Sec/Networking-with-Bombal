<img width="1420" height="298" alt="image" src="https://github.com/user-attachments/assets/4243a82d-090d-40a7-8bce-3e01769dd969" />David Bombal networking course day 01 : )
#Topics coverd in this files are
1: Build your first network with Packet Tracer
2: Configure Ip Addresses with switch & and other devices and server also
3: Web search through the pc1&pc2 to web servers
4: Configure switch with some commands and ARP 


---------------------------------------------------------------------------------- : )

Day02:
1: Creating two networks connecting them with the switech and then to the router 
and the router will be connected to the Internet and we are accessing the servers from the other side of 
the network like cisco server facebook server etc

--------------------------------------------------------------------------------------:  )
Day03: Binary Numbers
Binary numbers are the numbers that only understand by the computer 0 1 form
0=off
1= ON
no current in wire its 0 and if the current flows through the line its 1
Table i used to convert an IP address to Binary is:

2^7 | 2^6 | 2^5 | 2^4 | 2^3 | 2^2 | 2^1 | 2^0 |
128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |

Lets take an ip address then convert it:

192.168.1.100

There are four octets in the IPv4 address each address has 8 bits 8x4=32 bits
IPv4 is 32 bits long : )

192-128=64 , 64-32=16, 16-8=8, 8-4=4, 4-4=0;
128=1
64=1
32=1
16=1
8=1
4=1
That's mean for 192 the binary number is = 11111100

same with the 168, 1 and 100
This is called subneeting : )


------------------------------------------------------------------- :  )


Day 04: Hexadecimal Numbers

Hexadecimal is base 16
That means instead of counting 0–9 only (like decimal), it goes up to 15, but for numbers 10–15 we use letters A–F:
Decimal → Hex
10 → A
11 → B
12 → C
13 → D
14 → E
15 → F

Lets break down this more
convert 192.168.1.100 to binary which is 

192= 11000000
168= 10101000
1= 00000001
100 = 01100100

Step 3: Split into 4 bits

1100 0000

1010 1000

0000 0001

0110 0100


Step 1: Binary → Decimal

Take 4 bits (a nibble) and expand them using the table of powers of 2:

Binary	2³ (8) |	2² (4) |	2¹ (2) |	2⁰ (1) |	Add them → Decimal
1100	  1×8=8  |	1×4=4  |	0×2=0  |	0×1=0  |	8+4 = 12
1010	  1×8=8  |	0×4=0  |	1×2=2  |	0×1=0	 |  8+2 = 10
0110	  0×8=0  |	1×4=4  |	1×2=2  |	0×1=0  |	4+2 = 6
0100	  0×8=0  |	1×4=4  |	0×2=0  |	0×1=0  |	4 = 4

Hex uses 0–9 and A–F:

10 = A

11 = B

12 = C

13 = D

14 = E

15 = F


Step 5: Write in Hexadecimal

192 = C0

168 = A8

1 = 01

100 = 64

👉 IP in Hex = C0.A8.01.64

Done we converted it to Hexadecimal : )




------------------------------------------------: )

Day05: IP addresses IPV4 and the classes

IPv4 Address Classes

IPv4 addresses are 32 bits (4 octets). To make things easy, they were divided into classes (A, B, C, D, E) based on how many networks and hosts they can support.

Think of it like different sizes of boxes 🧰: small, medium, large, special use.

Class A:
Range: 1.0.0.0 – 126.0.0.0
Default Subnet Mask: 255.0.0.0 (/8)
First Octet (1–126) identifies the Network, rest are Hosts.
Supports: Few networks, but millions of hosts in each.
Example: 10.0.0.1 → Class A


Class B:
Range: 128.0.0.0 – 191.255.0.0
Default Subnet Mask: 255.255.0.0 (/16)
First 2 Octets = Network, last 2 = Hosts.
Supports: Medium number of networks & hosts.
Example: 172.16.5.10 → Class B


Class C:
Range: 192.0.0.0 – 223.255.255.0
Default Subnet Mask: 255.255.255.0 (/24)
First 3 Octets = Network, last = Hosts.
Supports: Many networks, but only 254 hosts per network.
Example: 192.168.1.10 → Class C


Class D (Multicast):
Range: 224.0.0.0 – 239.255.255.255
Not used for normal hosts.
Used for multicasting (sending data to a group).


Class E (Experimental):
Range: 240.0.0.0 – 255.255.255.255
Reserved for research/testing, not for normal use.


CIDR (Classless Inter-Domain Routing)
Now, here’s the trick 👉 The class system was wasteful. For example, if you only need 300 hosts, Class B gives you 65,534 hosts 😅 (too much wasted space).
So, CIDR was introduced.
What is CIDR?
CIDR = Classless Inter-Domain Routing
Instead of fixed Class A, B, C masks, we use a slash (/) notation to specify how many bits are network.
Example:
192.168.1.0/24 → First 24 bits = Network, last 8 = Hosts.
10.0.0.0/8 → First 8 bits = Network, rest 24 = Hosts.
172.16.0.0/20 → First 20 bits = Network, rest 12 = Hosts.
👉 This allows flexible subnetting, no waste.
🎯 Super Easy Analogy
Classes = Fixed box sizes (small, medium, large).
CIDR = Custom box size (you cut it exactly how much you need).
⚡ Example:
Old (Classful): 192.168.1.0 always = /24
New (CIDR): 192.168.1.0/26 → means only 64 IPs (not 256).


<img width="1337" height="870" alt="image" src="https://github.com/user-attachments/assets/51a2032f-a257-4750-b3e9-7f5fa2d84551" />



Loopback Address:
The loopback address is 127.0.0.1 (or the whole range 127.0.0.0 – 127.255.255.255).
It’s used to test your own computer’s networking.
Example: If you type ping 127.0.0.1, your computer pings itself.
💡 It’s like talking to yourself to check if your mouth and ears are working.


Local Broadcast Address:
The local broadcast address is 255.255.255.255.
It sends a message to all devices in the local network.
Example: When a device doesn’t know the IP of the DHCP server, it broadcasts a request to everyone using this address.
💡 It’s like shouting in a room — everyone in the same room hears you.



Network Mask (Subnet Mask):
A network mask (like 255.255.255.0) is used to separate the Network part and the Host part of an IP address.
Example:
IP: 192.168.1.10
Mask: 255.255.255.0
Network = 192.168.1.0
Host range = .1 to .254
💡 The mask decides which part of the address tells “which network” and which part tells “which device.”



