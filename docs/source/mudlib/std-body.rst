Mudlib *body*
**************

Documentation for the std-body functions for the mudlib in */std/body.c*.

Functions
=========
.. c:function:: int is_body()

Is this a body object?


.. c:function:: nomask object query_link()

Return our link object


.. c:function:: nomask string query_plan()

Returns our plan


.. c:function:: nomask void set_plan(string new_plan)

Sets our plan


.. c:function:: void save_me()

Saves us :-)


.. c:function:: void remove()

Handle mailboxes and the last login daemon, as well as the normal stuff


.. c:function:: void quit()

Quit the game.


.. c:function:: void net_dead()

This function is called when we lose our link


.. c:function:: void reconnect(object new_link)

This function is called when we get our link back


.. c:function:: int id(string arg)

id(s) returns 1 if we respond to the name 's'



*File generated by Lima 1.1a4 reStructured Text daemon.*
