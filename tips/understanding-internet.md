## Understanding technology


### internet
[CS50 : Internet - Understanding Technology](https://youtu.be/n_KghQP86Sw)

- #.#.#.# -> IP address (internet protocol)
- uniqely identify computers on the internet (집주소와 비슷)
- each of those numbers is a value between 0 - 255 (256개 each 2^8 : 8bits / all 32bits)
- IP주소는 DHCP 서버를 통해서 나온다
- DHCP Server (ISP 혹은 집에 router가 가지고 있다) - Dynamic Host Configuration Protocol : network management protocol used on TCP/IP networks whereby a DHCP server dynamically assigns an IP address
- ISP (Internet Service Provider)
- DNS Server (Domain Name System Server) - controlled by ISP
- DNS서버 `www.~.com` 이 IP주소로 바꿔준다
- computer가 서로 communicate 하는 방법은 packet을 통해서.
- TCP/IP : Transmission Control Protocol + IP 
- TCP ensures that packets can get to their intended destination.
- TCP vs UDP : UDP - video conference, face time, live stream (속도가 중요, 놓쳐도 상관없어)
- world standarized certain numbers to represent different services that servers might provide
- Port number : `80` or `443` means HTTP (Hyper Text Transfer Protocol) - it's a language that web servers speak (80: http | 443: https, and ssh-secure shell)
- protocol : set of standards, rules 


---

