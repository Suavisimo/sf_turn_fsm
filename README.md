# sf_turn_statem
A state machine for the cycle of a multiplayer turn-based game, implemented in Erlang. (15)


# Motivation

#### Why a State Machine?
At its core, this process will receive input, determine a mutation of internal state, and produce output.  At minimum, it will be signaled to the start of the turn, allow player(s) an action window and signify the end of the turn.  This representation is best modeled with a state machine.  The choice to use `gen_statem` is deliberate, as it allows for an "infinite" system which listens for events, as opposed to using a specific start and stopping point.

#### Why a Multiplayer Turn-based game?
For many, playing games is fun only when playing with others.  Whether that means playing against another Human, or playing against an AI opponent, the desire to have a true player to compete against, or cooperate with is a fundamental concept for this project. While embracing the concept of multiplayer, recognizing the difficulty of real-time multiplayer is equally important.  Therefore, the constraint of turn-based is to provide a known experience, from which there are countless examples to draw from.  Being able to leverage existing turn-based games to provide guidance is a huge asset.

#### Why Erlang?
Out of the box, Erlang provides all the tools required to build a living, distributed system.  Systems built in Erlang can be composed to create suites of interchangable rules, a platform upon which to experiment with mechanics and aestetics, and emergent and unique gameplay experiences.

#### Why Snowflake?
Many times a project is abadoned in the concept phase.  Possibly due to lack of motivation, possibly due to lack of fleshing out the concept.  The attempt to use Snowflake is to at minimum provide a way to document the thought process behind the project, in hopes that worse case (abandonment), it is carried on by those who share similar views.
