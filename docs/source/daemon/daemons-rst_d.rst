Daemon rst_d
*************

Documentation for the daemons-rst_d daemon in */daemons/rst_d.c*.

Module Information
==================

The RST (reStructured Text) daemon handles finding source files which have been modified and
updating the RST documentation. The intent of this daemon is to do formatting without forcing
new autodoc standards nor introducing RST formatting into MUD help pages.

Functions
=========
.. c:function:: void scan_mudlib()

Recursively searches the mudlib for files which have been changed
since the last time the docs were updated, and recreates the documentation
for those files.


.. c:function:: void complete_rebuild()

Rebuild all the data, regardless of modification time



*File generated by Lima 1.1a4 reStructured Text daemon.*
