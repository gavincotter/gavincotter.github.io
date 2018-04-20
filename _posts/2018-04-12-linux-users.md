


useradd test
cat /etc/shadow | grep test
test:!:17637:0:99999:7:::

#create a normal user account
useradd test
passwd test
cat /etc/passwd
test::17637:0:99999:7:::



#locked
passwd -l test
cat /etc/passwd
test::17637:0:99999:7:::


#create a system account
useradd --system test
test:!:17637::::::

adduser --system test
test:x:120:65534::/home/test:/bin/false
test:*:17637:0:99999:7:::

* means no password was set
! means the password was disabled




useradd test
no home directory created
passwd test:x:1001:1001::/home/test:
shadow test:!:17637:0:99999:7:::
ENV SHELL=/bin/sh




useradd test -m
directory created and all files in /etc/skell copied over to /home/test
.bash_logout
.bashrc
.profile

passwd test:x:1001:1001::/home/test:
shadow test:!:17637:0:99999:7:::
ENV MAIL=/var/mail/test
USER=test
LANGUAGE=en_IE:en
SHLVL=1
HOME=/home/test
OLDPWD=/root
DBUS_SESSION_BUS_ADDRESS=unix:path=/run/user/1001/bus
COLORTERM=truecolor
LOGNAME=test
_=/bin/su
TERM=xterm-256color
XDG_SESSION_ID=3
PATH=/usr/local/bin:/usr/bin:/bin:/usr/local/games:/usr/games
XDG_RUNTIME_DIR=/run/user/1001
DISPLAY=:0
LANG=en_IE.UTF-8
XAUTHORITY=/run/user/1000/gdm/Xauthority
SHELL=/bin/sh
PWD=/home


/etc/adduser.conf

debian create a system account
adduser --system btc
