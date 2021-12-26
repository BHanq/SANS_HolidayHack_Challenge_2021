# Goal 
Use classic tools with ipv6

Cheatsheet : https://gist.github.com/chriselgee/c1c69756e527f649d0a95b6f20337c2f


# Solution

## Our ip

- ifconfig : To display interface, we know that it is named eth0 

## Discovering other machine

ARP isn't an IPv6 protocol 

Then we need to use Neighbor Discovery protocol : https://en.wikipedia.org/wiki/Neighbor_Discovery_Protocol
Using : 
    ping6 ff02::1 -c2
    ping6 ff02::2 -c2 Then see what's in your ARP cache NDISC cache list:
    ip neigh

We got 1 ip machines (finishing by a002)

## Machine Enumeration
 nmap -6 <ipv6>:a002%eth0
 Nmap the machine and we got : port 80 and 9000 opened
 
## Service test
Curl service to see what it respond

curl http://[<ipv6>:a002] --interface eth0 (which is port 80 by default)
Say that we must check other tcp port

curl http://[<ipv6>:a002]:9000 --interface eth0
Gave the CandyStriper activation phrase
 
PieceOnEarth


See curl.png 
