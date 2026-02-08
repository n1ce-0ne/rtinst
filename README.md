#get script

sudo bash -c "$(wget --no-check-certificate -qO - https://raw.githubusercontent.com/arakasi72/rtinst/master/rtsetup)"

#add my rtinst to home dir

sudo mv ~/rtinst /usr/local/bin/ && sudo chmod 755 /usr/local/bin/rtinst && sudo rtinst
