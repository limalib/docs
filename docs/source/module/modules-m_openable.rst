Module *m_openable*
********************

Documentation for the modules-m_openable module in */std/modules/m_openable.c*.

Functions
=========
.. c:function:: void do_on_open()

Called from open_with() so modules that inherit from M_OPENABLE
Don't have to catch the "open" hook.


.. c:function:: void do_on_close()

Called from close() so modules that inherit from M_OPENABLE
Don't have to catch the "close" hook.


.. note:: doc forthcoming... (line 9)

*File generated by Lima 1.1a4 reStructured Text daemon.*
