# dotfiles/dns

Something to configure better **dns** nameserver.

## Linux

Open Terminal.

```bash
sudo nano /etc/resolv.conf # open "/etc/resolv.conf" file in a editor.
```

Change default nameserver to Google DNS nameservers.

```
nameserver 8.8.8.8
nameserver 8.8.4.4
```

Save and exit.

_Keep calm: this procedure may be temporary. After a reboot the file could come back as originally!_

### Files available

`resolv.conf` is a linux basic dns config file .