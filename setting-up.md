# Setting Up
Step-by-step instructions when setting up Ubuntu 20.0 as a server.

## Instructions
1. create a user with adduser command.
```zsh
# adding a user with the specified username
adduser username
``` 
2. Add the created user to the sudo group
```zsh
# adding user to the 'sudo' group
usermod -aG sudo username
```
3. Add the public key to the user authorized_keys file
```zsh
# going into the user .ssh directory
cd /home/username/.ssh
# making the user authorized_keys file
sudo vim authorized_keys 
# paste your public key into the file, save and quit
```
4. Modify the SSH config file to enhance the security while using SSH  
[SSH config file](/ssh/v1-ssh-config.conf).  
```zsh
# going into SSH config directory in Ubuntu
cd /etc/ssh/sshd_config.d
# creating a customize SSH config file
sudo vim v1-ssh-config.conf
# copy and paste the inside of SSH config file above into this newly created config file, save and exit
```
5. Set up MFA for the Ubuntu Server
```zsh
# installing google authenticator
sudo apt install libpam-google-authenticator
# running google authenticator
google-autenticator
# then answer yes to all prompts that appears
# then scan the QR Code using your preferred authenticator app
# also be sure to copy the emergency scratch codes, into a safe place
```
6. Configure the PAM sshd file for using the google authenticator 
```zsh
# backing up the defalt PAM sshd file
sudo cp /etc/pam.d/sshd /etc/pam.d/sshd-backup
# modifying the PAM sshd file
sudo vim /etc/pam.d/sshd
# comment out the line @include common-auth
# add this following line
# One-time password authentication via Google-Authenticator
auth required pam_google_authenticator.so
```
7. Restart the ssh service
```zsh
# restarting the SSH service
sudo systemctl ssh restart
```

8. Setup UFW firewall, see [ufw](./security/ufw.md)

9. Setup fail2ban, see [fail2ban](./security/fail2ban.md)

10. Test the SSH authentication in a new terminal tab

11. Create an SSH alias in Your own machine (optional), see [SSH aliases](/ssh/ssh-aliases.md)

> After completing these instructions above, logout from the root user, and from now on only login with the newly created user.

## Cautions
1. Only use root user if necessary.
2. In case the MFA is failing, please see [Recovering Failing MFA in Ubuntu](/mfa/recover-mfa.md).

## Note
1. This project's Ubuntu server is created through Digital Ocean droplet, with ubuntu image version 20.0.