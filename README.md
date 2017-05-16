# sf_turn_statem
A state machine for the cycle of a multiplayer turn-based game, implemented in Erlang. (15)


# Motivation
#### Why a State Machine?
At its core, this process will receive input, determine a mutation of internal state, and produce output.  At minimum, it will be signaled to the start of the turn, allow player(s) an action window and signify the end of the turn.  This representation is best modeled with a state machine.  The choice to use `gen_statem` is deliberate, as it allows for an "infinite" system which listens for events, as opposed to using a specific start and stopping point.


#### Why Erlang?
Out of the box, Erlang provides all the tools required to build a living, distributed system.  Systems built in Erlang can be composed to create suites of interchangable rules, a platform upon which to experiment with mechanics and aestetics, and emergent and unique gameplay experiences.
