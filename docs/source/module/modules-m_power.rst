Module *m_power*
*****************

Documentation for the modules-m_power module in */std/modules/m_power.c*.

Module Information
==================

This module keeps track of charge and charge expenditure for batteries and other
things that may hold a charge. In your setup() function call:

 |   void setup()
 |   {
 |      ...
 |      set_max_mah(3000);
 |      set_random_mah();
 |   }

To set the maximum mah and set it randomly within the interval from 0 to max.

.. TAGS: RST

Functions
=========
.. c:function:: int is_power_source()

Always returns 1 if this module is inherited.


.. c:function:: void set_rechargable(int r)

Set if power source can be recharged or not.


.. c:function:: int use_charge(int ma)

Spend an amount of charge in the power source.
Returns 1 if successful, otherwise 0 - we're out of power.


.. c:function:: int query_rechargable()

Returns 1 if rechargable, otherwise 0.


.. c:function:: void set_max_mah(int c)

Set the maximum charge the power source will hold. Remember to call
either set_random_mah() or set_mah(number) after this.


.. c:function:: int query_max_mah()

Returns the max mah of the power source.


.. c:function:: void set_mah(int c)

Set a specific charge for the power source. Number will be clamped
between 0-max mah always.


.. c:function:: void set_random_mah()

Sets the power source to a random mah betwen 25%-100%.
The chance to be 100% is >25%.


.. c:function:: int query_mah()

Returns the current charge of the power source.



*File generated by Lima 1.1a4 reStructured Text daemon.*
