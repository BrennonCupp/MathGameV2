# Addition Game V- 2.0

## Introduction
This is the addition game but accomplished using method calls and for loops.

## Outline
1. 	Define the variables we will use
2.	 Create a loop that loops through the desired number of rounds.
3.	If the user answers correctly award them points and increase the difficulty; if not do not award 	points, display the correct answer and decrease the difficulty. 
4. 	Once the game is over display the users final score.

## Reference and Literature
* Liang, Y. (2014). *Introduction to Java programming: Comprehensive version* (Tenth ed.).
* Dr. Evert and the class work posted on git hub.
* Previous work done on the addition game.

## Code
``` java

import java.util.Scanner;

public class MethodsAndLoopsPractice {
	public static void main(String[] args) {
		 
		// call the addition game.
		AdditionGameMethod();

	}
	public static void AdditionGameMethod() {
		System.out.println("Hello, let's play a game.");
		int roundCount = 4;
		int hardness = 5;
		int hardnessStepSize = 5;
		int score = 0;
		boolean isAnswerCorrect;
		
		for(int counter = 1; counter <= roundCount; counter=counter+1){
			System.out.println("Round: " + counter);
			
			
			// Call the get and check answer method
			isAnswerCorrect = getAndCheckAnswerMethod(hardness);
			
			if(isAnswerCorrect){
				System.out.print("Your score was " + score);
				score = score + hardness;
				System.out.println(" and is now " + score);
				if(counter < roundCount){
					System.out.print("Your hardness was " + hardness);
					hardness = hardness * hardnessStepSize;
					System.out.println(" and is now " + hardness);
				}
			
				
			}else{
				if((hardness > 5) && (counter < roundCount)){
					System.out.println("Your hardness was " + hardness);
					hardness = hardness / hardnessStepSize;
					System.out.println(" and is now " + hardness);
				}
			}
		}
		System.out.print("\nThe game is complete.");
		System.out.println(" Your final score is: " + score);
	}
	public static boolean getAndCheckAnswerMethod(int hardness) {
		
		int randomNumber1 = (int)(Math.random()*hardness);
		int randomNumber2 = (int)(Math.random()*hardness);
		System.out.println("\nWhat is " + randomNumber1 + " plus " + randomNumber2 + "?");
		Scanner input = new Scanner(System.in);
		int studentAnswer = input.nextInt();
		int correctAnswer = randomNumber1 + randomNumber2;
		if (studentAnswer == correctAnswer){
			System.out.println("Good work, your answer was correct.");
			return true;
		}else {
			System.out.println("Good try, but the correct answer was " + correctAnswer);
			return false;
		}
		
	}
}
```

## Console Output
```
Hello, let's play a game.
Round: 1

What is 0 plus 4?
4
Good work, your answer was correct.
Your score was 0 and is now 5
Your hardness was 5 and is now 25
Round: 2

What is 3 plus 17?
20
Good work, your answer was correct.
Your score was 5 and is now 30
Your hardness was 25 and is now 125
Round: 3

What is 30 plus 35?
55
Good try, but the correct answer was 65
Your hardness was 125 and is now 25
Round: 4

What is 10 plus 13?
22
Good try, but the correct answer was 23

The game is complete. Your final score is: 30
```

## Summary
This assignment was just a rehashing of the addition game but using method calls and if statements.  The majority of this code comes from the work we did in class especially in class on the 11th where we basically set up the entire code we would need. For this assignment I wasn't sure on how to use for loops but after this I understand them much better and I can see how method calls can make your code much easier to write and look a lot cleaner. 

