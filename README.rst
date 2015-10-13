user-callback
=============

During backup process Back In Time can call a user-callback script at different steps.
This callback is ``$XDG_CONFIG_HOME/backintime/user-callback`` 
(by default ``$XDG_CONFIG_HOME`` is ``~/.config``).

- The first argument is the profile id (1=Main Profile, ...).
- The second argument is the profile name.
- The third argument is the reason:

  1) Backup process begins.
  2) Backup process ends.
  3) A new snapshot was taken. The extra arguments are snapshot ID and snapshot path.
  4) There was an error. The second argument is the error code.
     Error codes:

     1) The application is not configured.
     2) A "take snapshot" process is already running.
     3) Can't find snapshots folder (is it on a removable drive ?).
     4) A snapshot for "now" already exist.

  5) On (graphical) App start.
  6) On (graphical) App close.
  7) Mount all necessary drives.
  8) Unmount all drives.
