Command *ls*
*************

Documentation for the ls command in */trans/cmds/ls.c*.

Command
=======

USAGE ``ls [ -a -s -F ] [path]``

This command will show you the files and directories in the
current directory.  You can change the default behavior of ls by
suppplying a valid path, and the optional - arguments.

 |  -l  --  shows file size in bytes and date last modified
 |  -s  --  shows the file size (KB) to the left of the file
 |  -p  --  suppresses / to the right of the directory name (for non-ansi users)
 |  -n  ..  suppresses "invisible" files (names starting with .)

The flags and path are both optional, if you leave off the path
ls assumes you meant the current directory.
You can use wildcards in the path - eg \*.h.

.. TAGS: RST



*File generated by Lima 1.1a4 reStructured Text daemon.*
