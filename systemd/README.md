# Systemd units

* `sht31.timer` to kick off the process
* `sht31.service` to collect and read the sensor"

```bash
# Install as a user unit (recommended):
cd systemd
mkdir -p ~/.config/systemd/user
cp sht31.service ~/.config/systemd/user/
cp sht31.timer ~/.config/systemd/user/
systemctl --user daemon-reload
systemctl --user enable --now sht31.timer
systemctl --user status sht31.timer

# If this should run even when you are not logged in, enable linger:
# sudo loginctl enable-linger $(whoami)
```
