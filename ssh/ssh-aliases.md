# SSH Aliases
Create an SSH alias that easy to remember, so You don't have to remember the IP and username of your server.

## Instructions
1. Go into the current user SSH directory
```zsh
# Go into user SSH dir
cd ~/.ssh
```
2. Check if SSH config file is available, if not then just create one
```zsh
# Creating SSH config file
sudo vim config
```
3. Write your SSH config file, for a reference please see [ssh config](./config).

## Usage
After you completed the instructions above, you can then just run this command to do some SSH connection.
```zsh
ssh HOST_NAME
```