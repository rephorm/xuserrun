xuserrun
========

Run commands as the currently-active X11 user

Usage: xuserrun <command> [arg1 arg2 ...]

Dependencies
------------

  * systemd
  * coreutils

Overview
--------

This uses loginctl to determine the active session. If it is an X11 session,
then the display and username are obtained from loginctl. `command` and all
additional arguments are executed after switching to the active user and
setting the DISPLAY variable appropriately.

Example Usage
-------------

On arch-linux, ACPI events are handled by `/etc/acpid/handler.sh`, which runs as root. To send notifications the the current user, add a line to this script like:

    /path/to/xuserrun notify-send "AC Adapter" "Plugged in"


Limitations
-----------

This currently assumes that the user is on the default loginctl 'seat', and
will need to be modified if you require multi-seat support (see [Multi-Seat on
Linux][multiseat] for more information).

[multiseat]: http://www.freedesktop.org/wiki/Software/systemd/multiseat
