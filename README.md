# LinuxKnowledge
MyLinuxCommandRefresher


FB
======== 

setInterval(function () {
    document.getElementById('see_older')
        .getElementsByClassName('content')[0].click();
}, 0.01);


PYTHON TUTORIALS
========
jessica mckellar python
https://youtu.be/MirG-vJOg04


MKDIR
========
mkdir -p a/s/d  nested folder
mkdir -p Subject{1..4}/Book{1..3}

LS
========
ls -l/a 
gives detailed info of files

MV
========
mv /path.to.folder/*.txt /path.to.new.folder/
mv *jpg* /home/mahi/Pictures

SCP
========
scp (-r) source ddest 
eg. 
scp -r s@192.168.40.99: hardware\ lab\ 1 Desktop

DOWNLOADING FULL ACCOUNT
========
scp -r mahi_809cs@192.168.40.99:/home/

TASK MANAGER
========
all process in bob account
pgrep -l -u bob 


TERMINAL FILE MANAGER
========
sudo apt-get install libgnome2-bin
gnome-open </path/to/folder>

ADDING AT END
========
echo "Hello you!" >> myfile.txt

TERM PROFILE EDIT
========
change bkgrnd terminal 
setterm -term linux -back <background_colour> -fore <text_color> -clear
setterm -term linux -back green -fore black -clear
setterm --foreground black
setterm --background green
Color options are black|blue|green|cyan|red|magenta|yellow|white|default

LISTING ALL INSTALLED PACKAGE
========
dpkg --get-selections | awk '{print $1}'


UNINSTALLING 
========
sudo apt-get purge package name && sudo apt-get autoremove
eg.
sudo apt-get purge cairo-dock cairo-dock-plug-ins && sudo apt-get autoremove


SCHEDULED SHUTDOWN
========
sudo shutdown -h hh:mm
sudo shutdown -h 01:30

FORMATTING A USB//PASSWORD PROTECTED
========
-i is override
umount /dev/sdb
mkfs.vfat /dev/sdb
mkfs.vfat /dev/sdb -I
mkfs.ntfs /dev/sdb
mkfs.ext4 /dev/sdb

DISPLAY ALL MOUNTS
========
df -h for all file system

SPACE
========
du -hsc *


SPEED UP
========
sudo gksu gedit /etc/default/grub
OR sudo gedit /etc/default/grub
change time
sudo update-grub


UPDATE I/O SCHEDULAR TO CFQ
========
first check
cat /sys/block/sda/queue/scheduler
then
sudo nano /etc/default/grub
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash" ->GRUB_CMDLINE_LINUX_DEFAULT="quiet splash elevator=cfq"
it speeds up system by increasing responsiveness

CHANGE SWAPPINESS
========
cat /proc/sys/vm/swappiness
sudo subl /etc/sysctl.conf
add vm.swappiness = 10
swapoff -a
swapon -a

MASTER UPDATE
========
sudo apt-get update
sudo apt-get upgrade
sudo apt-get dist-upgrade

VERSION UPDATE
========
sudo update-manager -d

ICON CHANGE
========
cd /usr/share/applications
sudo gedit firefox.desktop
edit link to icon with desired

CHANGE DEFAULT
========
cd  /usr/share/applications/
sudo subl defaults.list
sublime-text-2.desktop
change instances of default app with desired
sublime_text.desktop


HOTSPOT
========
cd /etc/NetworkManager/system-connections/
sudo gedit firex
change
adhoc->ap

Ubuntu 16.04

create new
choose 128/80
enter alphanumeric password
edit 
adhoc - hotspot
authentification - shared key


COSTOMISED LOGIN SCREEN
========
sudo -i
xhost +SI:localuser:lightdm
su lightdm -s /bin/bash
gsettings set com.canonical.unity-greeter draw-user-backgrounds 'true'
gsettings set com.canonical.unity-greeter background 'path-to-image'
exit
sudo  /usr/share/backgrounds/warty-final-ubuntu.png

SET DATE TIME
========
sudo date --set="Fri Jul 08 16:43:56 IST 2016"

CHANGE DEFAULT BRIGHTNESS
========
sudo gedit /etc/default/grub
replace
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"
with
DELL HP
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash nomodeset acpi_backlight=vendor"
LENOVO
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash  acpi_backlight=vendor"   
sudo update-grub and reboot.

Problem faced:
shortkt key stops

ALIASING 
========

SSH ALIASING
gedit ~/.ssh/config 
Host myremote             # any name for the host
HostName 192.168.178.05   # IP, .local, or hostname if defined
User username             # your username
Port 22                   # port to listen


COMMAND ALIASING
subl ~/.bashrc
alias name='command'
source ~/.bashrc

edit write and save command alias 


alias d='sudo apt-get update'
alias g='sudo apt-get upgrade'
alias cdr='cd /'
alias cdh='cd ~'
alias documents='cd ~/Documents'
alias cds='cd  ~/Scripts/'
alias arem="sudo apt-get autoremove"
alias rm='trash'
alias ed='subl ~/.bash_aliases'
alias save='source ~/.bashrc'
alias allow='sudo chmod 777 ~/folder'
alias lock='sudo chmod 000 ~/folder'
sudo apt install trash-cli




MAKING GLOBALLY EXECUTABLE BASH FILES
========
1.write one
2.copy to usr/local/bin
3.restart


DELETING FILE/FOLDER
========
rm -f path to file
rmdir path to file

PERMISSION MANAGEMENT
========
sudo chmod 000 path
FOR INCLOSED FOLDER TOO
sudo chmod -R  777 path


LIST OF CMDS
========
ls /bin /sbin /usr/bin /usr/sbin

SYS INFO
========
uname -a
uname -r

CHANGE BOOT ORDER
========
sudo gedit /etc/default/grub
change
GRUB_DEFAULT=0 to GRUB_DEFAULT=saved
sudo update-grub
sudo grub-set-default 0

EXTRACTING
Help on decompressing the files:
*.lzma: tar --lzma -xvf *.tar.lzma
*.xz: tar -xJvf *.tar.xz
*.lrz: lrzuntar *.tar.lrz (you may need to install 'lrzip')

ADVANCE OPTION FOR UBUNTU
========

CHANGING FORGOTTEN PASSWORD/HACKING A ACCOUNT
1 grub
2 adv option for ubuntu
3 drop to  root shell
4 mount -o remount,rw / (remounting shadow (password part to rw)) / is root(dont miss;))
5 passwd username
6 type in new password

CTRL+ALT+BACKSPACE
========
sudo dpkg-reconfigure keyboard-configuration
5 time enter
set


OPENING FILE MANAGER AS ROOT
========
sudo nautilus/caja


UNITY TO BOTTOM
========
gsettings set com.canonical.Unity.Launcher launcher-position Bottom


CONVERT .jpg TO SINGLE FILE OF PDF
========
convert *.jpg pictures.pdf

CONVERT PPT TO PDF
========
libreoffice --headless --invisible --convert-to pdf *.pptx
libreoffice --headless --invisible --convert-to pdf *.ppt



UPDATE
========
sudo apt-get update && sudo apt-get upgrade

INVERT COLOUR
========
install xcalib
sudo apt-get install xcalib
invert && revert back
xcalib -i -a


UBUNTU RESET
========
echo "Cleaning Up" &&
sudo apt-get -f install &&
sudo apt-get autoremove &&
sudo apt-get -y autoclean &&
sudo apt-get -y clean


APT_GET ERRORS FIX
========
sudo su
apt-get clean
cd /var/lib/apt
mv lists lists.old
mkdir -p lists/partial
apt-get clean
apt-get update


MUST HAVE REPOSITORIES
========
sudo add-apt-repository main
sudo add-apt-repository universe
sudo add-apt-repository restricted
sudo add-apt-repository multiverse
sudo apt-get install ubuntu-restricted-extras



SHOW USER NAME
========
gsettings set com.canonical.indicator.session show-real-name-on-panel true
gsettings set com.canonical.indicator.session show-real-name-on-panel false

MUST HAVE
sudo apt-get install adobe-flashplugin
sudo apt-get install icedtea-8-plugin openjdk-8-jre
sudo apt-get install ffmpeg gxine libdvdread4 icedax tagtool libdvd-pkg easytag id3tool lame libxine2-ffmpeg nautilus-script-audio-convert libmad0 mpg321 libavcodec-extra gstreamer1.0-libav
sudo apt-get install laptop-mode-tools
sudo apt-get install bleachbit
sudo apt install adobe-flashplugin

LAUNCHER RESET
========
sudo apt-get install dconf-tools
DISPLAY:=0 dconf reset -f /org/compiz/
unity --reset-icons
setsid unity


SHUTDOWN
========
sudo shutdown -r now


FIX MISSING TYPE
========
sudo apt-get -f install


EXFAT DRIVE READ ERROR FIX
========
sudo apt-get install exfat-utils

STUCK APT-GET
========
killall -9 apt-get
dpkg --configure -a
update && upgrade

TO SHOW HIDEN STARTUP APP
========
sudo sed -i "s/NoDisplay=true/NoDisplay=false/g" /etc/xdg/autostart/*.


SETTING 3.5 DEFAULT
========
ls /usr/bin/python
python --version
update-alternatives --install /usr/bin/python python /usr/bin/python2.7 1
update-alternatives --install /usr/bin/python python /usr/bin/python3.4 2
update-alternatives --list python
update-alternatives --config python


PID AND KILL
========
pidof codeblocks
2702
kill 2702
OR 
killall codeblocks
OR 
kill \`pgrep codeblocks\`


DBMS
========
sudo apt-get update
sudo apt-get install apache2
sudo ufw app list
sudo ufw app info "Apache Full"
sudo ufw allow in "Apache Full"
sudo apt-get install mysql-server
sudo apt-get install php libapache2-mod-php php-mcrypt php-mysql
sudo apt-get install mysql-server mysql-client
sudo systemctl status mysql




SESSION TIMING
========
last username 
last username  -1
last username  -2


CHANGE IP
========
sudo ifconfig eth0  192.168.0.007 netmask 255.255.255.0

VOLUME UP DOWN
========
set 50%
amixer -D pulse sset Master 50%
dec 5%
amixer -D pulse sset Master 5%-
inc 5%
amixer -D pulse sset Master 5%+

FIREWALL 
========
ufw 

sudo aptitude install ufw
sudo apt-get install ufw
sudo ufw status
sudo gedit /etc/default/ufw
sudo ufw disable
sudo ufw enable
sudo ufw default deny incoming
sudo ufw default allow outgoing

CHANGE GRUB BACKGROUND
========
sudo apt-get install grub2-splashimages
sudo nautilus /usr/share/images/grub
sudo gedit /etc/default/grub
add
GRUB_BACKGROUND="/usr/share/images/desktop-base/moreblue-orbit-splash.png"
sudo update-grub

WEBSITE DOWNLOAD
========
wget --mirror -p --convert-links -P ./mahiz  
wget --mirror -p --convert-links -P ./LOCAL-DIR WEBSITE-URL


MERGE FILES
========
sudo apt-get install pdftk

pdftk 1.pdf 2.pdf 3.pdf cat output 123.pdf

gs \
  -o merged.pdf \
  -sDEVICE=pdfwrite \
  -dPDFSETTINGS=/prepress \
   input_1.pdf \
   input_2.pdf \
   input_3.eps \
   input_4.ps \
   input_5.pdf



MD5 CONVERSIONS
========
echo -n mahaveer | md5sum


SYNC FOLDER WITH DRIVE
========
sudo add-apt-repository ppa:nilarimogard/webupd8
sudo apt-get update
sudo apt-get install grive
sudo  grive -a
man grive
grive -h
grive -s folder_path

CONVERT OR CROP VIDEO
========
avconv -ss <start-time> -t <duration> -i long-video.mp4 -codec copy funny-clip.mp4
avconv -i x.mp4 -s 640x480 -strict experimental xx.mp4
avconv -i input.mp4 -vn -f mp3 output.mp3
avconv -i input.mp4 -vn -c:a libmp3lame -q:a 2 output.mp3


TRASH
========
 cd ~/.local/share/Trash/


XDM
========
sudo add-apt-repository ppa:noobslab/apps
sudo apt-get update
sudo apt-get install xdman




REMOVE NUMBERS FROM FILE NAME
========
for f in [0-9]*; 
do 
mv "$f" "`echo $f | sed 's/^[0-9]*\W*//'`"; 
done



