# tic-tac-toe-game
A rudimentary tic-tac-toe game implemented 

The Assignment (Part of Unix Systems Programming course) was to write a script "ttt" that plays TicTacToe with the command-line.  This game will be rudimentary in the sense that the computer randomly picks an open place on the TicTacToe board and place its mark.  

The game starts by selecting X or O (case insensitive). If you don't select then the computer assigns you X.  The state of the game will be maintained  in a hidden directory ~/.ttt with files for the board, moves, computer's playing piece, and a file, gameover, with the winner's message.  All these provide different semantics for play, for example, once the game is over, then it will not let you add anymore marks on the board.  Here is a list of my directory and the contents of each:


Below is a sample session for the game:

$ ./ttt start o
Player: 'O', Computer: 'X'
   _ | _ | _ 
  ---+---+---
   _ | X | _ 
  ---+---+---
   _ | _ | _ 
$ ./ttt play 1 1
Player: 'O', Computer: 'X'
   O | _ | _ 
  ---+---+---
   _ | X | _ 
  ---+---+---
   X | _ | _ 
$ ./ttt play 1 3
Player: 'O', Computer: 'X'
   O | _ | O 
  ---+---+---
   _ | X | _ 
  ---+---+---
   X | _ | X 
$ ./ttt play 1 2
Game over: 'O' wins on first row
Player: 'O', Computer: 'X'
   O | O | O 
  ---+---+---
   _ | X | _ 
  ---+---+---
   X | _ | X 
$ ./ttt print
Game over: 'O' wins on first row
Player: 'O', Computer: 'X'
   O | O | O 
  ---+---+---
   _ | X | _ 
  ---+---+---
   X | _ | X 
moves:
put 'X' in location (2, 2)
put 'O' in location (1, 1)
put 'X' in location (0, 1)
put 'O' in location (1, 3)
put 'X' in location (1, 0)
put 'O' in location (1, 2)
$ ./ttt
usage: ttt command
where command is:
  start [X|O]     start a tic-tac-toe game as X or O (default X)
  play row col    play your piece at row (1-3), col (1-3)
  print        print current state of the game with moves
$


$ ls -l .ttt
total 16
-rw-rw---- 1 manoj manoj  17 Oct  10 9:18 board
-rw-rw---- 1 manoj manoj  33 Oct  10 9:18 gameover
-rw-rw---- 1 manoj manoj 162 Oct  10 9:18 moves
-rw-rw---- 1 manoj manoj   1 Oct  10 9:18 piece
$ more .ttt/moves
put 'X' in location (2, 2)
put 'O' in location (1, 1)
put 'X' in location (0, 1)
put 'O' in location (1, 3)
put 'X' in location (1, 0)
put 'O' in location (1, 2)
$ more .ttt/gameover
Game over: 'O' wins on first row
$
