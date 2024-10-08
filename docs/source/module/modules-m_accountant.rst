Module *m_accountant*
**********************

Documentation for the modules-m_accountant module in */std/modules/m_accountant.c*.

Module Information
==================

The accountant module includes almost everything that is needed for a
bank.  Only ``set_currency_type()``, ``set_exchange_fee()``, ``set_bank_id()``, and
``set_bank_name()`` are needed to define the bank actions.

Your accountant should inherit from LIVING or ADVERSARY.

.. TAGS: RST

Functions
=========
.. c:function:: void set_currency_type(string currency)

Sets the type of currency the bank will deposit.


.. c:function:: string query_currency_type()

Queries the type of currency the bank deposits.


.. c:function:: void set_exchange_fee(float fee)

The fee (in percent) is deducted when exchanging different currencies.


.. c:function:: void set_bank_id(string id)

The id is the identifier used with ACCOUNT_D for deposits.


.. c:function:: void set_bank_name(string name)

The name is used in the texts for the players.


.. c:function:: void show_money()

Prints the currencies carried and in the bank for ``this_body()``.


.. c:function:: void show_rates()

Printes rates defined in the MONEY_D.



*File generated by Lima 1.1a4 reStructured Text daemon.*
