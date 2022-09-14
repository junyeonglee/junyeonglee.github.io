# Linux Pocket Guide

- [Linux Pocket Guide](#linux-pocket-guide)
  - [Import New SSH keys on Launchpad](#import-new-ssh-keys-on-launchpad)
  - [Symbolic link](#symbolic-link)
  - [SSH Basic Conf](#ssh-basic-conf)
  - [User](#user)
    - [Add new user(wheel) with SSH key](#add-new-userwheel-with-ssh-key)
    - [Add supplementary group to user](#add-supplementary-group-to-user)
    - [Configure `sudo` to never ask for password](#configure-sudo-to-never-ask-for-password)
  - [Vim](#vim)
    - [Mode](#mode)
    - [Work](#work)
    - [Search](#search)

## Import New SSH keys on Launchpad

Import your public SSH key on Launchpad can be very handy to setup access to server

1. Visit https://login.launchpad.net/ssh-keys
2. Import new SSH key (usually `id_rsa.pub` or `id_dsa.pub`)

Example of `id_rsa.pub`

```sh
ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEAtBcTeRt6zKKsAIVt9g2z3DIDaMUW09B3AG90hTg44i/kN3GNKbZnjFblF/nlfTZ4D9k5V6OM1++FDYbLig00FHmjTOQ2+RsvZRfne5WvRQBPM7EV70zd9mQJLS/RuGV6MgoMT48RZJiah5ZkgDUWgl6KRvC6kvpl3cJ8q+l0ZMgRS7Ksz38iTi4IAuMeFuKySP5RS1AmlwXB+OH+OLMzGX0r6Ez3wN69MnCdmX+X7Xf9/dqQKI+Y6DYUQkfr1g5oXEGnVu/sw4MDibyQOTQvyxbYjNNJQ70/+MfhfLTU6S2NX21joyGCTs5X74sq7f1V/hV03uHi4sFiVAd7W4cbJQ== rsa-key-20180829
```

## Symbolic link

To create a symbolic link

```sh
# Example of switching python version
# Create a link to `python3` with the name `python`

cd /usr/bin
ln -sfn python3 python # python -> python3
```

## SSH Basic Conf

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

## User

### Add new user(wheel) with SSH key

```sh
# Login to remote server
ssh root@remote-server-ip

# Create new my-user(wheel) with SSH key
useradd -g wheel -m my-user # create my-user:wheel with home directory
su my-user # change to my-user

mkdir /home/my-user/.ssh # create .ssh directory
echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEAtBcTeRt6zKKsAIVt9g2z3DIDaMUW09B3AG90hTg44i/kN3GNKbZnjFblF/nlfTZ4D9k5V6OM1++FDYbLig00FHmjTOQ2+RsvZRfne5WvRQBPM7EV70zd9mQJLS/RuGV6MgoMT48RZJiah5ZkgDUWgl6KRvC6kvpl3cJ8q+l0ZMgRS7Ksz38iTi4IAuMeFuKySP5RS1AmlwXB+OH+OLMzGX0r6Ez3wN69MnCdmX+X7Xf9/dqQKI+Y6DYUQkfr1g5oXEGnVu/sw4MDibyQOTQvyxbYjNNJQ70/+MfhfLTU6S2NX21joyGCTs5X74sq7f1V/hV03uHi4sFiVAd7W4cbJQ==" >> /home/my-user/.ssh/authorized_keys # add public key

chmod 700 /home/my-user/.ssh # change folder permission
chmod 600 /home/my-user/.ssh/authorized_keys # change file permission
```

### Add supplementary group to user

```sh
usermod -aG my-group my-user # add user to group
```

### Configure `sudo` to never ask for password

```sh
sudo visudo # safely edit the sudoers file

# Add the following line
YOUR_USERNAME_HERE ALL=(ALL) NOPASSWD: ALL
```

## Vim

One of the most popular editors in unix

### Mode

`i` switch to insert mode\
`esc` switch to command mode

### Work

`dd` delete line\
`:set number` show line number

`:w` write\
`:wq` write + quit\
`:q!` quit without saving

### Search

`/text` search for text (`n` for next, `N` for previous)\
`gg` fo to fist line\
`G` go to last line


