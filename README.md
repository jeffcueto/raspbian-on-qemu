# raspbian-on-qemu
Installing raspbian jessie lite on qemu
In this tutorial for begeners as me we are going to install raspbian usin qemu(in this case i use ubuntu 16)

1) install qemu ubuntu:
sudo apt-get install qemu

2) create or use your folder in my case i use ~/Documents

3) download kernel for arm, i use kernel from  https://github.com/polaco1782/raspberry-qemu

4) download raspbian jessie lite form official web https://www.raspberrypi.org/downloads/

5) unzip  image raspbian jessie and then mount. for mount i have to do this:

  a) parted  2016-05-27-raspbian-jessie-lite.img hit enter the command line show this:
  
GNU Parted 2.3
Using 2016-05-27-raspbian-jessie-lite.img
Welcome to GNU Parted! Type 'help' to view a list of commands.
(parted) unit                                                             
Unit?  [compact]? B                                                       
(parted) print

  b) copy the offset of where the partition starts.
  
  Number   Start          End            Size           Type     File system     Flags
  
 1           32256B         10733990399B   10733958144B   primary  ext4
 
 2         10733990400B   21500881919B   10766891520B   primary  ext3
 
 c) sudo mount 2016-05-27-raspbian-jessie-lite.img -o loop,offset=32256  mnt/point

5) afet mount .img  i did cd mnt/point and then i have to find in /etc/  ld.so.preload , open with sudo nano 

6) comment with #  like this: #/usr/lib/arm-linux-gnueabihf/libcofi_rpi.so. then saved , exit and unmount the .img

7) execute the script for run your virtual pi. listo!!
 
