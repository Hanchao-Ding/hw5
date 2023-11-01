# HW5
# Overview
Our project aims to design a Reversi Game(also named Othello) in Java code.   
In our game, our grid will be made up of hexagons.  
This game need 2 players to play(or 1 player vs AI in the future deign).  
Players are allowed to modify the size of the board but not the basic game rules.  
  
# Quick Start
short example of how our code works:  
//Set up the game  
@Before  
public void setUp() {  
game = new Reversi( boardSize: 5，new HumanPlayer(HumanPlayer.Type.PLAYER1_BLACK),  
 &nbsp;&nbsp;&nbsp;&nbsp;new HumanPlayer(HumanPlayer.Type.PLAYER2_WHITE));  
 &nbsp;&nbsp;&nbsp;&nbsp;board = game .getBoard() ;  
}  
  
// Initial board display with board size of 11 should look like this:public static void main(String[] args) {  
Player player1 = new HumanPlayer(HumanPlayer.Type.PLAYER1_BLACK);  
Player player2 = new HumanPlayer(HumanPlayer.Type.PLAYER2_WHITE;  
Reversi game = new Reversi( boardSize: 5， player1， player2);  
HexagonalBoard board = game .getBoard();  
System.out.printin("Initial board setup:");String boardString = TextualView.displayBoard(board):System.out.printin(boardString);  
  
Before move:  
  &nbsp;&nbsp;&nbsp;&nbsp;_ _ _   
 &nbsp;&nbsp;_ O X _   
_ X _ O _   
 &nbsp;&nbsp;_ O X _   
  &nbsp;&nbsp;&nbsp;&nbsp;_ _ _   
  
Target Cell (3, 3): null  
Neighbor (3, 2): PLAYER1_BLACK  
Neighbor (2, 3): PLAYER2_WHITE  
Neighbor (2, 4): null  
Neighbor (3, 4): null  
Neighbor (4, 3): null  
Neighbor (4, 2): null  
Current Player: PLAYER1_BLACK  
  
After move:  
  &nbsp;&nbsp;&nbsp;&nbsp;_ _ _   
 &nbsp;&nbsp;_ O X _   
_ X _ X _   
 &nbsp;&nbsp;_ O X X   
  &nbsp;&nbsp;&nbsp;&nbsp;_ _ _   
  
# Key components  
-Model  
this model is going to represent the board in axial coordinate system.  
it will initialize the board with size given and set up the basic rules for the Revesi Game which includes:  
move: move a valid discs on the board and flip the discs by rules  
pass: switch player's turn  
gameover: check the game is over or not  
  
-View  
visualize the current board in simple String  
eg:  
  &nbsp;&nbsp;&nbsp;&nbsp;_ _ _   
 &nbsp;&nbsp;_ O X _   
_ X _ X _   
 &nbsp;&nbsp;_ O X X   
  &nbsp;&nbsp;&nbsp;&nbsp;_ _ _   
    
# Key subcomonents  
model  
 &nbsp;&nbsp;-Interface ReversiGame  
 &nbsp;&nbsp;general structure for a game  
 &nbsp;&nbsp;Reversi  
   
 &nbsp;&nbsp;-Interface Player  
 &nbsp;&nbsp;Human player  
 &nbsp;&nbsp;AI player(in future design)  
   
 &nbsp;&nbsp;-Class Reversi  
 &nbsp;&nbsp;implements ReversiGame  
 &nbsp;&nbsp;set up the board with size and players  
 &nbsp;&nbsp;isValidMove: check a move is valid  
 &nbsp;&nbsp;makeMove: move the discs and show the result on the board when the move is valid  
 &nbsp;&nbsp;switchPlayer: switch the turn to another player after move of there is not any move for current player  
 &nbsp;&nbsp;isGameOver: determine whether the game is over either the board is full or both player have no any valid move  
   
 &nbsp;&nbsp;-Class Cell  
 &nbsp;&nbsp;a cell that could be empty, player1, or player2  
   
 &nbsp;&nbsp;-Class Coordinate  
 &nbsp;&nbsp;axial coordinate include int q and int r to determine a cell's position  
     
 &nbsp;&nbsp;-Class HumanPlayer  
 &nbsp;&nbsp;implements Player  
 &nbsp;&nbsp;player1 black  
 &nbsp;&nbsp;player2 white  
   
 &nbsp;&nbsp;-Class HexagonalBoard  
 &nbsp;&nbsp;initialize the board and set up the first 6 discs as default  
  
view  
 &nbsp;&nbsp;-Class TexualView  
 &nbsp;&nbsp;visualize the board to String by print it row by row append in a StringBuilder  
   
# Source organization  
  
my-submission.zip  
+-src/  
| &nbsp;&nbsp;+-Model/  
|   &nbsp;&nbsp;&nbsp;&nbsp;+-Cell  
|   &nbsp;&nbsp;&nbsp;&nbsp;+-Coordinate  
|   &nbsp;&nbsp;&nbsp;&nbsp;+-Player  
|   &nbsp;&nbsp;&nbsp;&nbsp;+-HumanPlayer  
|   &nbsp;&nbsp;&nbsp;&nbsp;+-ReversiGame  
|   &nbsp;&nbsp;&nbsp;&nbsp;+-Reversi  
|   &nbsp;&nbsp;&nbsp;&nbsp;+-HexagonalBoard  
| &nbsp;&nbsp;+-View/  
| &nbsp;&nbsp;&nbsp;&nbsp;+-TexualView  
+-test/  
  &nbsp;&nbsp;&nbsp;&nbsp;+-Model/  
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;+-ModelImplementationTests  
  &nbsp;&nbsp;&nbsp;&nbsp;+-Examples  
  &nbsp;&nbsp;&nbsp;&nbsp;+-ModelInterfaceTests  









