# RPIPlay


## :one: Compile and install the project

For downloading the code, use these commands:

```
$ git clone https://github.com/FD-/RPiPlay.git && cd RPiPlay
```

For building on a fresh Raspbian Stretch or Buster install, these steps should be run:

```
$ sudo apt-get install cmake
$ sudo apt-get install libavahi-compat-libdnssd-dev
$ sudo apt-get install libplist-dev
$ sudo apt-get install libssl-dev
$ Vmkdir build
$ cd build
$ cmake ..
$ make
```

To make a global install `/usr/local/bin/rpiplay`

```
$ sudo make install
```


## :two: Install as a service 

- [ ] Get `root` prompt

```
$ sudo su -
```

- [ ] Install the `RPiPlay` Servicee

```
# cat <<EOF > /etc/systemd/system/RPiPlay.service
[Unit]
Description=RPiPlay service
After=network.target
StartLimitIntervalSec=0

[Service]
Type=simple
Restart=always
RestartSec=1
User=pi
# -l : Low Latency parameter is required since it doesn't drop video frames
ExecStart=/usr/local/bin/rpiplay -n "Bathroom TV" -b auto -l

[Install]
WantedBy=multi-user.target
```

- [ ] Enable the service at boot time

```
$ sudo systemctl enable RPiPlay
```

- [ ] Reboot

### :gear: What about `rpiplay`

```
$ rpiplay -n "Bathroom TV" -b auto -l
```

-n is the name of the ApplePlay Server

-b is for enabling the black window at startup (auto) means only required when there is an ApplePlay Connection

-l is for low latency (which seems to work better when using video)

## :three: TroubleShooting


```
$ tvservice --list
1 attached device(s), display ID's are : 
Display Number 2, type HDMI 0
```

  https://github.com/raspberrypi/firmware/issues/1243 (HDMI1 no sound use HDMI0)

  https://github.com/raspberrypi/firmware/wiki/Mailbox-property-interface
  
```  
  $ tvservice --status --name --json --modes=CEA
[
{ "code":1, "width":640, "height":480, "rate":60, "aspect_ratio":"4:3", "scan":"p", "3d_modes":[] },
{ "code":2, "width":720, "height":480, "rate":60, "aspect_ratio":"4:3", "scan":"p", "3d_modes":[] },
{ "code":3, "width":720, "height":480, "rate":60, "aspect_ratio":"16:9", "scan":"p", "3d_modes":[] },
{ "code":4, "width":1280, "height":720, "rate":60, "aspect_ratio":"16:9", "scan":"p", "3d_modes":["FP","TopBot"] },
{ "code":5, "width":1920, "height":1080, "rate":60, "aspect_ratio":"16:9", "scan":"i", "3d_modes":["SbS-HH"] },
{ "code":7, "width":720, "height":480, "rate":60, "aspect_ratio":"16:9", "scan":"i", "3d_modes":[] },
{ "code":16, "width":1920, "height":1080, "rate":60, "aspect_ratio":"16:9", "scan":"p", "3d_modes":[] },
{ "code":17, "width":720, "height":576, "rate":50, "aspect_ratio":"4:3", "scan":"p", "3d_modes":[] },
{ "code":18, "width":720, "height":576, "rate":50, "aspect_ratio":"16:9", "scan":"p", "3d_modes":[] },
{ "code":19, "width":1280, "height":720, "rate":50, "aspect_ratio":"16:9", "scan":"p", "3d_modes":["FP","TopBot"] },
{ "code":20, "width":1920, "height":1080, "rate":50, "aspect_ratio":"16:9", "scan":"i", "3d_modes":["SbS-HH"] },
{ "code":22, "width":720, "height":576, "rate":50, "aspect_ratio":"16:9", "scan":"i", "3d_modes":[] },
{ "code":31, "width":1920, "height":1080, "rate":50, "aspect_ratio":"16:9", "scan":"p", "3d_modes":[] },
{ "code":32, "width":1920, "height":1080, "rate":24, "aspect_ratio":"16:9", "scan":"p", "3d_modes":["FP","TopBot"] },
{ "code":34, "width":1920, "height":1080, "rate":30, "aspect_ratio":"16:9", "scan":"p", "3d_modes":[] }
]
state 0xa [HDMI CUSTOM RGB lim 16:9], 1920x1080 @ 60.00Hz, progressive
device_name=WET-WD55UDR101
```

```
$ cat /etc/rpi-issue
Raspberry Pi reference 2019-07-10
Generated using pi-gen, https://github.com/RPi-Distro/pi-gen, 175dfb027ffabd4b8d5080097af0e51ed9a4a56c, stage5
```

