Command *targetemote*
**********************

Documentation for the targetemote command in */cmds/wiz/targetemote.c*.

Command
=======

See: :doc:`Command: feelings <feelings>` :doc:`Command: m_messages <m_messages>` :doc:`Command: addemote <addemote>` :doc:`Command: rmemote <rmemote>` :doc:`Command: showemote <showemote>` :doc:`Command: stupidemote <stupidemote>` 

USAGE:  ``targetemote``

This command will create a default emote with the following rules;
  LIV, OBJ, STR, ""

>``targetemote swim``
Added.

Lets look at what was created by that command
>``showemote swim``
 |  "LIV" -> $N $vswim at $t.
 |  "OBJ" -> $N $vswim at $o.
 |  "STR" -> $N $vswim $o.
 |  "" -> $N $vswim.

.. TAGS: RST



*File generated by Lima 1.1a4 reStructured Text daemon.*
