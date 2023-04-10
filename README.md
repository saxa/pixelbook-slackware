# pixelbook-slackware
Stuff specific to slackware OS for the Google Pixelbook Eve

In this repository you will find my slackbuilds and scripts for Slackware OS I used to get my Google's Pixelbook EVE model configured.
I will also try to set all that info onthe repo wiki.

* GRUB

To make grub appear in a way that is readable we have to add/uncomment the following 
lines in the /etc/default/grub file.

In the line below put the 2400x1600 resolution. To check the supported resolutions
you can press c in grub and issue the vbeinfo.

GRUB_GFXMODE=2400x1600,auto 

Then uncomment the line below:

GRUB_FONT=/usr/share/grub/dejavusansmono.pf2

And rebuild grub.cfg with grub-mkconfig -o /boot/grub/grub.cfg .

* AUDIO with pipewire

To make audio working with pipewire you have to firstly force pipewire work in 16bit mode
by uncommenting the line below in /usr/share/pipewire/media-session.d/alsa-monitor.conf:

audio.format = "S16LE"

Then issue as root pipewire-enable.sh and re-login.

Rgds
Saxa
