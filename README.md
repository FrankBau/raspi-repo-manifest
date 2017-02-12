# A RasPi repo manifest

A manifest file for the [repo](https://source.android.com/source/using-repo.html) tool 
to get started with [Yocto Project](https://www.yoctoproject.org/) style development 
for the [Raspberry Pi](https://www.raspberrypi.org/).

If the `repo` command is not yet installed, install it 
* from your distro (Ubuntu 16.04: `sudo apt-get install repo`), or
* from the source http://commondatastorage.googleapis.com/git-repo-downloads/repo

Create a new empty folder, say `raspi`, on your Linux build host 
(20..50 GB free disk space and a fast machine needed) and setup all repositories:

    mkdir raspi
    cd raspi
    repo init -u https://github.com/FrankBau/raspi-repo-manifest -b morty
    repo sync
    TEMPLATECONF=meta-rpi/conf source sources/oe-init-build-env build 

This creates a build folder and a conf subfolder with some configuration files.
Review the configuration files and then, from the build folder, issue the first bitbake command:

    bitbake console-image

## Further Reading
* Jumpnow Technologies blog: http://www.jumpnowtek.com/rpi/Raspberry-Pi-Systems-with-Yocto.html

