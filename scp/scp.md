# SCP
SCP is a Linux binary program to upload files or directory to our server, it uses SSH in the background.

## Usage
```zsh
# Uploading a file to a server
scp file_name username@host_ip:server-directory

# Uploading a directory to a server
scp -r dir_name username@host_ip:server-directory
```