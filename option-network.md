option-**network**, gathers basic networking data with privacy switch (-z) and looks for network-manager running, copy/paste and execute **all the indented below** `via terminal`, "To View/**Share" the file**, [the instructions are here] (https://github.com/two-dogs/the-kennel/blob/master/to-share.md)
***
`
sudo inxi -U ;
(
 date ;
 echo --opt-network-- ;
 inxi -c0 -z -MSNnxx ;
 echo --rfkill--start ;
 rfkill list ;
 echo --rfkill--end ;
 echo --mintwifi--start ;
 mintwifi ;
 echo --mintwifi--end ;
 echo --dmesg--start ;
 dmesg | grep -Ei 'error|fail|blue|wifi|net:|tcp|udp|eth|wlan|ipv|80211' ;
 echo --dmesg--end ;
 echo --lsmod--start ;
 lsmod | grep -Ei 'bluetooth|wifi|80211' ;
 echo --lsmod--end ;
 echo --hciconfig--start ;
 hciconfig -a ;
 echo --hciconfig--end ;
 echo --search ps NM/Blue start-- ;
 ps aux |grep -Ei 'blue|network' ;
 echo --search ps NM/Blue end-- ;
 date
) > ~/trouble-shoot-history.txt ;
 echo "Done, the log has been saved to ~/trouble-shoot-history.txt"
`
***
[the raw view of the execute structure is here and easier to make out what is going on](https://github.com/two-dogs/the-kennel/raw/master/option-network.md)
