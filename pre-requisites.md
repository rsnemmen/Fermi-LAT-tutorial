Pre-requisites
=================

To participate in the tutorial we recommend that you bring your laptop. Your laptop should have at least 4GB of RAM in order to run the VM. You will need about 30 GB of free space in your computer: 10 GB for the download and 20 GB to run the VM.

All the analysis software and data files required for this hands-on activity are already installed in a ready-to-use, self-contained [virtual machine (VM)](https://en.wikipedia.org/wiki/Virtual_machine). The VM runs on Windows, Linux and MacOS and is based on the *Scientific Linux distribution* (64 bit). It contains the `Fermi ScienceTools`, `Enrico` and `ds9`.

In order to run the VM, you will need to [download and install the VirtualBox binaries](https://www.virtualbox.org/wiki/Downloads) appropriate for your OS. 

- [Download links](#download-links)
- [Instructions for installing VM](instructions-for-installing-vm) and [potential VM issues](#some-potential-vm-issues)
- [Introduction to Python and Linux](#python-and-linux-background)
- [Want to use your own tools instead of the VM?](#if-you-want-to-install-the-analysis-tools-on-your-own-linux-or-macos-system-instead-of-using-the-vm)



# Download links

We recommend that you start downloading early our virtual machine, given the large file size. 

*Please do not download large files during the tutorial or the WIFI network will overload*. We will also distribute the software and data you need via USB sticks, if you did not download them before the school.

1. [VirtualBox download](https://www.virtualbox.org/wiki/Downloads)
2. Virtual machine with all software and data: [Download link](https://www.dropbox.com/s/0b874qnu8slc51b/Hands-on%20Scientific%20Linux.ova?dl=0), [FTP link](ftp://astroweb.iag.usp.br/dalpino/Hands-on). File size: 10.2 GB. MD5 checksum: 83c909f0bf9a5bb6b6f7e3603db6f82e

`wget` command to download the VM: 

    wget -O Hands-on_Scientific_Linux.ova https://www.dropbox.com/s/0b874qnu8slc51b/Hands-on%20Scientific%20Linux.ova?dl=0

If the download gets interrupted, you can resume the download from where it stopped:

    wget -c -O Hands-on_Scientific_Linux.ova https://www.dropbox.com/s/0b874qnu8slc51b/Hands-on%20Scientific%20Linux.ova?dl=0

After downloading the VM file, follow the instructions below.

# Instructions for installing VM

1. Install and launch [VirtualBox](https://www.virtualbox.org/wiki/Downloads).
2. Click on `File` -> `Import Appliance`.
3. Browse and select the VM file (`Hands-on Scientific Linux.ova`).
4. Click on `Continue` and on the next screen click on `Import`. This step may take a few minutes.
5. Once you do that, you should see a window that looks something like the following. Click `Start` to start up the VM. You should see a window pop up, and see Linux starting up inside that window.

![](./figures/virtualbox.png "VirtualBox window listing the VM after successfull import")

6. In the end, you should have a window that looks like this. ~~Contact the organizers for the password~~ The password is `saopaulo`. You are good to go!

![](./figures/welcome_screen.png "VM after booting")

# Some potential VM issues

- If your filesystem is FAT or FAT32, it will not allow the creation of files with sizes bigger than 2 or 4 GB. Since the VM file size is >10 GB, you will not be able to download the file. In this case, you will have to [convert your filesystem to NTFS or VFAT](https://www.google.com.br/search?client=safari&rls=en&q=convert+from+fat+to+vfat+windows&ie=UTF-8&oe=UTF-8&gws_rd=cr&ei=ifkeWbvzJsy1wASQ24ToBw).
- If you try to run the VM in VirtualBox and you get the error message `VT-x/AMD-V hardware acceleration is not available in your system`, that means that either you have to access your computer’s BIOS and switch on a specific setting, or your CPU is too old and will not support virtualization. See [this link](https://www.howtogeek.com/213795/how-to-enable-intel-vt-x-in-your-computers-bios-or-uefi-firmware/) for more information. 



# Python and Linux background

This hands-on activity will make considerable use of Python and Linux. If you are not familiar with the Python programming language or Linux, we recommend that you study them *before* the hands-on session. Some suggested  preparatory material on the basics of Python as a scientific computing language or Linux: 

- [Lectures on scientific computing with Python](https://github.com/jrjohansson/scientific-python-lectures)
- [UNIX tutorial for beginners](http://www.ee.surrey.ac.uk/Teaching/Unix/)

# If you want to install the analysis tools on your own Linux or MacOS system instead of using the VM

Here are some directions for those that would like to run tutorial using the analysis software installed in their own OS instead of using our pre-packaged VM. You will need to:

1. Install all the analysis software separately
2. Download the supporting data files

## Software required

The software you will need to install are:

- [`Fermi ScienceTools`](https://fermi.gsfc.nasa.gov/ssc/data/analysis/software/)
- [SAOImage DS9](http://ds9.si.edu/site/Home.html)
- [Enrico](http://enrico.readthedocs.io/en/latest/index.html
) 

In order to get the ScienceTools and Enrico working together, you need to setup some environment variables after installing the software. If you are curious, please have a look at the `.bashrc` init file located in your home directory in the VM.

Also, note that the ScienceTools have their own Python distribution which conflicts with any pre-existing Python installed on your system, hence the need for setting up the environment variables properly. Keep that in mind.

## Data files for observations

All the data files required for the tutorial are pre-installed in the VM. However, if you are *not* using the VM to run the activity, you can download the data files [here](https://figshare.com/articles/Fermi_LAT_Hands-on_activity_Sao_Paulo_CTA_School_2017/5027513).
