# Add New User(wheel) with SSH key

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

## (Optional) adding supplementary group to user

```sh
usermod -aG my-group my-user # add user to group
```