WGET
========
URL FROM A FILE
wget -i url_list.txt

FROM 1 TO 15
wget https://www. kernel.org/pub/linux/kernel/v3.0/linux-3.2.{1..15}.tar.bz2"
RESUME
wget -c "http://www. openss7.org/repos/tarballs/strx25-0.9.2.1.tar.bz2"



GIT COMMANDS
========
git add .
subl new.c
git status 
git commit -m "new"
git remote add origin https:// github.com/profile_name/test.git
git push -u origin master 
git status 
git add *
git status 
git commit -m "new"
git push -u origin master 
history > git



VIRTAL ENVIRONMENT
========
python -m pip install --user virtualenv
pip install --upgrade pip
python -m virtualenv test
source djgirls/bin/activate
deactivate

AIRCRACK
========
airmon-ng start wlan0
airodump-ng mon0
walsh -i mon0
aircrack
apt-get install aircrack-ng
airmon-ng start wlan0
airodump-ng mon0


REAVER
========
tar xvfz reaver-1.4.tar.gz
sudo apt-get install libpcap-dev
2sudo apt-get install libsqlite3-dev
cd reaver-1.4/src
./configure 
make
make install


HOTSPOT DEVICE 
========
https:// askubuntu.com/questions/399796/how-to-install-leo-nano150n-leoxys-mini-usb-wifi-adapter-on-ubuntu

sudo apt-get install build-essential linux-headers-generic git
mkdir ~/RTL8188EU
cd ~/RTL8188EU
git clone git://github.com/lwfinger/rtl8188eu
make
sudo make install
cd ~/RTL8188EU/rtl8188eu
make
sudo make install
sudo cp -v ~/RTL8188EU/rtl8188eu/rtl8188eufw.bin /lib/firmware/rtlwifi/
sudo depmod -a
sudo update-initramfs -u
sudo modprobe 8188eu

