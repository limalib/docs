Command *dbxvars*
******************

Documentation for the dbxvars command in */trans/cmds/dbxvars.c*.

Command
=======

USAGE:
    ``dbxvars <ob> <var>``

Finds functions in an objects, e.g.:

 |   ``dbxvars /std/body name``
 |   Matches:
 |   proper_name         : 0
 |   old_fnames          : ({ /* sizeof() == 2 */
 |   "/obj/shells/wish",
 |   "/obj/pshell"
 |   })
 |   name                : 0
 |   corpse_filename     : "/std/corpse"
 |   invis_name          : 0
 |   nickname            : 0

.. TAGS: RST



*File generated by Lima 1.1a4 reStructured Text daemon.*
