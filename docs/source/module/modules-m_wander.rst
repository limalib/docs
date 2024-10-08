Module *m_wander*
******************

Documentation for the modules-m_wander module in */std/modules/m_wander.c*.

Module Information
==================


The wander module designed to be included by NPC's which allows monsters
to wander throughout various areas in the gaming area.

Functions
=========
.. c:function:: void set_wander_area(mixed areas)

Set the area(s) that an NPC can wander in.  If this is not set
it is assumed that the NPC can wander anywhere without area
restrictions.


.. c:function:: void add_wander_area(mixed areas)

Add area(s) which an NPC can wander in.  See set_wander_area()


.. c:function:: void remove_wander_area(string *area...)

Remove area(s) which an NPC can wander in.  See set_wander_area()


.. c:function:: void clear_wander_area()

Clear the area(s) in which an NPC can wander in.  Effectively
this allows the NPC to wander anywhere.  See set_wander_area()


.. c:function:: string *query_wander_area()

Returns an array of areas in which may wander.
See set_wander_area()


.. c:function:: void set_wander_time(mixed time)

Sets the time between an NPC's movements.

If the argument is an int it sets the time in seconds.

If the argument is a function pointer, the function
needs to evaluate to an int.  The fpointer is evaluated
during runtime.


.. c:function:: int query_wander_time()

Returns an integer which is the amount of time to be used
for the interval between movements.  It does not return
the time til the next movement.  query_wander_time()
will not return 0, if the return is 0 or less
ZERO_RETURN (refer to the M_WANDER file) will be returned


.. c:function:: void set_max_moves(int i)

Sets the maximum number of moves a monster will make without
running into a player.  This prevents too many NPCs
moving around for no reason.  If the argument is 0 it assumes
that the NPC will not stop moving, regardless of player
interaction


.. c:function:: int query_max_moves()

Returns the number of moves an NPC will make without player
interaction before stopping.


.. c:function:: void cease_wandering()

Stops an NPC from wandering.
start_wandering() is required to make the NPC move again


.. c:function:: void stop_wandering()

Stops an NPC from wandering.
If you use this function the npc will start moving again if a PC enters the
room.


.. c:function:: void start_wandering()

Starts an NPC wandering


TODO list
=========

1. Something to have the NPC's open doors or unlcok doors.  It is possiblethat this belongs in a separate module.


*File generated by Lima 1.1a4 reStructured Text daemon.*
