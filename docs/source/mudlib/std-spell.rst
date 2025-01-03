Mudlib *spell*
***************

Documentation for the std-spell functions for the mudlib in */std/spell.c*.

Functions
=========
.. c:function:: void set_category(string c)

Sets the category of the spell.
Parameters:
- c: The category of the spell.


.. c:function:: string query_category()

Returns the category of the spell.


.. c:function:: void set_level(int l)

Sets the level of the spell.
Parameters:
- l: The level of the spell.


.. c:function:: int query_level()

Returns the level of the spell.


.. c:function:: void set_name(string s)

Sets the name of the spell.
Parameters:
- s: The name of the spell.


.. c:function:: string query_name()

Returns the name of the spell.


.. c:function:: void extra_reflex_cost(int c)

Sets the extra reflex cost of the spell. A spell
always costs level + reflex_cost to cast.
Parameters:
- c: The reflex cost of the spell.


.. c:function:: int query_reflex_cost()

Returns the reflex cost of the spell.


.. c:function:: int check_reflex(object b)

Checks if the caster has enough reflex to cast the spell.
Parameters:
- b: The caster object.
Returns: 1 if the caster has enough reflex, 0 otherwise.


.. c:function:: int spend_reflex(object b)

Spends the reflex cost for casting the spell.
Parameters:
- b: The caster object.
Returns: 1 if the reflex cost was successfully spent, 0 otherwise.


.. c:function:: mixed valid_target(object target)

Checks if the target is valid for the spell.
Parameters:
- target: The target object.
Returns: 1 if the target is valid, 0 otherwise.


.. c:function:: mixed valid_spell_components(mapping sc)

Checks if the spell components are valid.
Parameters:
- sc: The spell components mapping.
Returns: 1 if the spell components are valid, 0 otherwise.


.. c:function:: mixed valid_circumstances(mixed target, mixed sc)

Checks if the circumstances are valid for casting the spell.
Parameters:
- target: The target object.
- sc: The spell components mapping.
Returns: 1 if the circumstances are valid, 0 otherwise.


.. c:function:: nomask mixed check_valid_spell(int has_target, int has_sc)

Checks if the spell is valid to cast.
Parameters:
- has_target: 1 if the spell has a target, 0 otherwise.
- has_sc: 1 if the spell has spell components, 0 otherwise.
Returns: 1 if the spell is valid to cast, an error message otherwise.


.. c:function:: nomask void set_targets(int targets)

Sets the valid targets for the spell.
Parameters:
- targets: The valid targets for the spell.


.. c:function:: nomask mixed check_valid_target(object target, mixed has_sc)

Checks if the target is valid for the spell.
Parameters:
- target: The target object.
- has_sc: 1 if the spell has spell components, 0 otherwise.
Returns: 1 if the target is valid, an error message otherwise.


.. c:function:: nomask mixed check_valid_spell_components(mapping sc, mixed has_target)

Checks if the spell components are valid for the spell.
Parameters:
- sc: The spell components mapping.
- has_target: 1 if the spell has a target, 0 otherwise.
Returns: 1 if the spell components are valid, an error message otherwise.


.. c:function:: void set_skill_used(string val)

Sets the skill used for casting the spell.
Parameters:
- val: The skill used for casting the spell.


.. c:function:: string query_skill_used()

Returns the skill used for casting the spell.


.. c:function:: void set_magic_skill_used(string val)

Sets the magic skill used for casting the spell.
Parameters:
- val: The magic skill used for casting the spell.


.. c:function:: string query_magic_skill_used()

Returns the magic skill used for casting the spell.


.. c:function:: void set_channeling_time(int t)

Sets the channeling time for the spell.
Parameters:
- t: The channeling time in seconds.


.. c:function:: void set_channeling_interval(int t)

Sets the interval between channeling actions for the spell.
Parameters:
- t: The interval time in seconds.


.. c:function:: void set_cast_time(int t)

Sets the cast time for the spell.
Parameters:
- t: The cast time in seconds.


.. c:function:: int query_cast_time()

Returns the cast time of the spell.


.. c:function:: nomask void delayed_cast_spell(object target, object sc, int success)

Initiates a delayed cast for the spell.
Parameters:
- target: The target object.
- sc: The spell components object.
- success: The success level of the spell casting.


.. c:function:: void continue_channeling(object target, object sc)

Continues the channeling of the spell.
Parameters:
- target: The target object.
- sc: The spell components object.


.. c:function:: void channel_failure(string message)

Handles the failure of channeling the spell.
Parameters:
- message: The failure message.


.. c:function:: int cast_action(mixed *args)

Executes the casting action for the spell.
Parameters:
- args: An array containing the target, spell components, and success level.


.. c:function:: object transient(string name, mixed *args...)

Creates a transient spell object.
Parameters:
- name: The name of the transient spell.
- args: Additional arguments for the transient spell.
Returns: The created transient spell object.


.. c:function:: int test_spell()

Tests if the spell is fully defined and valid.
Returns: 1 if the spell is valid, 0 otherwise.


.. c:function:: void internal_cast_spell(object target, object sc)

Internally handles the casting of the spell.
Parameters:
- target: The target object.
- sc: The spell components object.


.. c:function:: string set_description(string d)

Sets the description of the spell.
Parameters:
- d: The description of the spell.


.. c:function:: string target_to_str()

Converts the valid targets to a string representation.
Returns: A comma separated string representation of the valid targets.


.. c:function:: string cast_time_string()

Converts the cast time to a string representation.
Returns: A string representation of the cast time.


.. c:function:: string reflex_string()

Converts the reflex cost to a string representation.
Returns: A string representation of the reflex cost.


.. c:function:: varargs int spell_skill_rank(object target)

Returns the skill rank for the spell.
Parameters:
- target: (optional) The target object to check the skill rank for. If not provided, defaults to this_body()
(caster). Returns: The skill rank for the spell.


.. c:function:: string query_description()

Returns the description of the spell.



*File generated by Lima 1.1a4 reStructured Text daemon.*
