# Template fo raspberry startup configuration

## To disable wifi or bluetooth at start
```bash
dtoverlay=disable-wifi
dtoverlay=disable-bt
```
The `raspi-config` simply manipulates this symlink. To switch to manual login, execute (as root):

```bash
ln -fs /lib/systemd/system/getty@.service \
 /etc/systemd/system/getty.target.wants/getty@tty1.service
```

To switch back to automatic login, do:

```bash
ln -fs /etc/systemd/system/autologin@.service \
 /etc/systemd/system/getty.target.wants/getty@tty1.service
```
