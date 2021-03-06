An implementation of the Cheap Ass Game: Starbase Jeff
======================================================

This is a project of love, and I claim no copyright over the
original game or its bits.

Implemented
-----------
 * A few basic record and macro definitions
 * Create a new, sorted deck of cards
 * Really simple testing harness
 * Randomized deck
 * Game and session record constructors
 * Started text-based interface for getting player count
 * Markdown version of this README
 * Text display hand
 * Board structure and table set
 
TODO
----
 * Nearly everything
 * Game loop
 * Constructors for other records
 * Text interface to playing a game
 * Text display game state
 * Text display player state
 * A way to use a file as input to the text interface for testing
 * Design turn structure
 * Execute a turn
 * Legal card placement test
 * Legal sabotage test
 * Payment route indication
 * Payment route selection
 * Overall game play structure and timeline
 * Game end, clean-up and start next game
 * Non text-based interface
 * Simple AI (random card, random placement)
 * Smart AI
 * AIs with different playstyles
 * Advanced Jeff capsule rules
 * Player database and dbi
 * Proper Erlang documentation for modules, methods, data types, etc
 
Getting Started with the Erlang Shell
-------------------------------------
```
    cd("git_checkout_dir/ebin").
    make:all([load]).
    ok = sbjeff_test:unit_test().

    % create some objects in the shell
    Deck = sbjeff_cards:shuffled_deck().
    Player = sbjeff_player:new("Player_Name").
    % attempt to play a game
    sbjeff_text:start().
```

Development Process
-------------------
 * When creating a new module:
   1. add the new module name to the modules list in `ebin/sbjeff.app`
   2. create a matching _test module in the test folder with a unit_test method that
      returns ok if successful
   3. add another module line to the `sbjeff_test:unit_test` method
   4. make sure `ok = sbjeff_test:unit_test()`. before pushing to master
 * When adding new methods to a current module:
   1. Add at least one simple test to that module's `_test:unit_test()` method
 * When fixing bugs:
   1. If possible, cover the bug with a new unit_test
 * Where possible, use tagged data objects as returns to methods that will be used
   outside of that module
 * Keep documentation up to date
