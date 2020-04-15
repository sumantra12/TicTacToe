package tictactoeapplication;

import java.util.Scanner;
//Sumantra Das
//April 15, 2020
// This code is what is displayed to the user in the game window


public class TicTacToeApplication {

    
    public static void main(String[] args) {
        
        char playercharacter;
        char opponentToken;
        
      
       
        Scanner sc = new Scanner(System.in);
        
        //allows for games
        boolean play = true;
        
        while (play) {
           
            //Game introduction
            System.out.println("Welcom to tictactoe. I'm the gameMaster and hopefully you are ready "
                    + "to play TICTACTOE against me ");
            System.out.println();
            
            
            System.out.println("To continue enter a chracter or number token that you'll use for yourself and me");
             playercharacter = sc.next().charAt(0);
            
            
            System.out.println("Enter a single character that will represent your opponent on the board");
            opponentToken = sc.next().charAt(0);
            
            //brings classes from other files
            TicTacToeLogic game = new TicTacToeLogic(playercharacter, opponentToken);
            AIComputerOpponent ai = new AIComputerOpponent();
            
            //gameRules
            System.out.println();
            System.out.println("We can now start the game. Enter a number and your character will be placed in that spot"
                    + ".\nThe numbers are from 1-9, as shown on the board. Lets see who wins this now.");
            TicTacToeLogic.IndexBoard();
            System.out.println();
            
            //while game is not over
            while (game.GameOver().equals("notover")) {
                if (game.currentmarker == game.usermarker) {
                   
                    //lets players pick spot
                    System.out.println("Its your turn enter a spot for your character");
                    int spot = sc.nextInt();
                    //if player choses wrong sport
                    while(!game.playerTurn(spot)) {
                        System.out.println(spot + "invalid. The spot chosen"
                                + "is out of range or already taken");
                        spot = sc.nextInt();
                    }
                    System.out.println("You picked "+ spot + "!");
                } else {
                    
                    System.out.println("Its not your turn its my turn");
                   
                    //ai picks spots
                    int aiSpot = ai.pickSpot(game);
                    game.playerTurn(aiSpot);
                    System.out.println("The spot I Picked is "+ aiSpot+ "!");
                }
               
                System.out.println();
                game.tictactoeBoard();
            }
            System.out.println(game.GameOver());
            System.out.println();

            //if player wants to player again
            System.out.println("Would you like to play again. Press Y if you want to");
            char r = sc.next().charAt(0);
            play = (r == 'Y');
            System.out.println();
            System.out.println();
        }
        
    }
    
}
