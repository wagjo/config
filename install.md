* install OS, network, Google chrome, browse to this page :)
* configure chrome
    * sync
    * set download folder to desktop
    * add to panel
* mount /data
    * get UUID - sudo blkid /dev/sdb1
    * sudo gedit /etc/fstab
    * UUID=34732001-487f-4446-854f-642026ed3bc3   /data   ext4   defaults   0   0
* mount /backup
    * get UUID - sudo blkid /dev/sda1
    * sudo gedit /etc/fstab
    * UUID=1619cb1a-c0fb-4744-90a1-e7eb1e0b8045   /backup   ext4   defaults   0   0
* SSD support
    * add `defaults,noatime,discard` in `/etc/fstab`
    * see current scheduler, `cat /sys/block/sdX/queue/scheduler`
        * should be NOOP of Deadline
* up to date system
    * `sudo apt-get update`
    * `sudo apt-get upgrade`
    * `sudo apt-get dist-upgrade`
* restricted drivers
    * `driver-manager`, set hw display driver
* remove old linux kernels
    * `dpkg -l | grep linux-image` and review kernels
    * `sudo apt-get purge linux-image-x.x.x-x-generic`
* boot menu timeout
    * `sudo gedit /etc/default/grub` and change timeout to 1
    * `sudo update-grub`
* update, upgrade and install new apps
    * `sudo add-apt-repository ppa:ubuntu-wine/ppa`
    * `sudo apt-get update`
    * `sudo apt-get upgrade`
    * `sudo apt-get install mc vlc skype audacious k3b emacs24 gimp git cups-pdf subversion ttf-mscorefonts-installer openvpn wine1.6 gitk virtualbox-4.2`
* remove redundant apt
    * `sudo apt-get autoremove`
    * `sudo apt-get autoclean`
    * `sudo apt-get purge`
* fonts
    * `mkdir ~/.fonts`
    * `sudo ln -s /data/safe/fonts ~/.fonts/fonts`
    * `fc-cache -fv`
* system configure
    * set workspaces in hot corner
    * `cinnamon-settings`
        * background - change
        * applets - trash, workspace switcher
        * hot corners - disable
        * screensaver - remove lock
        * apps and media - set vlc
        * workspaces - cycling, primary monitor
        * regional-settings - add slovak and german layout, change switch layout combo to `left alt-left shift`
        * firewall - enable, add ports: skype, transmission, http, https, ssh, dns(54)
        * networking - wireless off
        * color profiles - configure
        * printers - add (when printer is turned on)
    * configure terminal
        * remove menubar, bind f11 and f12, set fonts and font size
* symbolic links
    * sudo ln -s /data/safe /safe
    * sudo ln -s /data/local /local
    * sudo ln -s /data/bla /bla
    * sudo ln -s /data/safe ~/safe
    * sudo ln -s /data/local ~/local
    * sudo ln -s /data/bla ~/bla
    * sudo ln -s ~/Desktop /desktop
    * sudo ln -s /data/safe /s
    * sudo ln -s /data/local /l
    * sudo ln -s /data/bla /b
    * sudo ln -s ~/Desktop /d
* copy stuff
    * `mkdir ~/.ssh`
    * `cp /data/safe/access/ssh-keys/* ~/.ssh/`
    * `cp -R /data/safe/config/desktop/* ~/Desktop`
    * `cp /data/safe/config/git/.gitconfig ~`
    * `sudo cp /data/safe/access/openvpn/openvpn-tuke /usr/local/bin/`
* ip aliases
    * `sudo gedit /etc/hosts`
    * 147.232.105.76 hi
* crashplan - install
    * /backup for backups (/backup/safe, /backup/local, /backup/inbound)
    * adapt to previous pc
    * `sudo gedit /etc/sysctl.conf` `fs.inotify.max_user_watches=1048576`
* lein
    * `wget https://raw.github.com/technomancy/leiningen/stable/bin/lein`
    * `chmod +x ./lein`
    * `sudo cp ./lein /usr/local/bin/`
* oracle java
    * sudo add-apt-repository ppa:webupd8team/java
    * sudo apt-get update
    * sudo apt-get install oracle-java7-installer
    * sudo gedit /etc/profile
        * `JAVA_HOME=/usr/lib/jvm/java7-oracle`
        * `PATH=$PATH:$JAVA_HOME/bin`
        * `export JAVA_HOME`
        * `export PATH`
* emacs
    * copy /data/safe/config/emacs.d to ~/.emacs.d
* wuala
* playonlinux

