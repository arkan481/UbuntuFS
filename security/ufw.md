# UFW
UFW is a firewall program that is by default installed in Ubuntu, it functions to block or allow specific port of our server.

## Instructions
instructions setting up UFW for SSH, HTTP, and HTTPS in Ubuntu.
1. Deny all outbound traffic coming from our server
```zsh
sudo ufw default deny incoming
```
2. Allow all outbound traffic outgoing from our server
```zsh
sudo ufw default allow outgoing
```
3. Allow ssh
```zsh
sudo ufw allow ssh
```
4. Allow HTTP
```zsh
sudo ufw allow http
```
5. Allow HTTPS
```zsh
sudo ufw allow https
```
6. Enable UFW
```zsh
sudo ufw enable
```

## Checking UFW Status
```zsh
# Checking which ports is opened
sudo ufw status
# Checking UFW with more details
sudo ufw status verbose
```

## Checking Iptables
```zsh
sudo iptables -L
```

## Removing UFW rules
```zsh
# checking UFW status, but numbered
sudo ufw status numbered
# deleting the UFW rule by the number
sudo ufw delete number
```

## Note
> You should not allow more traffic inward than you have to.