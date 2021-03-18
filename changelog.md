# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).


## [3.00] - 2010-10-25
### Added
- Added difficulty levels
  - Beginner
    - Use a weak evaluation board (all pieces have the same value)
    - 2-Ply search
    - No opening book
  - Easy
    - Use basic evaluation board
    - 2-Ply search
    -No opening book
  - Intermediate
    - Use basic evaluation board
    - 4-Ply search
    - Unrated opening book
  - Advance
    - Use basic evaluation board
    - 4-Ply search
    - Master opening book
  - More Advance
    - Use basic evaluation board
    - 6-Ply search
    - Master opening book
  - Manual
    - Define your own settings
- Added interface to the FICS (Free Internet Chess Server). You can
  now observe the following games in real time:
  - Lightning / Blitz / Untimed and Standard time
- Added tooltips in many dialog boxes and in the main interface
- Added more than 100 mates in N move games.
- Added a warning for saving a board before leaving a game.
- The new parser comes with an improved advanced book and a new
  intermediate one. The new books have been created from a 2.77
  millions TWIC games. Thank you to chess.com for the SCID file. The
  advanced book includes games from players with ELO rating of 2500 or
  more.
- Added a progress bar when finding a best move or waiting for a move
  from FICS server.
- The game is now saving its last position and size.

### Changed
- Simplified the user interface
- Moved the chessboard closer to the center
- Simplified status bar
- Did a major code clean-up

### Fixed
- Rewrote the PGN parser to handle bigger PGN files and to be more
  compliant with PGN specifications.


## [2.05]
### Added
- Added the Refresh (F5) option. It resynchronize the displayed board with the internal
  one. If you need this function, it's because there still a bug somewhere. If it happens,
  please let me know how you got it!

### Fixed
- Finally found this reentrance bug. If user press Ctrl-Z (Undo) or Ctrl-Y (Redo)
  fast enough, the undo command are being sent while the previous undo was stilled
  processed with two majors problems: 1) Crash, 2) Not refreshing every cell causing
  the shown board being different from the real one.


## [2.04]
### Added
- Add a new File > Create Debugging Snapshot option to create a snapshot
  of the current game. This file can be used to reload the board as it was
  when the snapshot has been taken to diagnose error (example: when a valid position is not accepted).
- Add support for FEN string in addition of a PGN one in File > Create Game

### Fixed
- Loading a PGN file was locking the file up to the next GC.
- Program was crashing when trying to load an board with no moves.
- Program was crashing when loading some valid FEN specification.
- When saving a FEN representation of a board, the En passant position
  was the position of the pawn instead of the position behind the pawn.
- The PGNUtil.GetFENFromBoard now set correctly the Halfmove Clock and Fullmove count in the FEN string.
- The ELO of white/black player was inversed in the description of the loading pane.
- Improved code for "en passant" handling.
- Don't allow player to clicked on the opponent piece.


## [2.03]
### Added
- Add a button to load a PGN games without the moves (so, having the board setting only)


## [2.02]
### Fixed
- Correct endless loop when loading or parsing pgn files


## [2.01]
### Added
- Add the GPL license

### Fixed
- The label for row position were inverse (1-8 instead of 8-1)
- Player against player and Design Mode menu -> Selecting the menu get unsynchronize with the real state
  (or why you must never set the IsCheckable property to true when you have an accelerator key)
- Typo in dialog title 'Test Board Avaluators' corrected to 'Test Board Evaluator'


## [2.00]
### Changed
- Move the application to WPF
- New user interface
- Add a list of piece sets to choose from
  - Thank you to Ilya Margolin for the XAML piece sets

## [1.00]
### Added
- Search engine
  - New searching mode: iterative depth-first search with a fix number of play
- Interface
  - Add a toolbar
  - Add timer for white/black player
  - Add option to select the color of the pieces and board
- Loading / Saving
  - Board can now also be saved in PGN format

### Changed
- Interface
  - Use vector graphic to draw the pieces of the board to improve quality when board is resized.
  - Improves messages related to the end of the game
- Interface
  - Improves the status bar
  - Improves messages related to the end of the game
- Loading / Saving
  - Saved format has changed a lot... so, it's not compatible with the old format

### Fixed
- Game
  - Permits pawn promotion to non-queen pieces

- Move Display
  - Moves can now be seen using PGN format or Start/End position format
  - Start/End position format use 'x' when a piece is eated
  - Book move shown between parentheses are now preserved after being saved

- Search engine
  - Correct problem with iterative search so it now perform better than before
  - Correct problem with point evaluation of draw in alpha-beta and min-max
  - Declare a draw when the minimum pieces requirement for checkmate is not met
  - Improve point evaluation by using the number of attacked pieces and the number of attacked positions

- Interface
  - Permits to undo the first move when in player vs player mode

- Loading / Saving
  - Correct bug which was discarding the move list when loading a PGN file with FEN included.


## [0.943.000]
- Add support for the threefold repetition rule
- Add support for the fifty-move rule
Add a new interface to help adding new board evaluation methods to the game. For more information, reads the BoardEvaluator.txt file.
Add a test mode to compare the performance and the efficiency of board evaluation method (Tool -> Test Evaluation Method...).
Clean-up the code a little...


## [0.942.000]
### Added
- Adds an option to configure move shuffling (to add some random to game). It's now possible to disable it to make debug easier.
- Add timing information about search.

### Fixed
- Ply count has been corrected so it represents a move by one player.


## [0.941.000]
### Added
- Iterative deepening depth-first search is now working. You can now choose a fixed amount of time for finding a best move instead of a number of ply.

### Changed
- The opening book will choose more often usual openings.


## [0.940.000]
### Added
- Add an option to enable/disable book opening
- Add an option to select the multi-threading mode
- Add an option to set the size of the transposition table
- Search setting is now persisted
- Iterative deepening depth-first search is close to be functional... but not yet.

### Changed
- Decrease the points given for castling in the board evaluation

## Fixed
- Correct the transposition table algorithm


## [0.930.002]
### Added
- New option to enable/disable the transposition table. (The option is off by default to correct a bug. Next version will enable it by default).

### Fixed
- Corrects exception occurring at the end of a game.


## [0.930.001]

Original posted version.
