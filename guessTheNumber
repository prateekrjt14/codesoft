import java.util.Scanner;
import java.util.Random;

public class GuessTheNumber
{
	public static void main(String[] args) {
	    System.out.println("Guess the number game");
		Random random = new Random();
		Scanner sc = new Scanner(System.in);
		int round = 1, player = 0, computer = 0;
		
		while(round < 4)
		{
		    int randomNumber = random.nextInt(100) + 1;
		    System.out.println("\nRound("+round+"/3)");
    		int guess = 1, flag = 1;
    		
    		while(guess < 6 && flag == 1)
    		{
    		    System.out.println("Guess (" + guess +")");
    		    System.out.println("Enter a number between 1-100");
    		    int guessedNumber = sc.nextInt();
    		    
    		    if(guessedNumber > 100 || guessedNumber < 1)
    		    {
    		        System.out.println("Guess wasted :(");
    		        guess++;
    		        continue;
    		    }
    		    
    		    if(guessedNumber == randomNumber)
    		    {
    		        System.out.println("Correct :)");
    		        player++;
    		        flag = 0;
    		    }
    		    
    		    else if(guessedNumber > randomNumber)
    		    {
    		        if(guess == 5)
    		        {
    		            System.out.println("Number was : "+randomNumber+"\nBetter luck next time...");
    		            computer++;
    		            guess++;
    		            continue;
    		        }
    		        System.out.println("Guess a bit lower number");
    		    }
    		    
    		    else
    		    {
    		        if(guess == 5)
    		        {
    		            System.out.println("Number was : "+randomNumber+"\nBetter luck next time...");
    		            computer++;
    		            guess++;
    		            continue;
    		        }
    		        System.out.println("Guess a bit higher number");
    		    }
    		    guess++;
    		}
    		round++;
		}
		System.out.println("\n\nStats\nNumber of rounds : 3\nYou : "+player+"\nComputer : "+computer+"\n");
	}
}
