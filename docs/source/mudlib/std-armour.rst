Mudlib *armour*
****************

Documentation for the std-armour functions for the mudlib in */std/armour.c*.

Module Information
==================

This is the base for creating a piece of armour.  It uses M_WEARABLE to
allow it to be worn, and M_DAMAGE_SINK to allow it to absorb damage.

Functions
=========
.. c:function:: void set_worn(int g)

set_worn(1) causes this object to be worn by whatever is holding it.
set_worn(0) takes it back off again.



*File generated by Lima 1.1a4 reStructured Text daemon.*
