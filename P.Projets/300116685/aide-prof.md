


https://www.mustbegeek.com/enable-ssh-in-cisco-ios-router/#.X9FXdapKgQ8


```
$ ssh 192.168.0.1
```


* From Windows10 side:

  Unable to negotiate with 192.168.1.31 port 22: no matching key exchange method found. Their offer: diffie-hellman-group1-sha1

* From switch side:

  00:35:35: SSH2 0: no matching cipher found: client chacha20-poly1305@openssh.com,aes128-ctr,aes192-ctr,aes256-ctr server aes128-cbc,3des-

:bulb: edit:

Seems Windows 10 in-built ssh has turned off by default several older (less secure) ciphers. Still, if you need them, you can enable them:

```
$ ssh -oKexAlgorithms=+diffie-hellman-group14-sha1  aes256-cbc 192.168.0.1
```

                 
        

