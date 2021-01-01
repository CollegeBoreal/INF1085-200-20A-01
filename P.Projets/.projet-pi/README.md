# Projet Raspberry PI

- [ ] :one: [MagicMirror](https://docs.magicmirror.builders)

- [ ] :two: [RPiPlay](https://github.com/FD-/RPiPlay)

  https://github.com/raspberrypi/firmware/wiki/Mailbox-property-interface
  
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
pi@isaha:~ $ cat /etc/rpi-issue
Raspberry Pi reference 2019-07-10
Generated using pi-gen, https://github.com/RPi-Distro/pi-gen, 175dfb027ffabd4b8d5080097af0e51ed9a4a56c, stage5


