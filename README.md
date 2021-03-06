# rc_aacv ROS package
## Basic Ubuntu Installation (Windows Machines)
__Use this if you want to create a partition on your HDD dedicated to Ubuntu.__

Download [Ubuntu 14.04 Trusty Tahr LTS Desktop Image (AMD64 for 64 bit machines)](http://releases.ubuntu.com/14.04/).

Follow [These Instructions](https://www.ubuntu.com/download/desktop/create-a-usb-stick-on-windows) to create a bootable usb of Ubuntu 14.04 (make sure to use the above image).

[Boot from the USB](https://www.ubuntu.com/download/desktop/try-ubuntu-before-you-install)

From here you can run Ubuntu 14.04 directly from the USB, or install Ubuntu 14.04 either as a complete overwrite of your machine, or you as a dual-boot arrangment.  Follow the installation wizard as desired.

## Basic Ubuntu Installation (Virtual Machine)
__Use this if you don't want to create a partition on your HDD.__

Download [Ubuntu 14.04 Trusty Tahr LTS Desktop Image (AMD64 for 64 bit machines)](http://releases.ubuntu.com/14.04/).

Download and install [Oracle Virtualbox for Your OS](https://www.virtualbox.org/wiki/Downloads)

[Windows Host Instructions](https://www.lifewire.com/run-ubuntu-within-windows-virtualbox-2202098)

[OSX Host Instructions](https://askubuntu.com/questions/710608/how-do-i-install-ubuntu-on-virtualbox-on-mac-os-x-el-capitan)

[Enabling copy/paste between host & virtual machine](https://www.liberiangeek.net/2013/09/copy-paste-virtualbox-host-guest-machines/)

## Configuring Ubuntu 14.04
Once Ubuntu is installed (however you like), open up a terminal and run the following:
```
sudo apt-get update
sudo apt-get install build-essential
```

## rc_aacv Install Instructions
__Built for [Ubuntu 14.04 Trusty Tahr LTS](http://releases.ubuntu.com/14.04/).__

Install [ROS Indigo](http://wiki.ros.org/indigo/Installation/Ubuntu)

[Create a ROS workspace](http://wiki.ros.org/catkin/Tutorials/create_a_workspace)

Make sure these ROS packages are installed:
```
sudo apt-get install ros-indigo-joystick-drivers
sudo apt-get install ros-indigo-sensor-msgs
sudo apt-get install ros-indigo-rosserial-arduino
sudo apt-get install ros-indigo-rosserial
```

Clone this repo into the package location for your ROS workspace and build the packages.
```
git clone https://github.com/FletcherFT/rc_aacv.git
cd ../..
catkin_make
```

Connect laptop up to wifi network, boot up aacv and check that you can ping the beaglebone black.

wifi SSID:  "FOX_network"

wifi passkey: "12345678"

```
ping aacv-bbb.local
```

Connect joystick to laptop, wait 30s then execute:
```
roscd rc_aacv/launch
. test.sh
```

All nodes should then launch, you should be able to remotely control Blue!
