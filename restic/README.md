# dotfiles/restic

Some install methods for **restic**.


### Install methods
##### Debian / Ubuntu
```bash
apt install restic
```
##### Docker
```bash
docker pull ghcr.io/restic/restic
```
and then add alias in `.bashrc`:
```txt
alias restic='docker rm restic >/dev/null 2>&1;docker run --rm -it -v /home/user:/home/user -v /media/user:/media/user -v /tmp:/tmp -v /home/user/.ssh:/root/.ssh:ro --network host --hostname=$(uname -n) --name restic ghcr.io/restic/restic'
```

### Configs
Add some ENVs in the `.bashrc` file:
```bash
export RESTIC_COMPRESSION="max"
```
See [all available environment variables](https://restic.readthedocs.io/en/stable/040_backup.html#environment-variables).
