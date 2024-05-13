Introduction
============
For further information, see the `backintime <https://github.com/bit-team/backintime>`_ repository and its `issue tracker <https://github.com/bit-team/backintime/issues>`_.

user-callback
=============

During the backup process, `Back In Time <https://github.com/bit-team/backintime>`_ can call a user-callback script at different steps.
This user-callback script is contained in the file ``$XDG_CONFIG_HOME/backintime/user-callback`` 
(by default ``$XDG_CONFIG_HOME`` is ``~/.config``).

- The first argument is the profile id (1=Main Profile, ...).
- The second argument is the profile name.
- The third argument is the reason:

1. Backup process begins.
2. Backup process ends.
3. A new snapshot was taken. The extra arguments are snapshot ID and snapshot path.
4. There was an error. The fourth argument is the error code.

   Possible error codes are:

   1. The application is not configured.
   2. A "take snapshot" process is already running.
   3. Can't find snapshots folder (is it on a removable drive ?).
   4. A snapshot for "now" already exist.
   5. Error while taking a snapshot (introduced Aug. 17, 2023)
   6. New snapshot taken but with errors (introduced Aug. 17, 2023)

   The optional fifth argument just for errors is the error message.

5. On (graphical) App start.
6. On (graphical) App close.
7. Mount all necessary drives.
8. Unmount all drives.

For implementation details see the source code in the file ``pluginmanager.py]`` (https://github.com/bit-team/backintime/blob/dev/common/pluginmanager.py).

