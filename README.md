# CODSOFT-TASK1
import java.util.Scanner;
import java.util.Random;

public class NumberGuessingGame {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();
        boolean playAgain = true;
        int score = 0;

        while (playAgain) {
            int targetNumber = random.nextInt(100) + 1;
            int attempts = 0;
            boolean isCorrect = false;
            
            System.out.println("Welcome to the Number Guessing Game, Ankit!");
            System.out.println("I have generated a number between 1 and 100. Can you guess it?");

            while (attempts < 5 && !isCorrect) {
                System.out.print("Enter your guess (Attempt " + (attempts + 1) + "): ");
                int guess = scanner.nextInt();
                attempts++;

                if (guess > targetNumber) {
                    System.out.println("Too high! Try again.");
                } else if (guess < targetNumber) {
                    System.out.println("Too low! Try again.");
                } else {
                    System.out.println("Congratulations, Ankit! You guessed the number in " + attempts + " attempts.");
                    score += 10 - attempts;
                    isCorrect = true;
                }
            }

            if (!isCorrect) {
                System.out.println("Sorry! You've used all attempts. The correct number was: " + targetNumber);
            }

            System.out.println("Your current score is: " + score);

            System.out.print("Do you want to play another round? (yes/no): ");
            String response = scanner.next();
            if (!response.equalsIgnoreCase("yes")) {
                playAgain = false;
            }
        }

        System.out.println("Thank you for playing, Ankit! Your final score is: " + score);
        scanner.close();
    }
}
