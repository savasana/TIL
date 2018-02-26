## frontendmasters : full stack course


---

### DNS

- IP(Internet Protocol) Adress : 127.0.0.1 /
- DNS(Domain Name Server) : Maps IP addresses to domains / internet phonebook
- DNS Provider

**ping**
- `$ ping google.com` is my site conneted?

**look ups**
- use Local cache
- LAN DNS server
- ISP DNS server
- DNS is constantly updating, communicating each others

**Security**
- DNS cache poisoning : 아이피 가로채기, https를 사용하면 안전

**Trace Route**
- `$ traceroute netflix.com` : how am I getting there?

---

### VIM
- [vimgifs](https://vimgifs.com/)
- command mode
- insert mode : i
- last-line mode

`i` - insert
`:q` - quit without asking
`:wq` - save and exit
`:q!` - exit and discards changes
`:wq!` - save and exit 
`u` - undo
`ctrl-r` - redo
`dd` - delete
`/something` - search something 
`n`, `shift-n` - search lists

---

### SSH
- secure socket shell
- username/pasword ,  ssh key
- password : easily breakable
- public key authentification (private key + public key = two way lock)


---

### Server
- Dedicated Server : server machine
- VPS : chunks of dedicated server - virtual private server (cloud)
- Cloud : flexible, scalable, on demand
- AWS, Rackspace, Digital Ocean, ..

---

### Create Server

- Digital Ocean
- add ssh key  `$ cat ~/.ssh/my_key.pub`


### Log into your server

- `$ cd ~/.ssh/`
- `$ ssh -i my_key root@$YOUR_SERVER_IP`

after login
- `top` : what's going on my system?
- `apt-get update` : update software
- `adduser $USERNAME` : create a new user `adduser ohda`
- usermod -aG sudo $USERNAME : super user do
- su ohda : swith user

logging in with ssh
- `$ cd ~/.ssh/my_key.pub | ssh ohda@SERVER_IP "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"`

diabled root access (at server)
- `sudo vi / etc/ssh/sshd_config`
- PermitRootLogin no
- `sudo service sshd restart` : restart server

---

### Sertting up the server

- Ubuntu
- Nginx
- Node


