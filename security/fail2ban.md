# Fail2Ban
Fail2ban is a program to ban IP that is trying to access our server mutiple times, with a wrong credentials.

## Instructions
instructions setting up fail2ban in Ubuntu
1. Install fail2ban
```zsh
# installing fail2ban
sudo apt install fail2ban
# installing sendmail and iptables-persistent so fail2ban is consistent between reboots
sudo apt install sendmail iptables-persistent
```
2. Start fail2ban service
```zsh
# starting fail2ban
sudo service fail2ban start
```

## Checking fail2ban status for sshd
```zsh
sudo fail2ban-client status sshd
```