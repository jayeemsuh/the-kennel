### userspace
option-**userspace**, 
copy/paste and execute `via terminal` the indented below in order to gather **_session/desktop/userspace output_** which may help in trouble-shooting the issue you are having, the "To **Share" instructions** are [here.](https://github.com/two-dogs/the-kennel/blob/master/to-share.md).

`
sudo inxi -U ;
(
  date ;
  echo --userspace-- ;
  inxi -c0 -MSGrsxxtcm20 ;
  grep -B1 -Ei 'error|fail' ~/.xsession-errors && date
  ) > ~/trouble-shoot-history.txt | echo "Done, the log has been saved to ~/trouble-shoot-history.txt"
  `
***
