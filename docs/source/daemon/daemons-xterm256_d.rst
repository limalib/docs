Daemon xterm256_d
******************

Documentation for the daemons-xterm256_d daemon in */daemons/xterm256_d.c*.

Module Information
==================

This daemon handles the 256 Colours of XTERM code.

Functions
=========
.. c:function:: varargs string substitute_ansi(string text, string mode)



.. c:function:: varargs string substitute_colour(string text, string mode)

Substitute_colour takes a string with tokenized xterm256 colour
codes and a mode, parses the tokens and substitutes with
xterm colour codes suitable for printing.
available modes are:

  plain - strip all colour and style codes
  vt100 - strip only colour codes
  xterm - replace all tokens with xterm256 colour codes
  ansi  - fall back to ansi colour codes



*File generated by Lima 1.1a4 reStructured Text daemon.*
