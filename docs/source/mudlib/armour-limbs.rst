Mudlib *limbs*
***************

Documentation for the armour-limbs functions for the mudlib in */std/adversary/armour/limbs.c*.

Functions
=========
.. c:function:: object *query_armours(string s)

object *query_armours(string s);
Returns the armours that are covering limb 's'.


.. c:function:: void update_cover(object what)

Update the cover of a piece of equipment using this function should the cover change between wearing it and it being
removed and worn again.


.. c:function:: nomask int wear_item(object what, string where)

nomask int wear_item(object what, string where);
Forces the adversary to wear 'what' on its 'where' limb.


.. c:function:: nomask int remove_item(object what, string where)

nomask int remove_item(object what, string where);
Removes armour 'what' from the 'where' limb.


.. c:function:: int has_body_slot(string slot)

int has_body_slot(string slot);
Returns 1 if the body slot is a valid one.


.. c:function:: string *query_armour_slots()

string *query_armour_slots()
Returns all valid armour slots on an adversary.



*File generated by Lima 1.1a4 reStructured Text daemon.*
