user-callback
=============

During backup process Back In Time can call a user-callback script at different steps.
This callback is ``$XDG_CONFIG_HOME/backintime/user-callback`` 
(by default ``$XDG_CONFIG_HOME`` is ``~/.config``).

#. The first argument is the profile id (1=Main Profile, ...).
#. The second argument is the profile name.
#. The third argument is the reason:

  #. Backup process begins.
  #. Backup process ends.
  #. A new snapshot was taken. The extra arguments are snapshot ID and snapshot path.
  #. There was an error. The second argument is the error code.
     Error codes:

     #. The application is not configured.
     #. A "take snapshot" process is already running.
     #. Can't find snapshots folder (is it on a removable drive ?).
     #. A snapshot for "now" already exist.

  #. On (graphical) App start.
  #. On (graphical) App close.
  #. Mount all necessary drives.
  #. Unmount all drives.
