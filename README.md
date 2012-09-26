========
xuserrun
========

Run commands as the currently-active X11 user

Usage: xuserrun <command> [arg1 arg2 ...]

Dependencies:
  systemd
  coreutils

This uses loginctl to determine the active session. If it is an X11 session, then the display and username are obtained from loginctl. `command` and all additional arguments are executed after switching to the active user and setting the DISPLAY variable appropriately.
