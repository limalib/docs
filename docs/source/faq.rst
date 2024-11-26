Frequently asked questions
==========================

.. contents::
   :local:

This FAQ describes commands in shorthand like
:menuselection:`menu --> i --> f` 

This tells you the commands you need to type and in which order. In this case first ``menu``
then ``i`` and then ``f``.

..
  Frequently asked questions should be questions that actually got asked.
  Formulate them as a question and an answer.
  Consider that the answer is best as a reference to another place in the documentation.

Initial woes
------------

I compiled the driver, what now?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

After running the ``rebuild`` script under ``adm/dist/`` you should:
   1. Edit ``config.mud`` file in same directory to adapt your settings.
   2. Edit the MUD ``name :``
   3. Change the default port to fit your server ``external_port_1: telnet ____``.

That's it! Run the mud by running ``./run`` or ``./run bg`` to run the MUD in a loop
in the background. To stop it later, just do ``./run stop``.


Why is IMUD_D complaining and how to fix it?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

IMUD_D requires a valid email set in ``/include/config.h`` under:

.. code-block:: c

   /* The administrator(s)' email address(es).
    * NOTE: This is required to be changed in order to have a working
    * I3/IMUD_D system. Must be changed for anything to work!
    */
   #define ADMIN_EMAIL "billg@microsoft.com"

Once that has been changed, log in to your MUD, and do 

   |  update \`IMUD_D\`

and it should then load. If you are in doubt about setting ADMIN_EMAIL correctly, you can
print it from your wizard shell like this:

   |  @ADMIN_EMAIL

And it will print your define.

Why am I getting "Too long evaluation. Execution aborted."?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This is usually caused by your MUD host being a bit on the slow side, and slowing down
the call_out() rate the daemons use can help this. Go to ``/include/config.h``
and change this:

.. code-block:: c

   /* Delay factor for DAEMON call_outs(). 
    * Some daemons may be a bit too greedy for your machine causing:
    * "Too long evaluation. Execution aborted."
    * If you are getting these increase this number to 5, or 10.
    * Otherwise, enjoy your powerful machine, and keep it at 1.
    */
   #define TOO_GREEDY_DAEMONS 1

Change the 1 here to a higher number that will make the issue go away. You can try
5 or 10, and then possibly reduce it a bit once the errors stop nagging you.

Alternatively, upgrade your hosting to a bigger potato. 🥔

How do I get the didlog working?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

:menuselection:`didlog -newversion 0.0.1`
:menuselection:`I did something`

When you first start the MUD, you will get a message like:

    |  No active mudlib version. Set your first version with:
    |  didlog -newversion 0.0.1
    |  didlog -help (for more)

This is the didlog system complaining that you need to set a new version. The didlog
is a system where you and your team of wizards can log your changes and make it easier
to cooperate. First, create a new version:

    |  didlog -newversion 0.0.1
    |  I created the first didlog for version 0.0.1! Woo!

Yes, "I" is a command, try it out, like above!

This will give you a warning ``Sorry, but only full wizards may use the didlog.``. 
But you are an admin? What is going on? Simple, LIMA supports guest wizards, and
full wizards and guest wizards are separated by having a home directory. So, 
go create a directory for yourself.

    |  cd /wiz
    |  mkdir bob

If your name is Bob - use the right name here, obviously. Then try didlog again:

    |  I tests the didlog system.
    |  didlog

Now, you can see your didlog entry in the didlog, and you will not see the warning
when logging in again. Talk to your wizard team on when to create a new version 0.0.2
or even 1.0 at some point. Happy didlogging!

.. tip::

    You can undo a didlog by doing ``@DID_D->someone_didnt()``, if you regret
    or one of your fellow developers made a boo-boo.

Administration
--------------

How do I make someone admin?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

:menuselection:`admtool --> 1 --> d --> a [user] admin`

When you first logged in, you were automatically set to be admin. The 
:doc:`who <player_command/who>` command will confirm this.

To make another person admin, add them to the admin domain using the admtool.
They need to be a wizard already to become an admin.

.. figure:: images/make_admin.png
  :width: 400
  :alt: Make someone admin.

  Example of the making an existing wizard admin.

How do I (de)wiz someone?
~~~~~~~~~~~~~~~~~~~~~

:menuselection:`admtool --> 1 --> u --> w [name]`
:menuselection:`admtool --> 1 --> u --> d [name]`

If you have defined ``AUTO_WIZ`` in ``/include/config.h``, everyone logging In
will be a "guest wizard". If you want to make them full wizards, you need to create
a home directory under /wiz/ matching their login name.

If you have turned off ``AUTO_WIZ``, you can use the :doc:`admtool <command/admtool>`
to change players into wizards or vice versa. Open the admtool, go to privilege 1 
(that is admin only), go to user, then use the "wiz a user" option to wiz or "dewiz"
if needed.

A wizard has issues writing to his folder under /wiz?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

:menuselection:`admtool --> 1 --> u --> d [name]`
:menuselection:`admtool --> 1 --> u --> w [name]`

The wizard will get an error about not being able to write to their folder even when it was created:

   |  ``Permission denied: /wiz/tsath/exec.c.``

The most likely cause of this is that you have ``AUTO_WIZ`` on, and you created the folder manually.
The ``SECURE_D`` still needs to assign permissions for the wizard to the folder. The simple way
of fixing this is to dewiz and wiz them again using the :doc:`admtool <command/admtool>`.

.. note::

    This permissions could be added automatically when ``AUTO_WIZ`` is on as soon as the wizard
    join the MUD. This is not a great idea, since you will likely accumulate a lot of unused security
    rules for people that just stopped by and left, never to be seen again.

    You know who is staying and gets to be a full wizards, and who is just a guest - the system
    cannot know.

What does USE_INTRODUCTIONS change in config.h?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Enabling this option in ``config.h`` hides player names for other players in some very specific situations:
   1. Players passing through rooms (entering and leaving).
   2. Players saying something in rooms with other players.
   3. Players whispering to other players in rooms.

So, as an example, a player whispering another player in a room will be seen by other players as:

   |  A strong orc whispers something to a tall beautiful elf.

The players can introduce themselves to each other via the ``introduce`` verb. Either to one person in the room
or the entire room. After being introduced, they will show up normally by name.

LIMA relies heavily on a centralized parsing structure where all messages for receivers are created at once.
The parsing allows the messages to be created for the sender, the other person involved, 
and the rest of people in the room. This system is very effective, and widely used for 
combat, emotes, verbs and  other in-room actions and is not recommended to be changed.

Short version: If players want to keep their identity hidden, do not do emotes or actions.
