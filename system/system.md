# System
Contains general commands to check the system performance, RAM, and disk space.

## Real-time system performance
Provides task manaager like interface to monitor system performance in details.
```zsh
# provides regular top interface
top
# provides more modern top inteface
sudo apt install htop
htop
```

## Checking disk space
```zsh
df
# shows disk space left in megabyte
df -m
# shows disk space left in gigabyte
df -h
# shows inodes
df -i
```

## Checking RAM usage
```zsh
free -h
```