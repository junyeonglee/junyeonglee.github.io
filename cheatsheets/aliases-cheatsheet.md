# Bash Shell Aliases Cheat Sheet

My own defined aliases to `.bashrc`\
Inspired by [30 Handy Bash Shell Aliases For Linux / Unix / Mac OS X](https://www.cyberciti.biz/tips/bash-aliases-mac-centos-linux-unix.html)

`.bash_aliases`

```bash
# Alias definitions.
# You may want to put all your additions into a separate file like
# .bash_aliases, instead of adding them here directly.

## clear command in shorthand
alias c='clear'

## Colorize the ls output ##
alias ls='ls --color=auto'

## Use a long listing format ##
alias ll='ls -la'

## Show hidden files ##
alias l.='ls -d .* --color=auto'

## get rid of command not found ##
alias cd..='cd ..'

## a quick way to get out of current directory ##
alias ..='cd ../../'
alias ...='cd ../../../'
alias ....='cd ../../../../'
alias .....='cd ../../../../../'

## Colorize the grep command output for ease of use (good for log files)##
alias grep='grep --color=auto'

## Create directory(ies) with making parent directories as needed
alias mkdir='mkdir -pv'

# Stop after sending count ECHO_REQUEST packets #
alias ping='ping -c 5'

# Show open ports
alias ports='netstat -tulanp'

# get web server headers #
alias header='curl -I'

# do not delete / or prompt if deleting more than 3 files at a time #
alias rm='rm -I --preserve-root'

# confirmation #
alias mv='mv -i'
alias cp='cp -i'
alias ln='ln -i'

# Parenting changing perms on / #
alias chown='chown --preserve-root'
alias chmod='chmod --preserve-root'
alias chgrp='chgrp --preserve-root'

# become root #
alias root='sudo -i'

# reboot / halt / poweroff
alias reboot='sudo /sbin/reboot'
alias shutdown='sudo /sbin/shutdown'

# Control web servers
alias httpdreload='sudo /usr/sbin/apachectl -k graceful'

# Resume wget by default
alias wget='wget -c'
```

Execute alias commands

```sh
source .bashrc # or .bash_aliases
```
