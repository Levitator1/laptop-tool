laptop-tool
===========

_A script that enables screen brightness keys and/or automatic touchpad-blocking for some laptops
under some Linux distributions, especially the ASUS Vivobook 15 under Debian Buster_  
Jose Batista 2020  

Here we provide two main functions intended to improve the usability of an Asus Vivobook 15
on Debian Buster. However, these may prove useful on other configurations. Try it and find out.

Firstly, we provide the "brightness\_keys" feature, which enables the otherwise unresponsive
backlight keys, which on an the Asus Vivobook 15 are the fn-F4 and fn-f5 keys.
We accomplish this by adding acpid hooks for the keystrokes and we route them to a script
which talks to sysfs to bump the hardware brightness up and down in fixed increments.
We can autodetect the key events, so your device need not have the exact same keys.
Based on concept here: https://ptc-it.de/screen-brightness-workaround/

Secondly, we offer the "synd" function, which configures the Elantec or Synaptics touchpad
to shut off whenever you are typing, so that accidental contact will not produce spurious
input events which otherwise make text editing and other things a nightmare.
We accomplish this by installing an Xsession script which starts syndaemon for every
new X11 session on the system. The delay with which the touchpad is re-enabled is
adjustable, and is specified in decimal or float seconds.


LICENSE
=======

Do whatever. If this script nukes your system, it's your fault. We make an effort to
warn before any files are overwritten, but there is no guarantee that our choice
of file names will not conflict with some other application or OS, now or in the future.
So, run without -f initially and make note of any potential conflicts.

