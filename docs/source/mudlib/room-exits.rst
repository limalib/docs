Mudlib *exits*
***************

Documentation for the room-exits functions for the mudlib in */std/room/exits.c*.

Functions
=========
.. c:function:: void set_default_exit(mixed value)

Set the default exit message (the message given when someone goes a direction
with no exit).  This should be a string or a function ptr returning a string.


.. c:function:: int has_default_exit()

returns true if the room has a default exit error


.. c:function:: string show_exits()

Return a string giving the names of exits for the obvious exits line



*File generated by Lima 1.1a4 reStructured Text daemon.*
