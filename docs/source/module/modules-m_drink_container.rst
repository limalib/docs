Module *m_drink_container*
***************************

Documentation for the modules-m_drink_container module in */std/modules/m_drink_container.c*.

Module Information
==================

This module is almost obsolete.
Use m_fluid_container instead, unless
you want no fluid associated with your
drink container.

Functions
=========
.. c:function:: void set_needs_contents(int x)

If needs_contents is 1, then the container can only be drunk from if it
contains a drink.  Otherwise the 'drink' is assumed to be handled as
part of the container itself (either by also inheriting M_DRINKABLE or
otherwise).



*File generated by Lima 1.1a4 reStructured Text daemon.*
