nice-one edit:

just got this working on the raspberry pi v5 using Ubuntu 23.10 server (GNU/Linux 6.5.0-1012-raspi aarch64)

fresh os install then:

###############
#UPDATE SYSTEM#
###############

sudo bash -c 'for i in update {,full-}upgrade auto{remove,clean}; do apt-get $i -y; done'

sudo reboot now

#############
#INSTALL FTP#
#############

sudo apt install vsftpd -y

sudo nano /etc/vsftpd.conf

change listen to YES

IPV6 TO NO

uncomment #write_enable=YES

AND ADD listen_port=21201

#THEN

sudo service vsftpd restart

#get php repo

sudo apt-get install -y language-pack-en-base && sudo export LC_ALL=en_US.UTF-8 && sudo export LANG=en_US.UTF-8 && sudo apt-get install -y software-properties-common

#then

sudo add-apt-repository ppa:ondrej/php

sudo reboot now

#get script & files from https://github.com/arakasi72/rtinst
sudo bash -c "$(wget --no-check-certificate -qO - https://raw.githubusercontent.com/arakasi72/rtinst/master/rtsetup)"

get my rtinst and upload to your home dir, then:
sudo mv ~/rtinst /usr/local/bin/
sudo chmod 755 /usr/local/bin/rtinst
sudo rtinst
