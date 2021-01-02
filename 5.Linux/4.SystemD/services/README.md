# Services


https://medium.com/@benmorel/creating-a-linux-service-with-systemd-611b5c8b91d6

Comment créer un service sous Linux?

Installer https://github.com/FD-/RPiPlay comme example

```
$ rpiplay -n "Washroom TV" &

```

```bash
sudo cat <<EOF > /etc/systemd/system/RPiPlay.service
[Unit]
Description=RPiPlay service
After=network.target
StartLimitIntervalSec=0
[Service]
Type=simple
Restart=always
RestartSec=1
User=pi
ExecStart=/usr/local/bin/rpiplay -n "Bathroom TV" 

[Install]
WantedBy=multi-user.target
EOF
```
