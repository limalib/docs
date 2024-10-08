Module *m_messages*
********************

Documentation for the modules-m_messages module in */std/modules/m_messages.c*.

Module Information
==================

The message module.  The correct way to compose and send any messages
To users is using this module, as it will automatically get the grammar
right for each person involved.

Functions
=========
.. c:function:: varargs string compose_message(object forwhom, string msg, object *who, mixed *obs...)

The lowest level message composing function; it is passed the object
for whom the message is wanted, the message string, the *of people
involved, and the objects involved.  It returns the appropriate message.
Usually this routine is used through the higher level interfaces.


.. c:function:: varargs string *action(object *who, mixed msg, mixed *obs...)

Make the messages for a given group of people involved.  The return
value will have one *per person, as well as one for anyone else.
inform() can be used to send these messages to the right people.
see: inform


.. c:function:: void inform(object *who, string *msgs, mixed others)

Given an array of participants, and an array of messages, and either an
object or array of objects, deliver each message to the appropriate
participant, being careful not to deliver a message twice.
The last arg is either a room, in which that room is told the 'other'
message, or an array of people to recieve the 'other' message.


.. c:function:: varargs void filtered_inform(object *who, string *msgs, mixed others, function filter, mixed extra)

Given an array of participants, and an array of messages, and either an
object or array of objects, deliver each message to the appropriate
participant, being careful not to deliver a message twice if the filter
evaluates to true. The 'extra' argument is parsed to the filter function.
The last arg is either a room, in which that room is told the 'other'
message, or an array of people to recieve the 'other' message.


.. c:function:: varargs void filtered_simple_action(mixed msg, function filter, mixed extra, mixed *obs...)

Generate and send messages for an action involving the user and possibly
some objects


.. c:function:: varargs void simple_action(mixed msg, mixed *obs...)

Generate and send messages for an action involving the user and possibly
some objects


.. c:function:: varargs void my_action(mixed msg, mixed *obs...)

Generate and send a message that should only be seen by the person doing it


.. c:function:: varargs void other_action(mixed msg, mixed *obs...)

Generate and send a message that should only be seen by others


.. c:function:: varargs void targetted_action(mixed msg, object target, mixed *obs...)

Generate and send a message involving the doer and a target (and possibly
other objects)


.. c:function:: varargs void targetted_other_action(mixed msg, object target, mixed *obs...)

Generate a message involving the doer and a target (and possibly
other objects), but do not SEND to doer.



*File generated by Lima 1.1a4 reStructured Text daemon.*
