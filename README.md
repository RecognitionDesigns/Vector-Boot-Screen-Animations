# Vector-Boot-Screen-Animations
Customise the boot screen animation with a video of your choice.

Installation instructions adapted from https://oskr.ddl.io/doc/examples.html#change-boot-animation

Prerequisites:
Vector Robot running custom firmware image for OSKR.
Animated .gif file.

1.  Convert the .gif file to a raw image using the script, gif_to_raw.py + the .gif you want to convert.

  python3 ./gif_to_raw.py matrix.gif
  
2.  Mount the filesystem for writing to disk. Change the IP address to that of your Vector.

  ssh root@192.168.0.123 "mount -o remount,rw /"
  
3.  Copy the raw image to the animations folder in Vectors filesystem.

  scp matrix.gif.raw root@192.168.0.123:/anki/data/assets/cozmo_resources/config/engine/animations/boot_anim.raw
  
4.  Reboot Vector for the changes to take effect.

  ssh root@192.168.0.123 "/sbin/reboot"
