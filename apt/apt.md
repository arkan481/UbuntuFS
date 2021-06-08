# apt
Managing Ubuntu softwares with apt.

## Updating apt sources database
To update the database of apt sources, this command can be run:
```zsh
apt update
```

## See upgradeable packages
Usually after we update our database of sources, we'll be prompted to see which packages can be updraded, and to upgrade them you can run:
```zsh
apt upgrade
```

## Full upgrade
Doing command apt upgrade won't upgrade package that needs another package to be removed first, to do so you can run:
```zsh
sudo apt full-upgrade
```