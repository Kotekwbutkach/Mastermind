# Mastermind

A small console game for 1 or 2 players, written in C# as an exercise in programming, cooperation using GitHub and console user interfacing.

## Game rules

At the beginning of the game, a secret code is either randomly generated or input by one of the players. The code's length and number of options for each digit can be adjusted (the default settings are length 4 with 6 options). The remaining player then tries to guess the correct combination by inputting guesses. For each guess, two scores are returned: the number of correctly positioned digits and the number of correct digits that exist elsewhere in the code (and have not been guessed yet). This can be illustrated with an example:

Player 1 secretly sets a combination of [1,3,3,6] as the code. Player 2 then tries the following guesses:
1. [1,1,2,2] -> (1,0) - here the first '1' has been correctly guessed, and no misplaced guesses are present. Player 2 now knows that exactly one of patterns [1,·,·,·], [·,1,·,·], [·,·,2,·] or [·,·,·,2] occurs.
2. [3,1,3,2] -> (1,2) - one of the '3' digits have been correctly guessed. '1' and the other '3' are misplaced guesses. Upon closer inspection, Player 2 notices that only [·,3,1,2], [2,1,·,3], [1,3,3,·], [3,3,2,·], [3,·,2,3] remain as possible patterns, and the remaining digit must be a '4', '5' or '6'.
3. [3,4,2,3] -> (0,2) - despite a 'low' score, this is a great guess. It excludes [3,3,2,·], [3,·,2,3] [·,3,1,2], [2,1,·,3] scenarios and shows that 4 cannot be included in the remaining [1,3,3,·] pattern. Only two possible codes remain: [1,3,3,5] and [1,3,3,6].
4. [1,3,3,5] -> (3,0) - this is almost correct and leaves Player 2 with only one possible guess.
5. [1,3,3,6] -> (4,0) - the code has been successfully cracked in 5 tries.

Depending on the game mode, after successfully guessing the code the players might now switch places.

## Additional sources

Link to the Wikipedia article on Mastermind - https://en.wikipedia.org/wiki/Mastermind_(board_game)
