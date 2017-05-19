# Summary
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


# Features

- Simulates the interactions between players during a turn.
  - Sets up Action windows for the current player.
  - Sets up Action windows for the non-current player.
- Allow events to exist as "hooks" for other processes to be invoked.
  - Based on events, enable ways to interconnect mutliple action windows and/or other systems.
- Provides a drop-in process for Erlang game systems that want to leverage turn-based interactions between players.
- Builds a template to follow for using the Snowflake technique


# Personas

1.  **Coders** - Looking for a start into using a gen_statem behavior in erlang.
2.  **Game Designers** - Looking for a simple, drop-in Game-Engine to run their turn-based game.
3.  **Game Developers** - Looking for something extensible, to attach their game idea to, but without the hassle of building something from scratch.
4.  **Developers** - Looking for a template of using the snowflake method to start their projects, and vette the use of this technique with the success of the project.
5.  **Contributors** - Recognizing a good idea, and willing to help see it come to fruition.  Also, adding to the community by providing advice and guidance.


# User Stories

1.  As a **Coder**, I need to leverage the deployment pipeline for this process in Erlang
    - Investigate Rebar package management
    - Investigate ErlangVM (BEAM) deployment
    - Build gen_statem process
    - Deploy and Run gen_statem process
2.  As a **Game Designer**, I need to use the Turn logic in this process to augment my game design.
    - Implement TurnStarted
    - Implement TurnCompleted
    - Implement Phase
    - Implement Action Window for current player
    - Implement Action Window for non-current player
3.  As a **Game Developer**, I need to leverage the Action Windows in this process to expose other systems to occur during the course of the phase
    - Implement TurnAffected
4.  As **Developer**, I need access to the documentation around the snowflake technique and how it was used to design the project.
    - Include Snowflake documentation 
5.  As a **Contributor** I have ample documentation for adding insight and providing guidance from a technological and use-case perspective.
    ~~- Add licensing to the project~~
