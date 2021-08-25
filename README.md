# preempt-rt-rpi-5.4.81-rt
Cross- compiled PREEMPT RT patch of version 5.4.81-rt for Raspberry Pi 4b

Follow the steps below to uncompress and install the new RT-Kernel on your Raspberry Pi 4b ...

1. Open a new terminal on your Raspberry Pi
2. pi@raspberrypi:~$ cd /tmp
3. pi@raspberrypi:~$ git clone https://github.com/AndrejLeber/preempt-rt-rpi-5.4.81-rt.git
4. pi@raspberrypi:~$ cd preempt-rt-rpi-5.4.81-rt
5. pi@raspberrypi:~$ tar xzf rt-kernel.tgz
6. pi@raspberrypi:~$ cd boot/
7. pi@raspberrypi:~$ sudo cp -rd * /boot/
8. pi@raspberrypi:~$ cd ../lib
9. pi@raspberrypi:~$ sudo cp -dr * /lib/
10. pi@raspberrypi:~$ cd ../overlays
11. pi@raspberrypi:~$ sudo cp -d * /boot/overlays
12. pi@raspberrypi:~$ cd ..
13. pi@raspberrypi:~$ sudo cp -d bcm* /boot/
14. pi@raspberrypi:~$ sudo gedit /boot/config.txt

Add the following line to the the end of congig.txt file, save and exit.
  kernel=kernel7_rt.img

Reboot your Pi. You can check if everything went right with the following command:
pi@raspberrypi:~$ uname -r

You should get the response: 5.4.81-rt45-v7l+

Good luck with your new preemptible kernel!
