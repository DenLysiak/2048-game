# 2048 game
 - [DEMO LINK](https://denlysiak.github.io/2048-game/)

This classic 2048 game is build using pure JavaScript with HTML and CSS.

CSS file has BEM-structure written with SASS сasscading styles. 
HTML file represent game layout, table with cells and rows.

In 'main.js' file, located function to power 'Game.class' component.
Using 'new Class' key word, new copy of the 'Game.class' is created.
Using 'querySelector' and 'querySelectorAll' to get to the elements on the page.

'displayGameField' function is used to update current state of the game for the user, after every single move, by checking current score and cell layout.
The fucntion accepts two argumnets:
  - state - acceced by using class methog 'getState';
  - cellElements - an array of cells acced by 'usingQuerySelectorALL' getting collection of elements, then transfroming collection to array using spread operator([...]);

'updateScore' by checking elements 'innerHTML', function accepts two arguments: 
  -score - got by clasa method 'getScore';
  - element - got by using 'querySelector'

'showMessage' fuction shows new message according state of the game, if state was changed, by calling written 'Game.class' method 'getStatus' and toggling
certain message in message container.

In 'main.js' file two 'event listeners' are used. The first one, on starting button 'click', then by comparing buttons 'textContent' according to current game state,
certain new value will be displayed (start/restart). After getting game state using class method 'getState' and by checking current game status using 'displayGameField',
new message will appear at the bottom.

The second 'event listener' 'keydown'. Executes function which accepts one argumnet 'keyEvent'.
By comparing which key was pressed down using object, with keys as keyValue and properties as action functions written in 'Game.class', the needed sequences of function will be fired.
After every move functions: 'displayGameField', 'updateScore' and 'showMessage' will be fired to update current game state.

The game itself is represented by 'Game.class' components including 20 written class methods and constructor.
Constructor in game creates four values: state, score, status and initialState.

Class method: 'moveRight/Left', 'moveDown/UP' are used to fire function wich moves cells. By checking current using 'isValidState', 'moveCells' methods and
'updateStateGame' to check the new state.

Method 'moveCells' moves tiles by creating new array and reassigning current cell position to the new using 'while' loop and 'if block' to compare values.

Methods 'getScore', 'getState', 'getStatus' return class values.

Methods 'start' and 'restart' chage game state and status. Start generates new cells by using method 'completeMove', restart, resets all values to the initial.

Methods 'isVictory' and 'isDefeat' check rows for cell '2048' or if there any empty cells on the board.

Method 'completeMove' generate new cell, by using 'generateNewTile' and comparing for 'isVictory' or 'isDefeat'.

Method 'generateNewTile' by checking for empty cell using 'getEmptyCells' and assigning new values.

Method 'getEmptyCells' returns array of cell layout got by 'getState' and filtered for empty cell.

Method 'updateGameState' assign new state value.



