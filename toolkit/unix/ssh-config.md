# SSH Basic Conf

ssh config template `.ssh\config`

```bash
Host website
  User junyeonglee
  IdentityFile /home/junyeonglee/.ssh/id_rsa
  Hostname junyeonglee.github.io
  Port 22
  ServerAliveInterval 60
  TCPKeepAlive yes
  Compression yes
```
