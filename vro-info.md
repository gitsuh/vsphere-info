# Resetting vRO 7.3 ROOT password

## change bootloader settings
- append init=/bin/bash to kernel line
- boot into new defined shell

- - -

## reset account lockout with pam_tally
- pam_tally --user root --reset
- passwd root
- enter new password

- - -

## disable auto lockout
- vi /etc/pam.d/common-auth
- comment out line with pam_tally2.so

- - -

## reboot in /bin/bash alternative way
- mkfifo /dev/initct 
- reboot -f
