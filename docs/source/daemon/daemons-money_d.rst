Daemon money_d
***************

Documentation for the daemons-money_d daemon in */daemons/money_d.c*.

Module Information
==================

The money daemon manages the legal types of money within the game and their
exchange rates.

The money system consists of currencies and denominations.

Different currencies can only be exchanged at a bank (for a fee) and
vendors only use one currency.  You can pay with any of the
denominations of the vendor's currency though and you get change if
needed.  If you want to drop or give money to somebody you can only
use the denominations which you really have though.

Each currency consists of its name, the plural name, a list of
denominations and an exchange rate.  By default a currency has a base
denomination with the same name and the exchange rate factor 1.0.  The
exchange rate is the value of one unit of a denomination of a currency
with factor 1.0.  For example if the exchange rate of dollars is 1000
then 1 dollar is worth as much as an object with set_value(1000).

Each denomination consists of its name, the plural name to use, and an
exchange rate factor relative to the base denomination of the currency
(e.g. the base denomination has the factor 1.0).  A denomination cent
would have the factor 0.01 for example which means 1 cent is worth as
much as an object with set_value(10) (if the exchange rate of dollars
is 1000).  Each denomination belongs to only one currency.

Currencies are administrated with admtool at daemons/currency.

When a new currency is created in admtool (by "add currency" or "add a
denomination to a currency") the exchange rate is set to 1000.  If
"add currency" a base denomination is added.  If you want to change
some property of a denomination or the plural of a currency just add
it again with the same name.

Objects have an inherent "value".  This is then translated into a
particular currency via that currency's value.actual exchange rate.

Currencies have different denomiations, e.g. dollar have dollar and cent.
Calculation is always based on the lowest denomination. Functions for
displaying a currency with denominations are provided

Functions
=========
.. c:function:: string singular_name(string name)

singular_name returns the canonical name for a denomination/currency
e.g. lover case, without spaces and singular.


.. c:function:: nomask int query_exchange_rate(string type)

Returns the exchange rate to map from an object's inherent value to its
actual value in a particular currency.  The value returned is the number
of units this currency is worth.


.. c:function:: nomask string *query_currency_types()

Returns the names of the currencies that are valid within the mud


.. c:function:: varargs nomask string *query_denominations(string type)

Returns the array of denominations of a currency
or all available denominations


.. c:function:: nomask int is_currency(string name)

tests if name is a currency


.. c:function:: nomask int is_denomination(string name)

tests if name is a denomination


.. c:function:: nomask string query_currency(string name)

Returns the currency of a denomination


.. c:function:: nomask string query_plural(string name)

Returns the plural name of a denomination


.. c:function:: nomask float query_factor(string name)

Returns the exchange rate factor of a denomination


.. c:function:: varargs nomask void add_currency(string type, string plural, int flag)

Add a currency to the money system. The base denomination with the same
name will be created too if flag is 0.


.. c:function:: nomask void remove_currency(string type)

Removes a currency from the money system.


.. c:function:: nomask void set_exchange_rate(string type, int rate)

Set the exchange rate (that is the value) of a currency


.. c:function:: void add_denomination(string type, string name, string plural, float factor)

add a denomination to a currency


.. c:function:: void remove_denomination(string name)

removes a denomination from a currency


.. c:function:: nomask string denomination_to_string(int amount, string type)

create a string with correct use of plural from an amount of a denomination.


.. c:function:: mapping calculate_denominations(float f_amount, string currency)

calculate denominations which add up to a certain amount.


.. c:function:: varargs nomask string currency_to_string(mixed money, string currency)

create a string with denominations from an amount of money.
The money is a mapping from denomination to amount or a float.
If the currency is not 0 only money of that type of currency is regarded.
The output is only sorted if you specify the currency.


.. c:function:: mapping *handle_subtract_money(object player, float f_amount, string type)

substracts an amount of currency from a player and adds change.
returns an array of two mappings: substract and change, which
consist of the denominations which were used.



*File generated by Lima 1.1a4 reStructured Text daemon.*
