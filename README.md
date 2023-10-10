# kali-kernel-source
kernel header update instructions for custom-kernel / wifi driver install

    kali-tweaks
select 'repositories'

check 'bleeding-edge'

check 'expiremental'

select 'Apply'

    sudo apt update


    sudo apt upgrade


    sudo apt install linux-image-amd64


    sudo reboot


    sudo apt install build-essential libelf-dev linux-headers-$(uname -r)


For nineplus AC1200 wireless card (capable of packet injection)


    sudo su
    lsusb
    apt -y install git
    apt -y install dkms
    mkdir /apps
    cd /apps/

--copy all the lines down to (and including) the command '..'-- 

    git clone "https://github.com/RinCat/RTL88x2BU-Linux-Driver.git" /usr/src/rtl88x2bu-git
    sed -i 's/PACKAGE_VERSION="@PKGVER@"/PACKAGE_VERSION="git"/g' /usr/src/rtl88x2bu-git/dkms.conf
    dkms add -m rtl88x2bu -v git
    dkms autoinstall
    ..
