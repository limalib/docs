Mudlib *menu*
**************

Documentation for the std-menu functions for the mudlib in */std/menu.c*.

Module Information
==================

Fancy menu, loosely based on /std/menu by John Viega (rust@virginia.edu) from 1995.

Several examples for how to use this module in /obj/mudlib.
"help","?","HELP","h" will always print out the menu again.
Implement "h" shortcut as a standard to provide additional help text for your menu.
"q" should always get the user out of the menu, unless you have a very good reason.

This object consists of menus, that hold sections, that hold the menu items.
Create the menu, sections and items, and add the sections to the menus,
then add the menu items to the appropriate sections.

Sections have colours you can specify via the codes in ``palette``, but you can also
use "warning", "accent" and "title" to reuse the theme colours the user has picked
if you do not want to specify new section colours that risk not fitting the themes.

Functions
=========
.. c:function:: void user_is_active()

Called when the user is active in the menu.
Can be overriden for your own purposes.



*File generated by Lima 1.1a4 reStructured Text daemon.*
