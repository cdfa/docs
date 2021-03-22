Exposing host directories
=========================

Anbox reads a file similar to ``fstab`` called ``bindtab`` from ``<data-path>/bindtab`` (for example ``/var/snap/anbox/bindtab``) to bind directories in the android file system to those on the host.
The file follows the ``fstab`` format with a few extra options described in the ``lxc.mount.entry`` section in the `LXC documentation <https://linuxcontainers.org/lxc/manpages/man5/lxc.container.conf.5.html>`_.
The file is read and passed to the internal LXC configuration.
It does not support inline comments and the host directory should be an absolute path.

Example:

.. code-block:: text

    # This file doesn't support inline comments
    # and it requires an absolute path for the host directory

    # <host>   <target in anbox> <type> <options>                   <dump>  <pass>
    /home/data data/media/0/data none   bind,create=dir,optional    0       0


